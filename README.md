This is base nodejs project templete, which anyone can use as it has been prepared, by keeping some of the most important code priciples and project management recommandations.

`src` -> Inside the src folder all the actual source code regarding the project will reside, this will not include any kind of tests. (you might want to make separate tests folders)

Lets take a look inside the `src` folder

- `config` -> In this folder anything and everything regarding any configurations or setup of a library or module will be done. for example, setting up `.env` so that we can use environment variables anywhere in a cleaner fashion, this is done in the `server-config.js`. One more example can be to setup logging library that can help you to prepare meaningful logs, so configuration for this library should also be done here.

-`routes` -> In the routes folder we register a route and the corresponding middleware and controllers to it.

-`middlewares` -> they are just going to intercept the incoming request where we can write out validators, authenticators etc.

-`controllers` -> the are kind of the last middlewares as post them you call your business layer to execute the business logic. In controllers 
we just receive the incoming req and them pass it to the business layer, once business layer returns an output, 
we structure the API response in controllers and send the output.


- `repositories` -> this folder contains all the logic using which we interact the db b y writing queries, all the raw queries or orm quries will go here.


- `services` ->  contains the business logic and interacts with repositories for data from the database.

- `utils` -> container helper methods, error classes etc.       



### Setup the project
- Download this templete from github and open it in your favourite text editor.
- Go inside the folder path and execute the following command:
    ```
        npm install
    ```
- In the root root Dirctory create a `.env` file and add the following env variables.
    ```
        PORT=<port number of your choice>
    ```
   ex:
    ```
       PORT=3000
    ```
- go inside the `src` folder and execute the following command: 
    ```
        npx sequelize init
    ```
- By executing the above command you will get migrations and seeders folder along with a config.json inside the config folder.
- If you are setting up your developement environment , then write your username and pass of your db and in dialect mention whatever db you are using for example, mysql, mariaDB.
-If You are setting up test or production environment, make sure you also replace the host with the hosted db url.

- To run the server execute
    ```
        npm run dev
    ```