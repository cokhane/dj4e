
Disclaimer: This video is the property of its original creator and is shared here for educational/informational purposes only. All rights belong to the original content owner,

FreeCodeCamp . Original video: https://www.youtube.com/watch?v=o0XbHvKxw7Y&t=989sIf you are the copyright owner and would like this content removed, please contact me directly. rhidzkhan.ahmad99@gmail.com

329

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































# dj4e
