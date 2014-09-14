# Say hello to Sinatra!

To follow along, please clone this repository to your computer first.

## Goals: 

* Learn about the structure of a Sinatra app


## Release 0

### What is Sinatra?

Sinatra is a framework for creating web apps with Ruby. Have you heard of Ruby on Rails? Think of Sinatra as a lighter version of Rails, with less built-in features. It's a great tool for creating simple web apps without all the hidden complexities of rails.

In your spare time, you should take a look at the [Sinatra Website](http://www.sinatrarb.com), and especially their [docs](http://www.sinatrarb.com/intro.html). 

Let's move on to understanding Sinatra's file structure. If you have the repository cloned, then jump in to the Sinatra-Intro folder.

### What are all these files and folders?

Up until now, you have probably been working with challenges involving just one or two files. If you take a look at the Sinatra-Intro folder, you will see a bunch of files and folders that may seem unfamiliar. Wait! Don't run away! There's nothing to be scared of.

We'll go through these files and folders to understand what they do and how they're connected. But I do want to point out something. The reason why this sinatra app is structured this way is because Dev Bootcamp wants you to get used to how things will work when you move on to learning the Ruby on Rails framework. Being exposed to this structure with Sinatra will make the transition smoother. However, if you really wanted to (and not that you ever should), you CAN build a Sinatra app with a single file. That's right. AN ENTIRE SINATRA APP CAN BE BUILT WITH A SINGLE FILE. But we'll use the the multi-file approach because it will help us organize our code better, and again, it will help you see how real web apps are structured. Let's explore!

#### 1. The app folder

This folder contains some additional folders, namely Models, Views, and Controllers. Remember the MVC concept? Well, here it is. There's also a folder called helpers, but we're going to ignore that for now.

In the model folders is where you will place all the Ruby files pertaining to the models in your database.

The view folder will contain all the views for our app such as the layout, homepage, forms, etc.

The controller folder will contain all our ruby files that tells our app how to move data around. What happens when a user visits our app? What happens when a user clicks a button to sign up? What happens when a user submits some information through a form? All these actions will be handled in our controller.

#### 2. the config folder

In this folder you will see 2 files; database.rb and environment.rb. These two files contain some settings for our database and app environment. The environment tells our app some basic things like which gems are required by our app, which controllers should be required, etc. the database file contains some configurations that ties in our models and the code required to establish a connection between ActiveRecord and our postgres database. You don't need to worry too much about what you see in these files at the moment, but just know that they contain some key configurations to connect the many different parts of your app.

#### 3. The DB folder

This file contains a folder called migrate and a file called seeds.rb. The migrate folder is where we will place the migrations files, which are basically instructions telling the database how to build the tables for our models, and what type of information each table will contain. 

The seeds file is an easy way for us to populate our database with dummy data. So let's say we wanted to test our database and app with some fake data. Instead of manually and individually creating a hundred users in our database, we can use a seed file to do that for us very quickly and with minimal effort.

#### 4. The public folder

This folder contains 2 more folders, CSS and js. The css folder will hold all of the stylesheets that makes our apps look pretty. The js older will contain, you guessed it, javascript files. So if you wanted to implement some jquery/ajax, you will throw those js files in this folder. Sinatra, by default, knows that it has to look in this public folder to find these types of files, and this will become clearer as you continue to work with sinatra and build web apps in phase 2.

#### 5. The Spec folder

This folder has to do with testing. If you were to implement tests for your app, you would place those files in here.

#### 6. config.ru file

This file is what will set tie in all other configurations that we defined in our config folder and start our sinatra app when we run a command like shotgun. You will also see that it also tells the app where the views are located. This is how Sinatra knows it has to look in app/views for things like our layout page, index page, etc. And lastly, it runs the command "run Sinatra::Application" which fires up our app. 

#### 7. Gemfile

the gemfile contains all the gems we will use in our apps. Gems are basically packaged programs (or modules) ruby developers have built to make repetitive tasks easier for you. Take a second to say "Thank you Rubyists!". If it wasn't for gems, we'd be here for days trying to get some of the most basic parts of our app configured before we can even begin to build the more fun stuff. 

If you take a look in the gemfile, you will see some gems including pg (postgres, which is the database we will use), sinatra (yes, sinatra itself is a gem), thin (a ruby webserver), activerecord (the Ruby interface that allows us to interact with our postgres database without having to write SQL), and shotgun (starts up our sinatra app, and automatically restarts it for us whenever changes are made). Can you see how gems are useful? One day you will go on to write your own gem, and you will make us proud.


#### 8. Gemfile.lock

This creates a more detailed version of your gemfile, including version numbers. Some gems depend on other gems, and this lists those as well. For example, the sinatra gem needs 3 other gems:

```Ruby
sinatra (1.3.4)
      rack (~> 1.4)
      rack-protection (~> 1.3)
      tilt (~> 1.3, >= 1.3.3)
```

#### 9. Rakefile 

The rakefile contains a very detailed set of instructions to perform some common tasks. To put things in to perspective, let's say I had a robot that does whatever I tell it to. But I have to give it very specific instructions. If I wanted a peanut butter sandwich, I would have to type the following commands in to my robot controller. 


* open the bread bag
* grab 2 slices
* open peanut butter jar
* grab knife
* scoop up some peanut butter
* spread on first slice
* scoop up some peanut butter
* spread on 2nd slice (extra peanutty buttery!)
* place the slices together

I'll probably lose my appetite by the time I've finished giving my robot instructions.

What if I had a rake task like

```Ruby
rake robot:make_peanut_butter_sandwich
```

which contains all of the above instructions? Then I wouldn't have to type them each time I wanted a peanut butter sandwich. Genius!

If you look at the rakefile, on line 10 you will see "namespace :generate", and within this section you will see 2 tasks, "task :model" and "task :migration". This will allow us to run commands such as "rake generate:model" and "rake generate:migration", which will instantaneously create Ruby files for our models and migrations. 

Look at lines 88 where it says "namespace :db". Inside this you will see some common database rake tasks like create, drop, migrate, seed. This is what allows us to run commands such as "rake db:create", "rake db:migrate", etc. You can even create your own custom rake tasks. Programming is the only profession where you will be rewarded for laziness. Embrace it!

#### 10. The readme.md

It's always good practice to include a README.md file, such as this one, to let people know what your app is about and give some insight. Although it seems like a small and negligible thing, it is actually taken very seriously in the developer community. So get used to creating a README.md file whenever you build an app from now on.

## Release 1: Building our first Sinatra app 

Coming Soon!