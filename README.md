# Lab-8_202001223
Junit Testing

# Lab Exercises

**1. Created a new Eclipse project - Lab__8 and within that created a package - lab__8**

![image](https://user-images.githubusercontent.com/124246644/233325346-5ba92987-99e9-463a-8d60-b7c9582199a6.png)

**2. Created a class in the package - class name - Boa** 

```
package lab__8;
public class Boa {
	private String name;
	private int length; // the length of the boa, in feet
	private String favoriteFood;
	public Boa (String name, int length, String favoriteFood){
	this.name = name;
	this.length = length;
	this.favoriteFood = favoriteFood;
	}
	// returns true if this boa constrictor is healthy
	public boolean isHealthy(){
	return this.favoriteFood.equals("granola bars");
	}
	// returns true if the length of this boa constrictor is
	// less than the given cage length
	public boolean fitsInCage(int cageLength){
	return this.length < cageLength;
	}
}

```

![image](https://user-images.githubusercontent.com/124246644/233326099-2f0b0c7f-970d-4dee-be55-19b2b4953ed9.png)

**3. Created another file BoaTest for jUnit Test.**

**4. First added basic setup function in BoaTest class**

```
package lab__8;

import static org.junit.Assert.*;
import org.junit.Before;
import org.junit.Test;

public class BoaTest {
	
	@Before
	public void setUp() throws Exception {
		jen = new Boa("Jennifer", 2, "grapes");
		ken = new Boa ("Kenneth", 3, "granola bars");
	}
 }
 ```

Method annotated with @Before will be run before each test executes.

**5. Added private fields for jen and ken in the Boa class.** 

After adding this code of BoaTest.java file

```
package lab__8;

import static org.junit.Assert.*;

import org.junit.Before;
import org.junit.Test;

public class BoaTest {
	private Boa jen;
	private Boa ken;
	
	@Before
	public void setUp() throws Exception {
		jen = new Boa("Jennifer", 2, "grapes");
		ken = new Boa ("Kenneth", 3, "granola bars");
	}
}
```

We added private fields for jen and ken to the BoaTest class, and initialized them in the setUp method. We also updated the testIsHealthy and testFitsInCage methods to use these Boa objects for testing.

Note that the setUp method will be executed before each test method, so any changes made to the Boa objects during a test will not affect the objects used in other tests.

**6. Adding 1st test case - Modified code** 

```
package lab__8;

import static org.junit.Assert.*;

import org.junit.Before;
import org.junit.Test;

public class BoaTest {
	private Boa jen;
	private Boa ken;
	
	@Before
	public void setUp() throws Exception {
		jen = new Boa("Jennifer", 2, "grapes");
		ken = new Boa ("Kenneth", 3, "granola bars");
	}
	
	@Test
	public void testIsHealthy() {
		assertEquals(false,jen.isHealthy());
		assertEquals(true,ken.isHealthy());
	}
	
}
```

In the first test case, we're testing the isHealthy method of the Boa class. We create two Boa objects with different favorite foods, and verify that isHealthy returns false for the first object and true for the second object.

**7. Output of first testcase after jUnit Testing:** 

![image](https://user-images.githubusercontent.com/124246644/233329334-16c30319-d205-4854-aa56-b4eeeec41fd8.png)


**8. Adding 2nd test case - Modified code** 

```
package lab__8;

import static org.junit.Assert.*;

import org.junit.Before;
import org.junit.Test;

public class BoaTest {
	private Boa jen;
	private Boa ken;
	
	@Before
	public void setUp() throws Exception {
		jen = new Boa("Jennifer", 2, "grapes");
		ken = new Boa ("Kenneth", 3, "granola bars");
	}
	
	@Test
	public void testIsHealthy() {
		assertEquals(false,jen.isHealthy());
		assertEquals(true,ken.isHealthy());
	}
	
	@Test
	
	public void testFitsInCage() {
		assertEquals(false,jen.fitsInCage(1));
		
		assertEquals(false,jen.fitsInCage(2));
		
		assertEquals(true,jen.fitsInCage(3));
	}
}
```
In the second test case, we're testing the fitsInCage method of the Boa class. We create three Boa objects with different lengths, and test whether they fit in cages of different lengths. 

**9. Output of first 2 testcase after jUnit Testing:** 

![image](https://user-images.githubusercontent.com/124246644/233331936-3dd4f747-074a-4a05-aca1-84c124ba5985.png)


**10. Adding 3rd test cases - Modified code** 

```
package lab__8;

import static org.junit.Assert.*;

import org.junit.Before;
import org.junit.Test;

public class BoaTest {
	private Boa jen;
	private Boa ken;
	
	@Before
	public void setUp() throws Exception {
		jen = new Boa("Jennifer", 2, "grapes");
		ken = new Boa ("Kenneth", 3, "granola bars");
	}
	
	@Test
	public void testIsHealthy() {
		assertEquals(false,jen.isHealthy());
		assertEquals(true,ken.isHealthy());
	}
	
	@Test
	
	public void testFitsInCage() {
		assertEquals(false,jen.fitsInCage(1));
		
		assertEquals(false,jen.fitsInCage(2));
		
		assertEquals(true,jen.fitsInCage(3));
	}
	
	@Test
	
	public void testlengthInInches() {
		assertEquals(24,jen.lengthInInches());
		
		assertEquals(36,ken.lengthInInches());
	}
	
}
```
**11. Output of all testcase after jUnit Testing:** 

![image](https://user-images.githubusercontent.com/124246644/233333335-40273e7a-3de5-4b93-a938-f964c6d60bff.png)




