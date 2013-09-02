Thanks to a careless technical specialist at Neev, selection sort and quick sort just stopped working.
As a fresher, debug the program with the help of browser developer tools using breakpoints and save the day by fixing the program.

The catch - also document your steps below. 

Name : 


Selection Sort
==============

## Steps

1. First opened the javascript file in Google Chrome.  
2. Go to Developer Tools
3. Then kept several brealpoints to find that which statement is going wrong
4. Two BreakPoints are kept in the line contains "for (var i = 0; i < this.a.length; i++)" 
    and "for (var j = 0 ; j < i; j++)" 
    to understanding the looping procdure. 
5. Executed the code using Google Chrome.
6. Code stoped to execute at the line containig
            "for (var i = 0; i < this.a.length; i++)" 
  for further execution I found 'i' value is 0 now and a.length is 50.And 'i' will increment for every loop. 
7.Then again it stoped executing in the line
            "for (var j = 0 ; j < i; j++)"
  after further execution we found that the execution happnes from zero to the value 'i'.
  So i made changes like  
      FROM    for (var j = 0 ; j < i; j++)
      TO      for(var j=i; j< this.a.length;j++)
8. Now it should give the maximum value by j (as index) but in the code maximum value is giving the 'i' which is wrong.
   So I change the given below code i.e

    if (this.a[j] < this.a[max])

    max = i;

    To


    if (this.a[j] < this.a[max])

    max = j;

9. Then i found the correct output.

QuickSort
=========

## Steps

1. open index.html in browser and start debugging tool.

2. Apply breakpoint at following line
    this.qsort(0, this.a.length);
here "a.length" is returning value as 50. and since array location start from zeroth location. so value has to be 49
change the above statement  to
 this.qsort(0, this.a.length-1);

3. then we put a breakpoint at the first while loop.
since it was true always and no condition was getting checked their.
so put a condition to break of the loop
while(i<=j)

4. inside part function ,  in if statement their is no need to increment and decrement the i and j. only swap is necessary.
so remove the increment and decrement statements.

5. swap of pivot is also necessary after the swapping of "i" and "j". so add statement 
this.a.swapVerbose(j,v);
after the while loops.

6. after first iteration pivot element is at its correct position. 
from next iteration we have to pass locations which doesn't include this pivot position.
so we have to pass q-1 and q+1 positions for next iterations.
so change following functions
 this.qsort(p, q-1);
 this.qsort(q+1, r);
