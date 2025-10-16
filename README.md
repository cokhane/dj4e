
Disclaimer: This video is the property of its original creator and is shared here for educational/informational purposes only. All rights belong to the original content owner,

FreeCodeCamp . Original video: https://www.youtube.com/watch?v=o0XbHvKxw7Y&t=989sIf you are the copyright owner and would like this content removed, please contact me directly. rhidzkhan.ahmad99@gmail.com

5:29 // 5:54 // 6:13 // 6:30 // 7:30 // 7:51 // 8:26 / 8:50 / 8:55

#How basic request response cycle works
- in web page if you click an href 
- it will be intercepted by an browser then it will open a socket and sends a request from the webserver
- then webserver will do something to retrieve something then will send the response 
to the same socket

 
#Network sockets
- http://data.pre4e.org/page1.html
protocol | host        | document
- its like a phone call for computers

- so how they thought it would do, you would dial a connetion you get the data
then you release the connection
- its connect, talk, disconnect

#TCP connection / socks
- in computer networking, an internet socket or network socket is an endpoint 
of bidirectional inter-process communication flow across an internet protocol-based
computer network, such as the internet

- two computers talks to each other via internet


#TCP Port Numbers
- a port is an application-specific or process-specifc software
communication endpoint
- allows multiple networked application to coexist on the same server
- its like a phone extension

#HTTP 
- the dominant application layer protocal on the internet
- Invented for the web - to retrieve HTML
- Basic Concept: make a connection - request a document - retrive the document - close the connection
- internet sockets were created in the 1970, http was invented 

#Making an HTTP Request
- Connect to the server like data.pr4e
- a handshake
- request a document

#World Simplest browser
- we dont usually send a string we send UTF-8
- python inside itself uses unicode

#Web server
- the server knows the client should go first

#Safari
- not good for debugger


#Django Terminology 
- is a way of building django application
- puts files in certain ways
- project is a collection of applications


#Django
- settings.py and wsgi
    - they route things to the right application

- all this files contains object
- change the behavior by changing the object


#Flow of a web request
- when a request is made at a django app the incoming request URL is compared 
to the list of path in urls.py
- if there is a match it selects a view. which is a bit code that handles
a database access and then produces and delivers the response to the browser
- view access the database thru a model
- this is general web pattern called Model-View-Controller


- if a user clicks on a dom ( to make request )
    - it goes to route which now pick a url if it matches choosess a view to be displayed 
    so a view and form is combined that will now be a template
    - if there is data included it go to models.py
    - if everything is ready it will return response in a rendered form


#Virtual Hosting
- many domains in one system

#
- python manage.py check
    - lets you check the sanity of your aplication


#HTML
- the web invented in 1990s
- popi
- robert caliu founder of web

- tim bernlee created world wide web consortium
- insure that web was based on open standars rather than proprietary vendor
products a bit like cat herding
- when you a url points to a directory in you web server its looking for
index.html, index.php, index.htm


#Before databases
- elizabeth fong
    - www.youtube.com/rLUm3vst87g

#Disk drives
- are magnetic media

#Common database system
- postgres - open source, enterprise scale
- oracle - large, commercial ,enterprise scale
- mysql - simple but very fast and scalable
- sqlserver - very nice 

#Database model
- model or schema is the structure or format of a database, 


#ORM
- allows us to map tables to object and columns 
- we use those object to store and retrieve data from the database
- allows you to have multiple databases



################################## DJANGO

class User(models.Model):
    name = models.CharField(max_length=128)
    email = models.CharField(max_length=128)

- models.Model: is considered inheritance
- makemigrations are the one making the file for the migration script
- migration is the one who does it



###Django Models feature
- implements ORM
- we can write python code
- database portability
- automatic from generatiom and validation


### what to do if migration is not working

- better do python3 manage.py check
- then better t

# ORM
- if you have an Album model, and Track model and if you have
class Track(models.Model)
    album = models.ForeignKey('Album', on_delete=models.CASCADE)
- if Album gets deleted all the tracks will be deleted


- if you have an Genre model, and Track model and if you have
class Track(models.Model)
    genre = models.ForeignKey('Genre', on_delete=models.SET_NULL)
- if Genre gets deleted you will only have a null value for it


### MVC 

- mode represents the data of the app, bussiness rules used to manipulate the data,
view is the interface, controller manages details involving the communication to the model of of user action,

- another interpretation,
Controller - the code that does the thinking and decision making
View - HTML, CSS. which makes up the look and feel of the app
Model - the data that we store

Controller orchestrates
- browser, model, session, cookies, ajax, view, logic

- we call the data bit the model or data model
- we call the making the next HTML bit the View
- we call the handling of input and general orchestration of it all the controller

#Task inside the server

### Views are the core of our application
- django looks for URL and uses urls.py to select a view
- views.py
    - handle any incoming data in request and copy it to database through the model
    - retrieve data to put on the page from the database through model
    - produce HTML that becomes response and return 

### Reading Url


#Url dispatcher
- a clean url schema is an important detail, in high quality web application.
Django lets you design URL however you want
- to design URLS. you create Python module informally called a URLconf ( url configuration )
this module is pure Python and is mapping between URL path expressions.
because is Py code it can be constructed dynamically


### Three patterns for view(in urls.py)
- request are routed to a pre-defined class from django itself

- request are routed to a function in views.py. that takes the http 
request as a parameter and retusn a response

- request are routed to a class in views.py that has get() and post()
methods that take the http request as a parameter and return a response


###

- django uses request and response objects to pass information througout django
- when a page is requested by a browser. django creates an HttpRequest object
that contains metadata

- then django loads appropriate view passing the http request as the first argument
to the view function.

- the API for HttpRequest and HttpResponse objects are defined in the django http module

- attributs should be considered read-only, unless stated otherwise

- HttpRquest.scheme: a string repressenting the scheme of request

- HttpRequest.body: the raw http as a bytestring. This is useful for processing data in different ways than
conventional HTML forms. 

- HttpRequest.POST: for processing conventional form data

- each view you write is responsible for instantiating, populating and return HttpResponse.

- Passing strings: typical usage to pass the contents of the page, as a string or bytestring, to the HttpResponse
constructor


################################################## Danger - What Danger?

### Why is that view name danger

- its dangerous to take data from the user and include it in the httpp response
without using escaping

- HTML + JS is programming language and you dont want your users sending code to other browser

- XSS: read site from your site and deliver it to a rouge site



### Function View

### Clsas View

- this can allow you to define a GET method and a Post method within a class


### HTTP status code


### HTTP location header
- you can send a redirect response instead of a page response to communicate
a Location. header to browser

- the location header includes a URL that browser is supposed to forward itself to



################################################## Templates to Organize HTML

### Templates 

- template is to generate HTML in a convenient way
- it contains the static parts of the desired HTML output as well as some special syntax describing
content will be inserted.
- django ships built-on backend for its own template system. creatively called the Django template
language ( DTL ) and another alternative called Jinja2
- a template is simply a text file. it can genearate any-text base format

### Templates in Folder
- it is common to reuse the name of template in several application
- we use a technique called "namespace" so that each application can load its own templates

#how to create namespace in templates
- pics/templates/pic/detail.html
    - we take the application name and create a subfolder and put the name as of the application


################################################## Django template language (DTL)

### template tags/code

- substitution {{ zap }} {{zap|safe}}
- calling code { % url 'cat-detail' cat.id % }
- logic { % if zap > 100 % } {% endif % }
- blocks { % block content % }

- anything in the double brackets is escape



################################################## Template inheritance 

### Inheritance 

- when we make a new template we can extend an existing template then add our own little bit tow make our new class
- another form or store and reuse
- DRY


################################################## URL Mapping / Reversing

- we have another page then we wanted to go to another page via link

- its is a set function that allows as to read urls.py

- it is a way to look up a view


### Reverse resolution of URLS

- it is strong desirable to avoid hardcoding these URLS


- reverse, reverse_lazy


################################################## Generic Views

### DRY
Concep: Don't Repeat Yourself (DRY)
- is a principle of Software development aime at reducing repition of software patterns,
replacing it with abstraction or using normalization to avoid redunduncy.
look for the Pragmatic Programmer

- when DRY principle is applied successfull, a modification of any single element of a system does not 
requre a change in other logically unrelated elements. Additionally, element that are logically related all
change predictability and uniformly and are thus kept in sync

- so the idea is there a logic that is being use in other places, that can get us in trouble


### Summary 

- Generic views allow us to produce lots of similar pages without cutting, pasting and deleting boilter plate
- quicker development
- consistent user experience
- less lines of code means fewer mistake


################################################## Form Processing


### Forms GET vs POST

two ways the browser can send paramaters to the webserver

GET - a parameter are placed on the URL which is retrieved
POST - the url is retrieved and parameters are appended to the request in the HTTP connection

### Rules of POST/GET

- post for creating 
- get for read/search
- get should not be used for insert,modify or delete
- web search spider will follow GET URL but generally not POST URLS



################################################## Cross Site Request Forgery

- a rogue site generates a page that includes form that posts data to a 
legitimate site where the user is logged in via a session cookie 

- so the rogue site creates a form in which a user can be convince to press
a button then the cookie will be sent along side it
 
 ### CSRF Defense

 - the legitimate site chooses a large random number and add it with the session
 - when the legitimate site generates a POST form it includes the CSR token
 - when the form is submitted the CSRF token is sent as well as the cookie
 - the site looks up the session and reject the request if the incoming CSRF token
 does not match the sessions CSRF token



 ################################################## CSRF forms


################################################## Post refresh oops



################################################## Cookies and Sessions

- cookies are a browser concept
- sessions are server concept 
- when we write python in our views.py we talk to the sessions
- cookies are essential to session 
- one of the main use of cookies is to establish and maintain sessions


### Multi-User/ Multi-Browser

- when a server is interacting with many different browser at the same time,
the server needs to know which browser a particular request from..

- request/ response initially was stateless- all browser looked identical.
this was really bad and did not last long at all

### Web cookies to the rescue

- cookies are arbitrary pieces of data chosen by the web server
and sent to the browser. the browser returns them unchanged to the server.
introducing a state. ( memory of previous events ) into otherwise
Stateless HTTP transcation. without cookies, each retrieval of a web page 
or component of a web page is an isolated event. mostly unrelated to all
other views of the pages of the same site.

1. browser request a page
2. server send a page + cookie
3. browser request another page + cookie

### Cookies in the browser

- cookies are marked as to the web address where they come from. the browser
only send back cookies were originally set by the same web server

- some cookies have expiration some short, some long

browser -> set cookie -> brower ( has the cookie  ) -> web server ( request.Cookies ) -> cycle repeats  -> 
browser ( has the cookie  ) -> web server ( request.Cookies )


################################################## Django Sessions

### In the Server - Sessions

- In most server, as soon as we start a session on a new (unmarked ) browser we create a session.
- we set a session cookie to be stored in the browser marking it
- the creating and destruction of sessions is handled by django middlewar e

### Session identifier

- a large, random number that we place in a browser the first time 

- this number is used to pick from many sessions that  the servr has active at any one time 

- server software stores data in the session that it wants to have from one request  to another
from the same browser 

- cart or login is stored in session in the server 

- its like a session is a variable that last across many request/response cycle 


### Django Sessions 

- the incoming request object has a request.session attribue 
that we can treat like dictionary ( keys, delete, update ) that persist from one request to the next request

- as long as we have the session middleware enabled in settings.py and the data table.
and browser allows cookies. we store and read request.seession in our views 
and pretend it is a magic 

-  each browser has its own dictionary, but when we are view function we are only dealing
with one browser, so that sessions is the one associated with that browser 

- sessions dont stay long since the django sessions middleware cleans it up.
- the session string is written in an algorithm known as base 64

### Summary

- cookies a way of marking each browser with an encrpyted number 
- sessions which are bit of data that is stored in db index by that large number 
- each request come we get the cookie back then we look at the session


################################################## Data modeling one to many


### Model Design

- its an art form

- avoid really bad mistakes and design clean and easily understood models

- starts with a sample data set and draw a picture

- if you build an online model design that is wrong it can cause you some perfomarnace problem
let say for facebook you built the wrong design its possible to have a slow login retrieving your data



### Database Normalization (3NF)

- tons of theory and math but we simplyfiy this to a few rules
- do not replicate data - reference - data
- add a special unique key to make reference
- use integer for to make links between tables - integers are fast and small

- dont replicate string data, names ,url
- by using integer, its faster since its what computer use its fast for calculation



################################################## Design a data model 




################################################## Representing Links in a database

################################################## Representing Links in a Django

- in django its automatic for you to add the fields no need to add them 

- makemigrations only works if you did changes in model. migrate only work i
if there are any migrations that we need , we need to remember 
before migration we need to add it in our settings. 

- if you didnt put the app in the setting. there is a chance that "make migrations wont work"

### About on_delete 

- what do we do when a row in one table points to a row in a "foreign" table
via a forieng key and the "destination row" is deleted.

on_delete = set_null keep the row but set foreign key to null
on_delete = cascade - Delete row, if the thing we are pointing to is deleted.
then delete this row


################################################## Using Models in the Django shell

### What happen when you run djangp shell
- reads settings to py -> finds app -> loads it!


################################################## Demo batch loading from CSV

- source of data to put in database you can do it via script 

### Loading data from a file

- sometimes we need to preload a data in our django db
- this data might come from an API or file
- we need to write a python program to function like the Django shell

 ### Installing django-extension

 - running script is part of the feature

 - what is this __init__. well if you have a class that needs to be imported

 - get_or_create is a good thing to use in scripts


 ################################################## Login and logout

 ### User authentiction in Django

- django comes with a user authentication system. it handles user accounts, groups, permission
cookie based user session.

- consist of 
- Permission: Binary (yes/no) flag designated wether a user may perform a certain task.
- Groups: A geneeric way of applying labels and permission to more than one user
- A configurable password hashing system
- Forms and view tools for logging in user, restricting content
- A pluggable backend system

- aith support is bundles as django contrib module. by default the required config is already included in settings.py


### Making the super user 


### Wiping out your database 

- sometimes you want to clear out and reinitialize your db.sqlite
- super users,user are stored in db so when you remove it you need to recreate 

### Additional users and permissions

- once you have the super user you can group, associate them
- read about the users and permission 


 ################################################## Logging Users into our Application

 ### Sessions are not "logging in"

 - a session is way of marking browser and storing data on the server 
 which can be stored and retrieve aross multiple request/response cyle 

 - sessions exist irrespective of wether or not the user is logged in

 - when the user passes the login check, the server adds data to the session identifiyng the user

 - when user logs out the data in session is removed
 
 - session is required to implement login

 - sessions build on cookie, login build on session

 ### Sessions, Users, Login , and Django

 - login is included in your django by default


 ### Where to go after login / logout completion

 - we want to transfer the user to a login page from many pages in our 
 application and when they successfully log in, we want to bring them
 back to our page or some other page

 - the next= parameter tells login or logout where to redurect the user after login

 - request.path return the user to the view page once its logged in


 ################################################## Look and Feel - Login Template

- to allow us to control the look and feel of the login page 
we must provide a template called "registration/login.html"

- django describes what need to be in this template 

- we can put this in any of our application templates folder 

- login page is provided by django but we need a template 

- we get to control the template  

### Data for the logged in user


### Accessing user data in Python


### Views that require a logged in user 

- Many of your views need to make sure that someone is logged in 
before performing some operation that depends on the request.user
data being set
    request.user.id
    request.user.email

- you could check user.is_authenticated at the beginnin of each view
and if user is not logged, redirect them to reverse('login) appropriate next = parameter