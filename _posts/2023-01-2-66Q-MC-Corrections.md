---
toc: true
layout: post
description: 66 Question Practice Exam MCQ
categories: [markdown]
title: 66 Questions MC Corrections
---
## Score
![image](https://user-images.githubusercontent.com/72475804/213950259-ca01897d-c2aa-456b-8aef-434ce163113c.png)


## Question 10
![image](https://user-images.githubusercontent.com/72475804/213950305-9426ccc8-fa30-4bc2-900d-424733ae33f9.png)
- I got this wrong because I didn't realize that this will prevent an ArrayIndexOutOfBoundsException from being thrown if target does not appear in data, however if target is at element 0, -1 will be returned instead of 0 as intended.
- Answer B is correct because the seqSearchRecHelper recursive method does not work as intended when target does not appear in data. In this case, when last becomes -1, the method will throw an ArrayIndexOutOfBoundsException in the first if statement after line 1. To prevent this, we should add a check to see if last is less than 0 and if it is, return -1 as expected.
- I can watch 10.1 Daily Videos #1 and #2 to learn these skills.

## Question 19
![image](https://user-images.githubusercontent.com/72475804/213950366-1e69f53b-a925-4e40-a6fe-8acd55829417.png)
- I got this wrong because I was not sure if this would be the return value if k started at 0.
- Answer C is correct because the value of the loop control variable k starts at 1 and is incremented by 2 as long as it is less than input.length. In this case, input is assigned “computer”, so input.length is 8. The values of k are 1, 3, 5, 7, and then when k is 9, the loop terminates. The statement input.substring (k, k + 1) will return the value of input at index k. The values that are added to output in order are “o”, “p”, “t”, and “r”. The value “optr” is returned.
- Resources : 2.7: Daily Video 1 (Skill 2.C), 2.7: Daily Video 2 (Skill 3.A), 2.7: Daily Video 3, 4.3: Daily Video 1 (Skill 2.C), 4.3: Daily Video 2 (Skill 3.C), 4.3: Daily Video 3 (Skill 3.C)

## Question 25
![image](https://user-images.githubusercontent.com/72475804/213950390-7127f42b-6ae1-4077-9237-e45c2ec238bb.png)
- This was an accidental error not from lack of knowledge but just cause I thought it was super easy.
- Answer B is correct because De Morgan’s Law states that !(p && q) is equivalent to !p || !q. By applying De Morgan’s Law to this expression, we negate the first expression !(!(a !=b)) and the second expression !(b >7) to form !(!(a != b)) || !(b > 7). In the first expression the two consecutive not operators (!) cancel each other out giving us (a != b). In the second expression, the opposite of > is <= giving us (b <= 7). The equivalent expression is (a != b) || (b <= 7).
- Resources: 3.6: Daily Video 1, 3.6: Daily Video 2

## Question 32
![image](https://user-images.githubusercontent.com/72475804/213950415-881be64f-0df2-4f58-8a59-9f689f2744ba.png)
- This question had a lot of code to follow along with and I got lost in the middle. I didn't understand that objects of subclasses can be assigned to variables of the type of superclass. In this case, the array elements are of type Book and can be assigned objects of type Book or any subclass of Book.
- Answer B is correct since the books array has been declared of type Book, at compile time all objects stored in books are considered Book object regardless of their actual type. Therefore, any methods that are called on elements of books must be declared in Book. In order to call the pagesPerMinute() method on Book[0], we would need to use typecasting to let the compiler know that the object stored in the books array at this index is actually an AudioBook object.
- Resources: 9.6 Daily Videos #1, #2, #3

## Question 36
![image](https://user-images.githubusercontent.com/72475804/213950481-ab568cdd-de64-49f5-a41f-dfdc3387ca84.png)
- I got this wrong as I did not realize that the row and column indices for 2D arrays start at 0. The value 8 is at newArray[1][2].
- Answer D is correct as the enhanced for loop iterates over the array oldArray. In the first iteration, newArray[0][0] is assigned the value 1. The value of row is incremented to 1. Since 1 % 3 does not equal 0, the statements in the if are not executed. In the next iteration, newArray[1][0] is assigned the value 2. The value of row is incremented to 2. The algorithm continues to fill column 0 with the subsequent values of oldArray. Once row is 3, the if condition is true and row is assigned 0 and col is incremented to 1. The algorithm proceeds to fill column 1. When the for loop terminates, newArray contains the following values { {1, 4, 7}, {2, 5, 8}, {3, 6, 9} }. The value of newArray[0][2] is 7.
- Resources: 8.1: Daily Video 1 (Skill 3.E), 8.1: Daily Video 2 (Skill 3.E), 8.1: Daily Video 3 (Skill 1.B)

## Question 43
![image](https://user-images.githubusercontent.com/72475804/213950548-a3ec27a5-84d5-4645-996c-5b34987ade6d.png)
- I got this wrong as I did not understand that this will print the values 1, 5, 9, 13, 17, 21, 25, 29, 33, 37, 41, 45, 49, 53, 57, 61, 65, 69, 73, 77, 81, 85, 89, 93, and 97. This will output the same number of values but the values will not be the same.
- Answer E is correct as the original code segment prints all values between 1 and 100 that are evenly divisible by 4. The following values are printed: 4, 8, 12, 16, 20, 24, 28, 32, 36, 40, 44, 48, 52, 56, 60, 64, 68, 72, 76, 80, 84, 88, 92, 96, and 100. Choice E shows these values can also be printed by having a for loop that has a loop control variable k that starts at 4, increments by 4, and terminates when k is greater than 100.
- Resources: 4.2: Daily Video 1 (Skill 5.C), 4.2: Daily Video 2 (Skill 4.C), 4.2: Daily Video 3 (Skill 3.C)

## Question 48
![image](https://user-images.githubusercontent.com/72475804/213950577-e8212e87-efdf-4b67-9a27-7a8d2b343c40.png)
- I got this wrong as I did not realize that this would be correct if answer was initialized to 0 and during each iteration of the loop, n was added to answer.
- Answer C is correct when you consider the example when n is assigned the value 2 and k is assigned the value 3. The for loop has a loop control variable i that starts at 1, increments by 1 and terminates when i is k + 1. Therefore, the loop iterates k times. During each iteration of the loop, answer, which was initialized to 1, is multiplied by n. In our example, that means answer is multiplied by 2, three times. Or answer is assigned 1 * 2 * 2 * 2, which is equivalent to 2 raised to the power 3.
- Resources: 4.2: Daily Video 1 (Skill 5.C), 4.2: Daily Video 2 (Skill 4.C), 4.2: Daily Video 3 (Skill 3.C)

## Question 50
![image](https://user-images.githubusercontent.com/72475804/213950605-f96cd424-5e05-4f72-8672-969c4f9aae8b.png)
- I got this wrong because I didn't realize that this will prevent an ArrayIndexOutOfBoundsException from being thrown if target does not appear in data, however if target is at element 0, -1 will be returned instead of 0 as intended.
- Answer B is correct because the seqSearchRecHelper recursive method does not work as intended when target does not appear in data. In this case, when last becomes -1, the method will throw an ArrayIndexOutOfBoundsException in the first if statement after line 1. To prevent this, we should add a check to see if last is less than 0 and if it is, return -1 as expected.
- I can watch 10.1 Daily Videos #1 and #2 to learn these skills.

## Question 51
![image](https://user-images.githubusercontent.com/72475804/213950366-1e69f53b-a925-4e40-a6fe-8acd55829417.png)
- I got this wrong because I was not sure if this would be the return value if k started at 0.
- Answer C is correct because the value of the loop control variable k starts at 1 and is incremented by 2 as long as it is less than input.length. In this case, input is assigned “computer”, so input.length is 8. The values of k are 1, 3, 5, 7, and then when k is 9, the loop terminates. The statement input.substring (k, k + 1) will return the value of input at index k. The values that are added to output in order are “o”, “p”, “t”, and “r”. The value “optr” is returned.
- Resources : 2.7: Daily Video 1 (Skill 2.C), 2.7: Daily Video 2 (Skill 3.A), 2.7: Daily Video 3, 4.3: Daily Video 1 (Skill 2.C), 4.3: Daily Video 2 (Skill 3.C), 4.3: Daily Video 3 (Skill 3.C)

## Question 53
![image](https://user-images.githubusercontent.com/72475804/213950647-3bcc5a8c-62ac-4d29-9adb-59436fcf0788.png)
- This was an accidental error not from lack of knowledge but just cause I thought it was super easy.
- Answer B is correct because De Morgan’s Law states that !(p && q) is equivalent to !p || !q. By applying De Morgan’s Law to this expression, we negate the first expression !(!(a !=b)) and the second expression !(b >7) to form !(!(a != b)) || !(b > 7). In the first expression the two consecutive not operators (!) cancel each other out giving us (a != b). In the second expression, the opposite of > is <= giving us (b <= 7). The equivalent expression is (a != b) || (b <= 7).
- Resources: 3.6: Daily Video 1, 3.6: Daily Video 2

## Question 54
![image](https://user-images.githubusercontent.com/72475804/213950673-654c91af-12ce-497d-bef8-a1eccf8e204b.png)
- This question had a lot of code to follow along with and I got lost in the middle. I didn't understand that objects of subclasses can be assigned to variables of the type of superclass. In this case, the array elements are of type Book and can be assigned objects of type Book or any subclass of Book.
- Answer B is correct since the books array has been declared of type Book, at compile time all objects stored in books are considered Book object regardless of their actual type. Therefore, any methods that are called on elements of books must be declared in Book. In order to call the pagesPerMinute() method on Book[0], we would need to use typecasting to let the compiler know that the object stored in the books array at this index is actually an AudioBook object.
- Resources: 9.6 Daily Videos #1, #2, #3

## Question 55
![image](https://user-images.githubusercontent.com/72475804/213950694-ef4dc74c-9a0a-4f97-9594-afdbbbefee85.png)
- I got this wrong as I did not realize that the row and column indices for 2D arrays start at 0. The value 8 is at newArray[1][2].
- Answer D is correct as the enhanced for loop iterates over the array oldArray. In the first iteration, newArray[0][0] is assigned the value 1. The value of row is incremented to 1. Since 1 % 3 does not equal 0, the statements in the if are not executed. In the next iteration, newArray[1][0] is assigned the value 2. The value of row is incremented to 2. The algorithm continues to fill column 0 with the subsequent values of oldArray. Once row is 3, the if condition is true and row is assigned 0 and col is incremented to 1. The algorithm proceeds to fill column 1. When the for loop terminates, newArray contains the following values { {1, 4, 7}, {2, 5, 8}, {3, 6, 9} }. The value of newArray[0][2] is 7.
- Resources: 8.1: Daily Video 1 (Skill 3.E), 8.1: Daily Video 2 (Skill 3.E), 8.1: Daily Video 3 (Skill 1.B)

## Question 56
![image](https://user-images.githubusercontent.com/72475804/213950708-8c30caa9-3735-4a5c-8b71-3f4c8f13f95a.png)
- I got this wrong as I did not understand that this will print the values 1, 5, 9, 13, 17, 21, 25, 29, 33, 37, 41, 45, 49, 53, 57, 61, 65, 69, 73, 77, 81, 85, 89, 93, and 97. This will output the same number of values but the values will not be the same.
- Answer E is correct as the original code segment prints all values between 1 and 100 that are evenly divisible by 4. The following values are printed: 4, 8, 12, 16, 20, 24, 28, 32, 36, 40, 44, 48, 52, 56, 60, 64, 68, 72, 76, 80, 84, 88, 92, 96, and 100. Choice E shows these values can also be printed by having a for loop that has a loop control variable k that starts at 4, increments by 4, and terminates when k is greater than 100.
- Resources: 4.2: Daily Video 1 (Skill 5.C), 4.2: Daily Video 2 (Skill 4.C), 4.2: Daily Video 3 (Skill 3.C)

## Question 58
![image](https://user-images.githubusercontent.com/72475804/213950722-99eb844e-d279-4905-bdcc-acafcc5f3de8.png)
- I got this wrong as I did not realize that this would be correct if answer was initialized to 0 and during each iteration of the loop, n was added to answer.
- Answer C is correct when you consider the example when n is assigned the value 2 and k is assigned the value 3. The for loop has a loop control variable i that starts at 1, increments by 1 and terminates when i is k + 1. Therefore, the loop iterates k times. During each iteration of the loop, answer, which was initialized to 1, is multiplied by n. In our example, that means answer is multiplied by 2, three times. Or answer is assigned 1 * 2 * 2 * 2, which is equivalent to 2 raised to the power 3.
- Resources: 4.2: Daily Video 1 (Skill 5.C), 4.2: Daily Video 2 (Skill 4.C), 4.2: Daily Video 3 (Skill 3.C)

## Question 59
![image](https://user-images.githubusercontent.com/72475804/213950744-6b1646c0-d7c3-4a31-ab70-67f15e4fe253.png)
- I got this wrong because I didn't realize that this will prevent an ArrayIndexOutOfBoundsException from being thrown if target does not appear in data, however if target is at element 0, -1 will be returned instead of 0 as intended.
- Answer B is correct because the seqSearchRecHelper recursive method does not work as intended when target does not appear in data. In this case, when last becomes -1, the method will throw an ArrayIndexOutOfBoundsException in the first if statement after line 1. To prevent this, we should add a check to see if last is less than 0 and if it is, return -1 as expected.
- I can watch 10.1 Daily Videos #1 and #2 to learn these skills.

## Question 60
![image](https://user-images.githubusercontent.com/72475804/213950763-0b6b3720-b725-4bb0-b5a6-96096b3e2bf0.png)
- I got this wrong because I was not sure if this would be the return value if k started at 0.
- Answer C is correct because the value of the loop control variable k starts at 1 and is incremented by 2 as long as it is less than input.length. In this case, input is assigned “computer”, so input.length is 8. The values of k are 1, 3, 5, 7, and then when k is 9, the loop terminates. The statement input.substring (k, k + 1) will return the value of input at index k. The values that are added to output in order are “o”, “p”, “t”, and “r”. The value “optr” is returned.
- Resources : 2.7: Daily Video 1 (Skill 2.C), 2.7: Daily Video 2 (Skill 3.A), 2.7: Daily Video 3, 4.3: Daily Video 1 (Skill 2.C), 4.3: Daily Video 2 (Skill 3.C), 4.3: Daily Video 3 (Skill 3.C)

## Question 63
![image](https://user-images.githubusercontent.com/72475804/213950787-97ef5411-1aa0-4f64-a94e-df045af39a5f.png)
- This was an accidental error not from lack of knowledge but just cause I thought it was super easy.
- Answer B is correct because De Morgan’s Law states that !(p && q) is equivalent to !p || !q. By applying De Morgan’s Law to this expression, we negate the first expression !(!(a !=b)) and the second expression !(b >7) to form !(!(a != b)) || !(b > 7). In the first expression the two consecutive not operators (!) cancel each other out giving us (a != b). In the second expression, the opposite of > is <= giving us (b <= 7). The equivalent expression is (a != b) || (b <= 7).
- Resources: 3.6: Daily Video 1, 3.6: Daily Video 2
