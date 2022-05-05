Frontend of Fifa football management system for database project

Backend of Fifa football management system for database project

To Run the App first install MySql create connection with host: "localhost" user: "root" password: "Levw1234" database: "fifa"

create new schema called fifa, right click and make it default create the fifa.sql query file and insert the sql code and run it same with triggers.sql and assertions.sql (sql file for each is in sql folder)

Run Node with npm start (at port 3000 so serving images work fine) and React with npm start (at port 3001)

now you can start Creating Tuples in that order: Country > League > Club > Manager > Player


Requirments and Specifications
The Club entity refers to the sports club which all other entities branch from. It has a unique ID ‘CID’, ClubName, and an establish date. The Club also has a composite attribute referring to its detailed Address (street, city, zip code). Each Club has a manager who manages the Club and Players who play for the club.

The player entity has all the information on players including their name, unique ID, Image and a   composite attribute that lists their stats (Pace, Dribbling, Shooting, Physical, Defending, Passing)
Each Country has unique name and a  continent which it belongs to and each player has a nationality and each country has leagues.
Each Manager has a ID and a name who manages a club. Clubs participate in leagues.
Each League holds the league that each club participates in with a name and a ranking category which ranks it among other leagues in the country.








ER Model










Relational Schema















SQL Create Statements, Triggers & Assertions

Implemented using MYSQL


 

















Triggers

This Trigger makes sure that if any of the player stats (pace, dribbling, shooting, passing, physical defending) are values between 0 and 100 so if less than 0 is inserted the value is set to 0 and if more than 100 the value is set to 100

 

Assertions
This assertion makes sure the number of tuples in country table cannot exceed 195. As this is the number of countries in the world.






Tables Filled

Country
  

Leagues
 

Clubs
 

Managers
 

Players











Frontend and Backend Queries DB Connection

Code with Instructions in Readme on how to run the project
Backend Code: https://github.com/LevwTech/fifa-db-backend
Frontend Code: https://github.com/LevwTech/fifa-db-frontend

Backend
We connected to the database using NodeJS express server
And implemented queries for creating and reading each table (10 queries)
Such as 
Select * from player - to get all players.
And 
Insert INTO country (CountryName, Continent) - to create a country.
We then created then created two complex queries that use aggregate functions and nested queries.
The first complex query takes from the request all the maximum and minimum stats and returns all the players within that range of stats and ther count.
The second complex query takes the club ID from the endpoint and selects all players in that club and most importantly, it also returns Average stats of all players as the Club Stats.
Find the code for all backend endpoints of the queries below. (We used multer to get the image upload of each player)
https://github.com/LevwTech/fifa-db-backend/blob/main/index.js
Frontend
We used React, Javascript, Html and Css to create a user interface to talk to the backend via rest api and insert to the database via forms from client side and display the data obtained from select queries. We display players inform of nice fifa cards.

 
 
We must follow domain, key, null, referential & entity integrity rules while creating the tables. Otherwise, it will result in an error from the database/backend.















