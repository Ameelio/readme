# Project Overview

If you look at the GitHub Organization, you'll see a number of projects. We're taking an semi-API Driven Development approach with most of the projects, except for the official Ameelio website which will be a single application.

This README isn't meant to be a complete design document (yet), but should give you an overview of the projects that we'll be working on. Also note that besides the demo, none of these projects have been started. Don't feel too intimidated by that though, because it's a good chance to be a part of the true beginnings of Ameelio and gain experience doing this sort of development from start to finish (or from start to maintain).

# Projects

## Ameelio.org

The official Ameelio website. This is a [Laravel 6](https://laravel.com/docs/6.x) application. We chose Laravel for this because it's fairly fast and lightweight compared to the previous WordPress implementation, simple to use (but powerful if necessary) and the ecosystem is pretty great. There won't be much backend logic to worry about with this project. The core of the work will be done on the Views (templates), involving HTML, CSS and *some* JavaScript.

We're using the [Recidiviz](https://www.recidiviz.org) website as inspiration. While we don't want to copy-paste the template, or mimic it exactly, the relevant site gives a solid idea of how we want the site to look. The navbar is simple. You are presented with a Logo and an option to Login. Then you have a large banner which contains a bit of dynamic information and a "call to action" of sorts. Then you have a Supporters and Collaborators section which we will also have. After that, we'll have a section presenting our projects (Tablet, Connect, Letters, Forum) which will give a sentence overview of each project and then link to a dedicated page for each. At the bottom, we'll have a standard footer. We want to try to stick to the color scheme you see on the current site.

## Connect

Connect is the application which inmates, facility administrators and regular users will access to have video/message communication as well as manage those things. Users can sign up, add inmates, schedule to connect with inmates and video chat when their request has been approved by a Facility Administrator. Inmates will be managed by Facility Administrators and will be able to log in, see which users they're connected with, previous messages/schedules and their current schedule. We're building the front-end as a web application and will package it for mobile later on.

The **Connect** project itself has been split up into two sub-projects...

### Connect API
This Python/Flask/MySQL RESTful JSON API will handle things like user authentication/authorization, inmate/facility/request management, etc...The **connect-demo** project has attempted to construct the database migrations as close as possible to how they will be for the *pilot* version of this API. It would be worth checking out the migrations there to understand how the database will look.

### Connect UI
This will be the front-end application that will eventually consume the Connect API when it is at a *stable-enough* version. The initial work will be working out a solid plan on the components that the application will need as well as a clean and concise *style* in CSS. Most of the planning as gone into the API, so there's really not much *set-in-stone* with this project, so communication will be key when piecing things together.

## Letters

This project is independent and the goal is to release it before the Connect pilot. The Connect application is meant to be modular and tweaked per facility (if necessary) while the Letters application is completely independent.

Letters is the application that regular users (on the *outside*) will access that will allow them to easily find an inmate and send letters to them. So users will sign up, add inmates to their contact list, and write up a "letter" the same way one would write an e-mail. Then we will interact with a separate API/servicve.

Letters will be another PHP/Laravel application but will also involve a web-scraping project written in Python. Some things are still TBD regarding this project but if you're interested in web-scraping then this project is for you.

## Letters Nationwide Inmate DB
We'll be scraping publicly available information and building a database of inmates across the nation, and doing our best to keep it up to date. This will help for getting in touch with inmates even if you don't know their inmate number. If for some reason our database can't automatically fill in the information on the inmate that the user is searching for, we'll link the user to the appropriate website where they can find the correct information.

The web scraping piece of the project will be written in Python.
