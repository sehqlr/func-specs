ProtoCall: the Social Media Agent
	write it in Go, but define a good spec for porting to other langs (esp. Erlang)
	One program can interact with all of your social media sites
	ID management
		Logins handled via OAuth when available
		ID is obfuscated when wanted
	Aggregate all your social media messages, reply with same service
		you can save all of the messages, like an email inbox
	Agent can speak over 6 million different protocols!
		mascot is like C3PO but "legally distinct"
	new usages on existing platforms, including...
		email client
			ProtoCall would implement functionality of an email client
			fall back on email messages when other methods fail
			include strong encyption as a first class feature
		group text message management
			aggregates messages into converstation threads
			SMS messages could contain metadata from app
	New kinds of social networks build with this in mind, including...
		CryptoZoo
	extensions
		server mode that supports RAFT, cluster management, etc
		cypto keyring management
			implements an internal module, or use external program
	next actions

		Services 
			a service syncs data between local storage and remote resources
			it accepts requests from clients, and provides them with local data
				this is part of the operational offline mode strategy
			it manages connections, encodings, crypto, identities, contacts, etc
			struct fields
				remote connection to remote host
				listener on localhost for client requests
				log pointer to log.Logger
				storage db pointer
				event channel to event bus for future notifcation system

		Clients
			a client interfaces with the user and a service via CLI, GUI, or API
			sends requests to service
			clients can be written in any language, since the service connects via socket/localhost, and passes around JSON
				the "default" clients will be written with a CLI (go) and an SPA (something else), with a language agnostic specification
		Remotes
			remotes are processes running on another machine across the network
			services will be designed to have an operational offline mode in case of network partition
		the "default" client will support these services
			email
			texting
			IRC
			RSS

CryptoZoo: the simple, secure social network
	adding friends is exchanging keys
		then, and only then, do you exchange messages
	TTL on keys, shorter for temporary discussions, longer for friendships
	completely p2p for private convos, server/client for public rooms
		rooms would have different ways of slicing conversations
			participants
			topics
			datetimes
		bot (keeper) as moderator for public rooms
			keeper manages keys and message exchanges
			could enforce rules based on owner code, or not
	build on top of email
	could this be monetized??
		One idea is that users can send companies an "advert" key with a TTL
		As long as the key is valid, companies can send advertising to that user
		the key can be revoked any time

