GraFS
	what if someone created a kernel level graph database specifically for a file system? 
	Essentially, managing OS state with graphs?
	for one thing, directories would be nodes that have edges pointed to their files. 
	The edges can have access control properties, where nodes have encodings and timestamps
	(sym)links would be replaced with multiple edges to same node
	remote resources are just a different kind of file path edge.
	There could be the equivalent of a /net dir, with FS path matching the URIs of network resources
	The edges that point to files are called indexes in this description, to match the concept in current OSes
	to get a file, you call 'access', and grafs walks the indexes until it gets the file
	One thing that you could do with this is to build different views of
	the graph. For example, the /bin directory could just be indexes to all
	of the executables on the system, with extra metadata in the index
	about the file, not just permissions but also what program/package it
	belongs to, etc
	Different tools add properties to existing ones
