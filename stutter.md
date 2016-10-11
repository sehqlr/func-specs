nCod
	Types as encodings
		Deep down, types are just interpretations of binary data. So what happens if we expose that abstraction?
		What if we build a language that has three primatives: indexes, encodings, and pure functions
	The primatives
		indexes
			Indexes relate regions of memory with a name and an encoding
			the name can be any non-numeral string
			This includes the normal things that a pointer knows: offset and width (type)
			indexes can either refer to data allocated in the stack or in the heap 
			This could include other things, like Rust's lifetime information, and other things that I don't even know about
			The main idea is that any kind of cool features that you need for referencing data, indexes should do it
		pure functions
			These operate on indexes & encodings and transform the underlying data from one form to exactly one other form
			these functions write the transformations to a different index, typically called index' (index prime)
			these maybe lambda expressions or bound to an index
		encodings
			This is the part of the language is the experimental part
			An encoding interprets a chunk of data by defining operations on that data, including header interpretation, graph traversals, etc
			These operations are not pure, because the data is altered in place
	the environment tree
		the environment tree is an encoding that holds execution state for the process
		indexes are stored as branches in the tree, and the binary data or lambda expression is the leaf
	strings
		strings in the language refer to any whitespace-delineated set of Unicode points (chars)
		they make up the source code, and are used to define other types of literals
		kinds of literals
			numerals
				a string that starts with a numeric character
				1E4, 15EE-7, 1+8i, 1.000
			text
				a string contained inside quotes, include whitespace
				the Text encoding allows formating, templating, etc
				"this is text"
			 set
				sorted collections of values
				indexed by hash of value 
				{  }
			 list 
				ordered collection of repeatable values
				indexed sequentially
				(  )
			 array
				n-dimentional collection of repeatable values
				indexed orthogonally 
				[  ]
		functions
			these come in two forms: operators and expressions
			operators
				infix notation
				operators can be bound to a char, e.g. + - U etc
				defaults
					: k/v assignment
					.. output to stdout (..such and such)
					- minus|negation
					+ plug|positive
					* multiplication
					/ division
					% modulo
					^ power
					, sequence marker
					=> eager evaluation
					-> lazy evaluation
			expressions
				function_name args 
Uniface
	Uniface is an object that represents all the different ways that a bit of library code needs to interact with the world
	This includes
		Documentation
		Automated testing
		IO types and validation
		the actual code
	Why?
		Unless a developer/team is very strict, implementation often moves faster than auxillary elements
			documentation falls behind, especially example code
			automated testing often falls out of sync as well
			If a uniface is implemented around the code, then documententation, testing, and everything else lives in the same place
		Type validation is taken care of by some languages, but not in others. This can cause problems, especially when automated testing is not written
			Uniface is planned for being implemented in Python, which is not statically type checked
			Many types of testing could be handled as a type validation instead
		This could implement that pattern from that Idris blog that I read from Hacker News that one time, the one with proofs?
	How?
		The uniface would be a base class that has several fields associated with it:
			docs
				return documentation, either statically or dynamically generated
			test
				run automated tests, and return a report
			init
				load needed config into memory, and calls main
			main
				actually run the code
			exit
				handles any cleanup for the process, and returns the exit code
			input
				type definition/validation for the input
			output
				type definition/validation for the output
	Each module in your library would have a different uniface.
	The code in the uniface could be entirely stateless/functional, and can
		be further subdivided into many subroutines, but the bottom of the call
		stack is called in "main"
	Extensions
		make
			have a field called make, build, cook, etc., that outputs compiliation instructions to make, or to OS directly
		Literate source code
			We could define a lightweight markup language that compiles to a Uniface class
		IO requisition pattern
			I have this idea that the OS could validate all IO requests before a process starts its main run.
				This would require a process to execute init step
					request all needed resources before main
					validate permissions and availability during init step
					if an IO error occurs before the end of the init step, abort process right away
					a file request can include directories, in case a process needs to create/destroy many files
			Uniface could implement this pattern in the prexisting init step
		functional IO?
			Following the idea for the IO requisition pattern, if we can guarantee that the IO will be allocated/mapped in a deterministic fashion,
			then we could have a system for IO that has functional properties. I can't actually prove this, but I'd try for it
		uniface -> unikernel/container
			If uniface is as truely comprehensive as I dream of, then it could provide a basis for a unikernel or container image.
			And, if we could have the functional IO pattern, then we could have functional unikernels??
