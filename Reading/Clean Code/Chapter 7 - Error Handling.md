### Write try/catch's first
this develops the scope first, helps with building tests, and TDD

build tests that force exceptions (errors) and then add behavior to your handler to statisfy your tests.

### Provide context with Exceptions
create informative error messages and pass them along with your exception, mentioning the operation that failed and the type of failure.

### Special Case Pattern
create a new class to handle special cases instead of using a 'catch' to handel special cases.

### Don't Return or Pass `Null`
