two variants exist: 

1. Centralized: all the team members connect to a central server to get the lates version of the code and to share changes with others. It has a single point of failure problem, if the central server is down we can't collaborate or save snapshots of the server.
	1. Subversion
	2. Microsoft Team Foundation Server
3. Distributed: every team member has a copy of the project and its history on their machine so we can save snapshots of our project locally on our machine. if the central server is down we can synchronize our work directly with others
	1. Git
	2. Mercurial
	3. GitLab?