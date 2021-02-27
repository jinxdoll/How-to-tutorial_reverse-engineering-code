# How-to-tutorial_reverse-engineering-code

#TITLE:
1-Passport-Example

#DESCRIPTION:
This app is designed to authenticate a user's email and password. If the user does not have either of those items, then they will be redirected to a sign up page.

#DEPENDENCIES:
-bcryptjs
-express
-express-session  
 -mysql2
-passport  
 -passport-local

#PORT:

process.env.PORT || 8080

#INSTALLATION
1)Clone this repository
2)Inspect dev folders
3)Create a database. This app uses MySQL. After creating the database, open the config.json file and update with your user information for the database platform used.
4)Install dependencies
5)Run the command from your terminal “node server.js” while in your server.js file
6)Once connected, open the browser at the port designated via your internet host platform.

#FILE ANALYTICS:

> CONFIG-
    *config.json -  connect to server
    *passport.js- code to login with email address and password

> middleware
> *isAuthenticated.js - This is middleware for restricting routes a user is not allowed to visit if not logged in.

> MODELS-
  *index.js - Connects and exports database
  *user.js - requires "bcrypt" for password hashing.

> PUBLIC-
> js
    *login.js - Getting references to our email and password form and inputs.
    *members.js - GET request to figure out which user is logged in and updates the HTML on the page.
    *signup.js-   Does a post to the signup route.

> STYLESHEETS -
> style.css- Custom style sheet styling.

> *Login.html- Login form email password.
> *Members.html- Member authentication for email and password.
> *Signup html- Redirects clients from login.html page to signup page if not account associated.

> ROUTES-

  *api-routes.js -
   Using the passport.authenticate middleware with our local strategy
   Route for signing up a user.
   Route for logging user out
   Route for getting some data about our user to be used client side

  *html-routes.js -
   If a user who is not logged in tries to access this route they will be redirected to the signup page

*package.json -
contains all package info, node modules used, version info etc };

*server.js -
Requires packages, sets up PORT, creates express and middleware, creates routes and syncs database / logs message in terminal on successful connection to server };
