---
layout: post
title:      "IronJobs - Data Gem Project"
date:       2019-01-02 04:40:36 +0000
permalink:  ironjobs_-_data_gem_project
---


First of all, this project was super cool. It was the first real test of coding ability so far in the course based purely off our knowledge with little instruction. I felt relatively comfortable building this. I did some refactoring before the code review and that process was actually more interesting to me than the actual construction of the application (not that it was boring or anything). It's pretty cool to realize that you can recreate a piece of functionality in a completely different way and have it perform identically to the original codebase for it.

Let's get into it.


My application, Ironjobs, is a search engine for developer jobs found on Github's job resoruce (https://jobs.github.com/). Their database of jobs has an open API for anyone to use, so naturally I chose that to avoid an API key. I think the best way to explain this application is to explain it step by step, as if you are actually using it. That being said, here is how it works.

1. The application is a Ruby gem, so you would install and run the gem to use it. Once you have it launched, it will greet you and ask for your name, where you're from, your favorite programming language, and the job title you're looking for. Once you answer those questions, it will create a "user profile" for you which will allow you to save job listings from searches you conduct as you use the application.

2. Once a profile is created, the application will automatically direct the user to the help menu which offers several options which the user can select from. The first option is to view or alter profile. This feature allows the user to view the attributes they have set for their profile. Although I haven't actually added the functionality to alter those attributes, it would be fairly easy to implement and I will probably add that in the future. 

3. The next option on the help menu is to view your list of saved jobs. This will display a list of individual jobs that you have  saved from job searches. If the list is empty, it will state that you haven't saved any jobs to your profile yet.

4. The third option in the menu is to search for jobs. When you select this, the application will ask you a few questions to base your search off of.  It will ask you where you want the job to be, what programming language it should use, and whether you want it to be full time. Once you answer these questions, the application will automatically fetch data from the API using those keywords to find the most accurate job listings possible. Once it retrieves the data, it will display them in an ordered list for you to select from. 

5. Option number 4 is an easier search option. It will return job listing results based off your profile attributes. 

6. The last option on the list allows you to exit the application and displays a message thank you for using it.


I used to two gem dependencies for this application. The first gem is called "Colorize" and it's a simple way to change the color of the output of the text in the CLI. I did this because command line applications can be pretty ugly without a little extra spice added to them. The second gem I used is called TTY-Prompt This gem lets the user interact with the application using arrow keys to select menu options. Many command line applications ask for a typed response to navigate menus, so I wanted to add something to strengthen the user experience. 

That about sums up my application! I made a video to showcase the application and encapsulate the codebase behind it. 
https://www.youtube.com/watch?v=53LA_LROS4k&t=204s


colorize
tty prompt


