# Notes about the book

## Accelerate
by Gene Kim; Jez Humble; Nicole Forsgren
Published by IT Revolution Press, 2018

## Notes

The book started identify and explain all the evidences relative to sentence:

```
the strategic use of technology explains revenue and productivity gains more than mergers and acquisitions (M&A) and entrepreneurship (2017). Andrew McAfee and Erik Brynjolfsson have also found a link between technology and profitability (2008)
```

Than proceeds exploiting a way for effectively measure this efficiency identifying this four of metrics as the right set of number to cluster companies:

* _Lead Time For Change_
* _Change Fail Rate_
* _Mean Time To Restore_
* _Deploy Frequency_

Observing this 4 metrics you can identify the level of your tech organization using the identified clusters:

| Cluster | LTFC     | CFR       | MTTR | DF        |
|:-------:|:--------:|:---------:|:----:|:---------:|
|High     | <1h      | <15%      | <1h  | >1 per day|
|Medium   | 1W<<1M   | 31%<<45%  | <1d  | 1W<<1M    |
|Lower    | 1M<<6M   | 16%<<30%  | <1d  | 1M<<6M    |

this results seems to be not so up to date, but they are currently monitored in a specific [annual report](https://services.google.com/fh/files/misc/state-of-devops-2019.pdf) in which you can find the relevant numbers, other relevant information in the google [section](https://cloud.google.com/devops)

In the following sections authors explores some proved approaches to improve the efficiency of your tech organization:

* Having a relevant technical involvement into the work as an engineering manager is helpful.
* Changing is the only valid constant in tech organizations.
* A proper DevOps culture is not related of a specific technology is more about the approach
* Outcome over Output is a winning strategy even in tech org.
* Measurements are the only valid in a company with the proper culture.

The authors refer to the cultural classification model based on the information flow withing a company presented in 1988 by Ron Westrum(Westrum 2014):

* **Pathological** (power-oriented) organizations are characterized by large amounts of fear and threat. People often hoard information or withhold it for political reasons, or distort it to make themselves look better.
 
* **Bureaucratic** (rule-oriented) organizations protect departments. Those in the department want to maintain their “turf,” insist on their own rules, and generally do things by the book—their book.
 
* **Generative** (performance-oriented) organizations focus on the mission. How do we accomplish our goal? Everything is subordinated to good performance, to doing what we are supposed to do.

A lot of information about the information flow are presented within this part of the book, even some strategy to assets the company culture. Alongside a relevant note is presented:

```How organizations deal with failures or accidents is particularly instructive```

then the books proceed with more in deep on technicalities:

* Continuos Delivery:
  * Build quality in
  * Work in small batches
  * Computers perform repetitive tasks; people solve problems
  * Relentlessly pursue continuous improvement
  * Everyone is responsible

and foundations for CD:
* Comprehensive configuration management
* Continuous integration
* Continuous testing

this leads to discussions about the value of testability and deployability and the value of loosely coupled architecture

```
ARCHITECTS SHOULD FOCUS ON ENGINEERS AND OUTCOMES, NOT TOOLS OR TECHNOLOGIES
```

## Random notes

```
“who is on a team matters less than how the team members interact, structure their work, and view their contributions” (Google 2015)
```

```
the report points out that executives are especially prone to overestimating their progress when compared to those who are actually doing the work.
```


```
First, maturity models focus on helping an organization 'arrive' at a mature state and then declare themselves done with their journey, whereas technology transformations should follow a continuous improvement paradigm. 
The most innovative companies and highest-performing organizations are always striving to be better and never consider themselves 'mature' or 'done' with their improvement or transformation journey.
```


our research shows that none of the following often-cited factors predicted performance:age and technology used for the application (for example, mainframe “systems of record” vs. greenfield “systems of engagement”)whether operations teams or development teams performed deployments whether a change approval board (CAB) is implemented.


it should focus on a global outcome to ensure teams aren’t pitted against each other. The classic example is rewarding developers for throughput and operations for stability: this is a key contributor to the “wall of confusion” in which development throws poor quality code over the wall to operations, and operations puts in place painful change management processes as a way to inhibit change. Second, our measure should focus on outcomes not output: it shouldn’t reward people for putting in large amounts of busywork that doesn’t actually help achieve organizational goals.


 We can answer questions like, “Do change management boards actually improve delivery performance?” (Spoiler alert: they do not; they are negatively correlated with tempo and stability.)


 In organizations with a learning culture, they are incredibly powerful. But “in pathological and bureaucratic organizational cultures, measurement is used as a form of control, and people hide information that challenges existing rules, strategies, and power structures. As Deming said, ’whenever there is fear, you get the wrong numbers’




 Westrum’s description of a rule-oriented culture is perhaps best thought of as one where following the rules is considered more important than achieving the mission
 First, a good culture requires trust and cooperation between people across the organization, so it reflects the level of collaboration and trust inside the organization.
