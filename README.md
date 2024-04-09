
Certainly! Here's a comprehensive README file for the Family Travel Tracker application:

Family Travel Tracker
Family Travel Tracker is a web application built with Node.js, Express.js, PostgreSQL, and EJS to help users keep track of the countries they have visited. Users can add new countries they've visited, view their total count of visited countries, and switch between different family members' travel histories.

Installation
Clone the repository:
bash
Copy code
git clone https://github.com/arunshajizn333/Family-Travel-Tracker.git
Install dependencies:
bash
Copy code
npm install
Set up PostgreSQL:

Install PostgreSQL if not already installed.
Create a database named FamilyTravelTracker.
Execute the SQL commands in the provided schema.sql file to create the necessary tables.
Configure the database connection:

Modify the db object in app.js with your PostgreSQL credentials.
Start the server:

bash
Copy code
npm start
Open your browser and visit http://localhost:3000 to access the application.
Usage
Adding Visited Countries:

Enter the name of the country you have visited in the provided input field.
Click the "Add" button to add the country to your travel history.
Switching Users:

Select a family member from the dropdown menu to switch to their travel history.
Adding New Users:

Click the "Add New User" button to add a new family member.
Enter the name and preferred color for the new user.
Click the "Submit" button to add the new user.
Dependencies
express
body-parser
pg
Database Schema
sql
Copy code
DROP TABLE IF EXISTS visited_countries, users;

CREATE TABLE users(
id SERIAL PRIMARY KEY,
name VARCHAR(15) UNIQUE NOT NULL,
color VARCHAR(15)
);

CREATE TABLE visited_countries(
id SERIAL PRIMARY KEY,
country_code CHAR(2) NOT NULL,
user_id INTEGER REFERENCES users(id)
);

INSERT INTO users (name, color)
VALUES ('Angela', 'teal'), ('Jack', 'powderblue');

INSERT INTO visited_countries (country_code, user_id)
VALUES ('FR', 1), ('GB', 1), ('CA', 2), ('FR', 2 );

SELECT *
FROM visited_countries
JOIN users
ON users.id = user_id;
Author
[Your Name]

License
This project is licensed under the MIT License - see the LICENSE file for details.

Feel free to customize this README file according to your preferences and project specifics.

If you have any questions or need further assistance, feel free to reach out!
