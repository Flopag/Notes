# Advance database

## Deductive database

- [What is a deductive database, and how does it differ from a traditional relational database? Explain Datalog's basic concepts and syntax, and give an example of a rule-based program that can be expressed using Datalog.](Question/Q1/Q1.1.md)
- [Describe the key features and benefits of deductive databases (over relational databases), and give examples of where deductive databases can provide advantages over traditional databases](Question/Q1/Q1.2.md)
- [We have seen two conditions that rules and sets of rules must abide by. Name those conditions, and explain and illustrate their importance.](Question/Q1/Q1.3.md)

## Geospatial Databases

- [What are geospatial databases, and how do they differ from traditional databases (both conceptual and physical? Give an example of a use case for a geospatial database, and explain how it represents, stores, and uses the spatial data](Question/Q2/Q2.1.md)
- [Describe how a geospatial database extends a database. What are two ways to represent geospatial data? What are their advantages and disadvantages?](Question/Q2/Q2.2.md)
- [When modeling data for a GIS, one needs to model the data using three important concepts. What are those concepts, and how are they related? Provide an example illustrating the role of each concept](Question/Q2/Q2.3.md)
- [What is a spatial coordinate system, and how are they used in a coordinate reference system? Why are spatial coordinate systems not sufficient in GIS?](Question/Q2/Q2.4.md)

## Data Warehouses and Data Architectures

- What is a data warehouse? Explain the four key characteristics of a data warehouse (put forward by Bill Inmon). Why are data warehouses important in Business Intelligence (BI) and decision-making?
- What are the differences between a data warehouse and a data mart?
- We have seen two approaches to building and using a data warehouse. What are the two approaches and their advantages and disadvantages?
- When modeling data in a data warehouse, there are two important tables. Name and describe those two tables.
- What is denormalization in NoSQL databases? Provide and describe an example of how denormalization can improve performance in a document store.
- Describe the CAP theorem and how it relates to NoSQL databases. Explain the trade-offs between the three “guarantees” in a distributed NoSQL database.
- The description must include their role in a data model. Give an example of the simplest data model in a data warehouse. What is the name of that model?
- We have furthermore seen various models that can be built with fact- and dimension tables. What are the data models, and how do they differ?
- Describe the differences and commonalities between the models behind relational databases and data warehouses.
- Relational databases are used for OLTP, and data warehouses for OLAP. What do these acronyms stand for? Can you name and describe four other characteristic differences between OLTP and OLAP?
- How do dimension tables change over time? Describe SCD0 to SCD1, mentioning their advantages and disadvantages.
- Describe the ETL and explain its role in data warehousing. What are some common challenges and best practices for ETL development and maintenance?
- What are the 6 data quality dimensions? Provide an example of each.
- What is data governance, and what is its role in data architectures such as data warehouses and data lakes?
- What is a business glossary, and what is its role in data architectures such as data warehouses and data lakes? Describe the difference between a business glossary and a data catalog.
	- (The speaker described what a data catalog is during his talk. For a definition, you can refer to this link.)
- How do data lakes different from data warehouses?
- How do data hubs differ from data warehouses?

## NoSQL Database (including graph stores)

- What is the “definition” of NoSQL, and what is the motivation behind the movement and technologies?
- Compare the data modeling approaches used in relational databases and XXX. Provide compelling examples of scenarios where one approach is preferred over the other.
- Describe the key characteristics of XXX, including their data model, querying capabilities, possibilities, and limitations. Provide the name of a XXX database and explain how it differs from a relational database
- Describe the concepts of horizontal scaling, CAP, and BASE. How are these concepts related?
- Discuss the trade-offs of choosing a NoSQL database over a relational database. When would it be appropriate to choose a NoSQL database over a relational database, and why? Conversely, when would it be appropriate to choose a relational database over a NoSQL database?
- Explain the concept of eventual consistency in distributed NoSQL databases. How does the concept of consistency differ in ACID?
- What is denormalization in NoSQL databases? Provide and describe an example of how denormalization can improve performance in a document store.
- Describe the CAP theorem and how it relates to NoSQL databases. Explain the trade-offs between the three “guarantees” in a distributed NoSQL database. 

## NoSQL Database (focus on graph stores)

- Describe and compare RDF and property graphs. You may use an illustration to illustrate the commonalities and differences. When would you choose one over the other? Provide the names of an RDF and property graph store.
- What query language do we use to query RDF graphs? What are some key components, clauses, and elements of that query language? Provide a fairly simple example of such a query. You may draw a simple graph on which you query.
- What query language do we use to query property graphs? What are some key components, clauses, and elements of that query language? Provide a fairly simple example of such a query. You may draw a simple graph on which you query.
- How do graphs and graph stores compare to documents and document stores?
- Explain how RDF allows us to create a distributed graph database (over the Web and even the Internet). Describe the key (technological) concepts enabling this.