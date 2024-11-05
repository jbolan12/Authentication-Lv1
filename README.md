# Authentication-Lv1:
A web application where users can securely register and log in to access a page displaying secrets. Built using Express.js and PostgreSQL for handling user data.

->Features:

User Registration: Allows users to register with an email and password.
User Login: Users can log in with their credentials.
Secrets Page: Displays a hidden secrets page to logged-in users.

->Prerequisites
Ensure you have the following installed:

Node.js and npm
PostgreSQL

->Installation
Clone the repository:

bash
git clone https://github.com/jbolan12/Authentication-Lv1
cd 'repository_directory'

->Install dependencies:

bash
npm install

->Set up your PostgreSQL database:

-Create a new database named secrets;
Create a users table with the following schema:

sql:

CREATE TABLE users (
  id SERIAL PRIMARY KEY,
  email VARCHAR(255) UNIQUE NOT NULL,
  password VARCHAR(255) NOT NULL
);
Update the database credentials in the code as needed:

javascript

const db = new pg.Client({
  user: "your_username",
  host: "localhost",
  database: "secrets",
  password: "your_password",
  port: 5432,
});

->Usage
Start the server:

bash
npm start
Open http://localhost:3000 in your browser.

->Routes
GET /: Renders the homepage.
GET /login: Renders the login page.
GET /register: Renders the registration page.
POST /register: Handles user registration and redirects to the secrets page if successful.
POST /login: Handles user login and redirects to the secrets page if credentials match.

->Security
For real-world use, consider implementing the following for added security:

Password Hashing: Use a library like bcrypt to hash user passwords.
Session Management: Use sessions or JSON Web Tokens (JWT) to handle user authentication securely.

->Deployment
To deploy the app, consider using a platform like Railway or Render, which supports Node.js and PostgreSQL applications and simplifies environment variable management.

->Contributing
Feel free to fork the repository and submit pull requests if you would like to contribute to this project.
