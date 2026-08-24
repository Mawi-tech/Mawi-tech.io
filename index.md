# Professional Self-Assessment

Southern New Hampshire University's Computer Science program strengthened
technical skills including database management, programming across several
languages, testing, debugging, and system design. It also sharpened the skills
around the code, such as speaking through delivering a code review and written
communication through weekly discussions with classmates. It changed how I
judge my own work. Early in the program I measured progress by whether a
program compiled and produced output. By the end I was measuring against a
baseline: how many comparisons a lookup takes, and whether the next person to
open the file can follow it. My goal is a backend, DevOps, or platform
engineering role.

## Collaborating in a Team Environment

In the program there were times when I had to collaborate in a team environment
through a mock scrum, where we had to ensure that everyone knew their progress
on the project so that we collectively met expectations and deadlines. Keeping
that visibility current mattered, because a task nobody reported on was a task
the team could not plan around. I bring related experience from outside the
classroom, having worked several years in retail with responsibility for
assignment, coverage, and handoffs across shifts. The lesson carries over: work
that is not documented at handoff becomes work that gets redone. The discussion
and peer review components across the program added the specific mechanic of
technical collaboration, which is reading someone else's design, finding the
flaw, and saying so in a way that improves the code without putting the author
on the defensive.

## Communicating with Stakeholders

Another skill I have worked on is being able to break down technical concepts
and explain them to a non-technical audience. This is useful especially when
communicating with stakeholders, such as when presenting a project like Travlr
Getaways, an application for users to book vacations. A stakeholder does not
need to hear about Mongoose schemas or route guards. They need to know that a
customer can book a trip, that an administrator can manage listings, and that
the two cannot interfere with each other. The version of this skill I value
most is stating a trade-off honestly, which means not saying that something is
better but saying that it is faster on reads, costs more on insert, and here is
the number.

## Data Structures and Algorithms

The program changed my instincts here most. I moved from choosing a container
because it was familiar to choosing it because of what the access pattern
demanded. Java coursework implementing a service layer over in-memory
collections, with unit test coverage, taught me to treat lookup cost and
uniqueness constraints as design decisions rather than implementation details.
I apply the same thinking outside coursework. A personal trading system I
develop runs five strategies concurrently, and making sure one stalled API call
cannot block the other four is a concurrency and data flow problem rather than
a finance problem.

## Software Engineering and Databases

Across the program I worked in C++, Java, Python, and JavaScript or TypeScript.
The portable lesson was architectural rather than syntactic: separate data,
logic, and presentation, and the code survives change. Travlr Getaways made
that concrete, because one Express and Mongoose API served both a
server-rendered customer site and an Angular administrative client, so the
second interface was added without rewriting the data layer. Deploying a
Next.js tool of my own added hosting, build configuration, and users who find
edge cases I did not test for.

## Security

Security is the outcome where I changed most. I now start from what an attacker
can observe rather than what a user is supposed to do. Secure coding coursework
had me implement a Spring Boot service with TLS and cryptographic hashing for
data verification, along with dependency vulnerability checking. That was the
first time I understood that a vulnerability can arrive through a library I
never read. That mindset is now habit: no credentials in source control,
validation at the server rather than the client, and the assumption that any
value a user controls is hostile.

## How the Artifacts Fit Together

The three artifacts that follow trace one system from the interface down to the
data. Enhancement One improves the structure and maintainability of a C++ and
OpenGL renderer, which is the presentation layer and the question of whether a
codebase can be extended without breaking. Enhancement Two replaces an
unbalanced binary search tree with a self-balancing AVL tree, which is the
logic layer and the question of whether a solution holds up as input grows.
Worst-case height fell from 8 to 4 and average comparisons per lookup fell from
4.50 to 2.62. Enhancement Three adds the authentication and authorization layer
a MongoDB-backed dashboard never had, which is the data layer and the question
of who is permitted to see what.

Read in order, they move from what the user sees, to how the system decides, to
what the system protects. That is also the order in which I learned to think
about software. Individually each one shows competence in a single area.
Together they show that I can reason about a system as a whole, find the
specific weakness in existing code, and defend the change I made.

***

