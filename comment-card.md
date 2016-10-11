CommentCard: conversations app based on IPFS
	CommendCards are comments about things on the internet, including other cards
		Original Posts reference a non-Card URI
		reply cards reference other Cards
	Data is stored locally, transmitted securely to peers via IPFS
	Reactions are a simple form of comment
	Commenters have @ prepended to their public name, and can be referenced in other cards
		@@ is Anonymous
		@0 (zero) or @OP (Original Poster) refer to user at root of comment tree
		@^ means user you are replying to
	#Hashtags are labeling the thread itself
