## Pattern 2 :- (Interval greedy) now we have single resource and registered timeline, for the users and we have to server the max users. 

Our goal is to serve the max no of patients

```
Patient A : 9 AM - 5 PM
Patient B : 9 AM - 10 AM
Patient C : 10 AM - 11 AM
Patient D : 11 AM - 12 PM
Patient E : 12 PM - 1 PM
```

As early the resource free, as early it will be available for the next one.

**Signal**

```
The room is the scarce resource.

The room becomes available again at:

interval.end

Therefore:

The earlier an interval ends, the earlier the resource becomes reusable.
```

#### pattern :- sort by the end.


1. Sort by the end in ascending order.
2. Reource is busy till the end of it
3. Traverse interval , pick first end interval from sorted one, then 2nd interval compare if ()

```

if(interval.start >= lastEnd){
take interval
update lastEnd
}else{
Skip interval
}

```
#### Example :- Non-overlapping Intervals


Goal :- keep the max number of interval or remove the min number of interval.


Trick :- Always keep the interval that ends earliest. Because :- Earlier finish leaves maximum room for future intervals.


```ts
function eraseOverlapIntervals(intervals) {
    intervals.sort((a, b) => a[1] - b[1]); // sort by end time

    let countKept = 1;
    let lastEnd = intervals[0][1];

    for (let i = 1; i < intervals.length; i++) {
        const [start, end] = intervals[i];

        if (start >= lastEnd) {
            countKept++;
            lastEnd = end;
        }
    }

    return intervals.length - countKept;
}
```

Pattern

```ts
intervals.sort((a, b) => a[1] - b[1]);

let lastEnd = -Infinity;

for (const [start, end] of intervals) {
    if (start >= lastEnd) {
        // take interval
        lastEnd = end;
    }
}
```

=====================================================================================
Summary :- suppose we have a single resource , and multiple people to serve with timeline, and we have to serve the maximum person.
pattern :- sort with the end time of interval, because as easy the interval finish , it will provide the room for the next, person, to cover max no of person , we have to choose the early finish one every time thats the greedy aproach, serve max no of person.
=====================================================================================







