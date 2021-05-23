---
layout: post
title:      "CoffeeCoffeeCoffee"
date:       2021-05-23 02:04:02 +0000
permalink:  coffeecoffeecoffee
---

For this project I wanted to create a web application that would allow users to keep track of the espresso they brew. A user would be able to add a brewing entry, edit the brewing entry and include information about the equipment used. A user would also be able to add comments to the entry. 



**Models**

User
has_secure_password
has_many :brews
has_many :comments
has_many :brew_comments, through: :brews, source: :comments


Brew
belongs_to :user
belongs_to :equipment
has_many :comments
has_many :users_commented, through: :comments, source: :user

Comment
belongs_to :user
belongs_to :brew

Equipment
has_many :brews



**rails generate resource**

I wanted to allow the user to add information about the equipment they used to brew the coffee. I created another migration `Equipment` that had accepted brand_model as a string. 



**OmniAuth**
I used this [blog post ](https://medium.com/swlh/google-authentication-strategy-for-rails-5-application-cd37947d2b1b) to setup a social login for my web application. I followed the instructions by creating an app in  Google Developers Console and started the rails server to make sure it was working properly so far. I received the following error: ` No route matches [GET] "/auth/google_oauth2`. After checking for spelling errors in the routes and views I checked the authorized redirect URIs I had listed in the credentials section of the Google Developers Console. I was finally able to find a Stack Overflow [question](https://stackoverflow.com/questions/65783394/no-route-matches-get-auth-google-oauth2-error-keeps-coming-up) with a similar issue. The suggested [solution](https://github.com/omniauth/omniauth/wiki/Resolving-CVE-2015-9284) was to add:
```
# Gemfile
gem 'omniauth-rails_csrf_protection'
```

The next step entailed changing links to `POST` requests:
```
link_to "Log In with Google", "/auth/google_oauth2", method: :post
# or
button_to link_to "Log In with Google", "/auth/google_oauth2"
```

The code above worked! I ran the rails server and I didn't get the error I kept getting earlier. 












