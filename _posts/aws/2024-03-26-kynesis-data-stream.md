---
title: "Kinesis Data Streams "
date: 2024-03-26 00:00:00 +0800
categories: [aws, streaming analytics]
tags: [aws, streaming analytics]
---

Data streaming technology enables a customer to ingest, process and analyze
high volumes of high velocity data from a variety of sources in real time

## What are some technical requirements for streaming ?

- Be able to process high throughput data with low-
  latency, typically in the order of a few hundred
  milliseconds
- Fan out to multiple consumers
- Ordered consumption of data for certain use cases
- Replay data to handle downstream failures
- Granular scaling
- High availability
- High durability
- High read concurrency
- Data Retention

## Managed Ability to Capture & Store Data

- Data streams are made of Shards
- Each Shard ingests data up to 1MB/sec, and up to 1000 TPS
- Each Shard emits up to 2 MB/sec
- All data is stored for 24 hours to 7 days
- Scale Kinesis data streams by splitting or merging Shards
- Replay data inside of 24Hr -7days Window

## Routing data into the stream and ordering

### Partition key

- Segregate and route data records to different shards of a stream.
- Used by consumers to read data specific to the unique identifier in the exact order in which the records are stored.

## Enhanced Fan-Out and HTTP/2 support for Faster Streaming

- HTTP/2 to allow <100 ms deliverv
- Enhanced Fan-out allows for multiple consumers, each at 2MB/second independently.

## When to use standard consumers:

- Total number of consuming applications is low (<3)
- Consumers are not latency-sensitive
- Minimize cost

## When to use enhanced fan-out consumers:
- Multiple consumer applications for the same Kinesis Data Stream. Default limit of five registered consuming applications. More can be supported with a service limit increase request
- Low-latency requirements for data processing .Messages are typically delivered to a consumer in less than 70 ms