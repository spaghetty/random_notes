# About Architecture and Tech Debt

Architecture is quite a broard topic, it spans from library implementation to the IT organization(eg. applying the inverse conway maneuver), and also quite risky considering that a huge change in architeture increase the knowledge needed to deal with your system. As example, deciding that event streaming is the way to go does not means that your engineering community is ready to deal with eventual consistency and all other techinacal details involved.

When and how an evolution of your architecture is needed and how to measure if the change made is going in the right direction is hard to define.

Trying to apply a pragmatic approach avoiding the gut feeling is mandatory in this area.

## The tech debt and the ideal architecture

The best description that I can remember about tech debt sound like:

```tech debt is the distance between your system current implementation and the ideal one```

as this could sound reasonable it's not so useful per se without a clear measurament of the tech debt, and moreover the concept of `ideal one` is a moving target, because it gets more complex with the growth of your system.

This definition of the tech debt implies a definition for an `ideal architecture` in the form of:

```an architecture that allow you to deliver efficiently a good quality service```

The ideal architecture sadlly isn't a single recipe, there is no such thing as right solution, but a huge set of best practices that you can implement and adapt to your system and organization in order to reach the right trade off your organization's needs.


## Measurement

In order to have a good aproximaption of this distance you need to measure two different dimensions:

* Quality of your service
* Speed in building your service

and then define some thresholds relevant to define is you have an acceptable tech debt or it's the case to start paying your debit off.

## An example from my experience

### The definition of quality service

In the context of digital services there is a lot of studies about the definition of quality and you should find the one that fits better to your organization. In Subito we are using an iterative approach defining the relevant metrics and we add more dimensions as soon as we identify new desiderable characteristic. As of today we are monitoring these:

* Availability
* QoS
* Latency

We defined a complex system of thresholds in order to  be able to easily define if we are in target or not.

### The definition of efficiency (in the develpment phase)

We embrace totaly the definition presented within the book Accelerate (by Jez Humble, Gene Kim, Nicole Forsgren) and we define the development performance as:

* Deploy frequency
* Change fail rate
* Lead time for change
* Mean time to Recover

using as thresholds the _top performer_ cluster.

The _top performers_ cluster consist in some empirical defined threasolds for those metrics:

* Deploy frequency: > 60 deploy per month
* Change fail rate: < 15%
* Lead time for change: < 1 day
* Mean time to Recover: < 1 hour

## The hypothesis

If we meet both our target we can safely declare that:

```the architecture we are working on give us the ability to deliver with the right ammount of effort a product with the quality that is relevant for our business```

consideration on the hypothesis:

* What are the consequence of beeing able to deliver at the right speed but with lower quality? 
    * or you are loosing money because of the poor quality your users are experiencing
    * or you have defined wrong threshold for your quality
* What are the consequences of beeing able to deliver the right quality but with less efficiency?
    * or you are loosing grip on the market and gain some product debt because your competitor can move faster than you.
    * or you are compensating adding more tech debt in order to meet the objectives
    * or you have defined the wrong threshold for your efficiency

# Changing the architecture

In a big IT department, verify that the new architeture is implemented correctly in all the corner of the system is quite challenging topic due to the high parallelism within the organization.

## How do we deal with architectural evolution

Applying some priciples from evolutionary architecture, emergin architecture and google SRE approach seems to lead to a valid approach in order to achive a distributed architectural effort.

A need for an architecture emerge within the day by day experiment appening in all the teams, the more valuable idea is to collect those experiment and try to standardize the ones that perform better.

Apply a strict obervability in order to measure the system in all is parts is the basic enabler for introducing the fitnes functions concept presented in the topic of evolutionary architecture.

Having a team that is totally focused on those metrics usefull for describing the system allows you to form some champions (engineer totally focused on this matter) that can support product oriented teams(that are more focused on business results of their work) in order to improve their performance in those specific metrics as soon as they start to go down (as experessed into the SRE strategy)

Sharing the knowledge and coaching the engineering community is mandatory in order to avoid useless effort and polarize the efforts throward a specific direction, an approach in this direction is having public repository where all the engineer can discuss on best practices that need to be embedded in our development model making them accepted from all the members.