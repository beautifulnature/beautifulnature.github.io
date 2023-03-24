type:: [[Feature]]
platform:: [[All Platforms]]
description:: Provides keyboard shortcuts for running core commands and actions. Shortcuts can be customized through user configuration.

- ## Usage
	- **How to setup custom keyboard shortcuts?**
		- To add custom shortcuts, you can navigate to the shortcuts pages with `g s`. Press the blue button corresponding to a given shortcut and a modal should pop up. Press the keybinding you want and then press `save`. The shortcuts will be saved to your graph's [[config.edn]].
		- Alternatively, you can add/modify the `:shortcuts` section in [[config.edn]], for example, then refresh Logseq.
		  #+BEGIN_EXAMPLE
		  :shortcuts {:ui/toggle-theme "mod+c mod+t"}
		  #+END_EXAMPLE
		  To have shortcuts that work across all graphs, put the shortcuts in [[Global config.edn]]
- ## Functionality
	- **Which shortcuts can be customized?**
	  Type `g s` to see the full list of shortcuts by categories. The default shortcuts are [here](https://github.com/logseq/logseq/blob/master/src/main/frontend/modules/shortcut/config.cljs).
	- When the editor is not focused, Logseq recognizes key combos which are multiple letters pressed sequentially. The four letters used for key combos are:
		- `g` for Go e.g. `g s` goes to the shortcuts
		- `t` for Toggle e.g. `t r` toggles the right sidebar
		- `n` for new e.g. `n w` creates a new whiteboard
		- `c` for close e.g. `c t` closes top item in sidebar
	- Use this syntax when configuring shortcuts by hand:
		- `+` means keys pressing simultaneously e.g.: `ctrl+shift+a`
		- ` ` empty space between keys means key chords
			- e.g.: `t t`
			- e.g.: `mod+c mod+t`
		- `mod` means
			- `ctrl` for Linux and Windows
			- `cmd` for Macos
		- you can define multiple bindings for one action
			- e.g.: `:editor/down ["ctrl+j" " down"]`
- ## Background
	- > People come to Logseq from different operating systems, use different keyboard layouts and languages, and have different preferences. Customizable keyboard shortcuts is the only way to make everybody happy. - [[Cobbelbot]] [discussion](https://discuss.logseq.com/t/customizable-keyboard-shortcuts/146)