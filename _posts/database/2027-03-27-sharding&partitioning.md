---
title: "Partitioning & Sharing in DBMS (DB Optimisation)"
date: 2024-03-27 13:25:00 0530
categories: [database]
tags: [database]
---

# Problem

A big problem can be solved easily when it is chopped into several smaller sub-problems. That is what the partitioning technique does. It divides a
big database containing data metrics and indexes into smaller and handy slices of data called partitions. The partitioned tables are directly used by
SQL queries without any alteration. Once the database is partitioned, the data definition language can easily work on the smaller partitioned slices,
instead of handling the giant database altogether. This is how partitioning cuts down the problems in managing large database tables.

![alt text](../assets/database/shardingPartitioning.png) 

# Partitioning

Partitioning is the technique used to divide stored database objects into separate servers. Due to this, there is an increase in performance,
controllability of the data. We can manage huge chunks of data optimally. When we horizontally scale our machines/servers, we know that it gives us
a challenging time dealing with relational databases as it's quite tough to maintain the relations. But if we apply partitioning to the database that is
already scaled out i.e. equipped with multiple servers, we can partition our database among those servers and handle the big data easily.

# Patitioning Types

## Vertical Partitioning

- Slicing relation vertically / column-wise.
- Need to access different servers to get complete tuples.

## Horizontal Partitioning

- Slicing relation horizontally/ row-wise.
- Independent chunks of data tuples are stored in different servers.

# When Partitioning is Applied ?

- Dataset become much huge that managing and dealing with it become a tedious task.
- The number of requests are enough larger that the single DB server access is taking huge time and hence the system's response time become
  high.

# Advantages of Partitioning

- Parallelism
- Availability
- Performance
- Manageability
- Reduce Cost, as scaling-up or vertical scaling might be costly.

# Distributed Database

- A single logical database that is, spread across multiple locations (servers) and logically interconnected by network.
- This is the product of applying DB optimisation techniques like Clustering, Partitioning and Sharding.

# Sharding

- Technique to implement Horizontal Partitioning.
- The fundamental idea of Sharding is the idea that instead of having all the data sit on one DB instance, we split it up and introduce a
  Routing layer so that we can forward the request to the right instances that actually contain the data.

[Read more](https://www.digitalocean.com/community/tutorials/understanding-database-sharding)


![alt text](../assets/database/shardingTypes.png) 



## Pros

- Scalability
- Availability

## Cons

- Complexity, making partition mapping, Routing layer to be implemented in the system, Non-uniformity that creates the necessity of ReSharding
- Not well suited for Analytical type of queries, as the data is spread across different DB instances. (Scatter-Gather problem)
