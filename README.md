# List of security-related projects

This page contains a list of security-related projects.
If you own or have knowledge of any projects that should be added to this list,
please create a PR or open an issue!

---
# Fuzzers
|     Name     |                Repository               |                               Description                              |
|:------------:|:---------------------------------------:|:----------------------------------------------------------------------:|
|  Cargo Fuzz  |  https://github.com/rust-fuzz/cargo-fuzz  | Command-line wrapper for using libFuzzer. Easy to use, no need to recompile LLVM! |
| honggfuzz-rs | https://github.com/rust-fuzz/honggfuzz-rs | A fuzzer developed by Google. |
| afl.rs       | https://github.com/rust-fuzz/afl.rs       | Allows one to run the AFL fuzzer on code written in the Rust programming language.                                                                                                                   |
| cargo-libafl | https://github.com/AFLplusplus/cargo-libafl | A fuzzer backed by [LibAFL](https://github.com/AFLplusplus/LibAFL) |
| fuzzcheck | https://github.com/loiclec/fuzzcheck-rs | An experimental fuzzing engine that mutates Rust data structures directly, bypassing conversion to/from byte strings |
| QuickCheck   | https://github.com/BurntSushi/quickcheck  | QuickCheck is a way to do property based testing using randomly generated input.                                                                                                                     |
| Proptest     | https://github.com/altsysrq/proptest      | Proptest is a property testing framework (i.e., the QuickCheck family) inspired by the Hypothesis framework for Python.                                                                              |
---
# Model Checkers

|     Name     |                Repository                  |                               Description                              |
|:------------:|:------------------------------------------:|:----------------------------------------------------------------------:|
|     Loom     |    https://github.com/carllerche/loom      | Loom is a model checker for concurrent Rust code. It exhaustively explores the behaviors of code under the C11 memory model, which Rust inherits. |
| rutenspitz   |   https://github.com/jakubadamw/rutenspitz | А procedural macro to be used for testing/fuzzing stateful models against an equivalent implementation. |
| Rust Model Checker (RMC)   | https://github.com/model-checking/rmc | Bit-precise Rust model checker based on [CBMC](http://www.cprover.org/cbmc/). |
---
# Linters
|     Name     |                Repository                |                               Description                              |
|:------------:|:----------------------------------------:|:----------------------------------------------------------------------:|
| Cargo Clippy | https://github.com/rust-lang/rust-clippy | A collection of lints to catch common mistakes and improve your Rust code. |
---
# Static Analyzers
|     Name     |                Repository               |                               Description                              |
|:------------:|:---------------------------------------:|:----------------------------------------------------------------------:|
| MIRAI | https://github.com/facebookexperimental/MIRAI | Mirai is an abstract interpreter for the Rust compiler's mid-level intermediate representation (MIR). It is intended to become a widely used static analysis tool for Rust.                 |
| Prusti  |   https://github.com/viperproject/prusti-dev  | A static verifier for Rust, based on the Viper verification infrastructure. |
| Crux | https://github.com/GaloisInc/crucible | Symbolic execution tool to run tests on all possible inputs, exhaustively. |
| Rudra | https://github.com/sslab-gatech/Rudra | Static analyzer for finding memory safety bugs in `unsafe` Rust code. |
---
# Dynamic Analyzers
|     Name     |                Repository               |                               Description                              |
|:------------:|:---------------------------------------:|:----------------------------------------------------------------------:|
| sanitizers | [built into the compiler](https://doc.rust-lang.org/unstable-book/compiler-flags/sanitizer.html) | Provides sanitizers for checking uninitialized memory access, uses of freed memory, memory leaks and data races between threads. |
| Miri  | https://github.com/rust-lang/miri             | An experimental interpreter for Rust's mid-level intermediate representation (MIR). It can run binaries and test suites of cargo projects and detect certain classes of undefined behavior, including Rust-specific ones that sanitizers cannot detect. Moreover, it can do this for arbitrary CPU architectures independent of the host ("cross-interpretation"). |

Language-independent tools such as [Valgrind](https://www.valgrind.org/), [Dr. Memory](http://www.drmemory.org/), [libdiffuzz](https://github.com/Shnatsel/libdiffuzz) etc. also work.

---
# Input Sanitizing
|     Name     |                Repository               |                               Description                              |
|:------------:|:---------------------------------------:|:----------------------------------------------------------------------:|
| untrusted.rs | https://github.com/briansmith/untrusted | Allows for reliable and efficient parsing of untrusted inputs in Rust. |
| dangerous | https://github.com/avitex/rust-dangerous | Similar to `untrusted` but with a different API and more verbose error messages |
| semval | https://github.com/slowtec/semval | Library for semantic validation of complex data structures in Rust. |
---
# Hardened Allocators
|     Name     |                Repository               |                               Description                              |
|:------------:|:---------------------------------------:|:----------------------------------------------------------------------:|
| scudo | https://github.com/google/rust-scudo | Rust bindings for the LLVM project's [Scudo](https://llvm.org/docs/ScudoHardenedAllocator.html) hardened allocator. |
| mimalloc | https://github.com/purpleprotocol/mimalloc_rust | Rust bindings for Microsoft's [mimalloc](https://github.com/microsoft/mimalloc) allocator. Security features are an optional build-time configuration. |
---
# Vulnerability Disclosure

|           Name            |                  Repository                   |                      Description                       |
|:-------------------------:|:---------------------------------------------:|:------------------------------------------------------:|
| RustSec Advisory Database |    https://github.com/RustSec/advisory-db/    | The RustSec Advisory Database is a repository of security advisories filed against Rust crates published via https://crates.io. Works closely with Cargo Audit. |
|  RustSec Advisory Client  |    https://github.com/RustSec/rustsec-crate   | Client library for accessing the RustSec Security Advisory Database: fetches the advisory-db (or other compatible) git repository and audits Cargo.lock files against it. It is mainly used by   Cargo Audit but may be useful if you would like to consume the RustSec advisory database in other capacities. |
|        Cargo Audit        |     https://github.com/RustSec/cargo-audit    | Audit Cargo.lock for crates with security vulnerabilities reported to the RustSec Advisory Database. |
|       Crates Audit        |  https://gitlab.com/zachreizner/crates-audit/ | A tool to cross-reference the crates.io index with the RustSec Advisory database. |
|        Cargo deny         |  https://github.com/EmbarkStudios/cargo-deny  | A tool for checking you dependencies given some set of predefined rules. It can check for license conflict, banned crates, vulnerabilities and source of crates. The rules are defined in the [`deny.toml`](https://github.com/EmbarkStudios/cargo-deny/blob/main/deny.template.toml) file and can be configured for your needs. |

---
# Dependency Checker
|           Name            |                Repository                     |                      Description                       |
|:-------------------------:|:---------------------------------------------:|:------------------------------------------------------:|
|        Cargo Geiger       |    https://github.com/rust-secure-code/cargo-geiger   | A program that list statistics related to usage of unsafe Rust code in a Rust crate and all its dependencies. |
|        Cargo Guppy        |    https://github.com/facebookincubator/cargo-guppy   | A program/library for performing queries on Cargo dependency graphs |
|        Siderophile        |  https://github.com/trailofbits/siderophile/  | A program that list statistics of functions that use unsafe code in their call graph. It helps find fuzzing candidates. |
---
# Side-Channel Vulnerability Checking
|     Name     |                Repository               |                               Description                              |
|:------------:|:---------------------------------------:|:----------------------------------------------------------------------:|
| SideFuzz | https://github.com/phayes/sidefuzz | SideFuzz is an adaptive fuzzer that uses a genetic-algorithim optimizer in combination with t-statistics to find side-channel (timing) vulnerabilities in cryptography compiled to wasm.      |
| dudect-bencher  | https://github.com/rozbb/dudect-bencher  | Implements the DudeCT statistical methods for testing constant-time functions. It is based loosely off of the bencher crate. |
| ctgrind  |   https://github.com/RustCrypto/utils/tree/master/ctgrind  | Tool for checking that functions are constant time using Valgrind. Based on the work of Adam Langley and Michael Gehring. |
---
# Code Review
|     Name     |                Repository               |                               Description                              |
|:------------:|:---------------------------------------:|:----------------------------------------------------------------------:|
| Cargo Crev | https://github.com/dpc/crev | crev is an code review system as opposed to typically practiced code-change review system. |

---
# Books/Guides
|     Name     |                Repository               |                               Description                              |
|:------------:|:---------------------------------------:|:----------------------------------------------------------------------:|
| Secure Rust Guidelines | https://github.com/ANSSI-FR/rust-guide | A guide providing recommendations and resources for secure application development in Rust. |

---
# Groups of people
| Name | Repository | Description |
|:----:|:----------:|:-----------:|
| Rust Secure Code Working Group (Secure Code WG) | https://github.com/rust-secure-code/wg | Us, [an official Rust working group](https://www.rust-lang.org/governance/wgs/wg-secure-code): "Making it easy to write secure code in Rust" |
| Rust Formal Methods Interest Group (RFMIG) | https://github.com/rust-formal-methods/wg | Interest group for using [formal methods](https://en.wikipedia.org/wiki/Formal_methods) to verify the correctness of Rust software &mdash; not part of the Rust governance structure |
| Rust VMM community | https://github.com/rust-vmm/community | "rust-vmm is an open-source project [...] to build custom Virtual Machine Monitors (VMMs) and hypervisors" |
