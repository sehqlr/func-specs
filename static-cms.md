static site + DB CMS thing
	What/Why
		Currently, static site generators rely on config files as the control
		Dynamic sites are powered by databases. 
		Why should static sites not be the same?
	How
		this has three parts: database, template engine, and web admin
		the template engine pulls from the database and outputs the site
		the DB and template engine are controlled by the web admin
		the web admin can also control deploys, and provide analytics
		the app would come with default templates, but support custom ones
		the download would come with a makefile that can be customized/replaced
	Possible tech stack
		Jinja2 for templating
		SQLite as the database backend
		Flask as the web admin
	Extensions
		Dynamically generate search results with same engine that generates static pages
		RESTful API from same DB as site (would include search mentioned above)
		StreamEngine
			Replace the XML in RSS/Atom with JSON
				statically generate common/specific files
				dynamically generate files for everything else
			Expose a RESTful API for a content server
				create lists of episodes/articles/etc based on a GET request
				add comments/likes/etc with a POST request
				likely follow the OpenAPI specification
			Supplies streaming servies too, mostly to justify cool name
			Clients would be responsible for deciding what pieces of content to get
				clients keep track of read/unread, just like with RSS now
				clients could be programmed by developers/users to filter content
