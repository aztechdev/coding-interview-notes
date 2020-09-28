# Coding Interview Notes

Coding interviews can be one of the most stressful interviews for programmers.

This repo is inspired by [Kevin Naughton Jr.'s work](https://github.com/kdn251/interviews) on interview preparation.
Kevin's advice has four steps for what to learn in order:

1. [Data Structures](./data-structures.md)
2. [Big-O Analysis](./big-o.md)
3. [Algorithms](./algorithms.md) - sorting algorithms, graph-based algorithms, other classic textbook algorithms
4. Problem solve - use a website like [LeetCode](https://leetcode.com/) to practice how to approach and ultimately solve

Gayle Laakmann McDowell has a helpful table of "absolute, must-have knowledge"
from _Introduction Part VII: Technical Questions_ of CtCI:

Data Structures | Algorithms | Concepts
--- | --- | ---
Linked Lists | Bread-First Search | Bit Manipulation
Trees, Tries, & Graphs | Depth-First Search | Memory (Stack vs. Heap)
Stacks & Queues | Binary Search | Recursion
Heaps | Merge Sort | Dynamic Programming
Vectors / ArrayLists | Quick Sort | Big O Time & Space
Hash Tables | |

## Grokking the Coding Interview

It's also valuable to be able to recognize patterns in coding questions, which is
the approach taken in [Grokking the Coding Interview](https://www.educative.io/courses/grokking-the-coding-interview)
by [DesignGurus](https://www.designgurus.org/).

- [The Sliding Window Pattern](./sliding-window.md)
- [The Two Pointers Pattern](./two-pointers.md)
- [The Fast & Slow Pointers Pattern](./fast-and-slow-pointers.md)
- [Breadth First Search](./tree-bfs.md)
- [Depth First Search](./tree-dfs.md)

## Cracking the Coding Interview

I will also be going through the chapters in this classic book to get better at
coding interviews.

> Note: I have the 6th Edition of the book

- [Introduction Part VI: Big O](./big-o.md)
- [Chapter 1-4: Data Structures](./data-structures.md)

## Terminology

### Algorithms & Data Structures

- [Big O notation](https://en.wikipedia.org/wiki/Big_O_notation)
- [Time complexity](https://en.wikipedia.org/wiki/Time_complexity)
- [Master theorem](https://en.wikipedia.org/wiki/Master_theorem_(analysis_of_algorithms))
- [Space complexity](https://en.wikipedia.org/wiki/Space_complexity)
- [In-place](https://en.wikipedia.org/wiki/In-place_algorithm)
- [Brute-force search](https://en.wikipedia.org/wiki/Brute-force_search)
- [Divide-and-conquer algorithm](https://en.wikipedia.org/wiki/Divide-and-conquer_algorithm)
- [Mathematical induction](https://en.wikipedia.org/wiki/Mathematical_induction)
- [Data structure](https://en.wikipedia.org/wiki/Data_structure)
- [List of data structures](https://en.wikipedia.org/wiki/List_of_data_structures)
- [Search data structure](https://en.wikipedia.org/wiki/Search_data_structure)
- [List of terms relating to algorithms and data structures](https://en.wikipedia.org/wiki/List_of_terms_relating_to_algorithms_and_data_structures)

### Programming Languages

- [Programming paradigms](https://en.wikipedia.org/wiki/Programming_paradigm)
  - [Imperative](https://en.wikipedia.org/wiki/Imperative_programming)
  - [Declarative](https://en.wikipedia.org/wiki/Declarative_programming)
  - [Object-oriented](https://en.wikipedia.org/wiki/Object-oriented_programming)
    - [Inheritance](https://en.wikipedia.org/wiki/Inheritance_(object-oriented_programming))
    - [Composition](https://en.wikipedia.org/wiki/Object_composition)
    - [Class-based](https://en.wikipedia.org/wiki/Class-based_programming)
      - [Factory](https://en.wikipedia.org/wiki/Factory_%28object-oriented_programming%29)
    - [Prototype-based](https://en.wikipedia.org/wiki/Prototype-based_programming)
  - [Concurrent](https://en.wikipedia.org/wiki/Concurrent_computing)
    - [Concurrency](https://en.wikipedia.org/wiki/Concurrency_(computer_science))
  - [Parallel](https://en.wikipedia.org/wiki/Parallel_computing)
- [Polymorphism](https://en.wikipedia.org/wiki/Polymorphism_(computer_science))
  - [Generic programming](https://en.wikipedia.org/wiki/Generic_programming)
- [First-class citizen](https://en.wikipedia.org/wiki/First-class_citizen)
  - [First-class function](https://en.wikipedia.org/wiki/First-class_function)
- [Higher-order function](https://en.wikipedia.org/wiki/Higher-order_function)
- [Nested function](https://en.wikipedia.org/wiki/Nested_function)
  - [Anonymous function](https://en.wikipedia.org/wiki/Anonymous_function)
- [Non-local variable](https://en.wikipedia.org/wiki/Non-local_variable)
  - [Closure](https://en.wikipedia.org/wiki/Closure_(computer_programming))
  - [Partial application](https://en.wikipedia.org/wiki/Partial_application)
- [Currying](https://en.wikipedia.org/wiki/Currying)

### Software Engineering

- [Software design pattern](https://en.wikipedia.org/wiki/Software_design_pattern)
  - [_Design Patterns_ - Gang of Four](https://en.wikipedia.org/wiki/Design_Patterns)
  - [WikiWikiWeb](https://wiki.c2.com/?WelcomeVisitors)
  - [React in Patters](https://github.com/krasimir/react-in-patterns)
  - [JavaScript Design Patterns - Addy Osmani](https://addyosmani.com/resources/essentialjsdesignpatterns/book/)
  - [Creational Pattern](https://en.wikipedia.org/wiki/Creational_pattern)
    - [Factory method](https://en.wikipedia.org/wiki/Factory_method_pattern)
- [Software development process/life cycle](https://en.wikipedia.org/wiki/Software_development_process)
  - [Extreme programming](https://en.wikipedia.org/wiki/Extreme_programming)
  - [Scrum](https://en.wikipedia.org/wiki/Scrum_(software_development))
- [Composition over inheritance](https://en.wikipedia.org/wiki/Composition_over_inheritance)
  - [Composition vs Inheritance in React](https://reactjs.org/docs/composition-vs-inheritance.html)

#### Databases

- [Database model/paradigm](https://en.wikipedia.org/wiki/Database_model)
  - [Key-value](https://en.wikipedia.org/wiki/Key%E2%80%93value_database)
    - [Redis](https://redis.io/)
    - [Memcached](https://memcached.org/)
  - [Wide Column](https://en.wikipedia.org/wiki/Wide-column_store)
    - [Apache Cassandra](https://cassandra.apache.org/)
    - [Apache HBase](https://hbase.apache.org/)
  - [Document-oriented](https://en.wikipedia.org/wiki/Document-oriented_database)
    - [mongoDB](https://www.mongodb.com/)
    - [Firestore](https://firebase.google.com/docs/firestore/)
  - [Relational](https://en.wikipedia.org/wiki/Relational_model)
    - [PostgreSQL](https://www.postgresql.org/)
    - [MySQL](https://www.mysql.com/)
  - [Graph](https://en.wikipedia.org/wiki/Graph_database)
    - [Neo4j](https://neo4j.com/)
    - [Dgraph](https://dgraph.io/)
  - [Full-text Search Engine](https://en.wikipedia.org/wiki/Full-text_search)
    - [Apache Lucene](https://lucene.apache.org/)
    - [Apache Solr](https://lucene.apache.org/solr/)
    - [Elastic Search](https://www.elastic.co/)
    - [algolia](https://www.algolia.com/products/search/)
    - [MeiliSearch](https://www.meilisearch.com/)
  - [Multi-model](https://en.wikipedia.org/wiki/Multi-model_database)
    - [FaunaDB](https://fauna.com/)
  - [Data warehouse](https://en.wikipedia.org/wiki/Data_warehouse)
    - [BigQuery](https://cloud.google.com/bigquery/)
  - [Time series](https://en.wikipedia.org/wiki/Time_series_database)
    - [InfluxDB](https://en.wikipedia.org/wiki/Time_series_database)
- [Query language](https://en.wikipedia.org/wiki/Query_language)
  - [GraphQL](https://graphql.org/)
  - [SQL](https://en.wikipedia.org/wiki/SQL)
- [Object-relational mapping](https://en.wikipedia.org/wiki/Object-relational_mapping)
  - [Sequelize](https://sequelize.org/)
  - [TypeORM](https://typeorm.io/#/)
  - [Prisma](https://www.prisma.io/)
