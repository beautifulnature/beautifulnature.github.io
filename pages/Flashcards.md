type:: [[Feature]]
paltform:: [[All Platforms]]

- ## What's "card"?
	- A card is intended to be used as an aid in memorization. In logseq, it's just a block with either `#card` or `[[card]]`. It can have some [[Clozes]] too.
		- For example, this block is a card:
			- What does "Logseq" mean? #card #logseq
				- You can read it as "Log sequence" or "Logical sequence" (thank you [[Ed]] )
			- If you right click the bullet and select "Preview Card", you'll see something like this:
				- ![CleanShot_202021-07-22_20at_2021.46.52_1626961624975_0.png](../assets/CleanShot_202021-07-22_20at_2021.46.52_1626961624975_0_1675334973403_0.png)
- ## How to create a card?
	- There're 2 ways to create a card.
		- 1. You can add either `#card` or `[[card]]` to any block to make it a card.
		- 2. You can right click the bullet to "Make a card", which will add `#card` to the end of the current block.
			- ![CleanShot_202021-07-22_20at_2021.37.06_1626961037065_0.png](../assets/CleanShot_202021-07-22_20at_2021.37.06_1626961037065_0_1675335197875_0.png)
- ## What's a cloze?
	- The content in a cloze is not shown by default. For example, [...], you can click it to reveal its content. You can have multiple [...] in block too.
- ## How do I create a cloze?
	- Type `/cloze`.
		- ![2021-07-22_21.53.38_1626962063719_0.gif](../assets/2021-07-22_21.53.38_1626962063719_0_1675335350786_0.gif)
- ## I've created several cards, how can I review all of my cards?
	- Click the "Flashcards" tab on the [[Left sidebar]].
- ## Can I review parts of my cards instead of all of them? For example, only those cards related to Logseq?
	- Yes, you can use `/cards` and [[Queries]].
	- `{{cards [[Logseq]]}}` will be displayed as:
	  {{cards [[Logseq]]}}
	- You can also show all cards _except_ those tagged with a certain page. `{{cards (not [[Logseq]])}}` will be displayed as:
	  {{cards (not [[Logseq]])}}
- ## TIPs
	- Press `t c` (toggle cards) to review all of your cards
	- You can add your "cards" queries to the "Favorites" page in the right sidebar for quick access.
- [[Resources]]
	- [Augmenting Long-term Memory](http://augmentingcognition.com/ltm.html)
	- [SM5](https://www.supermemo.com/en/archives1990-2015/english/ol/sm5) by supermemo
- TODO Organize this page #docs
	- Maybe split out tutorial. Add Tienson's latest functionality
	- srs.edn