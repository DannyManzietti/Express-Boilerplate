# Express Starter Template

This will go over the step by step directions to set up a basic express template

## Step by Step

1. `mkdir project-name` - create the project on your local computer
2. `cd project-name` change directories into your project
3. `git init` create a new git repository for this project
4. `npx gitignore node` create a pre-built .gitignore file for node
5. `npm init -y` create a package.json file with all defaults answered yes
6. `touch index.js` create a root file
7. `npm i express` install the express package
8. `mkdir api` create folder for server file
9. `touch api/server.js` create server file
10. In the server.js file, add the sanity check server code

```js
const express = require("express");

const server = express();

server.use(express.json());

server.get("/", (req, res) => {
  res.status(200).json({ message: "Hello World" });
});

module.exports = server;
```

11. In index.js, add the following code:

```js
const server = require("./api/server");

const port = process.env.PORT || 8080;

server.listen(port, () =>
  console.log(` ===== Server is listening on port ${port} ===== `)
);
```

12. `node index.js` run the server as a sanity check

13. `npm i -D nodemon` install nodemon as dev dependency
14. Add this line to your "scripts" key in the package.json file `"server": "nodemon"`
15. Use `npm run server` to use start your server using nodemon.
16. Add knex and sqlite3 `npm i knex sqlite3`
17. Create knex configuration file with the following command `npx knex init`
18. Create a data folder for all of your database specific logic `mkdir database`
19. Update knexfile (configuration file) to handle migrations and database specific requirements (e.g. foreign key enforcement)
