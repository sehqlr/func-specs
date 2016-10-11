
abstract layout graph engine
	represent graphical layout of elements (such as a GUI) as a graph, then parse that graph to generate the layout
	nodes are elements in the layout, and edges are the layout itself
	examples
		elementA => elementB { left: 30px }
			elementA is to the left of elementB by 30px
		elementA => elementB { z-index: -100 }
			elementA's z-index is 100 levels less than elementB
	extensions
		represent graph in structured text (JSON) to send over the network
		store graph in DB for native applications with complex UIs
consecutive tiling manager
	basically, you have a sequence of windows, and the view over them can slide across.
	So, if you have windows A, B, C, and D, and a view of them (the ASCII box):
		-----          -----          -----
		|A B| C D => A |B C| D => A B |C D|
        	-----          -----          -----
	The effect I want is that if the windows were projected on the inside of a sphere, and I was
	wearing a VR helmet, as I turn my head, the windows would slide in and out of view like this
	In fact, there should be rows of windows that are different "workspaces"
