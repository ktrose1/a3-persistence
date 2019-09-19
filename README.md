Assignment 3 - Persistence: Two-tier Web Application with Flat File Database, Express server, and CSS template
===

## Book Tracker 2.0

Book Tracker
I love to read but I often find myself forgetting the book suggestions that people tell me, or vice versa not being able to provide suggestions on the spot. This project is an organizational tool to keep track of all the books you have read and you want to read, showing not only the name of the books and authors but also a comments section and ratings which furthermore sort the books into sections based on if you did or didn't like them. I've personally already started using the website, transitioning over from keeping my "To Read" list in my Notes on my phone, which was hard to visualize unlike my website. While this is a personal organizational tool at this time, in the future I could envision it as a forum for book lovers to share their best/worst book picks.

Note: Almost all the time, clicking the buttons will automatically update the tables (I have my loadData function for the tables called in all of the onclick functions) but sometimes if the website has been sitting open for a while you need to refresh the page if a button was pressed but the tables aren't automatically updating.

As far as authentication is concerned, I used the passport local strategy. The main reason was because I understood the documentation for it the most and there seemed to be a lot of resources with info about it. When logging in I would suggest using username: admin password: admin or username: Katherine password: kt because those are the accounts I have added the most data for. That said you can always make your own account and start
tracking books that you want to read too! Additionally, I used lowdb for the database, I have actually used lowdb before for a small project so it seemed like the logical choice to use it again and get some more practice.
The CSS framework I used was bootstrap. To be honest before this class I knew extremely little about web development but people always throw around words like 'node' and 'css' and 'bootstrap' so I decided it was finally time for me to really in depth understand what everyone is talking about. Also bootstrap just seems like the most common.
I had some custom changes to the background color and the buttons. Even though white might look cleaner, the background color I have just makes me feel relaxed, and if I'm going to stare at this website for over a week I wanted to be relaxed while doing so, also it kind of reminded me of the color of a book page which fit the theme.
The five express middleware packages I used are: passport, session, timeout, bodyparser, and helmet. Passport is for authentication of which I used the local strategy, session I used to help keep track of who was logged in so that people wouldn't have to start over on refresh,
timeout cuts off requests when they take too long and thus time out, bodyparser helps with parsing and in particular can be used in conjunction with passport, and helmet helps set http response headers.
I had a lot of issues with different types of inputs, whenever I would switch from a standard textbox my requests would time out. I also had trouble with passport for a while before finally getting it!

Link: https://a3-ktrose1.glitch.me/

## Technical Achievements
- **User Specific View**: I have authorized user specific data so when people login they only see their books throughout all three tables. I achieved this entirely server side so that looking for the 'currentUser' wouldn't clutter up the front end.
- **Multiple Databases**: I have two seperate 'databases' aka json files for users and data. This keeps the data seperate and if one file is corrupted I will still at least have the other and not lose everything. The user field in db.json corresponds (like a foreign key) to the username field in users.json so that you can still always connect the two.
- **Express Session**: The session middleware took my a while to fully understand but I believe it was one of the most useful pieces of middleware. In my case it creates and keeps a session until someone signs out. This way people can refresh/leave the website and come back to it and they won't have to login every single time, and instead can view their data during their session. As a user I would be very annoyed if I constant had to login so this middleware package was important for my to implement.

### Design/Evaluation Achievements
- **User Input**: I tested three different CSS frameworks: Bootstrap, Bulma, and Materialize. I then polled a couple of my friends and my roommates about which they like best before coming the the conclusion to use bootstrap.
- **CSS**: I still kept some of my own CSS for the buttons and the background. I hoped to make the background feel like a book to set the mood of the website, and keep away from the classic sterile looking framework
- **Create Account Page**: Though the directions said we could just let people login with a new uname/password and just add that to the db, I felt that as a user who didn't know that I would be discouraged from signing in unless I saw a specific place to create an account. So I added another page for account creation, to help minimize that confusion. I think that my login and account pages look very clean and professional, not unlike what you would see on a lot of other websites
