# Project Objectives (500 Words)

<!-- What are the key goals of the project? -->

The goal is to create a forum web server that is easy to maintain,
extensible, and fits academic use.

## Forum Web Server

A web server communicates with its clients via internet protocols such as
the Hypertext Transfer Protocol (HTTP).

Our prioritized client to support is the web browser,
the most popular clients.
Modern web servers often serves to the browser web applications,
which functions the same as native applications with graphical user interface
(GUI).
This empowers the users to access remote resources easily via a GUI.

A forum web server serves a web application called a web forum.
In a web forum,
users can create *posts* on particular topics and *comments* in response to
other people's posts and comments.
Posts and comments are usually publicly visible among a group of users,
but their visibility can also be tuned as needed.
These contents can be edited, hidden, or deleted by the author or moderators.

Besides satisfying these fundamentals above,
the server should meet the following requirements to be practical and valuable
for academic organizations to use.

## Maintainability and Extensibility

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
otherwise it would either result in large maintenance costs and suggests the
organizations to switch to other products,
or it would fail the organizations' needs.

Developers should be able to customize it and reuse a portion of its
functionalities.
For the server to be future-proof,
the code structure needs to be clear and modularized,
and the exposed application programming interface (API) should ideally to be
just enough to control the programs behavior.

## User Experience

The web forum needs to be user-friendly.

Not all academic users are internet enthusiasts,
they need an intuitive user experience.
The server should prioritize the focus on academic discussions,
and help the users to stay in a positive mood during their activities.
To help with users experience,
the server should provide functions that academic users need in obvious places
in the user interface,
support internationalization and localization (i18n) for
users using different languages,
and follow a mobile-first approach.

## Server Performance

<!-- May not need this part? -->

The forum web server needs to be able to handle high throughput and scale well.

Successful web forums can have its user numbers growing quadratically,
and such rapid growth can lead to server overloads,
slowing it down or even causing server downtime.

Two key solutions to this problem are baseline performance and scalability.
A server that is by itself more efficient and performant would naturally
perform better.
However, it also needs to gain performance relatable to the increase in
the resources provided to it.
