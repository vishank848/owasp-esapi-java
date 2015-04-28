Here is a "Hello World" using JUnit and ESAPI for Java's development test harness:

```

import org.owasp.esapi.ESAPI;
import org.owasp.esapi.Validator;

public class HelloWorldTest extends TestCase
{
	
   public static Test suite()
   {
      return new TestSuite(HelloWorldTest.class);
   }

   public HelloWorldTest(String testName)
   {
      super(testName);
   }

   protected void setUp() throws Exception
   {
      // none
   }

   protected void tearDown() throws Exception
   {
      // none
   } 

   public void testIsValidEmail()
   {
      Validator instance = ESAPI.validator();
      assertTrue(instance.isValidInput("test", "jeff.williams@aspectsecurity.com", "Email", 100, false));
   }
}

```