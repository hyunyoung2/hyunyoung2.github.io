---
layout: post
title: 12. Integer to Roman
subtitle: Difficulty - Medium
category: LeetCode
tags: [algorithm, medium]
permalink: /2017/01/06/12_Integer_To_Roman/
bigimg: 
    - "/img/Image/BigImages/marina.jpg" : "MRINA of San Francisco, CA (2016)"
---

## [12. Integer to Roman](https://leetcode.com/problems/integer-to-roman/)

Given an integer, convert it to a roman numeral.

Input is guaranteed to be within the range from 1 to 3999.

```c
char* intToRoman(int num) {
    
}
```

## My solution. 

Typically, If I solve a similar type of this problem, I make data by default beforehand as following. 

As you can see, the patterns of the roman numerals is repeated. 

this is my solution

- First, the basic condition of this problem is a range of roman numerals is from 1 to 3999. 

- Seconde, based on the above condition, you have to be careful several numerals, those key point numberal :

5, 10 , 50, 100, 500, 1000

- Third, I'm going to use loop to calculate the roman numberals. 

```c
//                           1 ,  2 ,  3  ,  4 , 5 , 6  ,  7  ,   8  , 9  ,10 ,50 ,100,500,1000  
static char * roman[] = {"","I","II","III","IV","V","VI","VII","VIII","IX","X","L","C","D","M"};      
//                        0,  1,  2 ,  3  ,  4 , 5 , 6  ,  7  ,   8  , 9  ,10 , 11, 12, 13, 14 
// The most simple way to make normal number to Roman number
// In my algorithm, key point is those numbers below
// 5 , 10 , 50 , 100, 500, 1000 
// as you can see the condition of this problem. a range of the roman numerals is from 1 to 3999.
char returnString[16]={0}; // you have to declar this as global varialbe.

char* intToRoman(int num) {
    int index = num;
   
    memset(returnString, 0, sizeof(returnString)); // you have to intialize this value
    
    while(index != 0) {
        
        if(index >= 1000) {
            strcat(returnString, roman[14]);
            index -= 1000;
        }
        else if(index >= 900){
            strcat(returnString, roman[12]);
            strcat(returnString, roman[14]);
            index -= 900;
        }
        else if(index >= 500){
            strcat(returnString, roman[13]);
            index -= 500;
        }
        else if(index >= 400){
            strcat(returnString, roman[12]);
            strcat(returnString, roman[13]);
            index -= 400;
        }
        else if(index >= 100){
            strcat(returnString, roman[12]);
            index -= 100;
        }
        else if(index >= 90){
            strcat(returnString, roman[10]);
            strcat(returnString, roman[12]);
            index -=90; 
        }
        else if(index >= 50){
            strcat(returnString, roman[11]);
            index -= 50;
        }
        else if(index >= 40){
            strcat(returnString, roman[10]);
            strcat(returnString, roman[11]);
            index -= 40;
        }
        else if(index >= 10){
            strcat(returnString, roman[10]);
            index -= 10;
        }
        else{
            strcat(returnString, roman[index]);
            index -= index;
        }     
    }
    
   // printf("%s\n",returnString);
   // printf("%c%c%c\n",*returnString, *(returnString+1), *(returnString+2));
   // printf("%c\n", NULL);
    
    return returnString;
}
```

**Be carefule when you solve this leetcode and make a code**

this mitake is trivial, Sometimes you could forget this.

**char returnString[16]={0}; // you have to declar this as global varialbe.**

- you can understand the fear of local variable. 

**memset(returnString, 0, sizeof(returnString)); // you have to intialize this value**

- you can understand the feature of the way leetcode use your answer code.

## to sum up the above code.

As you can see the above code, there are mutiple iteration statement. 

So I am going to remake it with two loops(while) 


```c
static int  number[] = {1000, 900, 500, 400, 100, 90, 50, 40, 10, 9, 5, 4, 1};

static char * roman[] = {"M", "CM", "D","CD","C","XC","L","XL", "X", "IX", "V", "IV", "I"};

char returnString[12]={0}; // you have to declar this as global varialbe.

char* intToRoman(int num) {
    int index = num;
    int i =0;
   
    memset(returnString, 0, sizeof(returnString)); // you have to intialize this value
    
    while(index != 0) {
        while(index >= number[i]) {
            index -= number[i];
            strcat(returnString, roman[i]);
        }
       i++;  
    }
    
   // printf("%s\n",returnString);
   // printf("%c%c%c\n",*returnString, *(returnString+1), *(returnString+2));
   // printf("%c\n", NULL);
    
    return returnString;
}

```


## Another way to resolve this problem

As you can see the above code, it is too long.

How can I reduce the lengnth of the above code. 

I found out the way to reduce the length of the above code. 

- my thought makes more global variable, it means that the total digits are just four, 

Becuase, the range of roman numerals is from 1 to 3999.


- So I think I just need to calculate each digit, after making global variables specifically.



```c
//                           1000, 2000, 3000
static char * romanM[] = {"", "M", "MM", "MMM"};

//                            100, 200 , 300  , 400 , 500, 600, 700   , 800  , 900  
static char * romanL[] = {"", "C", "CC", "CCC", "CD", "D", "DC", "DCC", "DCCC", "CM"};

//                            10 ,  20 ,  30  , 40  , 50 ,  60 ,  70  ,  80  ,  90                      
static char * romanX[] = {"", "X", "XX", "XXX", "XL", "L", "LX", "LXX", "LXXX", "XC"};

//                           1 ,  2 ,  3  ,  4 , 5 , 6  ,  7  ,   8  , 9  
static char * roman[] = {"","I","II","III","IV","V","VI","VII","VIII","IX"};


char returnString[12]={0};

char * intToRoman(int num) {
    int i = 0;
    char * temp = NULL;
    
    memset (returnString, 0, sizeof(returnString));
    
    temp = romanM[num/1000];
    if (temp != "")
        strcat(returnString, temp);
        
    temp = romanL[(num%1000)/100];
    if (temp != "")
        strcat(returnString, temp);
        
    temp = romanX[((num%1000)%100)/10];
    if (temp != "")
        strcat(returnString, temp);
    
    temp = roman[((num%1000)%100)%10];
    if (temp != "")
        strcat(returnString, temp);
    
    return returnString;
}
```



## Reference

- [What rule do the roman numerals have?](https://en.wikipedia.org/wiki/Roman_numerals)

So, key point numerals is 5 10 50 100 500 1000 in that range of the above problem,

in that case, subtractive notation is used.

- [strcat function](http://www.cplusplus.com/reference/cstring/strcat/)

char * strcat(char * destination, const char * source)

concatenate strings. 

Appends a copy of the source to the destination string. the terminating null character in destination is overwritten by the first character of source, and a null-character is included at the end of the new string formed by the concatenation of both in destination.

destination and source shall not overlap. 

- char * destination : Pointer to the destination array which should contain a C string, and be large enough to contain the concatenated resulting string.

- const char * source: C String to be appened. This should not overlap destination


- [void * memset (void * ptr, int value, size_t num)](http://www.cplusplus.com/reference/cstring/memset/)

 Fill block of memory
 
Set the first num bytes of the block of memory pointed by ptr to the specified value
