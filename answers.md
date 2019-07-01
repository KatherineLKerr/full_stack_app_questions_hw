### Questions

1. What is responsible for defining the routes of the `games` resource?

`createRouter` in create_router.js, after app uses `/api/games` with `gamesRouter` (which calls `createRouter()`)

2. What do you notice about the folder structure?  Whats the client responsible for? Whats the server responsible for?

Folder structure is clearly separated between client and server, with very little overlap apart from req and res.
The client is responsible for displaying, requesting routes/information from the server and database and getting input from the user.
The server is responsible for altering the database, taking requests from the client and sending back appropriate responses.

3. What are the the responsibilities of server.js?

Connecting to the right database
Getting the games collection from the database
Listening for any changes or requests from the client
Using the correct routes from createRouter

4. What are the responsibilities of the `gamesRouter`?

Creating a router using the games collection from the database. App uses gamesRouter to find the correct route for the request recieved.

5. What process does the the client (front-end) use to communicate with the server?

A fetch request in GamesService.js. There are separate fetch requests to add a game and to delete a game.

6. What optional second argument does the `fetch` method take? And what is it used for in this application? Hint: See [Using Fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch) on the MDN docs

Second paramater is an init which is used to control other settings in the request. Here it is used to submit a post request with json data type.

7. Which of the games API routes does the front-end application consume (i.e. make requests to)?

delete /api/games/:id and post /api/games/

8. What are we using the [MongoDB Driver](http://mongodb.github.io/node-mongodb-native/) for?
To let the server communicate with the database. To let us use non relational databases, and to allow us to make fetch requests with promises to the database.
