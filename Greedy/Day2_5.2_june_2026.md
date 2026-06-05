## Pattern 3 :- (Activity Selection) we will have rource , and persons with competetion for the resource. we have limited resource and number of people who need it, and they are competing for the resource, we have to choose the person who will maximize the oputcome.

Note :- Many activities want the same limited resource, but only some can be completed. We have limited resource we cant server all, thats why they are competinig and as a leader you have to choose the person from competiotion to get max out of it.

**Analogy**

```
Suppose you own a startup.

You receive:

100 projects

but have resources for:

10 projects

The problem isn't:

How do I do all projects?

The problem is:

Which 10 create the best outcome?
```


Q) how we can know which 10 to choose. or how many will survice in given resource, maximize the number of the porject , that should survive.

#### Variable that can directly affect fisibility 

```
deadline
profit
resource consumption
```

#### Which one to choose 

```
Not every task matters equally.

Example:

Task A
profit = 10

Task B
profit = 1000

One choice creates 100x more value.

Or:

Task A
duration = 1

Task B
duration = 100

One choice preserves much more future capacity.

Highest leverage variable:

Remaining Capacity

because capacity determines future opportunities.
```
#### Activity Selection

Select the activity which have
```
least resource consumption == highest value
```
Help to preserve the future resource.

Note :- Pattern 2 was about resource sharing but in time line, here we are doing same but we dont have timeline, we have priority.


#### Example

You have 3 days to visit more places, choose place which you can visit in minimum time, because time is resource and we have limited one.

```
Limited Resource
        +
Many Choices
        ↓
Choose best subset
```
Compressed form


```
Activities
      ↓
Consume Resources
      ↓
Resources Are Limited
      ↓
Choose Best Activities
```

Activity consumes resource, choose max activity, that will consume less resource , so that we will have max activity in given resource, its the way of greedy to maximize the profit.

**Activity selection is about managing the scarce resources.**

========================================================================================

Summary :- activity selection problem is resource allocation problem among the activity, to serve max activity in limited resource to maximize the profit, resource can be time, money , capital bugdet.

Pattern :- Max number of event that can be attained.


```
sort activities by end time

take first activity

lastEnd = first activity's end
count = 1

for each remaining activity:

    if activity.start >= lastEnd:

        take activity

        count++

        lastEnd = activity.end

return count
```
========================================================================================


```ts

function findLongestChain(pairs) {
    pairs.sort((a, b) => a[1] - b[1]);

    let count = 1;
    let lastEnd = pairs[0][1];

    for (let i = 1; i < pairs.length; i++) {
        const [start, end] = pairs[i];

        if (start > lastEnd) {
            count++;
            lastEnd = end;
        }
    }

    return count;
}
```

Activity selection is a category of Interval greedy , but its more specific , for the competion for resource.

Activity selection :- maximize the number of activity
Interval Greedy :- maximize any itnerval problem










































