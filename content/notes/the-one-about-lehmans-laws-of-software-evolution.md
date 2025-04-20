---
title: "The One About Lehman's Laws of Software Evolution"
summary: 'In the words of Lehman, “Evolution is an essential property of real-world software” and “As your needs change, your criteria for satisfaction changes”'
date: 2021-08-03T18:44:59-03:00
series: ['The One About']
tags: ["Software Evolution", "complexity"]
draft: false
---

Over the decades (studies on **software evolution** started in the late 1960s), Meir Lehman and László Bélády formulated, proposed and improved eight “laws” that we today call **Lehman’s Laws of Software Evolution**.

**I	- Law of continuing change**
- An E-type system must be continually adapted, else it becomes progressively less satisfactory in use.

**II - Law of increasing complexity**
- As an E-type is changed, its complexity increases and becomes more difficult to evolve unless work is performed to maintain or to reduce the complexity.

**III - Law of self-regulation**
- Global E-type system evolution is feedback regulated.

**IV - Law of conservation of organizational stability**
- The work rate of an organization evolving an E-type software system tends to be constant over the operational lifetime of that system or phases of that lifetime.

**V - Law of conservation of familiarity**
- In general, the incremental growth (growth rate trend) of E-type systems is constrained by the need to maintain familiarity.

**VI - Law of continuing growth**
- The functional capability of E-type systems must be continually enhanced to maintain user satisfaction over system lifetime.

**VII - Law of declining quality**
- Unless rigorously adapted and evolved to take into account changes in the operational environment, the quality of an E-type system will appear to be declining.

**VIII - Law of feedback system**
- E-type evolution processes are multilevel, multiloop, and multiagent feedback systems.


## Fundamental trouble behind software evolution

The first two laws, which are mildly conflicting each other, show the fundamental trouble behind software evolution:

- Software must be continuously changed to adapt to the environment.
- Changes increase the complexity of software.

In other words, **software must change, but changes increase complexity**. Unless work is performed to maintain or to reduce the complexity.

To deal with this trouble, we can consider what Martin Fowler said in his book Refactoring:

> "When you have to add a feature to a program but the code is not structured in a convenient way, first refactor the program to make it easy to add the feature, then add the feature".

## The SPE scheme

Initially the laws of software evolution were thought to be valid for large software projects.
But, in the early 1980s Lehman substituted the notion of "large programs" by a more specific classification, the SPE scheme:

- **S-type (specified)** programs are derivable from a static specification, and can be formally proven as correct or not.
- **P-type (problem)** programs attempt to solve problems that can be formulated formally, but which are not computationally affordable. 
- **E-type (evolving)** programs are embedded in the real world and it changes as the world does.

As can thus be seen, only one of those categories, E-type, is described by the laws.
This is due to the fact that, unlike E-type, S-type software does not show an evolutionary behavior. Once the program is written, it is either correct or not with respect to a specification.
And further studies of P-type programs suggested that, in practice, they always satisfied the definition of either S-type or E-type. Thus, in his subsequent work Lehman ignored P-type.
