# Rationale/purpose (500 Words)

<!-- What is the importance, to you, of the project? -->

## Web Programming

Web programming refers to programming software anywhere in the technology stack
of providing users online experiences.
It is one of the most challenging aspects of programming,
as it involves handling communication with the web client through the network,
maintaining the state of the application on both sides of the wire,
persisting data on disks using software like databases,
and scaling up the above abilities by taking up more resources.

Web programming brings up three immediate challenges:

- Fault tolerance in state management in systems programming when connecting
    to clients with potentially unstable network conditions.

    This means that the state of the application needs to be persisted on one
    side of the communication and somehow synchronized.
- Parallel programming and distributed programming when trying to scale up
    with more CPU cores and even more computer units.
- Managing the growing complexity of the code base and database.

These challenges make web programming the most desirable choice to gain more
knowledge and experience on systems programming.

## Forum on the Web

A forum is a place where a group of individuals can discuss.
A forum on the web enables users to discuss together about what they care
about regardless of the physical distance between them.

Forum on the web brings up all the major challenges web programming could:

- Persisting user states over unstable network.

    A forum needs to track whether a user is logged in to a client and
    what permission and access they have.
    Even if the user suddenly lost connection,
    they should not lose anything they just typed or get logged out.

- Handling large amounts of requests from many different users.

    A successful forum should have a large amount of users communicating
    frequently.
    Being able to process all the requests quick enough is crucial for a
    forum web server to stay responsive and not go down.

- Structuring the complex logic of a forum.

    A forum typically needs to embed a lot of logic to decide which user should
    be able to perform which operation and see with content.
    It also needs to handle a lot of edge cases because user behaviors are not
    predictable.

## Academic Forum
