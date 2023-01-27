# Methodology (750 Words – 1000 Words)

<!-- How do you intend to accomplish the project? -->

The forum web server, like most web server applications,
will require a back end to serve communicate with its clients,
and front end that will get shipped to the user for them to interact with,
and standalone auxiliary libraries that help the front end and the back end
accomplish certain tasks.
Besides these, the server needs to satisfy the special functionality that
an academic forum has.

## Back End

The plan is to use the Elixir Programming Language and the Pheonix web framework
to create the back end of the server.

Built on top of the Erlang programming language and its Open Telecom Platform
(OTP),
Elixir promises free concurrency, publish-subscribe, isolation,
first class documentation, and performance.

As a trade-off, Elixir enforces developers to write purely functional code,
which is distinct from the more popular imperative and object-oriented
programming patterns.
We will follow its functional pattern because it brings us huge benefits.
It is easier to do concurrent and parallel programming with functional
programming because each function owns all the data it needs to do its task.
It is also easier to define interfaces and APIs that have clear boundaries
using functional programming.

## Front End

The plan is to use Svelte for the front-end computation,
and Pheonix and Pheonix LiveView to deliver and update the front end.

## Auxiliary Libraries
