### Source

https://martinfowler.com/articles/microservices.html

### Notes

#### What are microservices?

Microservices are an alternative way of architecting software as a suite of small services, each of which runs its own process and communicates with other services through a communication method like HTTP. This approach is in contrast to a _monolith_ which is a single piece of software responsible for housing all of the functionality: routing, communication, business logic, and so on.

Microservice architecture isn't novel and can be traced back to the UNIX philosophy of designing programs: make each program do one thing and one thing well. Then we can construct other programs by connecting these smaller programs through a communication medium. For UNIX, this communication medium is a _pipe_; for microservices, the communication medium can be HTTP, a messaging system like RabbitMQ, or even RPC (remote procedure calls). Fowler refers to this as __smart endpoints, dumb pipes__.

#### Microservice Organization

> Any organization that designs a system (defined broadly) will produce a design whose structure is a copy of the organization's communication structure. -- Melvin Conway, 1968

1. Split up microservices by business function
    - user interface, database, business logic
    - team should be careful to strictly define and maintain service boundaries
2. Independent replacement and upgradability
    - split services with the idea that the services can be replaced and upgraded at any time
3. Design a microservice that uses a monolith API as a transition
    - this is useful for putting together a microservice for short-lived events for example
4. If you find yourself constantly changing two services together, it's a sign they should be merged.

#### Microservice vs Monolith

1. Monolith
    - tends to be the first solution developers go for due to its simplicity
    - centralized governance of API, languages, and data
    - can be horizontally scaled behind a load balancer to increase throughput
    - even single instances can provide excellent throughput for lighter workloads
    - more difficult to roll out changes quickly as entire monolith has to be rebuilt and deployed
    - handling failures is easier as all logic is built into one place
2. Microservices
    - more difficult to set up and splitting up of functions is not always clear
    - as a result, more infrastructure is required to manage microservices
    - decentralized governance of API, languages, and data
        - this means that each service can own its API, data, and be written in different languages
        - __polyglot persistence__
    - each service can be independently managed and deployed, decreasing TTL
    - since each service can fail independently, managing failure states is much more complex
        - as failure is much less predictable with microservices, more real-time monitoring is required

#### Limitations

1. Distribution: Distributed systems are harder to program, since remote calls are slow and are always at risk of failure.
2. Eventual Consistency: Maintaining strong consistency is extremely difficult for a distributed system, which means everyone has to manage eventual consistency.
3. Operational Complexity: You need a mature operations team to manage lots of services, which are being redeployed regularly.