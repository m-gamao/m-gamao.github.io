---
layout: post
title:      "Intro to Sinatra"
date:       2019-12-22 12:12:46 -0500
permalink:  intro_to_sinatra_gems
---


My second project for school is in Sinatra.  Sinatra is an open source framework that is written in Ruby.  A framework helps you by setting the control flow of a program.

Our assignment was to create an app that tracks a collection.  So, I created Travel App - it collects all the places that you would like to travel to in the world.  I wanted to make an app that allowed you to input the name of the destination, the location, and a description.  You should be able to save the places you want to visit, edit them, delete them, create new destinations, and see a list of all your entries.  It requires a user account, so I created sign in, sign up, login, and logout functions.
​
The first thing I did was install the Corneal gem.  Corneal set up most of the necessary files for my project.  It automatically generates the framework for you, including the folders for the models, views, and controllers.  I still had to manually create the database folder.

Sinatra utilizes MVC, a system for building web applications that governs 90% of the worlds' apps.  It stands for Model/Views/Controllers.  You have to manually set up routes and connect them to other pieces of your application.  This lets your application communicate with your database and know what HTML files to load in the browser.  You should have an application controller, and subsequent controllers for the objects (models) used in your app.  For mine, it’s users and destinations.

The controllers use a lot of Domain Specific Language.  DSL in Sinatra contains methods that allows the application to respond to HTTP requests. Methods such as GET - which retrieves information from the application/server, and POST - which updates the application with information provided by the user. There is also PUT, PATCH, and DELETE.  You can correspond them with either ‘/’, ‘new’, ‘edit’, ‘delete’, ‘1’, or ‘index’, depending on what you are trying to do.  In total, there are 7 routing methods in Sinatra.  In Sinatra, a route is an HTTP method paired with a URL-matching pattern.  Generally, the methods you create will correlate with CRUD (create, read, update, destroy). 

The application controller handles all incoming requests to our app, and sends back the appropriate responses to the client.  I created a users controller and destinations controller, and created methods in each one.  

In the model folder, you create files for each model and define those classes.  You also write the associations and relationships here (has_many, belongs_to, etc).

The view folder contains the files that display html for your app.  There is a view folder for each model and each one should have different files for each concern: index, new, create, edit.  These files use a combination of html and embedded Ruby, so the file names must end in html.erb.  Embedded Ruby has two different tags.  To evaluate code and display, use the <%= tag.  But if you want to just evaluate code, use the <% tag. 

Lastly, I created a migration file for each model, which included the model’s tables and attributes.  Once I migrated the files, I ran shotgun to see what the app looks like.  Shotgun is a small Ruby gem you can install, that makes it easier to develop and test Rack-based Ruby web applications locally by starting Rack with automatic code reloading. 

After some debugging I was able to get the app to work smoothly.  It took a little while but once I got the hang of the concepts, it was a lot of fun to do this project. 












