type:: [[Feature]]
platform:: [[All Platforms]]
description:: Annotate any bock or page with multiple pairs of values e.g. `rating:: 8` or `name:: foo`. Building block for organizing graphs

- ## Usage
	- Property naming rules:
		- 1. Properties are valid for alphanumeric characters and some special characters. When a property is invalid, it is not saved as valid property and an error message explains what is a valid property name:
			- `Property name begins with a non-numeric character and can contain alphanumeric characters and . * + ! - _ ? $ % & = < >. If -, + or . are the first character, the second character (if any) must be non-numeric.`
		- 2. Properties are case insensitive and lower cased. For example, property names `platform`, `Platform` or `PLATFORM` are all the same as `platform`.
		  3. Properties with a `_` character are renamed to `-` e.g. `done_at` is renamed to `done-at`. This rename is done so that users don't have to think about the difference between `_` and `-`.
	- To enter a property, type `::` to autocomplete a property name. After entering a property name, autocomplete a property value that is _specific_ to that property. To see this in action, [see this demo](https://www.loom.com/share/27804e1bcd7b4e4bbf71ec14956c42fe)
	- Markdown:
	  {{embed ((63da19a1-28b9-41c5-8f9f-2f89133ccfce))}}
	- org-mode:
	  TODO
- ## Functionality
	- _Page properties_ are defined by putting them into the first block of the page (_frontmatter_).
	- Block properties are defined by putting them into any other block.
	- Any page or block can have multiple pairs of properties.
	- Properties with no value are not visible or queryable e.g. `property::`
	- ### Property values
	  collapsed:: true
		- Property values can be a mix of almost any text, links, page links and tags. This means you can write like anywhere else in Logseq:
		  ``` 
		  description:: [[Logseq]] is the fastest #triples #[[text editor]]
		  ```
		  The pages `Logseq`, `triples` and `text editor` are all linked property values through the `description` property.
			- The exception to "any text" is that properties are currently embedded in their block and delimited by newlines. Since their delimiter is a newline, a property value can't have newlines.
		- Built-in properties `alias` and `tags` also have an additional way of recognizing pages through comma separation:
		  ``` 
		  tags:: motor, steering wheel
		  ```
		  `motor` and `steering wheel` are automatically treated as page references. If there is no comma, the single value is also treated as page ref. See the configuration section below to enable this behavior for specific properties.
		- To prevent a property value from having any links, wrap it within quotes (`"`);
		  ``` 
		  description:: "[[Logseq]] is the fastest #triples #[[text editor]]"
		  ```
	- ### Configuration in [[config.edn]]
		- `:property-pages/enables?` - Boolean which determines if properties have their own pages. This is enabled by default.
		- `:properties-pages/exclude-list` - Specific properties to exclude from having property pages
		- `:property/separated-by-commas` - Properties that also identify page references with comma separated values like `tags` e.g. tags:: foo, bar
		- `:ignored-page-references-keywords` - Properties that do not allow page referencing. Avoids the need to have to quote the property values with `""` every time.
- ## Background
	- Example data for this section
		- [[How to take smart notes]]
		  type:: [[book]]
		  author:: [[sonke ahrens]]
		  publication-date:: [[february 21, 2017]]
		  price:: 10
		- [[How to solve it]]
		  type:: [[book]]
		  autor:: [[george polya]]
		  price:: 20
		  qty:: 2
		- This example data is also used elsewhere.
	- **Properties** have multiple use cases including:
		- Selecting (querying) specific pages/blocks.
		- TODO finish explaining use cases #docs
- ## Additional Links
	- [[Built-in Properties]]