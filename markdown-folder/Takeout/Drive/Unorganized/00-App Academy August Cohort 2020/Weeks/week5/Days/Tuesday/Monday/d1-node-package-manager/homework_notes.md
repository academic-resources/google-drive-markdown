# INTRO TO NODE PACKAGE MANAGER (NPM)


Overview
- NPM: default package manager for JavaScript runtime environment, Node.js
- consists of:
	1. command line client (npm)
	2. online database of public & paid-for packages



Package Management
- package is collection of files & configurations wrapped up
- can rely on work of other developers to move our projects along
- can create our own packages and share with the world
- dependencies: packages our app depends on


Package Managers
- apps that accept code and provide services like versioning, change management, etc
- const of at least two parts:
	1. command line interface (CLI)
		 - enables us to download, install/uninstall packages
	2. registry
		 - database of package information


JavaScript Package Management
- before npm: embedded script tags used to share code
- Node.js released in 2010 with npm
  - most widely used package manager


Getting Started with NPM
- dont have to install since its part of Node.js
- `npm init`: generates `package.json` file
- `npm install [-g] <package-name>`: installs package into your project
	- optional -g (--global) flag installs package globally (everywhere in system)




# NPM AND DEPENDENCY MANAGEMENT


