# Invariants as Program Features

[Ben Lowman](https://www.github.com/lowmanb94/invariants-as-features)

## Problem

Implementing TLS is hard. Given the wide range of cipher suites, target platforms, and legacy code, it is unlikely that any TLS implementations are free of bugs (see Heartbleed, Apple's goto fail, CCS injection, etc.). Rigorous testing is required in cases where formal verification is not feasible. For most implementations, traditional software engineering techniques are the primary means by which confidence is gained in the correctness of the implementation.

## Goal

My goal is to explore the use of program invariants in testing TLS implementations. Intuitively, inferred program invariants are a compressed expression of program state, independent of control flow or output. Dynamically inferred invariants could be compared to ground truth invariants as a more robust method to verify program behavior when subjected to test cases. In addition, it is also likely that different TLS implementations exhibit similar invariants. I am interested in exploring the possibility of employing Frankencerts-type differential testing over dynamically inferred program invariants instead of outputs.

## Resources

* [Frankencerts paper](https://www.cs.utexas.edu/~shmat/shmat_oak14.pdf), and a [follow-up paper](http://stap.sjtu.edu.cn/images/c/ca/Mucert.pdf) that uses line coverage to guide certificate generation.
* [Daikon](https://plse.cs.washington.edu/daikon/), a tool for dynamically detecting possible program invariants.
* [SourcererCC](https://github.com/Mondego/SourcererCC), a fast, token based code clone detector. This might aid in finding "similar" code across TLS implementations. 
