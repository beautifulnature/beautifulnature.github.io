- Logseq comes with two built-in flavors to mark your block with built-in workflow mark keywords and manage your tasks:
  * `LATER` -> `NOW` -> `DONE` flavor (default)
  * `TODO` -> `DOING` -> `DONE` flavor
  * You can toggle between those two flavors in setting page
- There're two ways to attach workflow mark to your task (block)
	- when editing the block, press `Ctrl+enter` to cycle through the workflow mark
	  :LOGBOOK:
	  CLOCK: [2023-02-02 Thu 10:35:42]--[2023-02-02 Thu 10:35:43] =>  00:00:01
	  :END:
	- type these mark as command directly, e.g. `/LATER` `/NOW` `/DONE` `/TODO` etc...
	- Some examples:
		- LATER do grocery
		  :LOGBOOK:
		  CLOCK: [2023-02-02 Thu 10:37:21]--[2023-02-02 Thu 10:37:22] =>  00:00:01
		  :END:
		- NOW play with Logseq
		  :LOGBOOK:
		  CLOCK: [2023-02-02 Thu 10:38:28]
		  :END:
		- DONE watch Doctor Who
		  :LOGBOOK:
		  CLOCK: [2023-02-02 Thu 10:39:31]--[2023-02-02 Thu 10:39:32] =>  00:00:01
		  :END:
- Logseq also comes with three built-in priority mark to help you manage with task priorities
	- {{embed ((63db47ac-a90c-4a52-a7b6-0321541dc5b9))}}
	- Example:
		- LATER [#A] research balalah is a top priority
		  :LOGBOOK:
		  CLOCK: [2023-02-02 Thu 11:03:57]--[2023-02-02 Thu 11:03:58] =>  00:00:01
		  :END:
		- NOW [#C] play with Logseq
		  :LOGBOOK:
		  CLOCK: [2023-02-02 Thu 11:04:58]
		  :END:
- Deadline and Scheduled
	- You can leverage command `/Deadline` to setup a deadline for your task
		- e.g.: finish reading 1984 by 29th of May
		  DEADLINE: <2023-05-29 Mon>
	- You can leverage command `/Scheduled` to setup a scheduled task
		- e.g.: send John a birthday card Monday
		  id:: 63db4c7f-c7d4-46fb-adde-08d714b5da18
		  SCHEDULED: <2023-02-06 Mon>
	- Both of above commands support to mark the task as repeated:
	  after typing the command and click `Add repeater` in the date picker
		- e.g.: daily exercise routine at 7am
		  SCHEDULED: <2023-02-03 Fri .+2d>
- Time tracker
  id:: 63db4dd4-3576-41e6-a631-1a2263c0473e
	- ⏰ Time tracker
	  Logseq will record the time when you add or update the block todo keyword and display the spent time once you checked the task.
		- DONE Example
		  :LOGBOOK:
		  CLOCK: [2023-02-02 Thu 11:22:04]
		  CLOCK: [2023-02-02 Thu 11:22:20]--[2023-02-02 Thu 11:22:21] =>  00:00:01
		  :END:
	- you can toggle this off by [[setting/enable timetracking]]
- TODO [[Ramses]] to rename to Tasks #docs
- TODO Reorganize this page