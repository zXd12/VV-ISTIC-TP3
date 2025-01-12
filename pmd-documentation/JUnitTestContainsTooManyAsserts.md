
# JUnitTestContainsTooManyAsserts

*Usage:* 
`pmd check -d <source code folder> -R category/java/bestpractices.xml/JUnitTestContainsTooManyAsserts -format <output format>`

*Description:*

Unit tests should not contain too many asserts. Many asserts are indicative of a complex test, for which
it is harder to verify correctness.  Consider breaking the test scenario into multiple, shorter test scenarios.
Customize the maximum number of assertions used by this Rule to suit your needs.

This rule checks for JUnit4, JUnit5 and TestNG Tests, as well as methods starting with "test".
        

*Example:*
```java


public class MyTestCase extends TestCase {
    // Ok
    public void testMyCaseWithOneAssert() {
        boolean myVar = false;
        assertFalse("should be false", myVar);
    }

    // Bad, too many asserts (assuming max=1)
    public void testMyCaseWithMoreAsserts() {
        boolean myVar = false;
        assertFalse("myVar should be false", myVar);
        assertEquals("should equals false", false, myVar);
    }
}

        
```