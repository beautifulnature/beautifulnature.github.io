- #+BEGIN_WARNING
  **BACKUP** all your notes somewhere **first** before continue
  #+END_WARNING
- This migration guide is mainly targeted for Logseq users of **pre-beta version** with Markdown notes
- **Backup (make an extra copy)** of all your old notes first, then:
	- 1. Download the release https://github.com/logseq/logseq/releases/tag/0.1.2
	- 2. Load and open your old graph folder in this new Beta app
	- 3. Click the right three dots menu, go to `Export` and select `Convert Markdown headings to unorderd lists (# -> -)`
	- 4. Above will create a zip file of all your converted new notes under `/journal` and `/pages` folder, extract the zip to your desired location.
	- 5. Copy and replace all pages under `/journal` and `/pages` folder back to that same graph folder
	- 6. Finally, click the right three dots menu, go to `/All graphs` and unlink the graph and open it again to reload the graph
- Tutorial:
  ![migrate_1621935713657_0.gif](../assets/migrate_1621935713657_0_1675656822463_0.gif)
- Why & underneath the hood:
	- Previously Logseq use `#` markdown heading as outliner bullets, since beta, we've changed to use more standard `-` unordered list as outliner bullets
	- The converter essentially converts all Markdown headings to unordered lists (`#` -> `-`)
- Further steps you may need:
	- Since Logseq is using `-` unordered list of bullets, `-` will not work as a list item anymore, replace `-` with `*` or `+` if you need it. The converter doesn't convert it automatically because it might break your contents.
- Other noticeable changes:
	- Old syntax of adding property for Markdown is no longer recommended
	  ``` markdown
	  key: value
	  ```
	  Use below new [[Properties]] syntax instead {{embed ((63da19a1-28b9-41c5-8f9f-2f89133ccfce))}}