# ADR - Load Balancing and Redundancy

## Status

Accepted

## Context

In distributed systems having single point of failure can result to dramatic consequences.
As well as there is a need scale load on multiple instances of each services.  

## Decision
To prevent single point of failure and scalability issues, service and data redundancy is must to have. It allows nicely scale load among multiple service instances. In case one service instance is offline a load balancer will spread load onto other online service instances. 

## Consequences

* On one hand introducing load balancer layer causes additional network hope which negatively impacts on overall services latency.
* On the other hand, load balancer makes system highly available and often used for SSL offloading, which removes the need in having TLS/secure channel between internal services hence it's reduces over the network calls latency.
