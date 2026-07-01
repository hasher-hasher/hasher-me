---
title: 'Building a Knowledge Base Application'
date: '2026-07-01'
---
I don't like AI. It's just not as capable as it's been sold to everyone and it kills the joy of programming. These are not the only comments I have about it and there are a lot of layers to my perspective on the topic, but my current opinion about it is I don't like it and it is, to some extent, destructive.


I need to use it, tho. I use at work since a couple of products are AI oriented, so not knowing how it works is like not been qualified for the job.


This been said, I'm building a knowledge base software from scratch, and it's been one of the most interesting projects I've worked on. A knowledge base is a software that keeps "knowledge" in a database and consults it accordingly. The catch is that a model sits in from of it, which makes it way more capable than just save text content inside roles in a table, having to query them.

The database used is FalkorDB, a Graph Database. What does it mean? It means the relationships are not between entities but between nodes (read "content"). In depth explanation [here](https://en.wikipedia.org/wiki/Graph_database). This way the document ingested can be split into nodes and edges, creating some sort of logical network which a subject connects to another subject through a logical directional line, more or less how we connect the dots when trying to understand topics that are related to each other.


There are 2 models that sit in front of FalkorDB: an LLM and an Embedder model. One is used to interpret instructions and make the heavy lifting of understanding the information passed back and forth between the user and the database. The other vectorizes the inserted documents so then it can be stored accordingly in the graph. Here is one of the most interesting parts: The combination of those 2 makes it possible to insert a whole bunch of text information, and retrieve them using natural language. You don't need anymore to consult documentation or to remember exactly where a certain piece of information is located. You can just ask. The connection between all these information is already saved and can be accessed by the LLM. Accessing historical data can be a breeze with such tool.


It all works in an MCP server, which can be used by your MCP client of preference.

