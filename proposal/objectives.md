# Project Objectives (500 Words)

<!-- What are the key goals of the project? -->

The goal is to create a generic forum web server that is easy to maintain,
extensible, user-friendly, responsive, and fits academic use.

To get a grasp of how the server should look like,
think about a platform that behaves like Ed,
but with a more sophisticated ownership model like on [Reddit][Reddit],
an editor and an edit history viewer like on [GitHub][GitHub],
and more extension points to enable features like what
[Citation Machine][Citation Machine] provides.

To specify the goal,
the following breaks down and defines the concepts involved.

## Generic Forum Web Server

A [web server][Web Server] communicates with its clients via internet protocols
such as the Hypertext Transfer Protocol (HTTP).

Our prioritized client to support is the [web browser][Web Browser],
the most popular clients.
Modern web servers often serves to the browser [web applications][Web App],
which functions the same as [native applications][Native] with graphical user interface
(GUI).
This empowers the users to access remote resources easily via a GUI.

A forum web server serves a web application called a [web forum][Internet Forum].
While a forum is where its participants discuss on certain topics,
in a web forum,
users can create *posts* on particular topics and *comments* in response to
other people's posts and comments.
Posts and comments are usually publicly visible among a group of users,
but their visibility can also be tuned as needed.
These contents can be edited, hidden, or deleted by the author or moderators.

For the forum web server to be generic,
it needs to both provide a good foundation and leave enough room for extensions.
It needs to implement all of the basic protocols a web forum provides,
such as the ability to post different kinds of content,
change content visibility and ownership,
and help with content moderation.

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
otherwise the server would either result in large maintenance costs and suggests
the organizations to switch to other products,
or it would fail the organizations' needs.

Developers should be able to customize the server and reuse a portion of its
functionalities to fit different academic need.
For example, Mathematicians would probably want the ability to render LaTeX
expressions in their posts,
Media and Arts people may want a prompt that shows visual search results
corresponding to their text description.
Some functionalities could be generally desirable.
Automatically suggesting citations,
enabling simultaneous collaboration on a single post,
and version control are among these functionalities.

## User Experience

The web forum needs to be user-friendly.

Not all academic users are internet enthusiasts,
they need an intuitive user experience.
The server should prioritize the focus on academic discussions,
and help the users to stay in a positive mood during their activities.
To help with users experience,
the server should provide functions that academic users need in visually obvious
places in the user interface,
support internationalization and localization (i18n) for
users using different languages,
and follow a mobile-first approach.
It also should be responsive,
which means that users should be able to get responses very shortly after they
perform any actions.

## Server Performance

For the forum web server to stay responsive,
it needs to be able to handle high throughput and scale well.
In case the academic organization adopts the forum rapidly, its
web forums can have a quadratically growing user count.
Such rapid growth can lead to server overloads,
slowing it down or even causing server downtime.

Two key solutions to this problem are baseline performance and scalability.
A server that is by itself more efficient and performant would naturally
perform better.
However, it also needs to scale,
which means that the organization can simply deploy the server on more powerful
machines or more machines to handle a higher load.

Organizations can safely adopt the server to their use,
knowing that the server is performant and will scale if their needs grow.

[Citation Machine]: https://www.citationmachine.net
[GitHub]: https://github.com
[Internet Forum]: https://en.wikipedia.org/wiki/Internet_forum
[Native]: https://en.wikipedia.org/wiki/Native_(computing)#Applications
[Web App]: https://aws.amazon.com/what-is/web-application/
[Web Browser]: https://en.wikipedia.org/wiki/Web_browser
[Web Server]: https://developer.mozilla.org/en-US/docs/Learn/Common_questions/Web_mechanics/What_is_a_web_server
[Reddit]: https://www.reddit.com
