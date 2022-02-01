| Logical operation | Operator |
| --- | --- |
| Equivalence | == |
| less than | < |
| Less than or equal to | <= |
| Greater  than | > |
|Greater than or equal to | >= |


| Boolean Operation |	Operator |	Example |
| --- | --- | --- |
| Both conditions must be true for the statement to be true |	AND | if x >= 5 AND x <= 100<br /><br />Returns TRUE if x is a number between 5 and 100 ||
| Only one condition of the statement needs to be true |   OR | if x == 1 OR x == 10<br /><br />Returns TRUE if X is 1 or 10|
| If a condition is the opposite of an argument |	NOT | if NOT y <br /><br /> Returns TRUE if the y value is False | 

Sample of code

>```python 
>name = "bob" hungry = True
>if name == "bob" and hungry == True:
>     print("bob is hungry")
>else if name == "bob" and not hungry:
>     print("Bob is not hungry")
>else: # If all other if conditions are not met
>     print("Not sure who this is or if they are hungry") 
>```