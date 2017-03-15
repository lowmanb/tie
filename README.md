# TIE: TLS Invariants Exploration

[Ben Lowman](https://www.github.com/lowmanb94/tie)

## Problem

Implementing TLS is hard. Given the wide range of cipher suites, target platforms, and legacy code, it is unlikely that any TLS implementations are free of bugs (see [Heartbleed](https://en.wikipedia.org/wiki/Heartbleed), Apple's [goto fail](https://nakedsecurity.sophos.com/2014/02/24/anatomy-of-a-goto-fail-apples-ssl-bug-explained-plus-an-unofficial-patch/), [CCS injection](http://ccsinjection.lepidum.co.jp), etc.). Rigorous testing is required in cases where formal verification is not feasible. For most implementations, traditional software engineering techniques are the primary means by which confidence is gained in the correctness of the implementation.

## Goal

My goal is to explore the use of [program invariants](https://en.wikipedia.org/wiki/Invariant_(computer_science)) in testing TLS implementations. Inferred program invariants are a compressed expression of program state, independent of control flow or output. Dynamically inferred invariants (over test cases) could be compared to ground truth invariants as a more robust method to verify program correctness. It is also likely that different TLS implementations exhibit similar invariants. I am interested in exploring the possibility of employing Frankencerts-type differential testing over dynamically inferred program invariants in addition to expected output. This will require abstracting program invariants in a meaningful way so that such "similar" invariants can be compared directly.

## Resources

* [Frankencerts paper](https://www.cs.utexas.edu/~shmat/shmat_oak14.pdf), and a [follow-up paper](http://stap.sjtu.edu.cn/images/c/ca/Mucert.pdf) that uses line coverage to guide certificate generation.
* [Daikon](https://plse.cs.washington.edu/daikon/), a tool for dynamically detecting possible program invariants. There are dozens of papers listed that leverage Daikon.
* [SourcererCC](https://github.com/Mondego/SourcererCC), a fast, token based code clone detector. This might aid in finding "similar" code across TLS implementations.
* Microsoft's [miTLS](http://www.ieee-security.org/TC/SP2013/papers/4977a445.pdf) implementation. This implementation is annotated with invariants (required for the formal verification).
* To be continued...
