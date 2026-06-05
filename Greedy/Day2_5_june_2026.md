## Pattern 1 :-  sort then decide


according to the gred or requirement , we supply the resources.

```
if want 2 banana == give 2
if want 5 banana === give 5
if want 10 banana ==== give 10



small demand
small supply

medium demand
medium supply

large demand
large supply




Universal pattern==

Sort both sides
      ↓
Start from smallest
      ↓
If current supply satisfies demand
      Match
Else
      Find larger supply
```

Sort both to get min requirement 1st , and min cookie size , to optimize it.

Because


```
if we waste a large cookie , for a child who need only 1 coookie , cookie will be wasted.

child=1
cookie=5


we may later fail:

child=4
cookie=2


==> so sort the cookie and student(resource and takes of that resource in a lane)=> and give smallest possible cookie to the smallest requirement. to maximize the requirement.

```

#### Pattern (compressed form)

```
Order matching

or

demand or capacity
```
| Problem  | Demand     | Capacity       |
| -------- | ---------- | -------------- |
| Cookies  | Greed      | Cookie         |
| Trainers | Skill      | Trainer        |
| Trucks   | Box Size   | Truck Space    |
| Meetings | Start Time | Available Slot |


#### Why does greedy become correct after sorting?

Because the sorted order exposes the safer local decision.

```
Without sorting future is unknown

With sorting future is predictable
```
Sorting creates the environment where greedy become the safe.

```
Unordered Inputs
       ↓
Sorting
       ↓
Hidden Structure Appears
       ↓
Smallest Demand Visible
       ↓
Smallest Valid Resource Chosen
       ↓
Future Flexibility Preserved
       ↓
Global Optimum Emerges
```





#### Signal extraction 

Q1) when to sort.

**If you see that the elements have thr numeric property.**

```
size
weight
time
capacity
strength
```
Sort them , to make it predictable.

and 


**When see that we are matching the two group.**


```
A ↔ B
Demand ↔ Supply
Need ↔ Capacity
```

Sort them for optimal match.


Q) Can i process from smallest to largest.

**Greedy likely exist.**

Q) Does choosing the smallest valid option preserve future flexibility?

If yes → classic Sort Then Decide pattern.


```
Demand ↔ Capacity
Need ↔ Resource
Small ↔ Large
```

============================================================================================
Sorting is a tool for exposing structure.

Greedy works because sorting reveals which local choice is safest.
============================================================================================



**Summary** :- suppose we are the distrubutor of foor among poor people, and we have to serve max poor people, child can be fulfilled with small cookie, but other will not, so we have to sort both the , resource and the people, so tht we can predict the next element, and start distributing the small cookie to the small child, so that at the end we will serve the max person.


**Pattern** :- if we have two group, and each element of that group have numeric , value, and we have to give one to other , then we will use this pattern.


```
We will have 1st needy person,

we will traverse the cookie, until when we find the cookie that can satisfy that person,

if person will satisfy , then we will ++ both the cookie and the person.
```




































