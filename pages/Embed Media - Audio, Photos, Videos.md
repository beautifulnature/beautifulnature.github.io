- ## Audio
	- Using [[Hiccup]] or HTML embedding, it's possible to embed audio to your page and paly it back.
		- [:audio {:controls true :src "https://www.kozco.com/tech/piano2-CoolEdit.mp3"}]
	- ### Embedding an audio file on you PC (using [[Hiccup]])
		- To preview audio saved on your computer, type or copy-paste the following Hiccup ClojureScript, replacing the source `src` in "quotation marks" with the file path and file name:
		  ``` 
		  [:audio {:controls true :src "file:C://Users/USERNAME/Folder/audio.ogg"}]
		  ```
		  #+BEGIN_TIP
		  Make sure to include the `file:` at the start and to use forward slashes `/`
		  #+END_TIP
		  
		  #+BEGIN_TIP
		  You can also access other [HTML attributes for the audio tag](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) (see the markup for the `controls` attribute in the above example) 
		  #+END_TIP
	- ### Embedding an audio file on your PC (using "Embed HTML")
		-
- ## Photos, Images, GIFs
- ## Videos
- TODO Split this page up and/or create multiple features that refer to this page. This page is more a tutorial than a reference page #docs