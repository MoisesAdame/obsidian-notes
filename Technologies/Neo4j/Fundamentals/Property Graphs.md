---
tags:
  - database
  - graph
  - node
  - relationship
  - neo4j
---
Date: [[2024-05-13]]
***
## Structure

![[graph-parts.png|400]]

- Each **node** has attributes.
- A **relationship**, is the edge of the node.
	- The relation has to have a direction.
	- The relation can have attributes.

## Native Graph Advantage

- Everything in *neo4j* is graph and optimized for that.
- Stores nodes as objects that relate using pointers.
- This is called **index-free adjacency**.

## Non-Graph DB to Graph

- The query time is independent of the number of elements in the db.