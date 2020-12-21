---
title: Programming and Problem Solving - Chapter 3
subtitle: "**Dr. Alireza Manashty**<br>**University of Regina**"
style: chapter page-3
---

# **Selections**

## **3.1 Introduction and Objectives**

In the chapters 1,2 you have learned the fundamentals to start
programming. In this chapter we will learn how to write a program that
gives output to the input if satisfies some conditions provided.

## **3.2 The bool Data Type**
 ----------------------------------------------------------------------------------------------------------------
 In C++, data type **bool** is used to represent Boolean data.

 Each **bool** constant or variable contains one of two values:

 **true** or **false**.

 **true** and **false** are two C++ constants.

 **true** has the value 1.

 **false** has the value 0.

 - If a testing expression is not of **bool** type, it is coerced to **bool** type automatically when it is evaluated.
 - A nonzero value is coerced to **true** and a zero value is coerced to **false**.
 --------------------------------------------------------------------------------------------------------------
 <http://www.cplusplus.com/doc/boolean/>

<http://www.cs.uregina.ca/Links/class-info/110/selections/index.html>

## **3.3 if Statements**

The If statement allows the programmer to change the logical order of a
program; that is, make the order in which the statements are executed
differ from the order in which they are listed in the program.

### **3.3.1 If-Then Statement**

The If-Then statement uses a Boolean expression to determine whether to
execute a statement or to skip it. Here is the syntax template:
```cpp
 if (Expression)
 {
 Statement
 }
```
The expression in parentheses can be of any simple data type. Almost
without exception, this will be a logical (Boolean) expression; if not,
its value is implicitly coerced to type ```bool```(nonzero value means true,
zero value means false).

Now let's look at the following statement:
```cpp
int number, sum;
sum = 10;
cout << "Please enter an integer value: " << endl;
cin >> number;
 if (number < 0)
{
 number = 0;
}
sum = sum + number;
cout << "The sum is " << sum << endl;
```
The expression (number < 0) is evaluated. If the result is true, the
statement number = 0; is executed. If the result is false, the statement
is skipped. In either case, the next statement to be executed is sum = sum + number;.

### **3.3.2 If-Then-Else Statement**
If-Then-Else statement uses a Boolean expression to determine which one
of the two statements to execute. Here is the syntax template:
```cpp
if (Expression)
{
 Statement_A
}
 else
{
 Statement_B
 }
```
The expression in parentheses will be evaluated with the result of true
or false. Here is an example:
```cpp
cout << "You are ";
 if (age >= 65)
     cout << "a senior ";
 else
     cout << "not a senior ";
cout << "citizen." << endl;
```
The characters "You are " are sent to the output stream. The
expression age >= 65 is evaluated. If the result is true, the
characters "a senior " are sent to the output stream. If the result
is false, the characters "not a senior " is sent to the output stream.
In either case, the next statement to be executed sends the the
characters "citizen." to the output stream.

There is one thing to point out here: any statement in an ```IF``` or ```ELSE```
statement could be a block or a compound statement. If so, they must be
enclosed in a pair of braces. Here is an example which also shows a
compound expression:
```cpp
 if ( (age > 65) && (gender == 'f') )
{
 cout << "Quilting group meets:"; 
 cout << "Thursday afternoons at 4:00 p.m.";
}
```
<http://www.cplusplus.com/doc/tutorial/control/>
<http://www.cs.uregina.ca/Links/class-info/110/selections/index.html>

## **3.4 Two-Way if-else Statements**

## **3.5 Nested if and Multi-Way if-else Statements**

An ```If-Then``` statemeent uses Boolean expression to determine whether to
execute or skip a statemenet. An ```If-Then-Else``` statement uses a Boolean
expression to determine which one of the two statements to execute. The
statements to be executed or skipped could be simple statements or
compound statements (blocks). They also can be an If Statement. An If
statement within another If statement is called a ```nested If``` statement.

A look-ahead: You will soon be learning about the C++ SWITCH statement.
For very complex if/else constructs, it is preferable to use the switch
instead.

The following example is a nested If statement.
```cpp
cout << "You are ";
 if (age >= 65)
   cout << "a senior." << endl;
 else
    if (age >= 19)
      cout << "an adult." << endl;

    else
      if (age >= 13)
        cout << "a teenager." << endl;
      else
       cout << "a child." << endl;

cout << "You are a great person." << endl;
```
The characters "You are " are sent to the output stream. The
expression age >= 65 is evaluated. If the result is true, the
characters "a senior." are sent to the output stream. If the result
is false, the expression age >= 19 is evaluated. If the result
is true,the characters "an adult." are sent to the output stream. If
the result is false, the expression age >= 13 is evaluated. If the
result is true,the characters "a teeneager." are sent to the output
stream. If the result is false, the expression "a child. is sent to the
output stream. In any case above, the next statement to be executed
sends the the characters "You are a great person." to the output
stream.
Notice: once age has a value, only one statement is selected to be
executed. If we add braces to the program segment, it would be easy to
read. Let's look at it now:
```cpp
 cout << "You are ";
 if (age >= 65) 
 {
     cout << "a senior." << endl;
     cout << "*****" << endl;
 }
else
 {
    if (age >= 19)
    {
      cout << "an adult." << endl;
      cout << "*****" << endl;
    }
    else
    {
        if (age >= 13)
        {
          cout << "a teenager." << endl;
          cout << "*****" << endl;
        }
        else
        {
         cout << "a child." << endl;
         cout << "*****" << endl;
        }
   }
}
 cout << "You are a great person." << endl;
 ```
 <http://www.cplusplus.com/forum/beginner/186223/>

## **3.6 Another Example**
```cpp
#include <iostream>
using namespace std;
int main()
{
char grade;
cout << "Please enter a letter grade (A, B, C, D, or F): " <<
endl;
cin >> grade;
if (grade == 'A')
cout << "Great work. " << endl;
else if (grade == 'B')
cout << "Good work. " << endl;
else if (grade == 'C')
cout << "Passing work. " << endl;
else if (grade == 'D' || grade == 'F')
{
cout << "Unsatisfictory work. " << endl;
cout << "See your instructor." << endl;
}
else
cout << grade << " is not a legal grade." << endl;
cout << endl;
return 0;
} // end main
```
<http://www.cplusplus.com/forum/beginner/186223/>

## **3.7 Common Errors and Pitfalls**

The most common errors beginners make in this chapter are the syntax
errors. First check the syntax errors if you get any error such as
spellings of the identifiers (it should be ```if``` and ```else``` instead IF, If,
Else, ELSE).

The other most common error to check for is the usage of semicolon after
the if statement, below example will explain you the usage.
```cpp
if(x>5);
cout<<"x is greater than 5";
else
cout<<"x is less than 5";
```
It is absolutely fine not to use braces after the if and else statement
if there is only one statement inside the block. But here the error is
we should not use the semicolon after if statement which will end the
execution at that line and you will get "**unexpected else statement
found**" error. So, use of semicolon after the **if** or **else** or
**if else** statement is not preferred if you want to continue the
execution inside the block or after the block.

## **3.8 Generating Random Numbers**

Rand function:

```cpp 
int rand (void);
```

**Generate random number**

Returns a pseudo-random integral number in the range
between 0 and [RAND_MAX](http://www.cplusplus.com/RAND_MAX).

This number is generated by an algorithm that returns a sequence of
apparently non-related numbers each time it is called. This algorithm
uses a seed to generate the series, which should be initialized to some
distinctive value using
function [srand](http://www.cplusplus.com/srand).

[RAND_MAX](http://www.cplusplus.com/RAND_MAX) is a constant defined
in [<cstdlib>](http://www.cplusplus.com/cstdlib).

A typical way to generate trivial pseudo-random numbers in a determined
range using rand is to use the modulo of the returned value by the range
span and add the initial value of the range:

```cpp
v1 = rand() % 100; // v1 in the range 0 to 99        
v2 = rand() % 100 + 1; // v2 in the range 1 to 100    
v3 = rand() % 30 + 1985; // v3 in the range 1985-2014
```

Notice though that this modulo operation does not generate uniformly
distributed random numbers in the span (since in most cases this
operation makes lower numbers slightly more likely).

C++ supports a wide range of powerful tools to generate random and
pseudo-random numbers
(see [<random>](http://www.cplusplus.com/random) for more info).

An integer value between 0
and [RAND_MAX](http://www.cplusplus.com/RAND_MAX).

### ***3.8.1 Example***

```cpp
  /* rand example: guess the number */                                                      
                                                             
#include <stdlib.h> 
  /*srand, rand */                                            
                                                                                                               
#include <iostream>
using namespace std;
int main()                                                           
  {                                                          
     int iSecret, iGuess;                                       
                                                              
   /* initialize random seed:                              */                                                                                                               srand (time(NULL));                                        
                                                          
    /* generate secret number                                 
      between 1 and 10: */                                      
                                                           
iSecret = rand() % 10 + 1;                                 
                                                                 
      do 
      {                                                                                                  
      cout<<"Guess the number(1 to 10): ";                                            
      cin>>"%d",&iGuess;                                    
                                                                 
      if (iSecret<iGuess) 
      cout << "The secret number is lower";                                                                              
                                                                 
      else if (iSecret>iGuess)                                  
      cout <<"The secret number is higher";                                                 
                                                                 
      } while (iSecret!=iGuess);                                 
                                                                 
     cout <<"Congratulations!";                               
                                                                 
      return 0;                                                  
                                                                 
      }                                                          

```
In this example, the random seed is initialized to a value representing
the current time (calling [time](http://www.cplusplus.com/time)) to
generate a different value every time the program is run.
```cpp

Possible output:
 Guess the number (1 to 10): 5 
                               
 The secret number is higher   
                               
 Guess the number (1 to 10): 8 
                               
 The secret number is lower    
                               
 Guess the number (1 to 10): 7 
                               
 Congratulations!              
```

<http://www.cplusplus.com/reference/cstdlib/rand/>

## **3.9 Logical Operators**

The operator``` !``` is the C++ operator for the
Boolean operation ```NOT```. It has only one operand, to its right, and
inverts it, producing false if its operand is true, and true if its
operand is false. Basically, it returns the opposite Boolean value of
evaluating its operand. For example:

```cpp
!(5 == 5)   // evaluates to false because the expression at its right (5 == 5) is true
!(6 <= 4)   // evaluates to true because (6 <= 4) would be false
!true       // evaluates to false
!false      // evaluates to true 
                                 
```
The logical operators && and  are used when evaluating two
expressions to obtain a single relational result. The
operator && corresponds to the Boolean logical operation AND, which
yields true if both its operands are true, and false otherwise. The
following panel shows the result of operator && evaluating the
expression a&&b:
 <dl><style type="text/css">
	table.tableizer-table {
		font-size: 12px;
		border: 1px solid #CCC; 
		font-family: Arial, Helvetica, sans-serif;
	} 
	.tableizer-table td {
		padding: 4px;
		margin: 3px;
		border: 1px solid #CCC;
	}
	.tableizer-table th {
		background-color: #104E8B; 
		color: #FFF;
		font-weight: bold;
	}
</style>
<table class="tableizer-table">
<thead><tr class="tableizer-firstrow"><th>&& OPERATOR (and)</th></tr></thead><tbody>
 <tr><td>a</td><td>b</td><td>a && b</td></tr>
 <tr><td>true</td><td>true</td><td>true</td></tr>
 <tr><td>true</td><td>false</td><td>false</td></tr>
 <tr><td>false</td><td>true</td><td>false</td></tr>
 <tr><td>false</td><td>false</td><td>false</td></tr>
</tbody></table>
</dl>
The operator  corresponds to the Boolean logical operation OR, which
yields true if either of its operands is true, thus being false only
when both operands are false. Here are the possible results of ab:
<dl><style type="text/css">
	table.tableizer-table {
		font-size: 12px;
		border: 1px solid #CCC; 
		font-family: Arial, Helvetica, sans-serif;
	} 
	.tableizer-table td {
		padding: 4px;
		margin: 3px;
		border: 1px solid #CCC;
	}
	.tableizer-table th {
		background-color: #104E8B; 
		color: #FFF;
		font-weight: bold;
	}
</style>
<table class="tableizer-table">
<thead><tr class="tableizer-firstrow"><th>   || OPERATOR (or)</th></tr></thead><tbody>
 <tr><td>a</td><td>b</td><td>a || b</td></tr>
 <tr><td>true</td><td>true</td><td>true</td></tr>
 <tr><td>true</td><td>false</td><td>true</td></tr>
 <tr><td>false</td><td>true</td><td>true</td></tr>
 <tr><td>false</td><td>false</td><td>false</td></tr>
</tbody></table>
</dl>
For example:

```cpp
 ( (5 == 5) && (3 > 6) ) // evaluates to false ( true && false )       
                                                                       
 ( (5 == 5) || (3 > 6) ) // evaluates to true ( true || false )    
```

When using the logical operators, C++ only evaluates what is necessary
from left to right to come up with the combined relational result,
ignoring the rest. Therefore, in the last example ((5==5)||(3>6)),
C++ evaluates first whether 5==5 is ```true```, and if so, it never checks
whether 3>6 is true or not. This is known as *short-circuit
evaluation*, and works like this for these operators:
<dl>
<style type="text/css">
	table.tableizer-table {
		font-size: 12px;
		border: 1px solid #CCC; 
		font-family: Arial, Helvetica, sans-serif;
	} 
	.tableizer-table td {
		padding: 4px;
		margin: 3px;
		border: 1px solid #CCC;
	}
	.tableizer-table th {
		background-color: #104E8B; 
		color: #FFF;
		font-weight: bold;
	}
</style>
<table class="tableizer-table">
<thead><tr class="tableizer-firstrow"><th>operator</th><th>short-circuit</th></tr></thead><tbody>
 <tr><td>&&</td><td>if the left-hand side expression is false, the combined result is false (the right-hand side expression is never evaluated).</td></tr>
 <tr><td>||</td><td>if the left-hand side expression is true, the combined result is true (the right-hand side expression is never evaluated).</td></tr>
</tbody></table> </dl>

This is mostly important when the right-hand expression has side
effects, such as altering values:
```cpp
      if ( (i<10) && (++i<n) ) { /*...*/ } // note that the condition increments i   
```

Here, the combined conditional expression would increase i by one, but
only if the condition on the left of && is true, because otherwise,
the condition on the right-hand side (++i<\n) is never evaluated.

<http://www.cplusplus.com/doc/tutorial/operators/>

## **3.10 switch Statements**

The Switch statement is a selection statement that can be used instead
of a series of If-Then-Else statements. Switch statements are much
better for complex expressions. Alternative statements are listed with
a switch label in front of each. A switch label is either a case label
or the word default. A case label is the word case followed by a
constant expression. An integral expression is called a switch
expression is used to match one of the values on the case labels. The
statement associated with the value that is matched is the statement
that is executed. Execution then continues sequentially from the matched
label untill the end of the Switch statement is encountered or
a break statement is encountered.

Basically, transfers control to one of the several statements, depending
on the value of a condition.

### *3.10.1 Syntax*

  -------------------------------------------------------------------------------------------- -- --------------- -- -- -- -- -- -- --
  *attr*(optional) **switch** **(** *condition* **)** *statement*                                 (until C++17)                     
                                                                                                                                    
  *attr*(optional) **switch** **(** *init-statement*(optional) *condition* **)** *statement*      (since C++17)                     
                                                                                                                                    
  -------------------------------------------------------------------------------------------- -- --------------- -- -- -- -- -- -- --


 ***attr*(C++11)**            -    any number                   
                                    of [attributes               
                                    ](https://en.cppreference.co 
                                    m/w/cpp/language/attributes) 
+=============================+======+==============================+
 ***condition***              -    any expression of 
                                    integral or enumeration      
                                    type, or of a class          
                                    type contextually           
                                    implicitly                   
                                    convertible to 
                                    an integral or enumeration   
                                    type, or                     
                                    a declaration of 
                                    a single non-array variable  
                                    of such type with a          
                                    brace                        
                                    -or-equals initializer. 

 ***init-statement*(C++17)**  -    either                       
                                                                 
                                    -   an expression           
                                        statement             
                                        (which 
                                        may be a *null         
                                        statement* "**;**")  
                                                                 
                                    -   a simple                
                                        declaration, 
                                        typically a            
                                        declaration of a       
                                        variable with          
                                        initializer, but it    
                                        may declare            
                                        arbitrarily many       
                                        variables or           
                                        structured bindings    
                                                                 
                                    Note that                  
                                    any *init-statement* must  
                                    end with a                 
                                    semicolon **;**, which is  
                                    why it is often described  
                                    informally as an           
                                    expression or a            
                                    declaration followed by a  
                                    semicolon.                 

 ***statement***            -  any statement(typically 
                                    a compound                 
                                    statement). **cas          
                                    e:** and **default:** labels 
                                    are permitted              
                                    in *sta                    
                                    tement* and break; statement 
                                    has special meaning.       


  ------------------------------------------------------------------- ------- -- -- -- -- -- -- -- --
  *attr*(optional) **case** *constant_expression* **:** *statement*   (1)                        
                                                                                                   
  *attr*(optional) **default** **:** *statement*                      (2)                        
                                                                                                   
  ------------------------------------------------------------------- ------- -- -- -- -- -- -- -- --

  --------------------------- ---- -------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  ***constant_expression***   -   a constant expression of the same type as the type of *condition* after conversions and integral promotions
  --------------------------- ---- -------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### *3.10.2 Explanation*

The body of a switch statement may have an arbitrary number
of case: labels, as long as the values of all *constant_expressions* are
unique (after conversions/promotions). At most one default: label may be
present (although nested switch statements may use their
own default: labels or have case: labels whose constants are identical
to the ones used in the enclosing switch)

If *condition* evaluates to the value that is equal to the value of one
of *constant_expression*s, then control is transferred to the statement
that is labeled with that *constant_expression*.

If *condition* evaluates to the value that doesn't match any of
the case: labels, and the default: label is present, control is
transferred to the statement labeled with the default: label.

The [break](https://en.cppreference.com/w/cpp/language/break) statement,
when encountered in *statement* exits the switch statement:
```cpp
switch(1) {

case 1 : cout << '1'; // prints "1",

case 2 : cout << '2'; // then prints "2"

}

switch(1) {

case 1 : cout << '1'; // prints "1"

break; // and exits the switch

case 2 : cout << '2';

break;

}
```

Compilers may issue warnings on fall through (reaching the next case label without a break) unless the attribute [[fall through]] appears immediately before the case label to indicate that the fall through is intentional                       
                                                                    
 If init-statement is used, the switch statement is equivalent to
```                                                  
{
**init_statement*
switch ( *condition* ) *statement*
}
```                                                         
                                                                    
 Except that names declared by the *init-statement* (if *init-statement* is a declaration) and names declared by *condition* (if condition is a declaration) are in the same scope, which is also the scope of *statement*.                      


Because transfer of control is [not permitted to enter the
scope](https://en.cppreference.com/w/cpp/language/goto) of a variable,
if a declaration statement is encountered inside the *statement*, it has
to be scoped in its own compound statement:
```cpp
switch(1) {

case 1: int x = 0; // initialization

std::cout<< x <<'**n**';
break;
default: // compilation error: jump to default: would enter the scope of 'x'
// without initializing it
std::cout<<"default**n**";
break;

}
```
```cpp
switch(1) {

case 1: { int x = 0; 
    std::cout << x <<'**n**';
    break;
} // scope of 'x' ends here

default:
 std::cout<<"default**n**"; // no error
break;
}
```
### *3.10.3 Keywords*

[switch](https://en.cppreference.com/w/cpp/keyword/switch), [case](https://en.cppreference.com/w/cpp/keyword/case), [default](https://en.cppreference.com/w/cpp/keyword/default)

### Example

The following code shows several usage cases of the *switch* statement

**Run this code**
```cpp
#include <iostream>
int main()
{
int i = 2;
switch (i) {
case 1: std::cout <<"1";

case 2: std::cout <<"2"; //execution starts at this case label

case 3: std::cout <<"3";

case 4:

case 5: std::cout <<"45";

break; //execution of subsequent statements is terminated

case 6: std::cout <<"6";

}

 

std::cout << '\n';

 

switch (i) {

case 4: std::cout <<"a";

default: std::cout <<"d"; //there are no applicable constant_expressions

//therefore default is executed

}

 

std::cout << '\n';

 

switch (i) {

case 4:  std::cout <<"a"; //nothing is executed

}

 

// when enumerations are used in a switch statement, many compilers

// issue warnings if one of the enumerators is not handled

enum color {RED, GREEN, BLUE};

switch(RED) {

case RED: std::cout <<"red\n";
break;

case GREEN: 
std::cout <<"green\n";
break;

case BLUE: std::cout <<"blue\n"; 
break;

}

 

// the C++17 init-statement syntax can be helpful when there is

// no implicit conversion to integral or enumeration type

switch (Device dev = get_device(); dev.state())
{
case SLEEP: */*...*/* 
break;

case READY: */*...*/*
 break;

case BAD: */*...*/* 
break;

}


// pathological examples
// the statement doesn't have to be a compound statement

switch(0)

std::cout << "this does nothing\n";

// labels don't require a compound statement either
switch(int n = 1)
case 0:
case 1: std::cout << n << '**n**';
// Duff's Device: http://en.wikipedia.org/wiki/Duff's_device

}
```
```cpp
Output:
2345
d
red
1
```
<http://www.cs.uregina.ca/Links/class-info/110/loops/write-p1.html>

<https://en.cppreference.com/w/cpp/language/switch>

## **3.11 Conditional Operators**

The conditional operator evaluates an expression, returning one value if
that expression evaluates to true, and a different one if the expression
evaluates as false. Its syntax is:
```cpp
condition ? result1 : result2
```
If condition is ```true```, the entire expression evaluates to ```result1``, and
otherwise to ```result2```.

```cpp
7==5 ? 4 : 3     // evaluates to 3, since 7 is not equal to 5.
7==5+2 ? 4 : 3   // evaluates to 4, since 7 is equal to 5+2.
5>3 ? a : b      // evaluates to the value of a, since 5 is greater than 3.
a>b ? a : b      // evaluates to whichever is greater, a or b.  
```
For example:

```cpp
   // conditional operator                         
   #include <iostream>       
  using namespace std;                                     
  int main ()                                              
   {                                                        
    int a,b,c;                                               
     a=2;                                                     
     b=7;                                                     
     c = (a>b) ? a : b;                                      
   cout <<c<<'\n';                                                                                           
   }                                                        
```

In this example, a was 2, and b was 7, so the expression being evaluated
(a>b) was not true, thus the first value specified after the question
mark was discarded in favor of the second value (the one after the
colon) which was b (with a value of 7).

## **3.12 Operator Precedence and Associativity**

If relational operators and Boolean operators
are combined in the same expression in C++, the Boolean operator ```NOT (!)```
has the highest precedence, the relational operators have the next
highest precedence, and the Boolean operators ```AND (&&)``` and ``` OR (||)```
have the lowest. Expressions in parentheses are always evaluated first.

A single expression may have multiple operators. For example:
```cpp
      x = 5 + 7 % 2;   
  ```

In C++, the above expression always assigns 6 to variable x, because
the ``` %``` operator has a higher precedence than the ```+ ``` operator and is always
evaluated before. Parts of the expressions can be enclosed in
parenthesis to override this precedence order, or to make explicitly
clear the intended effect. Notice the difference:

```cpp
 x = 5 + (7 % 2); // x = 6 (same as without parenthesis)    
 x = (5 + 7) % 2; // x = 0                                  |
```

From greatest to smallest priority, C++ operators are evaluated in the order of precedence (we have seen in the previous chapter)

<!-- //   ----------------------------------------------------------------------------------------------------------------------
//   **Level**   **Precedence group**           **Operator**             **Description**                    **Grouping**
//   ----------- ------------------------------ ------------------------ ---------------------------------- ---------------
//   1           Scope                          ::                       scope qualifier                    Left-to-right

//   2           Postfix (unary)                ++ --                   postfix increment / decrement      Left-to-right

//                                              ()                       functional forms                   

//                                              []                     subscript                          

//                                              . ->                    member access                      

//   3           Prefix (unary)                 ++ --                   prefix increment / decrement       Right-to-left

//                                              ~ !                     bitwise NOT / logical NOT          

//                                              + -                     unary prefix                       

//                                              & *                     reference / dereference            

//                                              new delete               allocation / deallocation          

//                                              sizeof                   parameter pack                     

//                                              (*type*)                 C-style type-casting               

//   4           Pointer-to-member              .* ->*                access pointer                     Left-to-right

//   5           Arithmetic: scaling            * / %                   multiply, divide, modulo           Left-to-right

//   6           Arithmetic: addition           + -                     addition, subtraction              Left-to-right

//   7           Bitwise shift                  << >>                shift left, shift right            Left-to-right

//   8           Relational                     < > <= >=            comparison operators               Left-to-right

//   9           Equality                       == !=                    equality / inequality              Left-to-right

//   10          And                            &                        bitwise AND                        Left-to-right

//   11          Exclusive or                   ^                       bitwise XOR                        Left-to-right

//   12          Inclusive or                   |                       bitwise OR                         Left-to-right

//   13          Conjunction                    &&                       logical AND                        Left-to-right

//   14          Disjunction                    ||                     logical OR                         Left-to-right

//   15          Assignment-level expressions   = *= /= %= += -=       assignment / compound assignment   Right-to-left
//                                              >>= <<= &= ^= |=                                      

//                                              ?:                       conditional operator               

//   16          Sequencing                     ,                        comma separator                    Left-to-right
//   ---------------------------------------------------------------------------------------------------------------------- -->

 **NOTE**:  When an expression has two operators with the same precedence level, *grouping(associativity)* determines which one is evaluated first: either left-to-right or right-to-left. 
  *Enclosing all sub-statements in parentheses (even those unnecessary because of their precedence) improves code readability.* 

## **3.13 Debugging**

We have discussed the common errors in the section 3.8, to debug them
you need to know the error first. Execute the code then you will see the
corresponding error, if the error you see is syntax error go to the
error line and check for the misspelled keywords and syntax usage.

If you see there is no error and the output displayed is not the desired
one then there might be a problem with defining the conditions or the
flow is not continued further due to use of semicolons or other
statements like break, continue. So, to check that you can go into debug
mode and check each step in the flow to see where we are doing wrong.

## **3.14 Chapter Summary**

In this chapter, you have learned how to use the if-else, nested
if-else, switch statements to control the flow of the program depending
on the conditions and input from the user. There are some common errors
that you should be careful with, to enjoy the error free programming
using conditional statements. We have operators and Boolean variables
that are used in an operation to specify the condition.
