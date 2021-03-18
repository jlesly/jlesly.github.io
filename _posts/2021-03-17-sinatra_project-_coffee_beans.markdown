---
layout: post
title:      "Sinatra Project- Coffee Beans"
date:       2021-03-17 20:27:32 -0400
permalink:  sinatra_project-_coffee_beans
---




<a href="https://imgur.com/WLefBku"><img src="https://i.imgur.com/WLefBkul.jpg" title="source: imgur.com" /></a>

<span>Photo by <a href="https://unsplash.com/@soydanielwolf?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Daniel Lopez</a> on <a href="https://unsplash.com/s/photos/breville?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Unsplash</a></span>

My boyfriend and I got a Breville espresso machine for Christmas and it's been absolutely life changing. For the last two months we've kept a notebook with information of espresso shots we have made. The machine is fully automatic but we've learned a lot about coffee by pulling manual espresso shots. Depending on the brand of espresso beans we use, we get a different result. To improve our espresso-making skills we take note of the grind size, dose, extraction volume and extraction time. The pressure is also important but is difficult to quantify since espresso machines have different measures. For this project, I decided to make a web application that would allow users to keep track of the espresso-making proccess. A user would be able to create an account and login. A registered user will then be able to (CRUD) -- create, remove, update, and delete the brand name of espresso beans they are using, the name, grind size, dose, extraction volumen and extraction time. In order to perfect the art of making espresso, a user will be able to view all the data to see previous espresso variables. 

## Getting Started 

I used [Corneal](http://github.com/thebrianemory/corneal) to create the basic file structure for the application. 

<a href="https://imgur.com/whnfeFV"><img src="https://i.imgur.com/whnfeFV.png" title="source: imgur.com" /></a>

I crated a new repository on GitHub and then added the local repisotory by using: 
```
git remote add origin https://github.com/jlesly/coffee_beans.git
git branch -M main
git push -u origin main
```
<a href="https://imgur.com/3SMOaqF"><img src="https://i.imgur.com/3SMOaqF.png" title="source: imgur.com" /></a>

I decided to tackle this project by starting with the database, followed by the models, controllers, and lastly, views. 

## Database 

I created a user table by running `rake db:create_migration NAME=name_of_table.rb`. The table had name, email, and password_digest as columns. I created a beans table using that same command. 

<a href="https://imgur.com/LhjOlaY"><img src="https://i.imgur.com/LhjOlaY.png" title="source: imgur.com" /></a>

<a href="https://imgur.com/O4ZRanj"><img src="https://i.imgur.com/O4ZRanj.png" title="source: imgur.com" /></a>

The columns for the Espresso Beans table included: name, brand, grind size, dose (ground coffee input), extraction volume, and extraction time. 

The grind size, dose, extraction volume, and extraction time are all important variabes in making a shot of espresso that is not too bitter or too acidic. 

<a href="https://imgur.com/V0X5DdS"><img src="https://i.imgur.com/V0X5DdSl.jpg" title="source: imgur.com" /></a>

<span>Photo by <a href="https://unsplash.com/@that_person?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">J E S U S R O C H A</a> on <a href="https://unsplash.com/s/photos/espresso?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Unsplash</a></span>
## Models

The class user can have many beans and beans belongs to a user. 

<a href="https://imgur.com/ILynngI"><img src="https://i.imgur.com/ILynngI.png" title="source: imgur.com" /></a>

<a href="https://imgur.com/gcUTEs0"><img src="https://i.imgur.com/gcUTEs0.png" title="source: imgur.com" /></a>

Before starting the controllers I went back and changed the bean model to espresso. After making that change I moved on to the controllers and made a mental note to keep using espresso instead of beans in my code. 

## Controllers
In the application controller I enabled sessions and session_secret. I set the route '/' to display "Hello, World!". I ran shotgun as a test to make sure my local host address would display "Hello, World!".

I worked on the Users Controller and Espresso Controller and ran shotgun to make sure everything was functioning as I expected. 

I went to '/signup' and Sinatra did not recognize that ditty. I realized that the config.ru file needed to have 
```
Use UsersController
Use EspressoController 
```
in order for those two controllers to function properly. 

After I added the two lines above to the config.ru file I ran shotgun again and everything was running as expected. 


## Views
I worked on the login and signup form and checked by running shotgun that the forms were functioning the correct way. 
Because I had decided to use the word espresso instead of beans (what I had started the project with), my code was not working as expected since I still had a table beans instead of espresso.

I kept getting a BOOT ERROR and my pages were not displaying the views I had worked on. I tried renaming the tables in the database and that did not work. I also tried dropping a table and the 'table was not found.' After not getting anywhere with reanming and dropping the table, I decided to delete the database all together. I created the tables again and ran `rake db:migrate`. Both tables were migrated successfully. I ran shotgun and got a new error. 
`no acceptor (port is in use or requires root privileges) (RuntimeError)`. 

A suggested solution on Stack Overflow was to try
```
lsof -i :9393
ps ax | grep 9393
kill -QUIT 9393
```
but that did not work. 

Another solution was to run `npx kill-pot 9393` and that worked! 
<a href="https://imgur.com/mqNmAeh"><img src="https://i.imgur.com/mqNmAeh.png" title="source: imgur.com" /></a>

Now that I had a database with correctly named tables I was able to move on and work on the views.  The models still used beans instead of espresso so I would need to go back to that and correct it. 


