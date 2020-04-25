# About Architecture and Tech Debt

In order to discuss about architecture in a pragmatic way we need to define what the architecture is usefull for,
my opinion is that the main object for any improvement on a system architecture is relative to manage tech debt.

Next big question is what is the tech debt? and how to evaluate it?

The best description that I can remember about tech debt sound like:

```tech debt is the distance between your current implementation and the ideal one```

as this could sound resonable it's impossible to measure directly eaven because the 'ideal one' is a moving target, the best chance is estimate this distance using some sort of proxy metrics.

## The ideal architecture

The idel architecture sadlly isn't a single recipe, there is no such thing as right solution, but a huge set of best practices that you can implement and adapt to your system and organization.
The only sure thing is that the main characteristic for a perfect architecture could be stated like:

```an architecture that allow you to deliver rapidly a quality service```


### The definition of quality service

This is a relative complex topic but easier to deal with, we have a lot of accademia and previous research on how describe the desired behavour of a quality service, in a more specific example in Subito we use some metrics (and relative thresholds) to define the quality of our service (and this definition evolves with the time):

* Availability
* QoS
* Latency

Eaven if you have a differnt definito on Quality you can use your own definition as target.

### The definition of speed (in delivery)

This topic is as complex as the one before but in the same way you could relay on previous works and published researches (eg. Accellerate by Jez Humble, Gene Kim, Nicole Forsgren), so in Subito we define the development performance as:

* Deploy frequency
* Change fail rate
* Lead time for change
* Mean time to Recover

## The guarantees from the ideal architecture

If the architeture you are working on is ideal, it will enable you in delivery a system that satisfies your quality level and allow you to be into the 
_top performer_'s cluster

The best performers cluster consist in some empirical defined threasolds for those metrics:

* Deploy frequency: > 60 month
* Change fail rate: < 15%
* Lead time for change: < 1 day
* Mean time to Recover: < 1 hour

If it's not clear this could be read as:

```the architecture we are working on give us the ability to deliver with the right ammount of effort a product with the quality that is relevant for our business```

notes on this are:

* What happen if you are able to deliver in the right time but at lower quality? 
    * if you choose those levels as your requirement probably you are loosing money because of poor quality experience, or you have decided to use wrong threasholds for your quality definition.
* what happen if you are able to deliver the right quality but without been in the _top performer_ cluster?
    * It can be acceptable if you are in a not so competitive market, but if your market is competitive you are loosing grip on the market and for sure gain some product debt because your competitor can move faster than you.

# Changing the architecture

Architecture is quite a broarder topic, it spans from library implementation to the IT organization(eg. applying the inverse conway maneuver), and also quite risky considering that a huge change in architeture requires a switch in the engineering approach that is not easy to deliver to all your engineers as one. As example, deciding that event streaming is the way to go does not means that your software engineer are ready to deal with eventual consistency.

In a big IT department, verify that the new architeture is implemented correctly in all the corner of the system is quite challenging topic due to the high parallelism within the organization.

## How do we deal with architectural evolution

Applying some priciples from evolutionary architecture, emergin architecture and google SRE approach seems to lead to a valid approach in order to achive a distributed architectural effort.

A need for an architecture emerge within the day by day experiment appening in all the teams, the more valuable idea is to collect those experiment and try to standardize the ones that perform better.

Apply a strict obervability in order to measure the system in all is parts is the basic enabler for introducing the fitnes functions concept presented in the topic of evolutionary architecture.

Having a team that is totally focused on those metrics usefull for describing the system allows you to form some champions (engineer totally focused on this matter) that can support product oriented teams(that are more focused on business results of their work) in order to improve their performance in those specific metrics as soon as they start to go down (as experessed into the SRE strategy)

Sharing the knowledge and coaching the engineering community is mandatory in order to avoid useless effort and polarize the efforts throward a specific direction, an approach in this direction is having public repository where all the engineer can discuss on best practices that need to be embedded in our development model making them accepted from all the members.