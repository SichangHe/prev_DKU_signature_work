# Methodology (750 Words – 1000 Words)

<!-- How do you intend to accomplish the project? -->

## Overall Architecture

The overall architecture of the server would be similar to a typical web server
but with different module separation.
The forum web server, like most web server applications,
will require a *back end* to communicate with its clients,
and a *front end* to ship to the client for users to interact with,
and standalone *auxiliary libraries* that help the front end and the back end
accomplish certain tasks.
But, we will merge part of the back end and the front end into *the web end*,
and split the rest of the back end into database communication and business
logic.

The typical methodology would be to have a front end written in JavaScript,
a back end in some other programming language like Python that both serves
the front end and handles business logic,
and establish [REST][REST] or [GraphQL][GraphQL] APIs between them to communicate.
However, this design brings major drawbacks.
Any front end changes relating to the APIs require changes in the back end,
and vise versa.
The two changes are usually far away in the code base and
written in different programming languages,
causing a context switch and extra testing and maintainability burden.
Any business logic change or additional plugins would need to accommodate the
behaviors of the web part of the server,
making it less extensible.

As opposed to what typical servers do,
we will have a web end to handle the front end and facilitate communication,
a logic end to handle server logic,
and a database end to talk to the database.
The web end is possible because of Phoenix LiveView,
which we will explain later.
For the server to be future-proof,
the code structure needs to be clear and modularized,
and the exposed API should ideally to be
just enough to control the program's behavior.

While the server needs to be as generic and extensible as possible,
we shall also provide specific extensions that fits academic needs
to demonstrate its abilities.

## Back End

The plan is to use the Elixir Programming Language and the Phoenix web framework
to create the back end of the server.

Built on top of the Erlang programming language and its Open Telecom Platform
(OTP),
Elixir promises free concurrency, publish-subscribe (Pub/Sub),
process isolation, first class documentation, and performance.

As a trade-off, Elixir enforces developers to write purely functional code,
which is distinct from the more popular imperative and object-oriented
programming patterns.
We will follow its functional pattern because it brings us huge benefits.
It is easier to do concurrent and parallel programming with functional
programming because each function owns all the data it needs to do its task.
It is also easier to define interfaces and APIs that have clear boundaries
using functional programming.

We will use the Phoenix web framework to obtain basic back end capabilities.
Implementing the HTTP protocol,
parsing JSONs, preventing denial of service attacks,
and other basic capabilities should not be reimplemented,
but rather inherited from a battle-tested framework.
<!-- todo: stuck -->

We will use PostgreSQL for the database and Phoenix's Ecto Object-Relational
Mapping (ORM).

To properly use Elixir and Phoenix,
we need to first get used to these tools.
The plan is to first build dummy applications in Elixir and web servers with
Phoenix so we can gain experience with the common pattern in this programming
environment.
After that, we can use the experience to help us design the architecture of
the web server.

## Front End

The plan is to mainly use Phoenix and Phoenix LiveView to deliver and update
the front end,
and Svelte when front-end computation is needed.

The styling should not be the major part of the project because different
users of this server will probably want to tweak the theme themselves.
For the ease and speed of development,
we will use Tailwindcss to style the front end,
and probably use some Tailwindcss-specific utility components such as
TailwindUI.

## Auxiliary Libraries

Most of the components that could be separated into libraries will be
Elixir libraries because this will be an Elixir application.
These Elixir libraries could either be a set of synchronous functions
or some services implemented using GenServer.

If the performance of any of the libraries is critical,
we consider making Elixir native implemented functions (NIFs) library using
the Rust programming language.
Rust is ideal for this purpose because it is one of the fastest programming
languages,
Rust NIFs can be made safe and guaranteed not to crash the Erlang Virtual
Machine (VM),
and I am familiar with Rust since I have work with it a lot.

[GraphQL]: https://graphql.org
[REST]: https://en.wikipedia.org/wiki/Representational_state_transfer
