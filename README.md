# Lab-8_202001029
# Keshav Somani

![image](https://user-images.githubusercontent.com/75687413/233025994-6f7f4cd8-7019-44d6-b872-7cf008266f1d.png)


![image](https://user-images.githubusercontent.com/75687413/233031390-182bcff5-7f0f-48eb-a4e0-802b46584804.png)


![image](https://user-images.githubusercontent.com/75687413/233031957-bb8e69d0-be18-4fd2-8902-0c320d5d95ee.png)


![image](https://user-images.githubusercontent.com/75687413/233032369-f59542f3-72af-4b5f-b3d5-a83b91a38f92.png)


Code For Boa.java

package Lab8package;

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
	public int lengthInInches() {
		return this.length * 12;
	}
	}

Test Case code
package Lab8package;

import static org.junit.Assert.*;

import org.junit.Before;
import org.junit.Test;


public class BoaTest {

	@Test
	public void testIsHealthy() {
		Boa healthyBoa = new Boa("Healthy Boa", 5, "granola bars");
		Boa unhealthyBoa = new Boa("Unhealthy Boa", 5, "junk food");
		
		assertTrue(healthyBoa.isHealthy());
		assertFalse(unhealthyBoa.isHealthy());
	}

	@Test
	public void testFitsInCage() {
		Boa smallBoa = new Boa("Small Boa", 5, "granola bars");
		Boa largeBoa = new Boa("Large Boa", 10, "granola bars");
		
		assertTrue(smallBoa.fitsInCage(6));
		assertTrue(largeBoa.fitsInCage(12));
		
	}
	
	@Before
	public void setUp() throws Exception {
	Boa jen = new Boa("Jennifer", 2, "grapes");
	Boa ken = new Boa ("Kenneth", 3, "granola bars");
	
	assertFalse(ken.fitsInCage(2));
    assertFalse(ken.fitsInCage(3));
    assertTrue(ken.fitsInCage(5));
    
    assertFalse(jen.fitsInCage(1));
    assertFalse(jen.fitsInCage(2));
    assertTrue(jen.fitsInCage(3));
	}
	
	@Test
	public void TestLengthInInches() {
		Boa priyank = new Boa("Jennifer", 2, "grapes");
		Boa daksh = new Boa ("Kenneth", 3, "granola bars");
		
		assertEquals(23,priyank.lengthInInches());
	}

}

### 3. To test the Boa class:

#### Code:

~~~
import static org.junit.Assert.*;

import org.junit.Before;
import org.junit.Test;

public class BoaTest {

    private Boa healthyBoa;
    private Boa unhealthyBoa;

    @Before
    public void setUp() throws Exception {
        healthyBoa = new Boa("Healthy Boa", 6, "granola bars");
        unhealthyBoa = new Boa("Unhealthy Boa", 8, "mice");
    }

    @Test
    public void testIsHealthy() {
        assertTrue(healthyBoa.isHealthy());
        assertFalse(unhealthyBoa.isHealthy());
    }

    @Test
    public void testFitsInCage() {
        assertTrue(healthyBoa.fitsInCage(7));
        assertFalse(unhealthyBoa.fitsInCage(6));
    }

}
~~~

#### Explanation:

We first import the necessary JUnit classes and the Boa class we want to test.
We then create two Boa objects in the setUp() method. One is a healthy Boa and the other is an unhealthy one.
In the testIsHealthy() method, we test the isHealthy() method of both Boa objects. We expect the healthy Boa to be healthy and the unhealthy Boa to be unhealthy.
In the testFitsInCage() method, we test the fitsInCage() method of both Boa objects. We expect the healthy Boa to fit in a cage of length 7 and the unhealthy Boa not to fit in a cage of length 6.
We use the assertTrue() and assertFalse() methods to make assertions about the expected results of the methods being tested.

### 4. Modifying the set-up method

#### Code:

~~~
public class BoaTest {

    private Boa jen;
    private Boa ken;

    @Before
    public void setUp() throws Exception {
        jen = new Boa("Jennifer", 2, "grapes");
        ken = new Boa("Kenneth", 3, "granola bars");
    }

    // test methods go here
}
~~~

#### Explanation
This creates two Boa objects named jen and ken with different values for their name, length, and favorite food properties. The jen object has a name of "Jennifer", a length of 2 feet, and a favorite food of "grapes". The ken object has a name of "Kenneth", a length of 3 feet, and a favorite food of "granola bars". The private fields jen and ken are added to the BoaTest class so that they can be accessed in the test methods.

### 5. @Test stubs

#### A.

##### Code:

~~~
@Test
    public void testIsHealthy() {
        assertTrue(healthyBoa.isHealthy());
        assertFalse(unhealthyBoa.isHealthy());
    }
~~~

##### Output

~~~
import static org.junit.Assert.*;

import org.junit.Before;
import org.junit.Test;

public class BoaTest {

    private Boa healthyBoa;
    private Boa unhealthyBoa;

    @Before
    public void setUp() throws Exception {
        healthyBoa = new Boa("Healthy Boa", 6, "granola bars");
        unhealthyBoa = new Boa("Unhealthy Boa", 8, "mice");
    }

    @Test
    public void testIsHealthy() {
        assertTrue(healthyBoa.isHealthy());
        assertFalse(unhealthyBoa.isHealthy());
    }

    @Test
    public void testFitsInCage() {
        assertTrue(healthyBoa.fitsInCage(7));
        assertFalse(unhealthyBoa.fitsInCage(6));
    }

}
~~~

The first assertion in the testIsHealthy() method tests that the isHealthy() method returns true for the healthyBoa object, and the second assertion tests that it returns false for the unhealthyBoa object.

#### B.

##### Code:

~~~
@Test
    public void testFitsInCage() {
        assertTrue(healthyBoa.fitsInCage(7));
        assertFalse(unhealthyBoa.fitsInCage(6));
    }
~~~

##### Output

~~~
import static org.junit.Assert.*;

import org.junit.Before;
import org.junit.Test;

public class BoaTest {

    private Boa healthyBoa;
    private Boa unhealthyBoa;

    @Before
    public void setUp() throws Exception {
        healthyBoa = new Boa("Healthy Boa", 6, "granola bars");
        unhealthyBoa = new Boa("Unhealthy Boa", 8, "mice");
    }

    @Test
    public void testIsHealthy() {
        assertTrue(healthyBoa.isHealthy());
        assertFalse(unhealthyBoa.isHealthy());
    }

    @Test
    public void testFitsInCage() {
        // Test when cage length is less than length of the boa
        assertFalse(healthyBoa.fitsInCage(4));
        assertFalse(unhealthyBoa.fitsInCage(6));

        // Test when cage length is equal to length of the boa
        assertTrue(healthyBoa.fitsInCage(6));
        assertTrue(unhealthyBoa.fitsInCage(8));

        // Test when cage length is greater than length of the boa
        assertTrue(healthyBoa.fitsInCage(7));
        assertTrue(unhealthyBoa.fitsInCage(10));
    }

}
~~~

##### Explanation

The modified testFitsInCage() method tests the results of the fitsInCage() method when the cage length is less than, equal to, and greater than the length of the boa for both healthyBoa and unhealthyBoa objects.

Since the setUp() method initializes two different Boa objects, healthyBoa and unhealthyBoa, there is no need to write separate tests for "jen" and "ken". The tests should cover both objects as specified in the setUp() method.

### 7. Adding a new Method

~~~
private Boa healthyBoa;
private Boa unhealthyBoa;

@Before
public void setUp() throws Exception {
    healthyBoa = new Boa("Healthy Boa", 6, "granola bars");
    unhealthyBoa = new Boa("Unhealthy Boa", 8, "mice");
}

@Test
public void testIsHealthy() {
    assertTrue(healthyBoa.isHealthy());
    assertFalse(unhealthyBoa.isHealthy());
}

@Test
public void testFitsInCage() {
    assertTrue(healthyBoa.fitsInCage(7));
    assertFalse(unhealthyBoa.fitsInCage(6));
}

@Test
public void testLengthInInches() {
    assertEquals(healthyBoa.lengthInInches(), 72);
    assertEquals(unhealthyBoa.lengthInInches(), 96);
}
~~~

#### Explanation
After adding the lengthInInches() method to the Boa class, I can write a test case to verify its implementation in the BoaTest class. The test case should compare the expected result with the actual result from invoking the method on both the healthy and unhealthy Boa objects. The expected length in inches for a Boa with a length of n feet is n * 12 inches.
Results for feet to inch

![image](https://user-images.githubusercontent.com/75687413/233037134-66982172-9ea2-4cbc-a55d-4172034c6d7d.png)
