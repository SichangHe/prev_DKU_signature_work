# Rationale/purpose (500 Words)

<!-- What is the importance, to you, of the project? -->

## Motivation

My experiences using forums for academic discussions are unpleasant.
These discussions include discussions for courses on [Sakai][Sakai] and [Ed][Ed],
and general discussions on [Stack Exchange][Stack Exchange].
These experiences are unpleasant for different reasons:
for Sakai Discussion,
the web interfaces are unintuitive to use and the response is slow;
for Ed,
the online editor lacks enough power to help me type out what I want;
and for Stack Exchange,
it is not obvious which comments are replies to which;
and for all of them,
it is inconvenient to cite any sources so users usually only includes a link.

I would like to provide an extensible open source forum for organization
to adapt to their own usage.
Since the above forum platforms (except Sakai) are proprietary,
organizations cannot simply tweak them and rather need to rely on the
platform provider to address these issues or provide an extra setting.
By making a fully free and open source,
responsive and extensible academic forum,
I can give academic organizations the full power to adapt it to their needs
by programmatically modifying the interface.

Besides the practical applications,
the design and implementation of a generic academic forum web server
is also an attractive task from a developer's
perspective because it brings several challenges.
To be specific about these challenges,
we will define the concepts related to the server below.

## Web Development

[Web development][Web development] is one of the most challenging aspects of programming.
It refers to all software development that provides users online experiences,
which is also referred to as the [*Full Stack*][Full Stack].
It is challenging because it involves
handling communication with the web client through the network,
maintaining the state of the application on both sides of the wire,
persisting data on disks using software like databases,
and scaling up the above abilities by taking up more resources.

Web development brings up three immediate challenges:

- Fault tolerance in state management in systems programming when connecting
    to clients with potentially unstable network conditions.

    This means that the state of the application needs to be persisted on one
    side of the communication and somehow synchronized.
- Parallel programming and distributed programming when trying to scale up
    with more CPU cores and even more computer units.
- Managing the growing complexity of the code base and database.

These hard challenges require developers to gain more relevant knowledge and
improve their abilities to address them,
which makes web development the most desirable choice to gain more
knowledge and experience on systems programming.

## Forum on the Web

A forum is a place where a group of individuals can discuss.
A forum on the web enables users to discuss together about what they care
about regardless of the physical distance between them.
For example, Reddit has been a popular forum where users discuss about a
certain topic on each subreddit.

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
It could either be online or in-person.
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

    Academic activities are usually, unfortunately, closed-source because
    isolation is in the core of academic activities.
    Organizations want to stay one step ahead of their competition,
    education wants to isolate the students from the straightforward answer
    to their homework.
    The power in control of a certain academic forum typically will come to
    a point where they want someone to see a post but not others,
    and this requirement changes slightly or significantly from content to
    content.
    For example, instructors might want some of their Teaching Assistants to
    see posts by the students under a specific section for a specific time
    period.
    So, a powerful system to control visibility is required.

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

[Ed]: https://edstem.org
[Full Stack]: https://www.academia.edu/40632537/The_Full_Stack_Developer_Your_Essential_Guide_to_the_Everyday_Skills_Expected_of_a_Modern_Full_Stack_Web_Developer_Chris_Northwood
[Sakai]: https://www.sakailms.org
[Stack Exchange]: https://stackexchange.com
[Web development]: https://en.wikipedia.org/wiki/Web_development
