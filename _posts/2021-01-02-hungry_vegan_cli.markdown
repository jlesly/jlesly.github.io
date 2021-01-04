---
layout: post
title:      "Hungry Vegan CLI"
date:       2021-01-02 12:05:06 -0500
permalink:  hungry_vegan_cli
---

After reading the instructions for the first project, I felt excited and nervous at the same time. The project consisted of building a Command Line Interface (CLI) by scraping a website with Nokogiri or using an API. 

I used draw.io to create a diagram of how my program would work. As I worked on the CLI I went back and edited the diagram to reflect what I had coded. This was the final diagram: 

![Imgur](https://i.imgur.com/BDBwAgi.png)


I decided to use Yelp Fusion API to build a CLI that would allow users to find restaurant with vegan options. 

I navigated to the directory Flatiron and then got a list of the files in that folder and navigated to the Projects folder. I created a directory by using the command `mkdir hungry_vegan` and used *bundle gem hungry_vegan* to get a skeleton of the project files. 

![Imgur](https://i.imgur.com/Bf5r5gh.png)

A client id and an API key is required to use the [Yelp Fusion API](https://github.com/bkeepers/dotenv).  Since the client id and API key are unique to my account I needed to keep that informaton private. I used [dotenv](https://github.com/bkeepers/dotenv) to store my client id and API key. After I created a file in my root directory named *.env* I added *gem "dotenv"* and ran *budle install*. 

I created a folder hungry_vegan in lib and created an api, cli, and restaurant (.rb) file. I also created another file under bin named hungry_vegan that would be where the application would run. The executible file needs the line `#!/usr/bin/env ruby` , a shebang, that tells the interpreter to run the file in ruby. I also included `require_realtive '.../lib/hungry_vegan'` and a line to run the application 'HungryVegan::Cli.new.greeting' . After creating the files I added an initial commit by doing *git add .* . 

![Imgur](https://i.imgur.com/Voev2ve.png)

The hungry_vegan.rb file in lib served as an environment file and needed to be updated to require the gems and require relative the files under lib/hungry_vegan that would include api.rb, cli.rb, restaurant.rb, and version.rb.

![Imgur](https://i.imgur.com/yX5I9de.png)

In order for the file * bin/hungryvegan * to execute the application the file needed permission to execute. I ran `ls -lah`
to get a list of all attributes in human readable format and confirmed the file had readable and writeable permissions but not executible permissions. Using the `chmod` command I added executible permissions to the bin/hungry_vegan file. 

![Imgur](https://i.imgur.com/2yLY13S.png)

I opened the gemspec file and filled in the spec.summary, spec.description, sepc.homepage, and spec.metadata with the corresponding information for my project. 


I found that there are many [options](https://blog.bearer.sh/top-ruby-http-client-gems/) for a ruby http client and decided to use the gem [http](https://github.com/httprb/http) for my project. I added a list of gems (pry, dotenv, and http) needed for the project in the Gemfile and then ran bundle install. After I completed the project I added the gem [colorize](https://github.com/fazibear/colorize) to add color to my text. 

![Imgur](https://i.imgur.com/DMptI9l.png)

I used the [Yelp Fusion API](https://www.yelp.com/developers/documentation/v3/get_started) documentation and [http gem](https://github.com/httprb/http) documenation to build my api class. 

![Imgur](https://i.imgur.com/zfnRvsE.png)

I went back and forth to build the cli class and restaurant class by running the program using ruby bin/hungry_vegan and tacklig one error at a time. 


