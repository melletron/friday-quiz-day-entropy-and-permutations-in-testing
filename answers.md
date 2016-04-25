**A1**: The idea behind the complex system is that you have a collection of components that can all be in a specific state. If you can measure all states of each component individually and assume standard interactions you only have to add up all the numbers in the system (+1 for each integration line) which adds up to **75**.
**7+2+2+2+5 + 5+3+2+4+2 + (12x1) + 5+7 + 5+3 + (4x1) + 5 = 75**

**A2a**: If you take away a full level of testing, you have to measure each permutation of the system at the level of entry in order to guarantee that all possible states work. So we multiply the components that now together form a system.
**(5x7x2x2) + (3x1) + (7x2x2x5) + (3x1) + (5x5x3x2) + (3x1) + (3x3x4x2) + (3x1) + (4x1) + 5 = 523 **
**A2b**: The testing load now is moved to where in the system you have access, i.e. the functional/api tests.

**A3**: So now that we don’t even do component testing, we have a full system with one level of entry - of which we can only be certain it all works as expected by putting it in each permutation possible, i.e. multiplying all the states: (I’m taking the results of all the brackets from A2)
Component A: **(5x7x2x2) + (3x1) = 143**
Component B: **(7x2x2x5) + (3x1) = 143**
Component C: **(5x5x3x2) + (3x1) = 153**
Component D: **(3x3x4x2) + (3x1) = 75**
System integration: **(4x1) = 4**
System: **5 = 5**
**143 x 143 x 153 x 75 x 4 x 5 = 4,693,045,500**

**Bonus**:
Now in the real world some things never happen:
1. You can’t have the system in all possible states
2. You don’t need the system in all possible states
3. You always have some level of testing on each level
4. During development developers do uncoordinated testing to make sure the most common states work.
Therefore, you don’t need the 4.7 billion tests at system level. If you only do system testing you need probably several thousand tests (instead of the ideal seventy five). As a test manager in this case I would do the complete opposite as to what most enterprises do. I would encourage many small changes to all parts of the system releasing them very often. Leveraging from the fact that developers do measure and test during development. By having many releases any defect found will be solved quickly.
