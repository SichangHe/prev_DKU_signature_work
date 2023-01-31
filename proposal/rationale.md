# Rationale/purpose (500 Words)

<!-- What is the importance, to you, of the project? -->

## Motivation

My experiences using forums for academic discussions are unpleasant.
These discussions include discussions for courses on Sakai and Ed,
and general discussions on Stack Exchange.
These experiences are unpleasant for different reasons:
for Sakai Discussion,
the web interfaces are unintuitive to use and irresponsive;
for Ed,
the online editor lacks enough power to help me type out what I want;
and for Stack Exchange,
it is not obvious which comments are replies to which;
and for all of them,
it is inconvenient to cite any sources so users usually only includes a link.

Since these forum platforms are proprietary,
organizations cannot simply tweak them and rather need to rely on the
platform provider to address these issues or provide an extra setting.
It would be nice to provide an extensible open source forum for organization
to adapt to their own usage.

Besides the practical applications,
the design and implementation is also an attractive task.
A generic academic forum web server is particularly interesting to study
because it brings the below challenges.

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

Forum on the web brings up all the major challenges web programming brings:

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
    be able to perform which operation and see which content.
    It also needs to handle a lot of edge cases because user behaviors are not
    predictable.

## Academic Forum

An academic forum should provide a platform for participants to discuss
academic topics.
Academic discussions have special requirements that ordinary forums do not
provide:

- Explicit credit on all contents.

    An academic style requires the participants to provide proper citation
    for work done by others.
    However, manually following any citation style in a forum is laborious
    and tedious,
    and encourages the participants to skip doing so.

    Modern academic forums should move a large part of this burden to the
    computer and automatically generate citation based on links or text search.
- Visibility groups that are small and complex.

    Academic activities are usually, unfortunately, closed-source.
    Organizations want to stay one step ahead of their competition,
    education wants to isolate the students from the straightforward answer
    to their homework.
    The power in control of a certain academic forum typically will come to
    a point where they want someone to see a post but not others,
    and this requirement changes slightly or significantly from content to
    content,
    so a powerful system to control visibility is required.

    This also relates to security requirements.
    If the server can be hacked to view unauthorized content,
    we would lose the above functionality.
- Customizability to fit different academic topics.

    Academic activities vary and imposes different requirements to their
    platforms.

It also does not require much manual content moderation because people in
an academic forum are usually well-behaved.

Moreover, academic forums are in high demand as the academia world is quite
new to the concept and experiments are being made.
A generic server could satisfy a large portion of the requirements and lessen
the burden on each academic organization to develop it from scratch.
