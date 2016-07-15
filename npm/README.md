#npm
npm comes bundled with Nodejs. 

##Basic commands
```npm update -g``` - Updates all global packages.

##npm modules of note

###Global npm modules
Installed with ```-g```, may also need ```sudo```.

 - [http-server](https://www.npmjs.com/package/http-server) - This is an great tool for hosting static pages on your own machine. Sure, you could write a little node server to do the same thing but this is basically already done. Just run ```http-server (dir)``` and it will host those files on http://localhost:8080.
 - [react-server](https://github.com/redfin/react-server) (by Redfin) - Server side rendering with React.
 - [nodemon](https://github.com/remy/nodemon) - Replaces vanilla node, watches js files and restarts on changes, awesome for development.
 - [pm2](https://github.com/Unitech/pm2) - PM2 is a node processes manager. Automatic clustering, restarts on crash, startup order, logging, there is a lot to like. 

###Application npm modules
These are "required", may be server or client side.

 - [express](https://www.npmjs.com/package/express) - Swiss Army knife of a web framework.
 -  [mongoose](https://github.com/Automattic/mongoose) - Mongoose ODM is a great way to model and connect to MongoDB data.
 - [mongoose-history](https://github.com/nassor/mongoose-history) - Creates a shadow collection of changes.
 - [passport](https://github.com/jaredhanson/passport) - User Authentication with loads of plugins.
 -  [node_acl](https://github.com/OptimalBits/node_acl) - Library for adding ACLs to user accounts.