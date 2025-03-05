## JUnit 4 vs. JUnit 5

# 1. Architecture:
#### JUnit 4: Uses a single runner (org.junit.runner.RunWith) to execute tests.
#### JUnit 5: Three core modules
    - JUnit Platform: Provides the foundation for launching test frameworks.
    - JUnit Jupiter: Contains the API for writing tests, extensions, and assertions.
    - JUnit Vintage: Provides backward compatibility for running JUnit 3 and 4 tests.
![image](https://github.com/user-attachments/assets/821d0c45-20b3-4db4-a96e-8b42cf7f63a2)

    
# 2. Annotations:
#### JUnit 4: Uses annotations like @Test, @Before, @After, @BeforeClass, and @AfterClass.

#### JUnit 5: Introduces new annotations and a more flexible approach:

        - Test annotations: @Test, @RepeatedTest, @TestFactory
        - Lifecycle annotations: @BeforeEach, @AfterEach, @BeforeAll, @AfterAll
        - Display name annotations: @DisplayName, @Nested
# 3. Assertions:
#### JUnit 4: Provides a set of assertion methods for various data types.

#### JUnit 5: Offers a more comprehensive and flexible assertion API with additional features like:

        - Custom assertions: Creating custom assertion methods
        - Assumption API: Conditional test execution based on assumptions
# 4. Extensions:
#### JUnit 4: Limited extension capabilities.

#### JUnit 5: Introduces a powerful extension mechanism for customizing test execution:

        - Test listeners: Intercepting test events
        - Parameter resolvers: Providing custom parameter values
        - Condition evaluators: Dynamically enabling or disabling tests
# 5. Nested Tests:
#### JUnit 4: Nested tests are not directly supported.
#### JUnit 5: Provides built-in support for nested tests, allowing better organization and grouping of related tests.
# 6. Parallel Execution:
#### JUnit 4: Parallel execution is not built-in but can be achieved using third-party libraries.
#### JUnit 5: Supports parallel execution at the class and method level, improving test efficiency.  
        - junit.jupiter.execution.parallel.enabled = true
        - **JUnit 5 runs both classes and methods in a single thread by default, so this won't change anything.**
        - junit.jupiter.execution.parallel.mode.default = concurrent/same_thread

# 7. Exception
### Junit 4: Expected Exception 

```
import org.junit.Rule;
import org.junit.Test;
import org.junit.rules.ExpectedException;

public class JunitFourTest {

    @Rule
    **public ExpectedException expectedException = ExpectedException.none();**

    @Test
    public void shouldUseRuleToTestForException() throws DummyException {
        **expectedException.expect(DummyException.class);**
        ComponentUnderTest component = new ComponentUnderTest();
        component.exceptionThrowingMethod(-1);
    }

    **@Test(expected = DummyException.class)**
    public void shouldTestForException() throws DummyException {
        ComponentUnderTest component = new ComponentUnderTest();
        component.exceptionThrowingMethod(-1);
    }

}

```

### Junit 5: Expected Exception 

```
import org.junit.jupiter.api.Test;

import static org.assertj.core.api.Assertions.assertThatExceptionOfType;
import static org.assertj.core.api.Assertions.assertThatThrownBy;
import static org.junit.jupiter.api.Assertions.assertThrows;

public class JunitFiveTest {

    @Test
    void shouldThrowException() {
        ComponentUnderTest componentUnderTest = new ComponentUnderTest();
        DummyException dummyException =
                assertThrows(DummyException.class, () -> componentUnderTest.exceptionThrowingMethod(-1));
        // Use different asserts on the exception object.
    }

    @Test
    public void testException() {
        ComponentUnderTest componentUnderTest = new ComponentUnderTest();
        assertThatThrownBy(() -> componentUnderTest.exceptionThrowingMethod(-1))
                .isInstanceOf(DummyException.class)
                .hasMessageContaining("dummy")
                .hasNoCause();
    }
}
```


Link - https://igorski.co/running-tests-in-parallel-with-junit-5/       
Ref - https://www.lambdatest.com/blog/junit5-extensions/#Architecture
