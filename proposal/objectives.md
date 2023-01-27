# Project Objectives (500 Words)

<!-- What are the key goals of the project? -->

The goal is to create a piece of software that functions as a forum web server
that fits academic use.

<!-- todo: merge in `academic use` -->

## Forum Web Server

A server is a piece of software that can serves information to its clients,
which themselves are also software.
A web server is a server that communicates with its clients via web
communication protocols.
Among these protocols,
the most notable two are the Hypertext Transfer Protocol (HTTP) and its version
2 (HTTP2).

Web servers can support any client that implements the corresponding protocol,
but the most popular clients are web browsers.
Web browsers empowers the users to access web applications,
services provided by connecting users' browsers to specific web servers,
without having any knowledge of the programming behavior of any server.

A forum web server serves a web application called a web forum.
In a web forum,
users can create *posts* on particular topics and *comments* in response to
other people's posts and comments.
Posts and comments are usually publicly visible among a group of users,
but such their visibility can also be tuned as needed.
These contents can be edited, hidden, or deleted by the author or moderators.

Besides satisfying these fundamentals above,
the server should meet the following requirements to be practical and valuable
in production.

## Maintainability and Extendability

It should be relatively straightforward to maintain the server and change the
way it works.

As time goes by and the needs of the users change,
a web server in general needs maintenance to stay functioning and
modifications to meet the new needs.
These updates include tasks such as fixing bugs in the server,
improving its performance, and adding new features.
During these updates,
it is crucial that the server as a piece of software is highly maintainable
and extensible,
otherwise it would result in large maintenance costs.

On the other hand,
for the server to be useful for the future,
developers should be able to customize it and reuse a portion of its
functionalities.

To achieve such,
the server needs to be resilient to changes applied to it.
The code structure needs to be clear and modularized,
and the exposed application programming interface (API) needs to be just
enough to control the programs behavior.

## User Experience

The web forum needs to be user-friendly.

As mobile applications advance,
users are now more demanding about the ease of use of web applications.
A web forum is a place to communicate with other users.
Better user experience can lead to better users psychological conditions,
and promote them to be more positive online.

Easy and obvious navigation,
clean and mobile-first interface,
and glitch-free and responsive design are needed to ensure a nice user
experience.

## Server Performance

The forum web server needs to be able to handle high throughput and scale well.

Successful web forums can have its user numbers growing quadratically,
and such rapid growth can lead to server overloads,
slowing it down or even causing server downtime.

Two key solutions to this problem are baseline performance and scalability.
A server that is by itself more efficient and performant would naturally
perform better.
However, it also needs to gain performance relatable to the increase in
the resources provided to it.
