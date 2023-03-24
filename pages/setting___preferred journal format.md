- You can set your preferred daily journal date format via `Settings` page
- Alternatively, you can add it in [[config.edn]]
	- Custom journal date format support. [[Features]]
	  
	  You can set the `:date-formatter` in `logseq.edn`.
	  The default formatter is `"MMM do, yyyy"`, which will be something like `Jun 1st, 2020`.
	- Add your favorite date-formatter to [[config.edn]]
	  ``` clojure
	  :date-formatter "yyyy-MM-dd"
	  ```
	  Currently, logseq support:
	  ``` clojure
	  "MMM do, yyyy"
	  "E, MM/dd/yyyy"
	  "E, yyyy/MM/dd"
	  "EEE, MM/dd/yyyy"
	  "EEE, yyyy/MM/dd"
	  "EEEE, MM/dd/yyyy"
	  "EEEE, yyyy/MM/dd"
	  "MM/dd/yyyy"
	  "MM-dd-yyyy"
	  "MM_dd_yyyy"
	  "yyyy/MM/dd"
	  "yyyy-MM-dd"
	  "yyyy_MM_dd"
	  ```