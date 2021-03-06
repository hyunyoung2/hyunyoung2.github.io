---
layout: post
title: 11. Container With Most Water
subtitle: Difficulty - Medium
category: LeetCode
tags: [algorithm, medium]
permalink: /2017/01/04/11_Container_With_Most_Water/
bigimg: 
    - "/img/Image/BigImages/marina.jpg" : "MRINA of San Francisco, CA (2016)"
---

## [11. Container with Most Water](https://leetcode.com/problems/container-with-most-water/)

Given n non-negative integers a1, a2,....., an, where each represents a point at coordiate (i, ai). 

n vertical line are drawn such that the two endpoints of line i is at (i, ai) and (i, 0).

Find two lines, which together with x-axis forms a container, such that the container contain the most water

```c
int maxArea(int* height, int heightSize) {
    
}
```

## Solution. 

### Frist, what I understand is wrong 

I think what I understand from the above problem is which two lines make a container have the most water. 

based on this understading. I resolved this problem with my algorithm.

my misunderstood algorithm is  :

   First of all, I will calculate how much difference of lenghth there are between adjacent two lines. 
   
                 I mean how different length between the line and the subsequent line.
   
   Second of all, I think The biggest one is the most water. 
    
```c
// this function gain the size of container between the line and the subsequent line
int differenceOfTwoLine(int front, int back) {
    
    if (front > back)
        return back;
    else
        return front;
}

int maxArea(int* height, int heightSize) {
    
   // first of all, I think heightSzie variable is the size fo height array of int type. 
   // Second of all, height is array that has int type
   int max = -1; 
   int i = 0; 
   
   // My algorithm about which container has the most water. 
   // first, I will get difference between adjacent line. 
  
   for (i = 0 ; i < heightSize -1 ; i++) {
        
        int temp = differenceOfTwoLine(height[i], height[i+1]);
        
        max = max > temp ? max : temp;
        
   }
  
   // I will decide which one is the biggest. that is the most water. 
   return max;
}
```

**BUT,** the above process is wrong becuase I misunderstood this problem, 

How to realize my solution is wrong is because of testing another test case,

the  basic test case is [1,1], the answer of the test case is 1. 

But if you put another test case of [1, 1, 5], you will see the answer is 4. 
 
Besides, if you make other test case like [1, 1, 5, 8], You can understand intention of this problem more. 

Because if test case is [1, 1, 5, 8], Leetcode wants answer is 5. 

---

I recommend you to read [this article](https://leetcode.com/articles/container-most-water/) to understan this problem

So, From now on, let's think about this problem.

## the right Solution after I understand this problem exactly. 

 what I understood is what the width of the area is between any two lines.

### Brute force. 

  my algorithm is use of two for statements.
 
  In other words. the first for statement is a standard line. 
  
  the second for statement is another standard of caculating width with the standard of the first for statement 
  
  let's make a code

```c
// this function is for knowing which one is less between variables of front and back.
int lessNumber(int front, int back) {
    
    if (front < back)
        return front;
    else 
        return back;
}

int maxArea(int* height, int heightSize) {
    
    int i = 0, j = 0; 
    int max = -1;
    
    // this for statement is for calculating width between every two lines. 
    for (i = 0 ; i < heightSize ; i++) {
        for (j = i+1 ; j < heightSize ; j++) {
                int temp = lessNumber(height[i], height[j]);
                int width = temp*(j-i);
                max = max > width ? max : width;
        }
    }
    return max;   
}
```

**BUT** the above algorithm is too long in leetcode. 

So I have to think about another way to resolve this problem. 

First of all, If you want to reduce time complexity. you have to reduce use loop statement. 

let me think.. the above brute force way is not good, because that includes the useless casese. 

So I found out one ways. 

that is you start with first and last line. After that. you move one which is smaller. 

repeatedly, you have to do that with current lines. finally, you can find you maximum area. 

let's make a code with the above algorithm 

```c
// if you have a library about minimum number between two numbers.
// you don't need to make this function. 
int minimumNumber(int front, int back) {
    
    if (front < back) 
        return front;
    else 
        return back;
}

int maxArea(int* height, int heightSize) {
   
   int front = 0, back = heightSize-1;
   int max = -1;
   
   // front pass the back, 
   // you don't have to calculate the width of that area. 
   while (front <  back) {         
        int temp = minimumNumber(height[front], height[back]);
        int tempArea =  temp*(back-front);
        
        max = max < tempArea ? tempArea : max;
        
        if (temp == height[front])
            front++;
        else 
            back--;
   }
    return max;
}
```

and the above function is time complexity is O(n). 

I like it when I resolve the algorithm problem if I encounter O(n) as time complexity. 

thank you for reading. 

if you have any question about my way to resolve this problem. 

feel free to ask me ~
