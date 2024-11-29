# On assertions

Answer the following questions:

1. The following assertion fails `assertTrue(3 * .4 == 1.2)`. Explain why and describe how this type of check should be done.

2. What is the difference between `assertEquals` and `assertSame`? Show scenarios where they produce the same result and scenarios where they do not produce the same result.

3. In classes we saw that `fail` is useful to mark code that should not be executed because an exception was expected before. Find other uses for `fail`. Explain the use case and add an example.

4. In JUnit 4, an exception was expected using the `@Test` annotation, while in JUnit 5 there is a special assertion method `assertThrows`. In your opinion, what are the advantages of this new way of checking expected exceptions?

## Answer

1. Because fo float precision. A precision parameter should be added to the comparison

2. They use different functions to compare inputs, respectively `.equals()` and `==`. The main difference is when comparing instances of objects. `assertSame` will only pass if both parameters are litteraly the same instance, while `assertEquals` may be more leniant if a `.equals()` is implemented.

3. code that should be unreachable in the control flow of the test?

4. It allows for testing multiple throws in a single test.
