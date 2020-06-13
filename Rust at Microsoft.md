# Rust at Microsoft - Ryan Levick

- Cost of failure: 150 000$ in 2004, now can be much more
- Failures per year: 468
- Can the cost be even higher: yes
- Could have costed upward of 4 billion dollars for Microsoft and customers, for one failure
- Core of the problem is memory safety. Account for a large majority of CVEs -> double free, use after free, etc
- 70% of CVEs due to memory safety, not going down even after massive efforts
- At the core: C++, because not a safe language
- We need better programmers: 0 evidence that holistic training of C and C++ developers will fix the issue. Problem is not about individual programmer but at scale
- Static analysis: not on by default, slow things down -> incentives not to run, in a non memory safe language lacks informations to do everything
- Make these issues impossible to introduce: programmers can't introduce these issues. The cost of a bug at compile time is orders of orders of magnitude less costly than one in production
- Runtime check: programmers must do them
- Garbage collection: tracing, reference counting. If you can use it use it, but can't be here in systems software, like runtime checks.
- Microsoft Security Response Center - MSRC: Safe Systems Programming Language initiative. 1st: making C++ safer when they can. 2nd: developing new programming languages/constructs -> Verona project. 3rd: Rust, industry's best chance to fix these issues.
- What Rust offers us: Performance, on par with C++, seems to lean towards faster than C++. Correctness: You debug Rust at runtime less often.