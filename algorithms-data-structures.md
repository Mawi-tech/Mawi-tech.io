---
layout: default
title: Algorithms and Data Structures
---

[Back to portfolio home](index.html)

# Artifact Two: Algorithms and Data Structures

**Course Advising Program** | C++
**Origin:** CS-300 DSA Analysis and Design, final project

| | |
|---|---|
| **Original artifact** | [View original code](https://github.com/Mawi-tech/CS300) |
| **Enhanced artifact** | [View enhanced code](REPLACE_WITH_ENHANCED_LINK) |
| **Category** | Algorithms and Data Structures |
| **Course outcomes addressed** | Outcome 3, Outcome 4 |

---

## Describing the Artifact

The artifact I chose for the algorithms and data structures category is the
Course Advising Program I built for CS-300: DSA Analysis and Design. The
application is written in C++ as a console program for the ABCU computer
science department. It reads a CSV file containing course data, stores each
course in a binary search tree, and gives the advisor a menu to load the
catalog, print every course in alphanumeric order, or look up a single course
and see its prerequisites.

I originally created the project during my CS-300 term about a year ago as the
final project for the course. The goal was to select an appropriate data
structure for organizing the courses. I chose a binary search tree because it
keeps the courses sorted automatically, which helps when printing prerequisites.

## Justifying Its Inclusion

I selected this artifact because it showcases how algorithm choice impacts an
application. There are always different ways to evolve an algorithm to make it
faster and more efficient.

The components that showcase my skills are the rebalancing logic inside the
insert operation and the two rotation functions I added. Because insert is
recursive and returns a node pointer, the height update and balance check run
as the call stack unwinds. Every ancestor of the newly inserted node gets
checked and corrected on the way back up, without requiring a second pass. To
preserve ordering, I implemented four balancing cases built from the two
rotation functions.

## Measured Results

Instead of performing well only by luck, this data structure now performs well
by design.

| | Original BST | Enhanced AVL |
|---|---|---|
| **Tree height (8-course catalog)** | 8 | 4 |
| **Worst-case comparisons** | 8 | 4 |
| **Worst case at 1,000 courses** | 1,000 | ~10 |

The input file is already sorted by course number, so the original tree never
branched. Every course was greater than the one before it, which sent every
insert to the right and produced what amounted to a linked list with a height
of 8. That is the worst possible outcome, since a lookup must touch all 8
nodes. After the enhancement, the tree height is 4, cutting the worst case in
half. The file is relatively small, but on a catalog of 1,000 courses the worst
case would be 1,000 comparisons for a degenerate BST versus roughly 10 for the
balanced tree.

## Reflecting on the Enhancement Process

I learned that the original insert function was already recursive and returned
a node pointer, which is exactly what AVL rebalancing requires, so the new
logic was less difficult to implement than I expected.

Another concept I picked up is the difference between a cached value and a
computed one. Storing height in each node is what makes AVL viable, because it
keeps the balance check at every level of the recursion constant time. I had to
think about building around the worst case first.

The challenges I ran into were subtle rather than dramatic. At one point the
recursive call ended up inside the null check, which left the function with no
return value on the other path. Most of my bugs did not produce crashes. They
produced incorrect answers, which are harder to notice.

## Course Outcomes Met

**Outcome 3: Designing and evaluating computing solutions while managing
trade-offs.** Insertion is slightly slower because every insert now performs a
height update, balance check, and potentially a rotation. In exchange, search
time is bounded no matter what order the data arrives in. That is the right
trade for an advising program, where the catalog is loaded once and looked up
many times.

**Outcome 4: Using well-founded and innovative techniques and tools.** I
implemented rotation-based self-balancing directly rather than importing a
library container, which demonstrates that I understand the mechanism and not
just the interface.

---

[Previous: Software Design and Engineering](software-design-engineering.html) | [Back to portfolio home](index.html) | [Next: Databases](databases.html)
