ignorefile program
	Lots of different programs are implementing ignore files. Could we build one tool to manage all of them?
	The ignorefile would have two components: a list header, and then a list
		The list header would correspond to programs. This is the name of current ignore files between the leading . and `ignore`.
		The list would just be a list of fileglobs/regexps
	This could also include a "keep" function, too
		The list would be a whitelist instead of a blacklist, but otherwise it's the same
	could use the OBOE format for simple things, then "upgrade" to YAML for more complex features
