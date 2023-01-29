---
toc: true
layout: post
description: 52 Question MCQ
categories: [markdown]
title: 52Q Test Corrections
---

## Question 7
![image](https://user-images.githubusercontent.com/72475804/215360085-447702d7-2de1-4136-b098-30047b9c088d.png)
- I got this wrong because I didn't realize that this will prevent an ArrayIndexOutOfBoundsException from being thrown if target does not appear in data, however if target is at element 0, -1 will be returned instead of 0 as intended.
- Answer B is correct because the seqSearchRecHelper recursive method does not work as intended when target does not appear in data. In this case, when last becomes -1, the method will throw an ArrayIndexOutOfBoundsException in the first if statement after line 1. To prevent this, we should add a check to see if last is less than 0 and if it is, return -1 as expected.
- I can watch 10.1 Daily Videos #1 and #2 to learn these skills.

## Question 18
![image](https://user-images.githubusercontent.com/72475804/215360145-2331f344-e91e-4b8b-8076-d3494d3dd439.png)
- I got this wrong because I was not sure if this would be the return value if k started at 0.
- Answer C is correct because the value of the loop control variable k starts at 1 and is incremented by 2 as long as it is less than input.length. In this case, input is assigned “computer”, so input.length is 8. The values of k are 1, 3, 5, 7, and then when k is 9, the loop terminates. The statement input.substring (k, k + 1) will return the value of input at index k. The values that are added to output in order are “o”, “p”, “t”, and “r”. The value “optr” is returned.
- Resources : 2.7: Daily Video 1 (Skill 2.C), 2.7: Daily Video 2 (Skill 3.A), 2.7: Daily Video 3, 4.3: Daily Video 1 (Skill 2.C), 4.3: Daily Video 2 (Skill 3.C), 4.3: Daily Video 3 (Skill 3.C)

## Question 22
![image](https://user-images.githubusercontent.com/72475804/215360153-5035d444-b5cf-48c8-bcd9-56a21daa566c.png)
- This was an accidental error not from lack of knowledge but just cause I thought it was super easy.
- Answer B is correct because De Morgan’s Law states that !(p && q) is equivalent to !p || !q. By applying De Morgan’s Law to this expression, we negate the first expression !(!(a !=b)) and the second expression !(b >7) to form !(!(a != b)) || !(b > 7). In the first expression the two consecutive not operators (!) cancel each other out giving us (a != b). In the second expression, the opposite of > is <= giving us (b <= 7). The equivalent expression is (a != b) || (b <= 7).
- Resources: 3.6: Daily Video 1, 3.6: Daily Video 2

## Question 30
![image](https://user-images.githubusercontent.com/72475804/215360179-84a7f5ef-7b41-40b1-8ff6-877638f0c397.png)
- This question had a lot of code to follow along with and I got lost in the middle. I didn't understand that objects of subclasses can be assigned to variables of the type of superclass. In this case, the array elements are of type Book and can be assigned objects of type Book or any subclass of Book.
- Answer B is correct since the books array has been declared of type Book, at compile time all objects stored in books are considered Book object regardless of their actual type. Therefore, any methods that are called on elements of books must be declared in Book. In order to call the pagesPerMinute() method on Book[0], we would need to use typecasting to let the compiler know that the object stored in the books array at this index is actually an AudioBook object.
- Resources: 9.6 Daily Videos #1, #2, #3

## Question 48
![image](https://user-images.githubusercontent.com/72475804/215360192-c5785620-2f93-4153-843e-5cc1ae9f461b.png)
- I got this wrong as I did not realize that the row and column indices for 2D arrays start at 0. The value 8 is at newArray[1][2].
- Answer D is correct as the enhanced for loop iterates over the array oldArray. In the first iteration, newArray[0][0] is assigned the value 1. The value of row is incremented to 1. Since 1 % 3 does not equal 0, the statements in the if are not executed. In the next iteration, newArray[1][0] is assigned the value 2. The value of row is incremented to 2. The algorithm continues to fill column 0 with the subsequent values of oldArray. Once row is 3, the if condition is true and row is assigned 0 and col is incremented to 1. The algorithm proceeds to fill column 1. When the for loop terminates, newArray contains the following values { {1, 4, 7}, {2, 5, 8}, {3, 6, 9} }. The value of newArray[0][2] is 7.
- Resources: 8.1: Daily Video 1 (Skill 3.E), 8.1: Daily Video 2 (Skill 3.E), 8.1: Daily Video 3 (Skill 1.B)
