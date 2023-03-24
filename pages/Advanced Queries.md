description:: Advanced queries are written with [Datalog](https://en.wikipedia.org/wiki/Datalog) and query the [Datascript](https://github.com/tonsky/datascript) database. [[Learn Datalog Today]] is a great first reference if you're not familiar with Datalog.

- ## Intro
	- #+BEGIN_TIP
	  If this is your first time looking at an advanced query, first skim our beginner user resources. Several resources are listed so look ones for that fit your learning style.
	  #+END_TIP
- ## Advanced Query Shape
	- An advanced query looks like this:
	  #+BEGIN_EXAMPLE
	  {:title [:h2 "Your query title"]
	   :query [:find (pull ?b [*])
	                :where . . .]
	   :inputs [. . .]
	   :view (fn [query-result] [:div . . .])   ;; or :keyword from config.edn
	   :result-transform (fn [query-result] . . .)  ;; or :keyword from config.edn
	   :collapsed? true
	   :rules [. . .]}
	  #+END_EXAMPLE
	  |Name|Description|Default|Optional|
	  |title|query title, supports hiccup||true|
	  |query|datascript query or simple query||false|
	  |inputs|query inputs, can be multiple values||true|
	  |view|fn or keyword||true|
	  |collapse?|whether to collapse the result|false|true|
	  |result-transform|fn or keyword||true|
	  |rules|list of rules to apply to query||true|
	- **Query Tips**
	  #+BEGIN_TIP
	  1. `?b` and `?p` are special symbols in queries that must be used with blocks and pages.
	  2. Page names are stores as lower case in the database.
	  3. Most simple query operators are available as [rules](https://docs.datomic.com/on-prem/query/query.html#rules) in queries.
	  4. Titles can be hiccups or double-quoted strings. For example, if you wnat to put custom macros into the query title, you can write something like `{{poem,foo,bar}}`.
	  #+END_TIP
	- **Query Inputs**
	  These are special values for a query's `:input` key above:
		- Page and block inputs
			- `:current-page` - Name of current page. See [this example](((63e0a1b0-c368-4273-b264-676a7f24578c)))
		- Inputs for querying journal page blocks and rules like `between`
		- Timestamp inputs for block attributes that use millisecond timestamps e.g. `:block/created-at`
			- `:Xd-before-ms` - Timestamp of X days before today
			- `:Xd-after-ms` - Timestamp of X days after today
			- `:right-now-ms` - Timestamp for current time
			- `:start-of-today-ms` - Timestamp for beginning of today
			- `:end-of-today-ms` - Timestamp for end of today
- ## Query Examples
	- 1. Get all tasks
	  ``` clojure
	  #+BEGIN_QUERY
	  {:title "All tasks"
	   :query [:find (pull ?b [*])
	                :where
	                 [?b :block/marker _]]}
	  #+END_QUERY 
	  ```
	- 2. Get all tasks with a tag "project"
	  ``` clojure
	  #+BEGIN_QUERY
	  {:title "All blocks with tag project"
	   :query [:find (pull ?b [*])
	                :where
	                 [?p :block/name "project"]
	                 [?b :block/refs ?p]]}
	  #+END_QUERY 
	  ```
	- 3. Blocks in 7days with a page reference of datalog
	  ``` clojure
	  #+BEGIN_QUERY
	  {:title "Journal blocks in last 7 days with a page reference of datalog"
	   :query [:find (pull ?b [*])
	                :in $ ?start ?today  ?tag
	                :where
	                (between ?b ?start ?today)
	                (page-ref ?b ?tag)
	   :inputs [:7d-before :today "datalog"]
	  #+END_QUERY
	  ```
	- 4. All TODO tasks
	- 5. All the tags specified in the front matter (tags: tag1, tag2)
	- 6. All pages have a "programming" tag
	- 7. Get all the blocks with the property "type" and the value "programming_lang"
	- id:: 63e0a1b0-c368-4273-b264-676a7f24578c
	  8. TODO tasks tagged using current page
	  ``` clojure
	  #+BEGIN_QUERY
	  {:title "All tasks tagged using current page"
	   :query [:find (pull ?b [*])
	             :in $ ?current-page
	             :where
	             [?p :block/name ?current-page]
	             [?b :block/refs ?p]
	             (task ?b #{"TODO"})]
	   :inputs [:current-page]}
	  #+END_QUERY 
	  ```
	- 9. Active tasks from the last 2 weeks
	- 10. Tasks referencing due dates in the past
	- 11. Tasks referencing due dates up to 10 days ahead
	- 12. Tasks from last week which are still outstanding (may slip soon!)
	- 13. Tasks created more than 1 week ago, less old than 2 months but still outstanding
	- 14. Next 7 days' `deadline` or `schedule`
	  Add `Deadline` and `Scheduled` support!
- ## Additional Links
	- For beginner users
	  collapsed:: true
		- https://qwxlea.github.io/#/page/datalog%2Fintro%20to%20datalog - Beginner friendly intro to datalog
		- [[Learn Datalog Today]] - User-friendly, interactive datalog tutorial
		- https://mschmidtkorth.github.io/logseq-msk-docs/#/page/queries%2Fadvanced%20queries%2Ftutorial - Advanced query line by line explanations
		- https://max-datom.com/ - fun, interactive datalog tutorial
		- https://bgrolleman.gitlab.io/logseq_publish_toolsontech/#/page/logseq%2Fadvanced%20queries - Some useful tips on advanced queries
		- https://mschmidtkorth.github.io/logseq-msk-docs/#/page/queries%2Fadvanced%20queries - More useful tips on advanced queries
	- For advance users a.k.a. engineers
	  collapsed:: true
		- [Datomic query documentation](https://docs.datomic.com/query.html) - Thorough reference for datomic dialect of Datalog. Explains most datalog concepts well
		- https://nextjournal.com/try/learn-xtdb-datalog-today/learn-xtdb-datalog-today - Interactive datalog tutorial for engineers
		- [Datascript's intro docs](https://github.com/tonsky/datascript/wiki/Getting-started)
		- [Logseq's database schema](https://github.com/logseq/logseq/blob/master/deps/db/src/logseq/db/schema.cljs)