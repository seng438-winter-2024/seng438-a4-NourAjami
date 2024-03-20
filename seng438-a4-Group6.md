**SENG 438 - Software Testing, Reliability, and Quality**

**Lab. Report \#4 – Mutation Testing and Web app testing**

| Group \#:      |     |
| -------------- | --- |
| Student Names: |     |
| Nour Ajami     |     |                 
|                |     |
|                |     |

# Introduction

# Analysis of 10 Mutants of the Range class 
1. **combine** Method
**Original Code:** `if(range1 == null)`
**Mutated Code:** `if(false)`
**Analysis:** This mutant was killed by the test `range1IsNullTest`, the expected range returned should have been the same as the second input range `range2`, but instead an unexpected value was received since the mutant code was using an unexpected value the max and min values.

2.**combine** Method
**Original Code:** `return range1`
**Mutated Code:** `return null`
**Analysis:** This mutant was killed by the test `range2IsNullTest`, as the expected range to be returned should have been the same as the first input range `range1` since the second one from the test is null. The return value of the mutated code was null which was unexpected and thus led to the mutant being killed.

3. **constrain** Method
**Original Code:** `if (value > this.upper)`
**Mutated Code:** `If (value >= this.upper)`
**Analysis:** This mutant survived, as there are no tests that were used to check if the value is equal to the upper range value of the range that it is being used on.

4. **intersects** Method
**Original Code**: `return (b0 < this.upper && b1 >= b0)`
**Mutated Code**: `return (b0 <= this.upper && b1 >= b0`
**Analysis:** This mutant survived. The mutant code was not detected since there are no tests for intersects that use the arguments that are equivalent to the upper value of the range.

5. **intersects** Method
**Original Code**: `if (b0 <= this.lower)`
**Mutated Code**: `if (b0 < this.lower)`
**Analysis:** This mutant survived since none of the tests for this method tested the arguments that were the same as the lower value of the range in this case.

6. **getCentralValue** Method
**Original Code:** `return this.lower / 2.0 + this.upper / 2.0`
**Mutated Code:** `return this.lower / 1.0 + this.upper / 2.0`
**Analysis:** This mutant was killed. The single test that is present for this method `centralValueBetweenRange` was able to kill this mutation since the lower bound value was behaving differently and the center value was different than the expected one.

7. **getCentralValue** Method
**Original Code:** `return this.lower / 2.0 + this.upper / 2.0`
**Mutated Code:** `return this.lower / 2.0 + this.upper / 1.0`
**Analysis:** This mutant was killed. The single test that is present for this method `centralValueBetweenRange` was able to kill this mutation since the upper bound value was behaving differently and the center value was different than the expected one.

8. **getLength** Method
**Original Code:** `return this.upper - this.lower`
**Mutated Code** `return this.upper + this.lower`
**Analysis:** This mutant was killed. The mutant was killed by the test `getPositiveLengthTest()` this is because the original calculation of this test is 20 - 5 = 15, but since the operation was replaced with addition then it became 20 + 5 = 25 which is the unexpected value. 

9. **expand** Method
**Original Code**: `double lower = range.getLowerBound() - length * lowerMargin`
**Mutated Code:** `double lower = range.getLowerBound() + length * lowerMargin`
**Analysis:** This mutation was killed. This will now compute the addition of the lower bound range with the length multiplied by the lowerMargin. The test case `expandLowerBoundToNegative()` killed this mutation because the lowerMargin is incorrect now and thus the test fails.

10. **equals** Method
**Original Code:** `if (!(obj instanceof Range)) `
**Mutated Code:** `if (true)`
**Analysis:** This mutant was killed. The test `rangeObjectsAreEqual()` was able to detect and kill this mutation since an argument of type Range.class was sent to the equals method. This test should return true, but with this mutant code it will always return false which is the unexpected behavior that was detected and killed.

# Report all the statistics and the mutation score for each test class

# Analysis drawn on the effectiveness of each of the test classes

# A discussion on the effect of equivalent mutants on mutation score accuracy

# A discussion of what could have been done to improve the mutation score of the test suites

# Why do we need mutation testing? Advantages and disadvantages of mutation testing

# Explain your SELENUIM test case design process

# Explain the use of assertions and checkpoints

# how did you test each functionaity with different test data

# Discuss advantages and disadvantages of Selenium vs. Sikulix

# How the team work/effort was divided and managed


# Difficulties encountered, challenges overcome, and lessons learned

# Comments/feedback on the lab itself
