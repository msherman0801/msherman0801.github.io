---
layout: post
title:      "Rails Portolio Project"
date:       2019-05-15 16:37:35 +0000
permalink:  rails_portolio_project
---


Once again, I knew I wanted to take a step up from my previous project. I decided it would be interesting to make a small-scale content management system (CMS) using what I already know in rails. I figured it would be difficult, but conceptually, it seemed doable. One of my coworkers is getting married soon and wanted to create a website for her wedding, so people can get information and accept invitations at ease. I figured this could be what the CMS should be based off of. I would create an easy way for individuals to make a good looking website for their wedding. 

**The process:**

I knew i would need to plan this, as it would be somewhat intricate (at least compared to my previous projects). I knew I would need some sort of a dashboard that lets you manage the content (hence content management), because users will want to customize their wedding website to their own preferences. I also knew I would need a separate login portion of the website, and then the actual wedding websites that users could create. I started with the dashboard.

I figured the actual wedding website would be easy enough, because I could just create a good looking style and backfill the content that users change in their “admin dashboard”. I made it so users could register and log in first. I used OAuth for Facebook authorization on login, to allow people the ability to login using their pre-existing facebook account. That didn’t end up being too difficult. I started the basic functionality for the dashboard. I ended up making a list of types of content that the user will be able to manage. I came up with content, invitations, events, and images. Each one of those got their own model and controller. The dashboard got its own model and controller, and so did the website (the public sites that users create). 

**Essentially, the associations work like this:**

A user has many websites and invitations.
A website has many invitations, events, and uploads, and has one content. 
An invitation has many users and belongs to a website.
An event belongs to a website.
A content belongs to a website.
I used ActiveStorage for uploads, so it doesn’t have its own model, and associations are handled behind the scenes.

I tried to simplify the associations as much as possible to have them make sense and also make it able to scale if I were to grow this project. 

For styling, I ended up using bootstrap and some custom CSS, because it was quick to put together. It ended up coming together well and I for the view files, I just attached bootstrap classes onto the ERB tags.

**My Routes: **

Figuring out the routes was probably the most difficult part. I knew I wanted all the dashboard functionality to fall under a /dashboard/CONTROLLER_NAME. I used scoped routes for this and nested content, invitations, events, and images under it. However, because individuals can accept invitations whether they are logged in or not, I had to nest certain invitation views into under the :websites routes. This rose complications with restful routing, because an invitee would essentially be accessing an invitation edit page and submitting a patch request with whether they are attending or not. 

Overall, this was a fun project and I’m looking forward to refactoring it with Javascript. 

