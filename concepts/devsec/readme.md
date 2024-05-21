# DevSecOps

## Table of Contents
- <b>[CI/CD](#ci-cd)</b>


---

<details>
  <summary> <h2>CI-CD</h2> </summary>

### Key Concepts
- [Threat Modeling](#threat-modeling)
- [Secrets Management](#secrets-management)
- [Container Security](#container-security)
- [Data Security](#data-security)
- [Continuous Testing](#continuous-testing)
- [Monitoring & Logging](#monitoring--logging)

<br> 

<details>
  <summary> <h3>Threat Modeling</h3> </summary>

<br>

</details>

<br> 

<details>
  <summary> <h3>Secrets Management</h3> </summary>

<br>

</details>

<br>

<details>
  <summary> <h3>Container Security</h3> </summary>

<br>

</details>

<br>

<details>
  <summary> <h3>Data Security</h3> </summary>

<br>

</details>

<br>

<details>
  <summary> <h3>Continuous Testing</h3> </summary>

<p>Continuous testing is a software testing practice that involves testing applications throughout the entire software development life cycle (SDLC), providing quality-related feedback continuously. It provides critical feedback earlier which prevents costly reworks and enables improved product quality at every stage of development, and increases efficiency by reducing time to delivery. It also improves visibility of product quality, enabling organizations to make data-driven decisions about the readiness of software for release.</p>

<p>Continuous testing involves executing automated tests as part of the software delivery pipeline to obtain immediate feedback on the business risks associated with a software release candidate. The primary goals of continuous testing are to (1) Assess business risk coverage, (2) Provide instant insight into whether a software release candidate is too risky for release, and (3) Establish a safety net to protect the user experience.</p>

<table> 
  <tr>
    <th>Type</th>
    <th>Description</th>
    <th>Example</th>
  </tr>
  <tr>
    <td>Unit Testing</td>
    <td>Unit testing verifies that individual units of code work as expected. Unit tests are primarily written by developers.</td>
   <td> 

     
    import unittest
    from mymath import add, subtract, multiply, divide
    
    class TestMyMath(unittest.TestCase):
        def test_add(self):
            self.assertEqual(add(2, 3), 5)
            self.assertEqual(add(-2, 3), 1)
            self.assertEqual(add(-2, -3), -5)
    
        def test_subtract(self):
            self.assertEqual(subtract(5, 3), 2)
            self.assertEqual(subtract(-5, 3), -8)
            self.assertEqual(subtract(-5, -3), 2)
    
        def test_multiply(self):
            self.assertEqual(multiply(2, 3), 6)
            self.assertEqual(multiply(-2, 3), -6)
            self.assertEqual(multiply(-2, -3), 6)
    
        def test_divide(self):
            self.assertEqual(divide(6, 2), 3)
            self.assertEqual(divide(-6, 2), -3)
            with self.assertRaises(ValueError):
                divide(6, 0)

    if __name__ == '__main__':
        unittest.main()

  </td>
  </tr>
  <tr>
    <td>Integration Testing</td>
    <td>Integration testing verifies how different modules or services within an application work together. Integration tests may be written by developers, quality assurance (QA) engineers, or automated test engineers.</td>
    <td>
      
      import unittest
      from integration_example import add, multiply
      
      class TestIntegration(unittest.TestCase):
          def test_add_multiply_integration(self):
              result = add(2, 3) * multiply(4, 5)
              self.assertEqual(result, 50)
      
      if __name__ == '__main__':
          unittest.main()
  </td>
  </tr>
  <tr>
    <td>Regression Testing</td>
    <td>Regression testing is performed after a change is made to ensure existing functionality remains intact after changes are made to the codebase. Regression tests verify that the software behaves as expected both before and after modifications, thereby guarding against unintended side effects. Regression tests may be written by developers, quality assurance (QA) engineers, or automated test engineers.</td>
    <td>
      
      import unittest
      from regression_example import square, cube
      
      class TestRegression(unittest.TestCase):
          def test_square(self):
              # Regression test for the square function
              self.assertEqual(square(2), 4)
              self.assertEqual(square(3), 9)
              self.assertEqual(square(4), 16)
      
          def test_cube(self):
              # Regression test for the cube function
              self.assertEqual(cube(2), 8)
              self.assertEqual(cube(3), 27)
              self.assertEqual(cube(4), 64)
      
      if __name__ == '__main__':
          unittest.main()
  </td>
  </tr>
</table>

<br>

</details>

<br>

<details>
  <summary> <h3>Monitoring & Logging</h3> </summary>

<br>

</details>

</details>

---

