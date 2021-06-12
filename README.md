# Competitive Coding with C++

<!-- ![]() -->
 This repository will act as a guide for you throughout the webinar.

## Materials for the Session

It doesn't matter if you join our webinar a little late or you prefer to do it at your own pace, we have you covered. In this repository, you'll find everything you need.

- Webinar youtube link
- Slide deck
- [Whatsapp group chat](http://bit.ly/STS-1-WA)
- [Online Compiler](https://www.onlinegdb.com/online_c++_compiler)
- [Polling during session](https://www.menti.com/)

> *You need to have a basic knowledge of C/C++ language. If not, don't worry. Learn more about it [here](https://www.youtube.com/watch?v=BS3mT0NgKzM).*  

## Participation Certificate

- To get the participation certificate, you will have to fill the feedback form which will be floated at end of the session.
- All the details in the Feedback form will be used for generating the certificates. So please check it before submitting. No consideration will be there afterwards.  

> ***Note:** The Registration of the participants will be validated before providing them with the certificates.*

## Table of Contents
- [General info](#general-info)
- [Basic Input Output](#basic-input-output) <!-- - [Interactive Console](#interactive-console) - [Text Streams](#text-streams)-->
- [Datatypes](#datatypes)
- [Operators](#operators)
- [Control Statements](#control-statements)
- [Arrays](#arrays)
- [Space Time Complexity](#space-time-complexity)
- [Algorithms](#algorithms)
- [STL](#stl)
- [Create Your Profile on HackerRank](#create-your-profile-on-hackerrank)
- [Contest](#contest)

## General info

- Competitive programming is a mind sport usually held over the Internet or a local network, involving participants trying to program according to provided specifications. Competitive programming is recognized and supported by several multinational software and Internet companies, such as Google and Facebook. There are several organizations who host programming competitions on a regular basis.
- Focus of the webinar is to emphasize on the importance of Competitive Coding. That is:
  1. Practicing it makes you a better coder who learns to solve questions with ease.
  2. Trains our mind to be more focused and think faster.
  3. Improves logic-based thinking.
  4. Inculcate the habit of learning.
  5. Gives an edge in the technical interviews of big companies like Google, Microsoft, Yahoo! etc. 

## Basic Input Output

The very first step of getting started with competitive coding or rather programming is to understand:

- How to read input data?
- How to output the answer?

There are two ways of doing so:

1. [Interactive Console](#interactive-console)
2. [Text Streams](#text-streams)

### Interactive Console

In this method, we read the input data and print the result on the same console during the time of execution of the program. 
For project devlopment, most of the IDEs use this method as well as, it is also used when we run our code on the command prompt of our system.

- _Program to demonstrate input and output using interactive console._
 
```cpp
#include <iostream>
using namespace std;

int main()
{
    int a,b;
    cout << "Enter value of a: ";
    cin >> a;
    
    cout << "Enter value of b: ";
    cin >> b;

    cout << "The quotient is: "<<a/b;
    return 0;
}
```
<!-- ![]() -->

### Text Streams

In this method, input and out happens at different places. Input data is read from standard input stream (**STDIN**) and results are printed to standard output stream (**STDOUT**).
All the platforms for competitive coding usually use this method for input and output.

> _**Note:** We need to provide input before executing the code which was not in the case of interactive cnsole._ 

- _Program to demonstrate input and output using text streams._

```cpp
#include <iostream>
using namespace std;

int main()
{
    int a,b;
    cin>> a >> b;

    cout << a/b;
    return 0;
}
```
<!-- ![]() -->
<!-- ![]() -->

Careful not to print any thing else in the output, such as `cout << "The quotient is: " << a/b;` because the online judge directly compares your output to expected output like normal string comparison.  
Say if expected output is `2`, and the code prints`The quotient is: 2` then when online judge compares `2` with `The quotient is: 2`, it will say that the code produced wrong result. Every problem has a predefined input and output format in competitive coding which everyone needs to follow.

There is another stream known as the standard error stream (**STDERR**) where all the error messages are shown whenever an exception is occured in the code. Many times these messages are shown on the STDOUT only so that we don't need a differet STDERR.

- _Run this program using `10 0` as input and you will see the error message on the STDERR._

```cpp
#include <iostream>
using namespace std;

int main()
{
    int a,b;
    cin>>a>>b;
    try{
        if(b==0){
            throw "Can Not Divide by Zero!";
        }
        cout<<"The quotient is: "<<a/b;   
    }
    catch(const char* str){
        cerr<<str;
    }
    return 0;
}
```
<!-- ![]() -->

[Back to table of contents](#table-of-contents)


## Datatypes

**Data types** are used to tell the variables the type of data it can store. 
Whenever a variable is defined in C++, the compiler allocates some memory for that variable based on the data-type with which it is declared. 
Every data type requires a different amount of memory.

<!-- ![]() -->

Data types in C++ is mainly divided into three types: 

- Primitive
- Derived
- User-Defined
 
**Primitive Data Types:** These data types are built-in or predefined data types and can be used directly by the user to declare variables. 
_**example:** int num, char ch, float dec, etc._ 

- _program below shows the use data types with variables._

```cpp
#include <iostream>
using namespace std;

int main()
{
    int i = 10;
    float f = 0.09f;
    double d = 3.14698467890;
    char c = 'A';
    bool b = true;
    
    cout<<" Primitive Data Types: "<<endl<<endl;
    
    cout<<"             Interger: "<<i<<endl;
    cout<<"       Floating Point: "<<f<<endl;
    cout<<"Double Floating Point: "<<d<<endl;
    cout<<"            Character: "<<c<<endl;
    cout<<"              Boolean: "<<b<<endl;
    
    return 0;
}
```

**Derived Data Types:** The data types that are derived from the primitive or built-in data types are referred to as Derived Data Types. 
_**example:** int* ptr, char\[size\] str etc._  
For more info on this visit [here](https://www.geeksforgeeks.org/derived-data-types-in-c/).

**User-Defined Data Types:** These data types are defined by user itself. Like, defining a class in C++ or a structure.  
_**example:** class A{defination of this class}, struct B{defination of this structure}, etc._  
For more info on this visit [here](https://www.geeksforgeeks.org/user-defined-data-types-in-c/).

### Datatype Modifiers

<!-- ![]() -->

As the name implies, datatype modifiers are used with the built-in data types to modify the length of data that a particular data type can hold. 

- _The table below summarizes the primitive data-type's size and range, with and without modifiers._ 

<table>
<thead>
	<tr>
		<td> <strong>Data Type</strong> </td>
		<td> <strong>Size(in bytes)</strong> </td>
		<td> <strong>Range</strong> </td>
	</tr>
</thead>
<tbody>
	<tr>
		<td> bool </td>
		<td> 1 </td>
		<td><em>true</em> or <em>false</em> </td>
	</tr>
	<tr>
		<td> char </td>
		<td> 1 </td>
		<td> -128 to 127 </td>
	</tr>
	<tr>
		<td> unsigned char </td>
		<td> 1 </td>
		<td> 0 to 255 </td>
	</tr>
	<tr>
		<td> short int </td>
		<td> 2 </td>
		<td> -32,768 to 32,767 </td>
	</tr>
	<tr>
		<td> unsigned short int </td>
		<td> 2 </td>
		<td> 0 to 65,535 </td>
	</tr>
	<tr>
		<td> int </td>
		<td> 4 </td>
		<td> -2147483648 to 2147483647 </td>
	</tr>
	<tr>
		<td> unsigned int </td>
		<td> 4 </td>
		<td> 0 to 4,294,967,295 </td>
	</tr>
	<tr>
		<td> long int </td>
		<td> 4 </td>
		<td> -2147483648 to 2147483647 </td>
	</tr>
	<tr>
		<td> unsigned long int </td>
		<td> 4 </td>
		<td> 0 to 4,294,967,295 </td>
	</tr>
	<tr>
		<td> long long int </td>
		<td> 8 </td>
		<td> -2<sup>63</sup> to 2<sup>63</sup>-1 </td>
	</tr>
	<tr>
		<td> unsigned long long int </td>
		<td> 8 </td>
		<td> 0 to 18,446,744,073,709,551,615 </td>
	</tr>
	<tr>
		<td> float </td>
		<td> 4 </td>
		<td> ±1.18 x 10<sup>-38</sup> to ±3.4 x 10<sup>38</sup> (6 to 9 significant digits) </td>
	</tr>
	<tr>
		<td>  double </td>
		<td> 8 </td>
		<td> ±2.23 x 10<sup>-308</sup> to ±1.80 x 10<sup>308</sup> (15 to 18 significant digits) </td>
	</tr>
	<tr>
		<td>  long double </td>
		<td> 12 </td>
		<td> ±3.36 x 10<sup>-4932</sup> to ±1.18 x 10<sup>4932</sup> (18 to 22 significant digits) </td>
	</tr>
</tbody>
</table>

> _**Note:** In C++ the size of data types varies in different architectures. we have considerd here GCC 32 bit._ 

- We can display the size of all the data types by using the sizeof() operator and passing the keyword of the datatype as argument to this function as shown below: 
```cpp
cout << "Integer: " << sizeof(int) << " bytes.";   // this will give the output "Integer: 4 bytes." 
```

[Back to table of contents](#table-of-contents)


## Operators

**Operators** are symbols that tell the compiler to perform specific mathematical or logical manipulations. Here, we will try to cover the most commonly used operators in programming.

First, let's categorize them:

1. [Arithmetic](#arithmetic-operators)
2. [Relational](#relational-operators)
3. [Bitwise](#bitwise-operators)
4. [Logical](#logical-operators)
5. [Assignment](#assignment-operators)
6. [Increment](#increment-decrement-operators)
7. [Miscellaneous](#miscellaneous-operators)

### Arithmetic Operators
<table>
<thead>
	<tr>
		<td> <strong>Symbol</strong> </td>
		<td> <strong>Operation</strong> </td>
		<td> <strong>Usage</strong> </td>
		<td> <strong>Explanation</strong> </td>
	</tr>
</thead>
<tbody>
	<tr>
		<td> + </td>
		<td> addition </td>
		<td> x + y </td>
		<td>Adds values on either side of the operator</td>
	</tr>
	<tr>
		<td> - </td>
		<td> subtraction </td>
		<td> x - y </td>
		<td>Subtracts the right hand operand from the left hand operand</td>
	</tr>
	<tr>
		<td> * </td>
		<td> multiplication </td>
		<td> x * y </td>
		<td>Multiplies values on either side of the operator</td>
	</tr>
	<tr>
		<td>  / </td>
		<td> division </td>
		<td> x / y </td>
		<td>Divides the left hand operand by the right hand operand</td>
	</tr>
	<tr>
		<td>  % </td>
		<td> modulus </td>
		<td> x % y </td>
		<td>Divides the left hand operand by the right hand operand and returns remainder</td>
	</tr>
</tbody>
</table>


### Relational Operators
These operators are used for comparison. They return either **true** or **false** based on the comparison result. The operator '==' should not be confused with '='. The relational operators are as follows:

<table>
<thead>
	<tr>
		<td> <strong>Symbol</strong> </td>
		<td> <strong>Operation</strong> </td>
		<td> <strong>Usage</strong> </td>
		<td> <strong>Explanation</strong> </td>
	</tr>
</thead>
<tbody>
	<tr>
		<td>  == </td>
		<td> equal </td>
		<td> x == y </td>
		<td>Checks if the values of two operands are equal or not, if yes then condition becomes true.</td>
	</tr>
	<tr>
		<td>  != </td>
		<td> not equal </td>
		<td> x != y </td>
		<td>Checks if the values of two operands are equal or not, if values are not equal then condition becomes true.</td>
	</tr>
	<tr>
		<td>  &gt; </td>
		<td> greater than </td>
		<td> x &gt; y </td>
		<td>Checks if the value of the left operand is greater than the value of the right operand, if yes then condition becomes true</td>
	</tr>
	<tr>
		<td>  &lt; </td>
		<td> less than </td>
		<td> x &lt; y </td>
		<td>Checks if the value of the left operand is less than the value of the right operand, if yes then condition becomes true.</td>
	</tr>
	<tr>
		<td>  &gt;= </td>
		<td> greater than or equal </td>
		<td> x &gt;= y </td>
		<td>Checks if the value of the left operand is
		greater than or equal to the value of the right operand, if yes then condition becomes true.</td>
	</tr>
	<tr>
		<td>  &lt;= </td>
		<td> less than or equal </td>
		<td> x &lt;= y </td>
		<td>Checks if the value of the left operand is less
		than or equal to the value of the right operand, if yes then condition becomes true.</td>
	</tr>
</tbody>
</table>

### Bitwise Operators
These operators are very useful and we have some tricks based on these operators. These operators convert the given integers into binary and then perform the required operation, and give back the result in decimal representation.

<table>
<thead>
	<tr>
		<td> <strong>Symbol</strong> </td>
		<td> <strong>Operation</strong> </td>
		<td> <strong>Usage</strong> </td>
		<td> <strong>Explanation</strong> </td>
	</tr>
</thead>
<tbody>
	<tr>
		<td>  &amp; </td>
		<td> bitwise AND </td>
		<td> x &amp; y </td>
		<td>Sets the bit to the result if it is set in both operands.</td>
	</tr>
	<tr>
		<td>  | </td>
		<td> bitwise OR </td>
		<td> x | y </td>
		<td>Sets the bit to the result if it is set in either operand.</td>
	</tr>
	<tr>
		<td>  ^ </td>
		<td> bitwise XOR </td>
		<td> x ^ y </td>
		<td>Sets the bit if it is set in one operand but not both</td>
	</tr>
	<tr>
		<td>  ~ </td>
		<td> bitwise NOT </td>
		<td> ~x </td>
		<td>Unary operator and has the effect of 'flipping' bits,i.e, flips 1 to 0 and 0 to 1.</td>
	</tr>
	<tr>
		<td>  &lt;&lt; </td>
		<td> left shift </td>
		<td> x &lt;&lt; y </td>
		<td>The left operand's value is moved left by the number of bits specified by the right operand. It is equivalent to multiplying x by $$2^y$$</td>
	</tr>
	<tr>
		<td>  &gt;&gt; </td>
		<td> right shift </td>
		<td> x &gt;&gt; y </td>
		<td>The left operand's value is moved right by the number of bits specified by the right operand.It is equivalent to dividing x by $$2^y$$</td>
	</tr>
</tbody>
</table>

_**Examples:**_  
Assume x = 42, y = 27  
x = 0010 1010  
y = 0001 1011  
x & y = 0000 1010= 10 (in decimal)  
x | y = 0011 1011= 59  
x ^ y = 0011 0001= 49  
 ~x = 1101 0101  
x&lt;&lt;2 = 1010 1000 = 168. Notice, the bits are shifted 2 units to the left and the new bits are filled by 0s.  
x&gt;&gt;2 = 0000 1010 = 10. Notice, the bits are shifted 2 units to the right and the new bits are filled by 0s.


### Logical Operators 
These operators take boolean values as input and return boolean values as output.  

> _**Note:** In C,C++ any non-zero number is treated as true and 0 as false but this doesn't hold for Java._  

<table>
<thead>
	<tr>
		<td> <strong>Symbol</strong> </td>
		<td> <strong>Operation</strong> </td>
		<td> <strong>Usage</strong> </td>
		<td> <strong>Explanation</strong> </td>
	</tr>
</thead>
<tbody>
	<tr>
		<td>  &amp;&amp; </td>
		<td> logical AND </td>
		<td> x &amp;&amp; y </td>
		<td>Returns true if both x and y are true else returns false.</td>
	</tr>
	<tr>
		<td>  || </td>
		<td> logical OR </td>
		<td> x || y </td>
		<td>Returns false if neither x nor y is true else returns true</td>
	</tr>
	<tr>
		<td>  ! </td>
		<td> logical NOT </td>
		<td> ! x </td>
		<td>Unary operator. Returns true if x is false else returns false.
            </td>
	</tr>
</tbody>
</table>  

### Assignment Operators  
<table>
<thead>
	<tr>
		<td> <strong>Symbol</strong> </td>
		<td> <strong>Operation</strong> </td>
		<td> <strong>Usage</strong> </td>
		<td> <strong>Equivalence</strong> </td>
		<td> <strong>Explanation</strong> </td>
	</tr>
</thead>
<tbody>
	<tr>
		<td>  = </td>
		<td> assignment </td>
		<td> x = y </td>
		<td></td>
		<td>Assigns value from the right side operand(s) to the left side operand.</td>
	</tr>
	<tr>
		<td>  += </td>
		<td> add and assignment </td>
		<td> x += y </td>
		<td> x = x + y </td>
		<td>Adds the right side operand to the left side operand and assigns the result to the left side operand.</td>
	</tr>
	<tr>
		<td>  -= </td>
		<td> subtract and assignment </td>
		<td> x -= y </td>
		<td> x = x - y </td>
		<td>Subtracts the right side operand from the left side operand and assigns the result to the left side operand.</td>
	</tr>
	<tr>
		<td> *= </td>
		<td> multiply and assignment </td>
		<td> x *= y </td>
		<td> x = x * y </td>
		<td>Multiplies the right side operand with the left side operand and assigns the result to the left side operand.</td>
	</tr>
	<tr>
		<td>  /= </td>
		<td> divide and assignment </td>
		<td> x /= y </td>
		<td> x = x / y </td>
		<td>Divides the left side operand with the right side  operand and assigns the result to the left side operand.</td>
	</tr>
	<tr>
		<td>  %= </td>
		<td> modulus and assignment </td>
		<td> x %= y </td>
		<td> x= x % y </td>
		<td>Takes modulus using the two operands and assigns the result to the left side operand.</td>
	</tr>
	<tr>
		<td>  &lt;&lt;= </td>
		<td> left shift and assignment </td>
		<td> x &lt;&lt;= y </td>
		<td> x = x &lt;&lt; y </td>
		<td>Shifts the value of x by y bits towards the left and stores the result back in x.</td>
	</tr>
	<tr>
		<td>  &gt;&gt;= </td>
		<td> right shift and assignment</td>
		<td> x &gt;&gt;= y </td>
		<td> x = x &gt;&gt; y </td>
		<td>Shifts the value of x by y bits towards the right and stores the result back in x.</td>
	</tr>
	<tr>
		<td>  &amp;= </td>
		<td> bitwise AND and assignment </td>
		<td> x &amp;= y </td>
		<td> x = x &amp; y </td>
		<td>Does x&amp;y and stores result back in x.</td>
	</tr>
	<tr>
		<td>  |= </td>
		<td> bitwise OR and assignment </td>
		<td> x |= y </td>
		<td> x = x | y </td>
		<td>Does x|y and stores result back in x</td>
	</tr>
	<tr>
		<td>  ^= </td>
		<td> bitwise XOR and assignment </td>
		<td> x ^= y </td>
		<td> x= x ^ y </td>
		<td>Does x^y and stores result back in x.</td>
	</tr>
</tbody>
</table>  

### Increment Decrement Operators
These are **unary** operators. Unary operators are the operators which require only one operand.  
<table>
<thead>
	<tr>
		<td> <strong>Symbol</strong> </td>
		<td> <strong>Operation</strong> </td>
		<td> <strong>Usage</strong> </td>
		<td> <strong>Explanation</strong> </td>
	</tr>
</thead>
<tbody>
	<tr>
		<td>  ++ </td>
		<td> Postincrement </td>
		<td> x++ </td>
		<td>Increment x by 1 after using its value</td>
	</tr>
	<tr>
		<td>  -- </td>
		<td> Postdecrement </td>
		<td> x-- </td>
		<td>Decrement x by 1 after using its value</td>
	</tr>
	<tr>
		<td>  ++ </td>
		<td> Preincrement </td>
		<td> ++x </td>
		<td>Increment x by 1 before using its value</td>
	</tr>
	<tr>
		<td>  -- </td>
		<td> Predecrement </td>
		<td> --x </td>
		<td>Decrement x by 1 before using its value</td>
	</tr>
</tbody>
</table>

_**Examples:**_  
Let x = 10  
then, after  **y = x++**;  
y = 10 and x = 11, this is because x is assigned to y before its increment.  
but if we had written **y = ++x**;  
y = 11 and x = 11, because x is assigned to y after its increment.  
Same holds for decrement operators.

### Miscellaneous Operators  
**Conditional Operator**: It is similar to **if-else**:  
```
x = (condition) ? a : b
```
If condition is true,then a is assigned to x else b is assigned to x. It is a ternary operator because it uses the condition, a and b _i.e._ three operands (the condition is also treated as a boolean operand).  

### Operator Precedence and Associativity  
**Precedence Rules**:  
The precedence rules specify which operator is evaluated first when two operators with different precedence are adjacent in an expression.  
_For example:_ `x = a + ++b`

This expression can be seen as postfix increment on a and addition with b or prefix increment on b and addtion to a. Such issues are resolved by using precedence rules.  
**Associativity Rules**:  
The associativity rules specify which operator is evaluated first when two operators with the same precedence are adjacent in an expression.  
_For example:_ `a * b /c`

**Operator Precedence**:  
The following table describes the precedence order of the operators mentioned above. Here, the operators with the highest precedence appear at the top and those with the lowest at the bottom. In any given expression, the operators with higher precedence will be evaluated first.  
**LR** = Left to Right  
**RL** = Right to Left  
<table>
<thead>
	<tr>
		<td> <strong>Category</strong> </td>
		<td> <strong>Associativity</strong> </td>
		<td> <strong>Operator</strong> </td>
	</tr>
</thead>
<tbody>
	<tr>
		<td>  Postfix </td>
		<td> LR </td>
		<td>++ --</td>
	</tr>
	<tr>
		<td>  Unary </td>
		<td> RL </td>
		<td>+ - ! ~ ++ --</td>
	</tr>
	<tr>
		<td>  Multiplicative </td>
		<td> LR </td>
		<td>* / % </td>
	</tr>
	<tr>
		<td>  Additive </td>
		<td> LR </td>
		<td>+ - </td>
	</tr>
	<tr>
		<td>  Shift </td>
		<td> LR </td>
		<td> &lt;&lt; &gt;&gt; </td>
	</tr>
	<tr>
		<td>  Relational  </td>
		<td> LR </td>
		<td>&lt; &lt;= &gt; &gt;=</td>
	</tr>
	<tr>
		<td>  Equality </td>
		<td> LR </td>
		<td>==  != </td>
	</tr>
	<tr>
		<td>  Bitwise AND </td>
		<td> LR</td>
		<td>&amp; </td>
	</tr>
	<tr>
		<td>  Bitwise XOR </td>
		<td> LR </td>
		<td> ^ </td>
	</tr>
	<tr>
		<td>  Bitwise OR </td>
		<td> LR </td>
		<td> | </td>
	</tr>
	<tr>
		<td>  Logical AND </td>
		<td> LR </td>
		<td> &amp;&amp; </td>
	</tr>
	<tr>
		<td>  Logical OR </td>
		<td> LR </td>
		<td> || </td>
	</tr>
	<tr>
		<td>  Conditional </td>
		<td> RL </td>
		<td> ?: </td>
	</tr>
	<tr>
		<td>  Assignment </td>
		<td> RL </td>
		<td> = += -= *= /= %= &gt;&gt;= &lt;&lt;= &amp;= ^= |= </td>
	</tr>
</tbody>
</table>  

[Back to table of contents](#table-of-contents)


## Control Statements

A control statement is a statement that determines the execution of other statements.  
These can be classified into these three categories:

- [Decision Statements](#decision-statements)
- [Iterative Statements](#iterative-statements)
- [Jump Statements](#jump-statements)

### Decision Statemetns
these statemetns decides the flow of program on the basis of a deciding condition.

#### 1. if
It is used to decide whether a certain statement or block of statements will be executed or not i.e if the condition is true then a block of statement is executed otherwise not.  the condition after evaluation genrates a boolan value.

- _The syntax of the if statement._
```cpp
if(condition) 
{
   // Statements to execute if
   // condition is true
}
```
- _A program to demonstrate the use of if statement._
```cpp
#include<iostream>
using namespace std;

int main() {
    int i = 18;
 
    if (i >= 18)
    {
       cout<<"Eligible for Voting";
    }
    
    return 0;
}
```
#### 2. if else
The if statement alone tells us that if a condition is true it will execute a block of statements and if the condition is false it won’t. We can use the else statement with if statement to execute a block of code when the condition is false.

> _**Note:** any statement outside the if else block will get executed without depending on the condition of if where as the else statemetn will only get executed if the condition of if is false._

- _The syntax of the if else statement._
```cpp
if (condition)
{
    // Executes this block if
    // condition is true
}
else
{
    // Executes this block if
    // condition is false
}
```
- _A program to demonstrate the use of if else statement._
```cpp
#include<iostream>
using namespace std;

int main() {
    int i = 18;
 
    if (i >= 18) {
    	cout<<"Eligible for Voting";
    }
    else {
    	cout<<"Underage"; 
    }
    
    return 0;
}
```
> _**Note:** if statement can be written alone but there must be a if statement for every else statement _i.e._ else statement cannot be wriiten without a if statement._

#### 3. Nested if else
Nested statements means an if statement inside another if statement. These can be used when we require more than one conditions to be true for particular statement to get executed.
- _The syntax of the nested statement._
```cpp
if (condition1) 
{
   // Executes when condition1 is true
   if (condition2) 
   {
      // Executes when condition2 is true
   }
}
```
> _**Note:** You can aslo use combined condition in a single if condition rather than using nested if condition like `if(condition1 && condition2)` but be aware, statementws inside it will run only when both the conditions are true._
- _A program to demonstrate the use of neseted statements._
```cpp
#include<iostream>
using namespace std;
int main() {
    int i = 10;
 
    if (i == 10)
    {
        // First if statement
        if (i < 15)
           cout<<"i is smaller than 15\n";
 
        // Nested - if statement
        // Will only be executed if statement above
        // is true
        if (i < 12)
            cout<<"i is smaller than 12 too\n";
        else
            cout<<"i is greater than 15";
    }
    return 0;
}
```
#### 4. if else if Ladder
By using this a user can decide among multiple options. Conditions are checked from the top to down. As soon as one of the conditions controlling the if is true, the statement associated with that if is executed, and the rest of the else-if ladder is bypassed. If none of the conditions are true, then the final else statement will be executed.

- _The syntax of the if else statement._
```cpp
if (condition1)
    // statement1;
else if (condition2)
    // statement2;
else if (condition3)
    // statement3;
.
.
else
    // else statements;
```
- _A program to demonstrate the use of if else statement._
```cpp
#include<iostream>
using namespace std;
int main()
{
    int i = 20;
  
    if (i == 10)
        cout<<"i is 10";
    else if (i == 15)
        cout<<"i is 15";
    else if (i == 20)
        cout<<"i is 20";
    else
        cout<<"i is not present";
}
```
#### 5. switch case
Switch case statements are a substitute for long if statements that compare a variable to several values.  
The switch statement is a multiway branch statement. It provides an easy way to dispatch execution to different parts of code based on the value of the control variable.

> _**Note:** The control variable can only be of integer or character data type._

- _Syntax of a switch case statement._
```cpp
inty n;  // n is the control variable.
switch (n)
{
    case 1: // code to be executed if n = 1;
        break;
    case 2: // code to be executed if n = 2;
        break;
    default: // code to be executed if n doesn't match any cases
}
```
- _A program to demonstrate switch case._
```cpp
include <iostream>
using namespace std;
 
int main() {
	int x = 2;
    	
	switch (x) {
        	case 1:
        	    cout << "Choice is 1";
        	    break;
        	case 2:
        	    cout << "Choice is 2";
        	    break;
        	case 3:
       	     	    cout << "Choice is 3";
            	    break;
        	default:
        	    cout << "Choice other than 1, 2 and 3";
        	    break; 
    	}
	
	return 0;
}
```

### Iterative Statements
Iterative statements are called as loops. Loops in programming come into use when we need to repeatedly execute same block of statements.  
To create a loop we require:  

1. **Start point** from where we need to start the loop.
2. **Test condition** which will get us out of loop when it gets full-filled.
3. **Step difference** _i.e._ from start how much we need to increment or decrement in each iteration to reach the end.  

There are of two types of loops:

- **Entry controlled:** Test condition is tested before entering the loop body. The for loops and while loops are entry controlled loops.
- **Exit controlled:** Test condition is tested or evaluated at the end of loop body. Therefore, the loop body will execute atleast once, irrespective of whether the test condition is true or false. The do while loop is a exit controlled loop.

#### 1. for
- _Syntax for using for loop._
```cpp
for (initialization expr; test expr; update expr)
{    
     // body of the loop
     // statements we want to execute
}
```
- _A program to demonstrate for loop._
```cpp
#include <iostream>
using namespace std;
  
int main()
{
    for (int i = 1; i <= 10; i++)
    {
        cout << "Hello World\n";
    }
  
    return 0;
}
```

#### 2. while
- _Syntax for using while loop._
```cpp
initialization expression;
while (test_expression)
{
   // statements
 
  update_expression;
}
```
- _A program to demonstrate while loop._
```cpp
#include <iostream>
using namespace std;
  
int main()
{
    // initialization expression
    int i = 1;
  
    // test expression
    while (i < 6)
    {
        cout << "Hello World\n";
  
        // update expression
        i++;
    }
  
    return 0;
}
```

#### 3. do while
In do while loop the loop body will execute at least once irrespective of test condition as it is a exit controlled loop.  
- _Syntax for using do while loop._
```cpp
initialization expression;
do
{
   // statements

   update_expression;
} while (test_expression);
```

> _**Note:** Notice the semi – colon(“;”) in the end of loop._

- _A program to demonstrate do while loop._
```cpp
#include <iostream>
using namespace std;
  
int main()
{
    int i = 2; // Initialization expression
  
    do
    {
        // loop body
        cout << "Hello World\n";
  
        // update expression
        i++;
  
    }  while (i < 1);   // test expression
  
    return 0;
}
```

### Jump Statements
Jump Statement makes the control jump to another section of the program unconditionally when encountered.
#### 1. break
It is used to terminate the loop or switch-case immediately. In case of loops, as soon as the break statement is encountered from within a loop, 
the loop iterations stops there and control returns from the loop immediately to the first statement after the loop. Similarly, in case of switch,
when break is encountered the control returns from the case immediately to the first statement after the switch body.

- _Syntax to use break._
```cpp
// in case of loops
while(condition1){
	// statement(s)
	if(condition2){
		break;
	}
	// update loop
}

// in case of switch
switch(control_variable){
	case 1:
		// statement(s)
		break;
	case 2:
		// statement(s)
		break;
}
```

> _**Note:** In case of nested loops if we break out from inner loop the next statement from the outer loop will get executed._

#### 2. continue
Opposite to the break statement, instead of terminating the loop, it forces to execute the next iteration of the loop. 
When the continue statement is executed in the loop, 
the code inside the loop following the continue statement will be skipped and next iteration of the loop will begin.

> _**Note:** The continue can only be used inside a loop._

#### 3. return
This statement returns the flow of the execution to the function from where it is called. 
It is usually used at the end of a function to end or terminate it with or without a value.
The return statement only returns a value which is of the same data type as the return type of the function in its declaretion.

- _Syntax of a return statement._
```cpp
return_type function1(args){
	data_type value;	//data_type = return_type
	// statement(s)
	return value;
}
```

> _**Note:** a function decleared void cannot return any value._

- _A Program to demonstrate Jump statements._
```cpp
#include<iostream>
using namespace std;

int main()
{
    
    cout<<"Counting from 1 to 10"<<endl;
    
    for(int i=1; i<11; i++){
        if(i == 4){
            cout<<endl;
            continue;
        }
        if(i == 8){
            break;
        }
        cout<<i<<endl;
    }
    return 0;
}
```

[Back to table of contents](#table-of-contents)


## Arrays

[Back to table of contents](#table-of-contents)


## Space Time Complexity

[Back to table of contents](#table-of-contents)


## Algorithms

[Back to table of contents](#table-of-contents)


## STL

The Standard Template Library (STL) is a set of C++ template classes to provide common programming data structures and algorithms such as lists, stacks, queues, etc. 
It is a generalized library and so, its components are parameterized. 
A working knowledge of [template classes](https://www.geeksforgeeks.org/templates-cpp/) is a prerequisite for working with STL.

STL has three components:

- **Containers:**  
the container classes is the place where we store objects and data. 
Here are some important containers which we use in competitive coding:

	- vector
	- stack 
	- queue
	- map

  you need to include the specific header to use the container like:
```cpp
#include <vector>		//header to use vectors in the code.
#include <stack>		//header to use stacks in the code.
```

- **Iterators:**  
As the name suggests, iterators are used for working upon a sequence of values. 
Simply put, they are used to point at the memory addresses of containers.

- **Algorithms:**  
These are the functions especially designed to be used on ranges of elements.
They act on containers and provide means for various operations for the contents of the containers.
All the important Algorithms are defined in the algorithm header and we need to include it to use them.
```cpp
#include <algorithm>		//header to use STL algorithms in the code.
```
Let's now take an example of vectors to understand properly.

- _Program to initialize an empty vector, push some values in it and print the vector after it._
```cpp
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int main()
{
    vector<int> v;
    
    v.push_back(50);
    v.push_back(35);
    v.push_back(90);
    v.push_back(19);
    v.push_back(22);
    v.push_back(88);
    v.push_back(12);
    
    cout<<"The Elements are: ";
    for(int i=0; i<v.size(); i++){
        cout<<v[i]<<" ";
    }
    cout<<endl<<endl;
    
    return 0;
}
```

- _To get the size of vetor._
```cpp
    cout<<"Size of Vector: "<<v.size()<<endl<<endl;
```

- _To get the first and last element of vector._
```cpp
    cout<<"First Element: "<<v.front()<<"    "<<"Last Element: "<<v.back()<<endl<<endl;
```

- _To insert elements at desired index in vector._ 
```cpp
    v.insert(v.begin(), 5);
    v.insert(v.begin()+3, 5);
    v.insert(v.begin()+9, {1,11,111});
    
    cout<<"The New Elements are: ";
    for(int i=0; i<v.size(); i++){
        cout<<v[i]<<" ";
    }
    cout<<endl<<endl;
```

- _Algorithm to reverse a vector._
```cpp
    reverse(v.begin(), v.end());
    
    cout<<"Reversed Vector: ";
    for (int i = 0; i < v.size(); i++){
        cout << v[i] << " ";
    }        
    cout<<endl<<endl;
```

- _To sort a vector in ascending order._
```cpp
    sort(v.begin(), v.end());
    
    cout<<"Sorted Elements in Ascending: ";
    for (int i = 0; i < v.size(); i++){
        cout << v[i] << " ";
    }        
    cout<<endl<<endl;
```

- _To sort a vector in descending order._
```cpp
    sort(v.begin(), v.end(), greater<int>());
    
    cout<<"Sorted Elements in Descending Order: ";
    for (int i = 0; i < v.size(); i++){
        cout << v[i] << " ";
    }        
    cout<<endl<<endl;
```

- _To get the sum of all elements in the vector._
```cpp
    cout<<"Sum of all Elements: "<<accumulate(v.begin(),v.end(),0)<<endl<<endl;
```

- _To get the maximum element in a vector._
```cpp
    cout<<"Max Element: "<<*max_element(v.begin(), v.end())<<endl<<endl;
```

- _To get the minimum element in a vector._
```cpp
    cout<<"Min Element: "<<*min_element(v.begin(), v.end())<<endl<<endl;
```

- _To remove the last element from the vector._
```cpp
    v.pop_back();
    v.pop_back();
    
    cout<<"The Elements are: ";
    for(int i=0; i<v.size(); i++){
        cout<<v[i]<<" ";
    }
```

[Back to table of contents](#table-of-contents)


## Create Your Profile on HackerRank

- _**Step 1:** Open [HackerRank](https://www.hackerrank.com/) from your laptop._ 
- _**Step 2:** Click on Sign Up and Code Button under the "For Developers" Option._
- _**Step 3:** Enter your personal details and Submit the form._
- _**Step 4:** On the next screen, select Learn and Compete with others and then select the options according to you._ 
- _**Step 5:** Scroll down to the Skills Available for Practice Section and select Algorithms from there._

[Back to table of contents](#table-of-contents)


## Contest

We have a small contest planned for you. This will help you practice and implement the learnings from the session. 

The contest will be of 45 mins in which you will have to give solutions for just 3 problems. The contest will be hosted on HackerRank and the link for the same will be shared at the end of the webinar.
> _**Important:** The top rank holders of the leaderboard will be awarded by some exciting prizes!_

The winners will be announced according to the leaderboard, next week _i.e._, 20th June'21 in our next session.

##  The End

> _**The repository will get updated during the session.**_
