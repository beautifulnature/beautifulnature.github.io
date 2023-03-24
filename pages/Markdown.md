description:: Markdown is a popular markup language with many flavors. Our implementation is parsed by https://github.com/logseq/mldoc.

- Markdown is the most popular format that Logseq supports. Logseq supports most syntaxes including some extended ones.
- ### **Standard** syntax
	- what is logseq? #card
		- knowledge base
	- `**Bold**` -> **Bold**
	- `_Italics_` -> _Italics_
	- `~~Strikethrough~~` -> ~~Strikethrough~~
	- `^^Highlight^^` -> ^^Highlight^^
	- [:div [:code "`Code`"] "-> " [:code "Code"]]
	- `[label](https://exmaple.com)` -> [label](https://exmaple.com)
	- `![image](https://asset.logseq.com/static/img/logo.png)` -> ![image](https://asset.logseq.com/static/img/logo.png){:height 53, :width 42}
	- and so on. . .
- ### **Extended** syntax
	- [[term/page link]]
	  id:: 63d9eba6-22f0-4bcf-8abc-5d069c4d8d6d
		- syntax: `[[page name]]`
		  id:: 63d9f3d6-34c6-495e-953c-2b3781b4a7f2
	- [[term/block link]]
	  id:: 63d9f51c-4921-4dbd-9491-6485f902d434
		- syntax: `((block-uuid))`
		- How can I get a _block-uuid_?
			- Copy a bolck-reference using shortcut
			- Select a block when auto-completing
	- [[term/embedded page]]
	  id:: 63d9f946-7263-49db-9eaf-9e9ee22acfb5
		- syntax: `{{embed [[page name]]}}`
		- It will embed whole page content into current editing block
	- [[term/embedded block]]
	  id:: 63d9f97d-b03d-4ff5-9cea-ab732e526e09
		- syntax: `{{embed ((block-uuid))}}`
		- It will embed whole block content into current editing block
	- [[Properties]]
		- syntax: `property:: value`
		  id:: 63da19a1-28b9-41c5-8f9f-2f89133ccfce
		- some examples
			- [[Templates]] related properties
				- [:code "template:: template-name"]
				- [:code "template-including-parent::  false"]
				- {{embed ((63da36c7-f5aa-4a53-b2b1-1f72e8f6a60e))}}
			- see also: [[Properties]]
		- [[term/page link with label]]
			- syntax: `[display text]([[page name]])`
			  id:: 63da39e3-0ebc-4f73-8076-12b676b8a3a2
		- [[term/block link with label]]
			- syntax: `[display text]([[block-uuid]])`
			  id:: 63da423d-0d1a-4f88-a964-177f20d71606
		- [[Tasks & Todos]] marker
			- syntax: `TODO` `DOING` `DONE` `LATER` `NOW`
			- These markers can be set with commands (`/TODO`) 
			  or sortcut (default `ctrl+enter`)
		- Priority
			- syntax: `[#A]` `[#B]` `[#C]`
			- Priorities can be set with commands (`/A`, `/B`, `/C`)
			  id:: 63db47ac-a90c-4a52-a7b6-0321541dc5b9
		- [[Hiccup]]
			- Sometimes you want to express more complex text structure, you can embed Hiccup in blocks.
			- example
				- `[:p "Hello " [:em "World!"]]` 
				  -> 
				  [:p "Hello " [:em "World!"]]
			- [Hiccup syntax here](https://github.com/weavejester/hiccup/wiki/Syntax)
		- inline latex
			- `$$E = mc^2$$` -> $$E = mc^2$$