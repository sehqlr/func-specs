FractalProjects: project management app
	Project modeled as a network of projects, tasks, and workers
		vertices are projects, tasks, and workers
		edges are dependencies (this has to get done before this...) or assignments
		allows top-down, bottom-up, center-out, and edge-in creation
	Data is saved in graph datastore
	Vertex and edge types must be extensible
	Reports, checklists, etc., are views into the data
		BECCA H: Completed task reports as garden of growing trees
