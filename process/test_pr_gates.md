# Azure Cloud Native Upstream PR Test Gates Requirements

This document will standardize the requirements for PR test gates. In other words, what are the minimum number of passing test signals required prior to merging a PR in a project maintained by the Azure Cloud Native Upstream team?

## Summary

The following test signals will be returned for every PR:

- [Unit Tests](#unit-tests)
- [Unit Test Code Coverage Report](#unit-tests-code-coverage)
- [Static Analysis](#static-analysis)
- [End-to-End (E2E) Tests](#e2e-tests)

In order to minimize acceptance friction and encourage iterative velocity, the sum of the above signals should take no longer than 4 hours to complete, and should take no more than 2 hours on average (50th percentile). A strict test failure limit will be enforced for tests that cannot complete before the 4 hour maximum, and metrics should be regularly evaluated to maintain the target "less than 2 hours" P50 objective.

<a name="unit-tests"></a>
### Unit Tests

All new PRs, and changes to existing PRs, should initiate a discrete, thorough unit test execution against the entire code surface area. In order to ensure that unintended side effects are surfaced, it is discouraged to decompose projects into discrete unit testable boundaries, and then only target the assumed code inside the affected boundary. There are always exceptions to the rule, but in general it's more practical to "run all unit tests" for every change. In addition to revealing side effects, it also has the force-function-benefit of encouraging optimal unit tests: we should be able to execute unit tests across the entire project surface area in a "responsive" time duration (e.g., ~10 minutes).

<a name="unit-tests-code-coverage"></a>
### Unit Test Code Coverage Report

All projects should take advantage of code coverage CI APIs that conveniently express code coverage statistics to the PR author and code reviewers. There is no single required solution, but [codecov](https://codecov.io) in particular is a known-working provider for public github projects.

More important than 100% accurate code coverage reporting is consistent metrics to facilitate ongoing maintenance of the code coverage % requirements that are a part of each project (generally 70% is a recommended minimum).

<a name="static-analysis"></a>
### Static Analysis

<a name="e2e-tests"></a>
### E2E Tests

All projects are designed to be actually used by systems or users, and it's imperative that each PR be validated against an end-to-end simulation of what accepting that change will actually mean:

- will this change actually produce the intended result in a production environment?
- does this change have any side effects in a production environment, and are those side effects desirable?
- does this change ship with supporting, additive (or reductive, if appropriate) E2E test coverage to prove out any net new or removed functionality?

Different changes will be more effectively E2E-tested directly or indirectly, though generally a change that relies upon _indirect_ E2E test signal should be justified (i.e., changes to code that do not include changes to E2E logic will have to explain why the existing E2E logic is sufficient validation).
