# Project Objectives (500 Words)

<!-- What are the key goals of the project? -->

The goal is to create a piece of software that functions as a forum web server.

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
During these updates,
it is crucial that the server as a piece of software is highly maintainable
and extensible,
otherwise it would result in large maintenance costs.

To achieve such,
the server needs to be resilient to changes applied to it.
It needs to be clear and modularized.

## User Experience

## Server Performance
