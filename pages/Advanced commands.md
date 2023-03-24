type:: [[Feature]]
platform:: [[All Platforms]] except [[Publish Web]]

- ## Usage
	- Type `<` to kick off #autocompletion and list of advanced commands.
- ## Functionality
	- When a command is selected it expands to a BEGIN...END section inside a block. There can be multiple BEGINE...END sections in a block.
	- List of advance commands:
		- `Quote` - Displays text as quoted by indenting text and giving it left and right margins.
		- `Src` - Syntax highlights code text using CodeMirror. Passing an argument to the block e.g. `#+BEGIN_SRC clojure` sets the language. Default language is empty. Takes an optional `:results` argument which invokes [[ClojureScript Eval in a Block]]
		- `Query` - Defines a block for [[Advanced Queries]]. Block renders query results when not being edited.
		- Admonition commands display an icon next to a block to call attention to it for a specific purpose. These are inspired by [Asciidoctor admonitions](https://asciidoctor.org/docs/user-manual/#admonition).
			- `Note`
			- `Tip`
			- `Important`
			- `Caution`
			- `Warning`
		- `Example` - Displays text as an example with with white space preservation and a different colored background.
		- `Verse` - Displays text that are for poetry by preserving newlines.
		- `Comment` -
		- TODO List additional advanced commands #docs
		  `Latex export`
		  `Center`
		  `Ascii`
		  `Export`