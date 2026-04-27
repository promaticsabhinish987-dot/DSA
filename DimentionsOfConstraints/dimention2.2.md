
new constraints that did not exist before.


For elements i and j in same collection: relation(arr[i], arr[j]) is satisfied

For elements i in collection A and j in collection B:
relation(A[i], B[j]) is satisfied





Truth: Cross-collection constraints often need maintaining separate identities while building relationships.

Note :- selecting from 2nd group , we have to define its own feature property and data structure and specify that its dynamic or static or calculative.


What Different-Collection CAN'T Do
text
Problem: "Valid parentheses"
- String: "([])"
- Each ')' must match MOST RECENT unmatched '('
- This isn't about different collections — it's about TEMPORAL ORDER
- Different-collection doesn't capture "most recent"

Problem: "Decode string" — "3[a2[c]]"
- Need to know what was seen BEFORE current position
- Different-collection can't capture HISTORY



