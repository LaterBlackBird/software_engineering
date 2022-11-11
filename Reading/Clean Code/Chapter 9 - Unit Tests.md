### 3 Laws of TDD
1) You may not write production code until you have written a failing unit test
2) You may not write more of a unit test than is sufficient to fail, and not compiling is failing
3) You may not write more production code than is sufficient to pass the currently failing test

### Keep the numbers of assertions from a test to a minimum
some suggest one assertion per test with setups using the 'before' methods, but this is not a hard and fast rule.

instead, keep it to a single concept per test

### FIRST
1) **F**ast - tests should be fast
2) **I**ndependent - tests should not depend on each other
3) **R**epeatable - tests should be repeatable in any environment
4) **S**elf-Validating - tests should have a boolean output
5) **T**imely - tests should be written in a timely fashion



