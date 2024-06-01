
Techy 📚💻
Table of Contents
Description
User Story
Acceptance Criteria
Mock-Up
Getting Started
Database Models
Associations
Hints
Author
Description
Welcome to Techy, a CMS-style blog site designed just for you. Here, you can publish your articles, blog posts, thoughts, and opinions on various tech-related topics. Techy is built from scratch, following the MVC paradigm, and uses Handlebars.js for templating, Sequelize for ORM, and express-session for authentication. It’s your platform to share insights and engage with the developer community. ✨

User Story
css
Copy code
AS A developer who writes about tech
I WANT a CMS-style blog site
SO THAT I can publish articles, blog posts, and my thoughts and opinions
Acceptance Criteria
🏠 Homepage and Navigation:
When you visit the site for the first time, you'll see the homepage with existing blog posts (if any).
You'll find navigation links for the homepage, dashboard, and an option to log in.
🔐 Sign-Up and Authentication:
If you choose to sign up, you'll be prompted to create a username and password.
Your credentials will be saved, and you'll be logged in automatically.
When you revisit the site later, you can log in with your saved credentials.
📝 Post Interaction:
Once logged in, you'll see navigation links for the homepage, dashboard, and an option to log out.
The homepage will show existing blog posts with their title and creation date.
Clicking on a blog post will show you the title, content, creator's username, and creation date, along with an option to leave a comment.
When you leave a comment and submit it, the post will update to show your comment, your username, and the date it was created.
📋 Dashboard Functionality:
Your dashboard will display the blog posts you've created and give you an option to add new posts.
You can create, update, and delete your blog posts.
⏲️ Session Management:
You can log out by clicking the logout option.
If you’re idle for a while, you'll still be able to view posts and comments, but you'll need to log in again to add, update, or delete posts.
Mock-Up
You can see animations demonstrating the API routes tested in Insomnia Core in the assignment description.

Getting Started
Clone the Repository:

bash
Copy code
git clone <repository-url>
cd <repository-folder>
Install Dependencies:

bash
Copy code
npm install
Set Up Environment Variables:

Create a .env file with the following:
env
Copy code
DB_NAME='techy_db'
DB_USER='your_mysql_username'
DB_PASSWORD='your_mysql_password'
SESSION_SECRET='your_secret_key'
Database Setup:

Create the database using the schema.sql file:
bash
Copy code
mysql -u root -p < db/schema.sql
Run the Application:

bash
Copy code
npm start
Database Models
User

id (Integer, Primary Key, Auto Increment)
username (String, Not Null)
password (String, Not Null)
Post

id (Integer, Primary Key, Auto Increment)
title (String, Not Null)
content (Text, Not Null)
date_created (Date, Default: Current Date)
user_id (Integer, References User Model's id)
Comment

id (Integer, Primary Key, Auto Increment)
comment_text (Text, Not Null)
date_created (Date, Default: Current Date)
user_id (Integer, References User Model's id)
post_id (Integer, References Post Model's id)

Associations

User

Has many Post
Has many Comment
Post

Belongs to User
Has many Comment
Comment

Belongs to User
Belongs to Post

Hints

API Routes:
Make sure to complete CRUD operations in the product-routes.js, tag-routes.js, and category-routes.js files.

Seeding:
Run npm run seed to seed data to your database for testing routes.

Server Sync:
Sync Sequelize to the database on server start in the server.js file.

Author
👤 Jade Haney