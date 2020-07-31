# About Architecture and Tech Debt

Architecture is quite a broad topic; it spans from library implementation to IT organization(eg. applying the inverse conway maneuver). It is also quite risky, considering that a huge change in architecture requires higher knowledge to deal with the system. for instance, opt for event streaming does not mean your engineering team is ready to deal with eventual consistency and all other technical details involved.

When and how an evolution of your architecture is needed, and how to measure the impact is hard to define.

Favoring pragmatic approach over gut feeling is mandatory in this area.

## From tech debt to an the ideal architecture

The best definition of tech debt that I remember sounds like:

```tech debt is the distance between your current system implementation and the ideal one```

reasonable as it may sound, it is not useful without a clear definition of `ideal architecture`. Also, the concept of `ideal architecture` is a moving target as it evolves alongside your system.

The next big thing is having a clear understanding of what `ideal architecture` can be, and in my opinion something like the following is quite close:

```an architecture that allows you to efficiently deliver a good quality service```

Ideal architecture sadly isn't a single recipe. There is no such thing as the right solution, you only have a huge set of best practices and trade-offs to apply in order to meet your organization's needs.

## The evolutionary side of the architecture

A consideration needed here is that the ```ideal architecture``` is an ephemeral concept, because it change with the complexity of your system. As an example increasing the number of engineers change your teams number and it reflects to a change in your architecture and the level of distribution you are dealing with.

The main idea here is switching the measurement of the tech debt from a quantitative approach to a qualitative evaluation, from the solution space to the problem space.

This new approach will allow you to have a continuous measurement of your effectiveness and this need to be continuously improved because the condition under which you are building your system are evolving with the time.

## Measurement

The definition of `ideal architecture` leads us to identify two main dimensions for measuring that:

* The Quality of your service defines `good quality`;
* The Speed delivering your service defines `efficiency`.

Both this dimensions largely depend on your business needs and goals. To make them practical you need to dig a bit deeper into your requirements.

## An example from my experience

In my experiences at Subito.it, we spent grate effort defining those two dimension in the best way we could.

### The definition of quality service

In the context of digital services there is an extensive literature about measurement of quality and you should find the one that fits you best. In Subito we are using an iterative approach adding relevant metrics as soon as we identify the relative business value. As of today we are monitoring the following:

* Availability
* QoS
* Latency

We have defined a complete set of thresholds that best represent our needs. This threshold system is based on a concept of service Tier (from 0 to 2) to express the different level of quality that a service must honor.

### The definition of efficiency

The efficiency is related to the development phase and aims to measure the effort and complexity involved in changing the system. The design for change, as considered in "evolutionary architecture", is one of the desireable characteristic for our system. 

In the effort to define this, we follow the specifications presented in the book Accelerate (by Jez Humble, Gene Kim, Nicole Forsgren) considering:

* Deploy frequency
* Change fail rate
* Lead time for change
* Mean time to Recover

using the _top performer_ cluster values as thresholds.

The _top performer_ cluster consists in empirical defined thresholds for these metrics:

* Deploy frequency: > 60 deploy per month
* Change fail rate: < 15%
* Lead time for change: < 1 day
* Mean time to Recover: < 1 hour

## The hypothesis

If we reach both our targets, we can safely declare that:

```the architecture we are working on gives us the ability to deliver a product whose the quality is relevant for our business  with the right amount of effort```

considerations on the hypothesis:

* What are the consequences of being able to deliver at the timely but with lower quality? 
    * either you are losing money because of the poor quality your users are experiencing
    * or you have defined wrong threshold for your quality
* What are the consequences of being able to deliver the right quality but with less efficiency?
    * either you are losing grip on the market and gaining some product debt because your competitor can move faster than you
    * or you are compensating adding more tech debt to meet the objectives
    * or you have defined the wrong threshold for your efficiency

## The never-ending commitment

As final consideration about this approach is that you can never settle on a specific target for various reasons


### The efficiency 

The efficiency level of your competitors will increase with the time, this is well known reading the past reports in order to see how the cluster move with the time, and you want stay in a specific cluster not at a specific level.

Moreover sooner or later you will be tired to constantly try to catch up others and you will aim to be the leader.

### The quality

Although the quality is a business decision and you can be fine with your QoS targets for a long time this doesn't mean you will not struggle for improvement, be in target and be fast requires you to be way over your target (this concept comes directly from the error budget approach).

Your quality definition will change, for us ad the beginning we were considering just the QoS but with time we discovered that Latency was quite important for us and this lead to a more complex problem to solve with the same efficiency. You will constantly discover new dimensions within the quality spectrum and the challenge to be at the same performance level will be harder every day.

An interesting example I'm leaving to you is adding costs to the quality definition, and the imagine how this will impact solutions that were considered valid before.

Other hypothetical dimensions are:

* Size of responses (byte transfer can have different impact on accessibility from flaky connections and other things)
* Number of request per page or view
* Page Performance Index (that is not just latency)
* Security

and so many others you will discover relevant for you business. The point here is that when you start looking at numbers you will discover things that are going to make your life miserable.