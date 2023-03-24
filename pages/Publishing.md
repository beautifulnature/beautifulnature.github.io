type:: [[Feature]]
platform:: [[Desktop]]
description:: This feature publishes graph as a [[Publish Web]], single page applicaiton.

- ## Usage
	- [[Publishing (Desktop App Only)]] is a tutorial to publish your first graph.
	  :LOGBOOK:
	  CLOCK: [2023-02-02 Thu 15:34:31]--[2023-02-02 Thu 15:34:32] =>  00:00:01
	  :END:
	- An alternative to publishing from the menu is running the command `Export public graph page as html`.
- ## Functionality
	- Publishing permissions are per page, depending on whether the page is "public".
		- By default no pages are public. Individual pages can be marked as public with the property `publish:: true`.
		- Alternatively, in [[Settings]] all pages can be made public by default and then the property `publish:: false` can be used to make specific pages private.
	- All published pages are displayed in read-only mode.
	- Published apps can read user configuration from [[config.edn]], [[custom.css]] and [[export.css]]. [[custom.css]] and [[export.css]] are optional.