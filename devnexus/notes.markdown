# Notes for Devnexus

## Slide 1 - Title

Intro slide

## Slide 2 - Who am I

who am i.

My main focus in on mobile web and the javascript libs

check out my blog, where i like to show how to use our libs

go through the list and at the end say,  "wait a minute, that was from a different presentation"

## Slide 3 - The Past

Ok lets get started. There is all this talk about mobile first, but lets talk about the past first.

In the past we were creating our applications for desktop.  we created these rich applications and a user had to install that on there desktop and we rejoiced.

## Slide 4 - THis was mobile

Becuase this was mobile.  no one was writing apps for this thing, even though it was pretty cool.

## slide 5 - But Now..

But now,  we have these.  Smartphones,  although, really, its just a very tiny computer with a phone app.

i rarely use my iphone as a phone.

## slide 6 - And Don't Forget

and don't forget these.

## slide 7 - And Guess What

and guess what,  mobile devices and tablets are now outselling desktops.  in fact, there are people who only have a smartphone or a tablet.


## slide 8 - And the Web

this is now the web.  everything is connected.  Everything is mobile.  from our cars to our refrigirators.

## slide 9 - Our Focus

for our purposes,  Mobile is broken into these 3.5 to 4 categories

Mobile Web with REST services backend
Hybrid App - Hybrid+
Native - iOS/Android

## Slide 10 - Current Stack

just an overview of what the current stack looks like

## Slide 11 - New CHallenges

Now that we are in a mobile first world,  there are new challenges with moving our desktop apps to the mobile world.

There are 3 big challenges, which are


## slide 12 - Connectivity

Connectivity.  on desktop, we were either plugged in or on wifi,  but things were pretty simple.  But now with mobile, our connection can vary since we are always moving around.

We have carrier networks, which, depending on your provider can be really shitty,  also we have data plans.  So now we need to think about that.

and for mobile web stuff, we need to access services that are not on our domain,  so there are some tricky things with that

## slide 13 - Persistence

The second thing is Persistence.  Since we need to be mindful of users networks and data plans, we need to move more and more of our data layer to the client.

But there are challenges here too,  Things like offline, and different types of storage options depending on the device you are on.

WRT offline,  firefox, only triggers the offline event, when a user manually selects to go offline, not when a connection is lost.

## Slide 14 - Security

and last but not least is security.

Now that we are putting more and more data on the device,  how do we encrypt this and what happens when we lose the device.

And security is just hard.  Even on the desktop, its hard,  now we have to worry about mobile devices, so,  yea


## slide 15 - Aerogear

These challenges are where the aerogear project is starting to focus.  yup, shameless, project pitch


## slide 16 - Aerogear - list items

read through the list

## slide 17 - Main Goals

the overall goal of the project is to make developers lives easier when interacting with the challenges that we listed.

As developers, we want to create cool stuff, but not have to worry about all the little things.  Thats where aerogear comes in.  Let us do the heavy lifting.  Basically Aerogear is an abstraction layer framework


## slide 17 - Current Server Offerings

read list


## slide 18 - Aerogear security

A very lean security api.  we don't want to recreate the wheel

## slide 19 - Aerogear Security

one of the goals is to have a pluggable security providers.

and aerogear security is an abstraction layer that will take away the complexity so that there is a common api no matte what provider you use

currently, we are supporting the Picketlink project for IDM

## slide 20 - Aerogear security - Authentication

this is how you would create and Authentication class

## slide 21 - Aerogear Security - Registration

this is how to create the registration one

## slide 22 - Aerogear Security - REST Flavor

aerogear security comes with 3 REST endpoint by default

## slide 23 - OTP

 library for generating one time passwords according to RFC 4226

 currently we have a java library and iOS version

## slide 24 - Aerogear Controller

read the quote,  this comes from the aerogear-controller-demo readme

so what does that mean

ruby has rails and sinatra and you can use express for node but
java really doesn't have a lean mvc, theres struts, but it's very heavy

## slide 25 - Controller

NO XML

read list

## slide 26 - Controller - class is a view

here is the sample code from the previous slide,  controller will look for a view at a location.  Uses CoC

## slide 27 - Controller - beans as controller params

we can use POJO's as our parameters.  we see that the save method takes the Car class as its param,  the Car class has two variables

and then in our form in html, we can specify those values in the input tags

## slide 28 - COntroller - security hooks

Here we are hooking into Aerogear security methods.  Controller doesn't have it's own security.

This is just one example,  if there was some legacy server framework you wanted to work with,  you could write a hook from controller to the old tech.


## slide 29 - Controller - fine grained security

Here we have fine grained role based security

## slide 30 - COntroller - Consume and produce

Produce
The defualt view controller is JSP,  but we can also return JSON and HTML

Consume
with consume, we can "consume" JSON or HTML or something custom.  based on what you want.

## slide 31 - Controller - Paging
By defualt contoller uses the weblinking specification for paging

we use offset and limit for our page starting and how many things to return

## slide 32 - Controller - Pretty error handlers

With controller we can have pretty error handlers,  Error handlers are also routes

## slide 33 - Controller -CORS

now a days,  the view and the server sometimes don't run on the same domain, and setting up CORS can be a bit tricky.  Controller helps with this

## slide 34 - DEMO - COntroller

controller demo

first show beans thing

access the restricted page without login

next login and the roles

OTP


## slide 35 - Current Client offerings

now that we've talked about the server side,  not lets talk about the client side frameworks that we are working on.  Since this is what will be running on our mobile device.

Note that even though we talked about the server technologies first, each one of these librarys is server agnostic.

However, eventually, if you do use both the controller and a client lib, you might get some extra stuff for free

You may have been at Summers talk yesterday - Aerogear ANdroid

## slide 36 - Core Client Concepts

With the client side libs,  we have some core concepts.  they are ...

i know you are dying with anticipation to find out what these are,  so lets check them out

I'm going to discuss these in reverse order,  each concept actually gets more mature as we go on

## slide 37 - what is an authenticator

a collection of auth modules

this is how you would create it in the libs

## slide 38 - what is an auth module

an auth module contains both Authentication and enrollment api's

you can then easily call the login method that will hit your login REST endpoint on the server

we use enroll for registration since register is a reserved word in iOS. and we want to keep things similar

hit down a couple times


## DEMO - Maybe not

## slide 39 - what is a datamanger

a datamanager is a collections of Data objects, we call these stores

here is how you would create a DM for each

## slide 40 - what is a store

a store is basically an abstraction layer for the client side storage api's

stores have basic read/save/remove methods as well as a filter method.

Coming soon is a sync manager that will keep your data in sync with the server

Can be used standalone.  No need for pipeline or auth.  we actually have a js builder on the website

hit down a couple times

## DEMO

this is a demo that shows how DM and stores work for 2 different storage types in JS

paste the for loop in to create some data

the do a read,

then refresh

show that session storage is still there

do a remove

then do a read

the thing to note here is the common api

## slide 41 - what is a pipeline

a pipeline is a collection of server connections, we call them pipes

the code is just an example of how to create a pipeline in the js/android/iOS libs

## slide 42 - what is a pipe

A pipe is one server connection.  it has basic read/save/remove methods which translate to GET/POST - PUT/DELETE HTTP verbs

and the calls are async

example code:  very easy to create.  by default the REST enpoint will be the pipename.

but you can configure the pipe

hit down a couple times

again,  the goal is to have a common/similar api for all the libs

## slide 43 - Pipe paging

Pipeline also has a paging methods.  it can be as simple as putting true in the pageConfig, but there are also overrides

code for JS paging

## slide 43 - DEMO

demo that goes against controller, simple endpoint - yup

demo that shows paging against controller - yup

demo that shows paging against github - yup

demo that show jsonp - wow aerogear demo - server agnostic

## slide 44 - 1.0 Goals

you might be asking, is this just another REST library,  yes and no.  for 1.0 we are really focused on creating a solid foundation.

## slide 45 - 2.0

What are some of things we are looking at for 2.0,

Unified push,

Data sync - including collision detection

More Authentication Modules - oauth, social logins

Cordova PLugins, where they fit.  like core data

scaffolding with forge.  forge is a RAD tool.  get started quickly with controller and our client libs

## slide 46 - 50

where to get this


## slide 51 - Questions




