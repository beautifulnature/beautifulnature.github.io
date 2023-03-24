type:: [[Feature]]
platform:: [[All Platforms]] but some ways are not supported for [[Publish Web]]

- ## Usage
	- There are 3 ways to install custom themes
		- 1. Load a theme from the [[Marketplace]]
			- Click on top-right dot menu dropdown
			- Open plugins tab
			- Click on the `Marketplace` tab and the `Themes` sub-ta
			- install one
			- Themes rely on [[Plugins]] and thus will not work anywhere except where they are supported.
		- 2. Edit the [[custom.css]] file (aka. make your own theme)
			- Top-right dot menu dropdown -> [[Settings]]
			- Click on Edit [[custom.css]]
			- ![212510223-f234ab89-b63c-4b89-8558-2d40b3ecd18f.png](../assets/212510223-f234ab89-b63c-4b89-8558-2d40b3ecd18f_1675325794866_0.png)
			- This will open the custom.css file in Logseq, where you can make edits
		- 3. Specify a `:custom-css-url` in "logseq/config.edn". [[config.edn]]
			- Top-right dot menu dropdown -> [[Settings]]
			- Click on Edit [[config.edn]]
			- ![212511148-621eb05f-b164-49e3-9fd2-16f89925be89.png](../assets/212511148-621eb05f-b164-49e3-9fd2-16f89925be89_1675326138594_0.png)
			- This will open the config.edn file in Logseq, where you can add a line like this, importing a css file via url:
			- `:custom-css-url "@import url('https://cdn.jsdelivr.net/gh/dracula/logseq@master/custom.css');"`
- ## Additional Links
	- https://xyhp915.github.io/logseq-marketplace-table/ - Filter to `Themes` for a full list of available community themes
	- https://github.com/logseq/awesome-logseq#css-themes - Cool themes from [awesome-logseq](https://github.com/logseq/awesome-logseq#css-themes)