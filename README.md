# Junit
## Unit Testing with JUnit 4

## Parameterized Tests
```java

@RunWith(Parameterized.class)
public class StringHelperParameterizedTest {

	// AACD => CD ACD => CD CDEF=>CDEF CDAA => CDAA

	StringHelper helper = new StringHelper();
	
	private String input;
	private String expectedOutput;
	
	public StringHelperParameterizedTest(String input, String expectedOutput) {
		this.input = input;
		this.expectedOutput = expectedOutput;
	}

	@Parameters
	public static Collection<String[]> testConditions() {
		String expectedOutputs[][] = { 
				{ "AACD", "CD" }, 
				{ "ACD", "CD" } };
		return Arrays.asList(expectedOutputs);
	}

	@Test
	public void testTruncateAInFirst2Positions() {
		assertEquals(expectedOutput, 
				helper.truncateAInFirst2Positions(input));
	}
}


```


