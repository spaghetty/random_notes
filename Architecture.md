# About Architecture and Tech Debt

Architecture is quite a broad topic; it spans from library implementation to IT organization(eg. applying the inverse conway maneuver). It is also quite risky, considering that a huge change in architecture requires higher knowledge to deal with the system. for instance, opt for event streaming does not mean your engineering team is ready to deal with eventual consistency and all other technical details involved.

When and how an evolution of your architecture is needed, and how to measure the impact is hard to define.

Favoring pragmatic approach over gut feeling is mandatory in this area.

## From tech debt to an the ideal architecture

The best definition of tech debt that I remember sounds like:

```tech debt is the distance between your current system implementation and the ideal one```

reasonable as it may sound, it is not useful without a clear definition of `ideal architecture`. Also, the concept of `ideal architecture` is a moving target as it evolves alongside your system.

The next big thing is to have a clear understanding of what `ideal architecture` can be, and in my opinion something line the following is quite close:

```an architecture that allows you to efficiently deliver a good quality service```

Ideal architecture sadly isn't a single recipe. There is no such thing as the right solution, you only have a huge set of best practices and trade-offs to apply in order to meet your organization's needs.

## Measurement

As direct consequence of the previous definition of an `ideal architecture` we identify two main dimensions for measuring that:

* Quality of your service defines the `good quality`
* Speed in deliver your service defines the `efficiency` 

Both of those are really subjective to your business needs and your goals, to make them practical you need to go a bit deeper.

## An example from my experience

In my experience applying this method, during my work in Subito.it, we worked in order to define those two dimension in the best way we could.

### The definition of quality service

In the context of digital services there is an extensive literature about the measurement of the quality and you should find the one that fits you better. In Subito we are using an iterative approach adding relevant metrics as soon as we identify the relate business value. As of today we are monitoring these ones:

* Availability
* QoS
* Latency

We have defined a complete set of threshold that best represent our needs. This threshold system is based on a concept of service Tier (from 0 to 2) in order to express the different level of quality that a service must honor.

### The definition of efficiency

The efficiency is related to the development phase and amis to measure the effort and complexity involved in changing the system. The design for change, as considered in the evolutionary architecture, is one of the desireable characteristic for our system. 

In the effort to define this, we follow the specifications presented in the book Accelerate (by Jez Humble, Gene Kim, Nicole Forsgren), considering:

* Deploy frequency
* Change fail rate
* Lead time for change
* Mean time to Recover

using as thresholds the _top performer_ cluster.

The _top performers_ cluster consist in some empirical defined thresholds for those metrics:

* Deploy frequency: > 60 deploy per month
* Change fail rate: < 15%
* Lead time for change: < 1 day
* Mean time to Recover: < 1 hour

## The hypothesis

If we meet both our target we can safely declare that:

```the architecture we are working on give us the ability to deliver with the right amount of effort a product with the quality that is relevant for our business```

consideration on the hypothesis:

* What are the consequence of being able to deliver at the right speed but with lower quality? 
    * or you are loosing money because of the poor quality your users are experiencing
    * or you have defined wrong threshold for your quality
* What are the consequences of being able to deliver the right quality but with less efficiency?
    * or you are loosing grip on the market and gain some product debt because your competitor can move faster than you.
    * or you are compensating adding more tech debt in order to meet the objectives
    * or you have defined the wrong threshold for your efficiency
