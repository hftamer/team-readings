### Source

https://martinfowler.com/articles/microservice-trade-offs.html

### Notes

#### Pros
1. __Strong Module Boundaries__: Microservices reinforce modular structure, which is particularly important for larger teams.
    - microservices adhere to Conways' Law: a software system is designed to mirror the communication structure of the organization designing it
    - it is easier to avoid having a "Big Ball of Mud" with microservices because introducing interprocess DTOs is significantly more work than passing objects around in a monolith
    - each microservice maintains its own data leading to decentralized data management
    - it's important to note many of these advantages won't be seen right away when an application is young:
    >  You can only really tell how well a system has maintained modularity after time has passed. So we can only really assess whether microservices lead to better modularity once we see microservice systems that have been around for at least a few years.

2. __Independent Deployment__: Simple services are easier to deploy, and since they are autonomous, are less likely to cause system failures when they go wrong.
    - there is a big shift in the industry to favor small, frequent releases over big, infrequent ones and independent deployment of microservices certainly helps that cause
    - this is a double edged sword though: with microservices, you must have your CI/CD processes fleshed out and these can be a significant startup burden for new projects due to cost, time, developer priorities, etc
    - it is possible to also structure monoliths in such a way to allow them to be continuously deployed

3. __Technology Diversity__: With microservices you can mix multiple languages, development frameworks and data-storage technologies.
    - > with great power comes great responsibility
    - this advantage is only useful when you have parts of your architecture that are performance sensitive and may need to be written in lower level languages


#### Cons

1. __Distribution__: Distributed systems are harder to program, since remote calls are slow and are always at risk of failure.
    - distributed systems can incur a performance penalty
    > You have to be in a really unusual spot to see in-process function calls turn into a performance hot spot these days, but remote calls are slow. If your service calls half-a-dozen remote services, each which calls another half-a-dozen remote services, these response times add up to some horrible latency characteristics.
    - there are workarounds to this issue like making your API more coarse so less network/RPC calls need to be made. This opens the door to potential API design issues though as overly coarse APIs can themselves be a kludge.
    - asynchronous programming is a way to mask some of the performance issues seen in network calls. However, asynchronous programming is much harder to get right and reason about than synchronous programming.
    - reliability is also a concern. How do you handle one or more services failing? It's not always clear
2. __Eventual Consistency__: Maintaining strong consistency is extremely difficult for a distributed system, which means everyone has to manage eventual consistency.
    - in a nutshell, eventual consistency means that an update to a piece of data you made might not be visible right away since it has to propagate through the system. Sometimes, this can be a huge issue because business logic might operate on an out-of-date view of the model and create unexpected results
    - 
3. __Operational Complexity__: You need a mature operations team to manage lots of services, which are being redeployed regularly.
    - as mentioned before, CI/CD processes need to be well established and in working order to get the most out of microservices
    - getting these resources set up and keeping them up can be very expensive from an operational point of view as well as from a development time point of view.
    - for small or young projects, this can be a productivity killer