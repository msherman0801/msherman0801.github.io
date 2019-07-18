---
layout: post
title:      "JS/Rails Project"
date:       2019-07-18 18:58:16 -0400
permalink:  js_rails_project
---


My Rails/Javascript project was a continuation of my original rails project. As a quick recap, I made a small scale content management system that allows used to create a website for a wedding. Users can manipulate content on that website, as well as manage a built in invitation system that allows them to create a list of invitations, and lets invitee’s go to the wedding website and accept their invitation, electronically. 

I used javascript primarily for it’s AJAX functionality. I wanted to change some of the CMS to allow for asynchronous activity. Below, I will list the portions of my project that has AJAX implementation.


Dashboard Homepage: The main dashboard page has a form that allows you to create a new “website” and also lists the websites that have already been created. I used AJAX to intercept the new website form, and use JS native fetch function to complete a post request and obtain JSON data, which would allow it to append to the page. Additionally, I used a document load to make a request and get a list of all the previously made websites and append them to the page. This page essentially acts as an index, for all the websites. A user has many websites.
Dashboard Invitations: Very similar to the dashboard homepage, there is a form with two inputs, allowing a user to add a name for an invitation. From a RESTful perspective, this is a ‘new’ page. Again, using fetch, it performs that post request and appends the returned JSON data. After the page is loaded, the application automatically performs a request to get all the invitations created for that specific website. It shows all the details for that invitation, and allows you to open and manipulate it yourself. A website has many invitations.
The last section that uses AJAX is the website show page. Each website created has a show page. This is the ‘public’ version of the website, where anyone can go and get details, along with accept invitations for it. On the show page, there is a form that someone can fill out with their first and last name, which will look up the invitation for that person. The form submission uses AJAX to obtain the data for that invitation. The returned data is then appended to a modal which opens up and that page to display the invitation (if one is found, otherwise it will prompt an error message). There are different options that the user can select for their invitation, and then submit it using that form on the modal, which will prompt post fetch to send the data in. The user will then get a success message.

All uses of AJAX will take the data that is returned from the request, and create a JS object from a prototype for that specific type of data (website, invitation, invitation list). Anything that is appended to the page is actually the data from the JS object version of that information, not the JSON data itself from the fetch request. Any HTML that is appended is stored in a method within the related prototype and that method is invoked as an argument in a jquery .append.

That sums up my Rails/Javascript project!
