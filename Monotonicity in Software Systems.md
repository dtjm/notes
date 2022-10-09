---
tags: distributed systems
---

# Monotonicity in Software Systems

[Keeping CALM: When Distributed Consensus is Easy](https://arxiv.org/abs/1901.01930) asserts that a software program can avoid coordination if it is monotonic.  

Avoiding coordination is desirable because coordination is a key factor in performance of distributed systems. 

## What does monotonic mean?
The CALM paper defines it as this:

> A program $P$ is monotonic if for any input sets $S,T$ where $S ⊆ T , P(S) ⊆ P(T )$.

It doesn't provide a short intuitive summary, but what I think it means is that the result of a computation should not "change direction" in the face of new information.

Imagine a normal Cartesian $f(x) = y$ monotonic function like you learned in school, that always goes up and to the right.   That function always goes in the same general direction, never going down over the course of $x$.  

My mental model of a monotonic program is one which also doesn't change direction over the course of adding additional inputs to the program. 

The paper gives an example of both a monotonic and non-monotonic program:

* Deadlock detection in a distributed transaction (checking for cycles in a graph)
* Garbage collection (checking for graph connectedness from a root node)

Deadlock detection is monotonic, because once you find a cycle, no new information will cause the result to reverse, i.e. you can't go from a "deadlock detected" result to the opposite. 

However, garbage collection is non-monotonic because you can go from "no garbage found" result to a "garbage found" result as more information is added to the input.

## Monotonicity in data sets
[Robert Fink: Palantir Blog: On Monotonicity in Relational Databases and Service-oriented Architecture](https://blog.palantir.com/on-monotonicity-in-relational-databases-and-service-oriented-architecture-90b0a848dd3d) discusses what it means for a data set to be monotonic. 

The basic idea is that a monotonic data set is one that only grows and does not undergo deletions.  This is analogous to an append-only data struction.  This is useful because if you can expect monotonicity, then you can make some assumptions:

> it turns out that many query analysis and optimization problems can be solved for monotonic queries, but not for a large class of non-monotonic queries

Which means that certain query optimizations can be applied only for monotonic data sets. 

## Monotonicity in data types
I haven't found any reference for this, but I think [CUE](https://cuelang.org/)'s type system may be monotonic.  I don't know what the implications are.

Each CUE value can only become more and more specific:

```cue
foo: number
foo: int
foo: > 10
foo: < 100
foo: 12
```
[Cue playground](https://cuelang.org/play/?id=Rbpb3FAgbz4#cue@export@cue)

The constraint of the type cannot be loosened.  It's sort of like immutability...maybe more like a one-way mutability.

## Monotonicity in system behavior
This is not a formal declaration, and I think this touches a bit into control theory, but robust systems in the face of failure should tend to fail toward the desired state.  In some sense the monotonicity is over the "diff" between the current state and the desired state.  It should be hard or impossible to regress to a state that is further away from the desired state.

## Additional reading
* [Adrian Colyer: Review of the CALM paper](https://blog.acolyer.org/2019/03/06/keeping-calm-when-distributed-consistency-is-easy/)
* [Marc Brooker: The Fundamental Mechanism of Scaling](https://brooker.co.za/blog/2021/01/22/cloud-scale.html)
  > the fundamental approach used to scale distributed systems is _avoiding_ co-ordination