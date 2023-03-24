- **What are "Queries"?**
  title:: Queries
	- Queries are for asking questions from your knowledge base and the outside world (in future).
	  ![_5ff0a01d-47d4-487d-b346-4a43ded21ad02020_12_29_photo-1444703686981-a3abbc4d4fe3.jpeg](../assets/_5ff0a01d-47d4-487d-b346-4a43ded21ad02020_12_29_photo-1444703686981-a3abbc4d4fe3_1675657312831_0.jpeg)
	  By [Greg Rakozy](https://unsplash.com/photos/oMpAz-DN-9I)
- **How to write queries?**
	- There're 2 kinds of queries:
	  1. Simple queries by using `{{query }}`, the format is something like this:
	  #+BEGIN_EXAMPLE
	  {{query Something you're looking for}}
	  #+END_EXAMPLE 
	  2. [[Advanced Queries]]
- **Query Operators**
  These 3 operators can be applied around any query filters.
	- **and**
	  Examples:
	  #+BEGIN_EXAMPLE
	  (and [[page 1]] [[page 2]])
	  #+END_EXAMPLE
	- **or**
	  Examples:
	  #+BEGIN_EXAMPLE
	  (or [[page 1]][[page 2]])
	  #+END_EXAMPLE
	- **not**
	  Examples:
	  #+BEGIN_EXAMPLE
	  (not [[page 1]][[page 2]]
	  #+END_EXAMPLE
- **Query filters**
  Most filters apply to blocks. Some filters only apply to pages.
  The following page-only filters cannot be mixed with block filters: `page`, `page-property`, `page-tags` and `all-page-tags`
	- **between**
	  The format `(between start end)` will only support blocks on the journal pages.
	  
	  There're several built-in symbols:
	  1. `today|yesterday|tomorrow|now`
	  2. `+|- number y|m|w|d|h|min`
	  Examples:
	  
	  #+BEGIN_EXAMPLE
	  (between -7d +7d)
	  (between -2w today)
	  #+END_EXAMPLE
	- **Page**
	  Examples: [[questions]]
	- {{query (page "term/alias")}}
	- **property**[[Properties]]
		- This filter matches against any pages or tags in a property value. For example `type:: [[book]]`, `(property type book)` would match. For example `description:: I liked this #book and #movie`, `(property description book)` or `(property description movie)` would match. However, `(property description liked)` would not match as "liked" is not a page or tag.
		- Example
			- {{query (property type book)}}
	- **Full-text query**
	  #+BEGIN_NOTE
	  It's only enabled on the desktop app at the moment.
	  #+END_NOTE
	  Examples:
	  #+BEGIN_QUERY
	  {:title "Query: \"alias\""
	  :query "alias"
	  :collapsed? true}
	  #+END_QUERY
	- **task** (used to be `todo`)
	  Examples:
	  #+BEGIN_EXAMPLE
	  (task now)
	  (task now later)
	  #+END_EXAMPLE
	- **priority**
	  Examples:
	  #+BEGIN_EXAMPLE
	  (priority a)
	  (priority a b c)
	  #+END_EXAMPLE
	- **page-property**
	  Example:
	  {{query (page-property related "Block embed")}}
	- **page-tags**
	  Example:
	  {{query (page-tags embed)}}
	- **all-page-tags**
	  Example:
	  {{query (all-page-tags)}}
	- **sort-by**
	  This filter provides a default sort for a block or page. Note that `created-at` and `updated-at` only work for pages.
	  
	  Format: `(sort-by property-name order)` or `(sort-by property-name)`
	  `key`: can be any user property as well as built-in properties `created-at` and `updated-at`.
	  `order`: `desc` or `asc`, omit means `desc`.
	  #+BEGIN_EXAMPLE
	  (and (task now later) (sort-by created-at desc))
	  #+END_EXAMPLE
- **More query examples**
	- 1. Find the blocks containing page "tag 1"
	  #+BEGIN_EXAMPLE
	  {{query [[tag1]]}}
	  #+END_EXAMPLE
	  {{query [[tag1]]}}
	- 2. Find the blocks containing both `tag1` and `tag2`
	  #+BEGIN_EXAMPLE
	  {{query (and [[tag1]] [[tag2]])}}
	  #+END_EXAMPLE
	  {{query (and [[tag1]] [[tag2]])}}
	- 3. Find the blocks containing either `tag1` or `tag2`
	  #+BEGIN_EXAMPLE
	  {{query (or [[tag1]] [[tag2]])}}
	  #+END_EXAMPLE
	  {{query (or [[tag1]] [[tag2]])}}
	- 4. Find the blocks containing `tag2` but not `tag1`
	  {{query (and [[tag2]] (not [[tag1]]))}}
	- 5. Find journal blocks created between [[Jan 1st, 2023]] to [[Feb 06th, 2023]]
	  {{query (between [[Jan 1st, 2023]] [[Feb 06th, 2023]])}}