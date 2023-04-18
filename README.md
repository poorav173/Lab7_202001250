#IT314
# Lab-7_202001250
# Date: 18/04/2023

##Lab Session: Software Engineering

Section A:
Consider a program for determining the previous date. Its input is triple of day, month and year with the
## IT314: Software Engineering
## Name: Poorav Patel
### Section A:
1) Consider a program for determining the previous date. Its input is triple of day, month and year with the
following ranges 1 <= month <= 12, 1 <= day <= 31, 1900 <= year <= 2015.The possible output dates would be
previous date or invalid date. Design the equivalence class test cases?

### Test Cases:

| Test Case Id  | Day | Month | Year | Expected Output (DD/MM/YY) |
@@ -28,18 +26,18 @@ previous date or invalid date. Design the equivalence class test cases?

#### Input Classes:

Day
D1: Day between 1 to 28
D2: 29
D3: 30 
D4: 31

Month
M1: Month has 30 days
M2: Month has 31 days
M3: Month is February

Year
Y1: Year is a leap year
Y2: Year is a normal year 

@@ -77,6 +75,19 @@ Year:
| E11 | Less than 1 | Invalid |
| E12 | Greater than 2015 | Invalid |
## Program 1
The function linearSearch searches for a value v in an array of integers a. <br>
If v appears in the array a, then the function returns the first index i, such that a[i] == v; otherwise, -1 is returned.<br>
int linearSearch(int v, int a[])<br>
{
int i = 0;<br>
while (i < a.length)<br>
{<br>
if (a[i] == v)<br>
return(i);<br>
i++;<br>
}<br>
return (-1);<br>
}
*Equivalence partition for linear search*
| Tester Action and Input Data | Expected Outcome |
|------------------------------|------------------|
@@ -106,6 +117,20 @@ Year:
|[1,2,3,4,5,6,7,8,9,1,0,11,111],v = 1111| -1 |

## Program 2
The function countItem returns the number of times a value v appears in an array of integers a.<br>
int countItem(int v, int a[])<br>

{<br>
int count = 0;<br>
for (int i = 0; i < a.length; i++)<br>
{<br>
if (a[i] == v)<br>
count++;<br>

}<br>
return (count);<br>
}

*Equivalence Class partitioning for counting occurance*
| Tester Action and Input Data | Expected Outcome |
|------------------------------|------------------|
@@ -130,6 +155,27 @@ Year:
| [-890,890],v = 890 | 1 |

## Program 3
The function binarySearch searches for a value v in an ordered array of integers a. <br>
If v appears in the array a, then the function returns an index i, such that a[i] == v; otherwise, -1 is returned.<br>
Assumption: the elements in the array a are sorted in non-decreasing order.<br>
int binarySearch(int v, int a[])<br>
{<br>
int lo,mid,hi;<br>
lo = 0;<br>
hi = a.length-1;<br>
while (lo <= hi)<br>
{<br>
mid = (lo+hi)/2;<br>
if (v == a[mid])<br>
return (mid);<br>
else if (v < a[mid])<br>
hi = mid-1;<br>
else<br>
lo = mid+1;<br>
}<br>
return(-1);<br>
}

*Equivalent testcases for binary search:*
| Tester Action and Input Data | Expected Outcome |
|------------------------------|------------------|
@@ -157,6 +203,25 @@ Year:
| NULL,v = 4 | -1 |

## Program 4
 The following problem has been adapted from The Art of Software Testing, by G. Myers (1979). <br>
The function triangle takes three integer parameters that are interpreted as the lengths of the sides of a triangle. <br>
It returns whether the triangle is equilateral (three lengths equal), isosceles (two lengths equal), scalene (no lengths equal), or invalid (impossible lengths).<br>

final int EQUILATERAL = 0;<br>
final int ISOSCELES = 1;<br>
final int SCALENE = 2;<br>
final int INVALID = 3;<br>
int triangle(int a, int b, int c)<br>
{<br>
if (a >= b+c || b >= a+c || c >= a+b)<br>
return(INVALID);<br>
if (a == b && b == c)<br>
return(EQUILATERAL);<br>
if (a == b || a == c || b == c)<br>
return(ISOSCELES);<br>
return(SCALENE);<br>
}

*Equivalent class test cases of checking the type of triangle*
| Tester Action and Input Data | Expected Outcome |
|------------------------------|------------------|
@@ -186,6 +251,22 @@ Year:
| a = INT_MAX,b = 1,c = INT_MAX - 1 | SCALENE |

## Program 5
The function prefix (String s1, String s2) returns whether or not the string s1 is a prefix of string s2 (you may assume that neither s1 nor s2 is null).<br>
public static boolean prefix(String s1, String s2)<br>
{<br>
if (s1.length() > s2.length())<br>
{<br>
return false;<br>
}<br>
for (int i = 0; i < s1.length(); i++)<br>
{<br>
if (s1.charAt(i) != s2.charAt(i))<br>
{<br>
return false;<br>
}<br>
}<br>
return true;<br>
}
*Equivalent test cases for prefix searching are as follows:*
| Tester Action and Input Data | Expected Outcome |
|------------------------------|------------------|
@@ -212,6 +293,11 @@ Year:
| s1 = "poojan",s2 = "patel" | false |

## Program 6
Consider again the triangle classification program (P4) with a slightly different specification: <br>
The program reads floating values from the standard input. The three values A, B, and C are interpreted as representing the lengths of the sides of a triangle. <br>
The program then prints a message to the standard output that states whether the triangle, if it can be formed, is scalene, isosceles, equilateral, or right angled.<br>
Determine the following for the above program:<br>
<br>
*(a) All equivalent classes*
| Class ID | Class |
|----------|-------|
@@ -246,49 +332,41 @@ A = 0, B = 10, C = 0 <br/>
A = 0,B = 0,C = 0 <br/>
A = 0, B = -1, C = 10<br/>

### Section B:

#### 1. Convert the Java code comprising the beginning of the doGraham method into a control flow graph (CFG).

**i. Below is the control flow graph of converted Java code**<br>

![control-flow-diagram drawio](https://user-images.githubusercontent.com/84441910/231426230-4f73e587-ef87-4d39-83df-3722a17df30d.png)

#### 2. Test sets

Statement coverage test sets: To achieve statement coverage, we need to make sure that every statement in the code is executed at least once.<br>
Test 1: p = empty vector<br>
Test 2: p = vector with one point<br>
Test 3: p = vector with two points with the same y component<br>
Test 4: p = vector with two points with different y components<br>
Test 5: p = vector with three or more points with different y components<br>
Test 6: p = vector with three or more points with the same y component<br>


Branch coverage test sets: To achieve branch coverage, we need to make sure that every possible branch in the code is taken at least once<br>
Test 1: p = empty vector<br>
Test 2: p = vector with one point<br>
Test 3: p = vector with two points with the same y component<br>
Test 4: p = vector with two points with different y components<br>
Test 5: p = vector with three or more points with different y components, and none of them have the same x component<br>
Test 6: p = vector with three or more points with the same y component, and some of them have the same x component<br>
Test 7: p = vector with three or more points with the same y component, and all of them have the same x component<br>


Basic condition coverage test sets: To achieve basic condition coverage, we need to make sure that every basic condition in the code (i.e., every Boolean subexpression) is evaluated as both true and false at least once<br>
Test 1: p = empty vector<br>
Test 2: p = vector with one point<br>
Test 3: p = vector with two points with the same y component, and the first point has a smaller x component<br>
Test 4: p = vector with two points with the same y component, and the second point has a smaller x component<br>
Test 5: p = vector with two points with different y components<br>
Test 6: p = vector with three or more points with different y components, and none of them have the same x component<br>
Test 7: p = vector with three or more points with the same y component, and some of them have the same x component<br>
Test 8: p = vector with three or more points with the same y component, and all of them have the same x component.<br>
