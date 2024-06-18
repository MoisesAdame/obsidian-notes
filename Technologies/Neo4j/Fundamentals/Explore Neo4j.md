Date: [[2024-05-13]]
***
## The Movie

- Instead of **tables** we have **objects**. 
- In order to query all the objects of a given type in *node4j* we follow:

```cypher
MATCH (m: Movie) RETURN m
```

- To add filters we just simply use **JSON** notation.

```cypher
MATCH (m: Movie {title: 'Toy Story'}) RETURN m
```

- To show relations we simply use the following syntax.
- It's important to say that, this will return a list of objects that have the attributes m, p and n. showing the relation.

```cypher
MATCH (m: Movie {title: 'Hoffa'})<-[r: ACTED_IN]-(p: Person) RETURN m, r, p
```

- In order to get more granularity, we can access the objects properties using *object.property* notation.

```cypher
MATCH (m: Movie {title: "Top Gun"})<-[r: ACTED_IN]-(p: Person) RETURN m.title, p.name, r.role
```