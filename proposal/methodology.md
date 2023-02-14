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
The web end is possible because of [Phoenix LiveView][LiveView],
which we will explain later.
For the server to be future-proof,
the code structure needs to be clear and modularized,
and the exposed API should ideally to be
just enough to control the program's behavior.

While the server needs to be as generic and extensible as possible,
we shall also provide specific extensions that fits academic needs
to demonstrate its abilities.

## Web End

The plan is to use [the Elixir Programming Language][Elixir]
and [the Phoenix Web Framework][Phoenix]
to create the web end of the server.

### Elixir

We will embrace Elixir, the Phoenix Framework's language of choice,
and leverage its advantages.
Because Elixir is built on top of the Erlang Virtual Machine ([the BEAM][BEAM])
and its [Open Telecom Platform (OTP)][OTP],
it will be straightforward for us to leverage its free concurrency,
publish-subscribe (Pub/Sub),
process isolation, first class documentation, and performance.

On a programming level,
we will comply with Elixir's requirement that we write purely functional code
to satisfy its immutability rule.
Functional programming will bring us huge benefits.
It is easier to do concurrent and parallel programming with functional
programming because immutability eliminates most data races.
It is also easier to define interfaces and APIs that have clear boundaries
by simply defining pure functions.

### Phoenix Framework

We will use the Phoenix Framework as a solid web server base.
Phoenix is a [full stack][Full Stack] [MVC][MVC]
web framework that provides all the conventional features
that an MVC web framework provides,
from handling HTTP requests and routing to scaling horizontally.

Phoenix is also a battle-tested framework.
For example, [fly.io][flyio] uses Phoenix for
[their user interface][flyio stack].

### Phoenix LiveView

[Phoenix LiveView][LiveView] is a module the Phoenix Framework provides that
empowers developers to make interactive web applications while preserving all
the states of the application on the server.

We will simplify front-end development with LiveView as much as possible.
We will leverage LiveView to move all the front-end logic onto the server
and communicate the front end with the back end simply using function calls
on the server.

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

## Database End

We will use [PostgreSQL][PostgreSQL] for the database and [Ecto][Ecto] for
Object-Relational Mapping ([ORM][ORM]).
PostgreSQL is currently the most powerful open source relational database,
and has been the recommended database for Phoenix applications.
Ecto is the ORM that comes with Phoenix.
Since Ecto is database agnostic,
we or the users can in theory switch to another database.
But, both PostgreSQL and Ecto are battle-tested and should be good enough.

To properly use Elixir and Phoenix,
we need to first get used to these tools.
The plan is to first build dummy applications in Elixir and web servers with
Phoenix so we can gain experience with the common pattern in this programming
environment.
After that, we can use the experience to help us design the architecture of
the web server.

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

[BEAM]: https://www.erlang.org/blog/a-brief-beam-primer/
[Ecto]: https://hexdocs.pm/ecto/Ecto.html
[Elixir]: https://elixir-lang.org
[Full Stack]: https://www.academia.edu/40632537/The_Full_Stack_Developer_Your_Essential_Guide_to_the_Everyday_Skills_Expected_of_a_Modern_Full_Stack_Web_Developer_Chris_Northwood
[flyio]: https://fly.io
[flyio stack]: https://fly.io/docs/hiring/stack/
[GraphQL]: https://graphql.org
[LiveView]: https://hex.pm/packages/phoenix_live_view
[MVC]: https://developer.mozilla.org/en-US/docs/Glossary/MVC
[ORM]: https://en.wikipedia.org/wiki/Object–relational_mapping
[OTP]: https://www.erlang.org/doc/design_principles/des_princ.html
[Phoenix]: https://www.phoenixframework.org
[PostgreSQL]: https://www.postgresql.org
[REST]: https://en.wikipedia.org/wiki/Representational_state_transfer
