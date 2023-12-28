1. `npm init`
2. `git init`
3. Create .gitignore
4. `npm i express`
5. `npm i dotenv` to manage enviroment variables
6. `npm i http-status-codes`: does all the enum mapping for us.
7. Create `.src` folder, inside that 
    7.1. create `index.js` file, where our basic server configuration going to remain.
    ```Javascript
    const express = require("express");
    const { PORT } = require("./config");

    const app = express();

    app.listen(PORT, () => {
        console.log(`Successfully started the server on PORT: ${PORT}`)
    })
    ```
    7.2. create `.config` folder
        7.2.1. Inside config create `index.js` again
        ```Javascript
       const dotenv = require('dotenv');

       // at any particular time we call this file it'll require the dotenv module, that env module actually returns an object on that object you need to call the config function so that you can actually get our enviroment variables

        dotenv.config();

        //every file that we need  a particular enviroment variable we don't need to separately require *dotenv* what we will do is all exports we will do from dotenv and we will import our config file and everything should be a good to go
        module.exports = {
            PORT: process.env.PORT
        }
        ```
8. Create `.env` files, inside this we write our enviroment variables.
```Javascript
 
PORT = 3000

```

9. Run ``` node src/index.js```
Note: To check what all port running on your system run `sudo lsof -i -P -n | grep LISTEN` works in linux
for windows `netstat -a -b`

10. Create `controllers` `routes` `services` `utils`  `middlewares
` inside src folder and inside all these folders add `index.js`

11. Most of the time we will work with API driven application and API versioning is important so inside our routes we will have different route folder for different versions 

12. Add `"dev": "npx nodemon src/index.js"` inside script tag in package.json file, and run `npm run dev` to setup nodemon 

13. If we have to modularise app routings into separate folders for separate entities, then what we can do is we can make express router. 

- Whenever we will have some coding implementation definetel there will be some bugs and we would like to  have a good login information coming out of those bugs so that we would be able to debug it well, In order to handle that we have a package called  `winston npm`  we will integrate it and manage a small log file


-----

- ORM: Object Relational Mapping