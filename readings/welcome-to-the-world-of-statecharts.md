### Source

https://statecharts.github.io/

### Notes

#### What are state charts?

A state chart is a way of modeling a _state machine_. A _state machine_ is a software abstraction that defines a set of _states_ a program can be in as well as _transition rules_ that tell the machine how to transition from one state to the next. Each state machine should have, at a minimum, two states: an initial state where the machine starts and an ending state where the machine terminates.

#### The benefits of state charts

1. It’s easier to understand a statechart than many other forms of code.
2. The behaviour is decoupled from the component in question.
    - This makes it easier to make changes to the behaviour.
    - It also makes it easier to reason about the code.
    - And the behaviour can be tested independently of the component.
3. The process of building a statechart causes all the states to be explored.
4. Studies have shown that statechart based code has lower bug counts than traditional code.
5. Statecharts lends itself to dealing with exceptional situations that might otherwise be overlooked.
6. As complexity grows, statecharts scale well.
7. A statechart is a great communicator: Non-developers can understand the statecharts, while QA can use a statecharts as an exploratory tool.

#### The disadvantages of using state charts

1. It’s simply not needed.
2. It goes against the grain of already established technologies.
3. It increases the number of libraries, for web applications this means increased load time.
4. They are often a foreign concept to more junior and even mid level engineers so it can be difficult to train for.

#### State charts in the wild

[XState](https://dev.to/mazesch/xstate-the-new-opportunity-for-web-development-2l97https://dev.to/mazesch/xstate-the-new-opportunity-for-web-development-2l97) is an excellent JS library for modeling user flows as state charts.