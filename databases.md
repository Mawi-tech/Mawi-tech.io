[Back to portfolio home](index.html)

# Artifact Three: Databases

**CRUD Dashboard** | Python, Dash, PyMongo, MongoDB
**Origin:** CS-340 Client/Server Development, final project, 2025

| | |
|---|---|
| **Original artifact** | [View original code](REPLACE_WITH_ORIGINAL_LINK) |
| **Enhanced artifact** | [View enhanced code](REPLACE_WITH_ENHANCED_LINK) |
| **Category** | Databases |
| **Course outcomes addressed** | Outcome 4, Outcome 5 |

---

## Describing the Artifact

The artifact I selected for this enhancement is a CRUD dashboard I originally
built in CS-340: Client/Server Development. It was created in 2025 as the final
project for the course. The original version uses Python with a Dash front end
and a PyMongo data access layer, allowing users to filter and sort through
records stored in MongoDB.

One significant issue with the original application was that it had no
authentication layer and no role assignment, so anyone could modify any
document in the database.

## Justifying Its Inclusion

I selected this artifact for the databases category because it gave me a real
working system with live location data, records carrying many distinct
attributes, and specific identifiers to look them up by. It also lacked
security features, which makes it an ideal problem for backend work. It was a
dashboard that worked, but not a dashboard that was safe for users.

## The Enhancement

The enhancement replaces the dashboard's direct, unrestricted database calls
with a proper REST API layer that mediates every request.

**JWT authentication.** Users authenticate once and receive a signed JSON Web
Token that validates every subsequent request.

**Role-based access control.** Each endpoint checks the authenticated user's
role before allowing an operation. Destructive operations such as record
deletion are restricted to privileged roles.

**Password hashing.** Credentials are stored using bcrypt rather than in
plaintext.

**Least-privilege service account.** The application connects to MongoDB
through an account scoped to only the permissions it actually needs.

Key implementation files: `auth.py`, `user_service.py`, `seed_users.py`, and
`test_auth.py`.

## Reflecting on the Enhancement Process

The biggest technical challenge was that the original dashboard was written
without any API in mind, so all of the callback logic talked to the database
directly. That meant I could not simply bolt a REST API layer on top. I had to
reconsider the architecture of the whole system.

The other challenge was ensuring that non-administrators could not perform
administrative tasks such as deleting records, which could have detrimental
effects if a malicious actor obtained those privileges.

## Course Outcomes Met

**Outcome 4: Using well-founded and innovative techniques, skills, and tools in
computing practices.** I implemented JWT authentication and role-based access
control on top of an existing MongoDB data layer, which required understanding
both the existing data access patterns and the standards for securing a REST
API.

**Outcome 5: Developing a security mindset that anticipates adversarial
exploits.** By implementing the token authentication system, hashing stored
credentials, and restricting privileged operations by role, I closed the gap
that would have allowed an unauthenticated actor to read or destroy data.

---

[Previous: Algorithms and Data Structures](algorithms-data-structures.html) | [Back to portfolio home](index.html)
