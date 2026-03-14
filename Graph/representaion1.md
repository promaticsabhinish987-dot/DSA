
# Graph DSA Learning Ladder (20 Problems)

## Level 1 — Graph Representation (Foundation)

### 1. Build a Graph From Edge List

**Problem**

You are given `n` nodes and an edge list.

```
edges = [[0,1], [1,2], [2,3], [3,0]]
```

Build:

* adjacency list
* adjacency matrix

**Gap**

Most people use libraries without understanding:

* adjacency list memory → `O(V + E)`
* adjacency matrix memory → `O(V²)`

Key realization:
Graph storage choice affects algorithm complexity.

---

### 2. Count Degree of Every Node

Given an **undirected graph**, compute degree of each node.

```
0--1
| /
2
```

**Gap**

Understanding difference between:

* **degree**
* **in-degree**
* **out-degree**

Important for directed graphs.

---


## Solution 1.  buld a graph from edge list

**Graph is for finding neighbors.**
**Storage must support fast neighbors lookup.**

For fast neighbor lookup we have two standard structures.

1. Adjacency list
2. Adjacency Matrix


### Undestand Input

```ts

Input = n (no of nodes) , like 4
const n = 4

const edges = [
  [0,1],
  [1,2],
  [2,3],
  [3,0]
]
// 4edges , edges.length


=======================

nodes = 0 1 2 3
edges = [u,v]
//edge between u and v node, u is from , v is to

```

### Adjacency List

What it stores

```
node --- > list of connected nodes.

eg:-

0 --> [1,3]
1 --> [0,2]
3 --> [1,3]
4 --> [2,0]

```

Space complexity 

```

O(E + V)

2E for undirected graph

```

good for sparce graph.

```ts
// build a empty graph with adjacency list

// step 1 build empty adjacency list (n = no of nodes)

function createAdjList(n){
   const adj=[];

   for(let i=0;i<n;i++){
      adj[i]=[]
   }
   return adj;
}


console.log(createAdjList(6)); //[ [], [], [], [], [], [] ]

// now each node have a list of his neighbor node

// step 2 , populate connection, insert edges.(till now we have nodes in memory)
// for un directed graph
//u → v
// v → u


// now we will take number of nodes = n , and information of their connection = edges , and push at each node , their connected node

function buildAdjList(n,edges){
   const adj=createAdjList(n);

   for(let [u,v] of edges){
      adj[u].push(v);  // in u node connection array , push its connected node.
      adj[v].push(u);  // for undirected graph , we can go from a to b and b to a , so connection should be in both node
   }

   return adj;
}

const n = 4

const edges = [
  [0,1],
  [1,2],
  [2,3],
  [3,0]
]

console.log(buildAdjList(n, edges)) //[ [ 1, 3 ], [ 0, 2 ], [ 1, 3 ], [ 2, 0 ] ]


```


### Adjacency Matrix (take O(n*n) space)


even for few edges entire matrix exists.


```
martix[u][v] = 1  // edge exist
martix[u][v] = 0  // no edge between u and v node
```


#### Representaion 

it is represented by 2d array 
But takes unwanted space if we store less node connection.

#### Space complexity 

O(V*V)

```ts


// matrix representaion of graph

// step 1 create empty matrix

function createMatrix(n) {
   const matrix = [];

   for (let i = 0; i < n; i++) {

      matrix[i] = [];

      for (let j = 0; j < n; j++) {
         matrix[i][j]=0; // all should be 0 at first
      }
   }

   return matrix;
}

console.log(createMatrix(6));

// [
//   [ 0, 0, 0, 0, 0, 0 ],
//   [ 0, 0, 0, 0, 0, 0 ],
//   [ 0, 0, 0, 0, 0, 0 ],
//   [ 0, 0, 0, 0, 0, 0 ],
//   [ 0, 0, 0, 0, 0, 0 ],
//   [ 0, 0, 0, 0, 0, 0 ]
// ]

// for one node out of n we have n, predefined space to store other connection, always.

// take O(nsquare) space


// insert edges into graph 
// for undirected graph 

//matrix[u][v] = 1
// matrix[v][u] = 1


function buildAdjMatrix(n,edges){
   const matrix=createMatrix(n);

   for(let [u,v] of edges){
      matrix[u][v]=1;
      matrix[v][u]=1; // for undirected graph
   }

   return matrix;
}

console.log(buildAdjMatrix(n, edges)) //[ [ 0, 1, 0, 1 ], [ 1, 0, 1, 0 ], [ 0, 1, 0, 1 ], [ 1, 0, 1, 0 ] ]

```

Comparison Table

| Operation         | Adjacency List | Adjacency Matrix |
| ----------------- | -------------- | ---------------- |
| Memory            | O(V + E)       | O(V²)            |
| Add Edge          | O(1)           | O(1)             |
| Check Edge        | O(degree)      | O(1)             |
| Iterate Neighbors | O(degree)      | O(V)             |



## Solution 2 


 **degree** :- no of edges connected to tht node., it is a structural metadata about a node.
 Indegree :- no of edges entering a node.
 Outdegree :- no of edges leaving a node.

But why we care about it.

to know no of connection  a node have
how much influence a node have to other node.
```ts

// calculate no of degree of each node, if we have given, no of node n and edges

function computeDegree(n,edges){
 let degree=Array(n).fill(0);
 for(let [u,v] of edges){
   degree[u]++; // we have to calculate the degree for both in undirected greaph
   degree[v]++; 
 }

 return degree;
}

console.log(computeDegree(n,edges)); //[ 2, 2, 2, 2 ]
//node 0--> has 2 connection


// in directed graph, edges have direction , so Now the concept of degree splits into two types.

function computeDirectedDegree(n, edges) {

  const inDegree = Array(n).fill(0)
  const outDegree = Array(n).fill(0)

  for (const [u, v] of edges) {
    outDegree[u]++
    inDegree[v]++
  }

  return { inDegree, outDegree }
}

// topological short require indegree , if indegree is 0, remove that node.
```




# 3. Check if Edge Exists

implement hasEdge(u,v)


```ts

// 3 implement hasEdge(u, v) if edge exist between this nodes, u to v

function hasEdge(adjMatrix,u, v){
return adjMatrix[u][v]==1;
}

console.log(hasEdge(buildAdjMatrix(n,edges),0,3))  //O(1)

// for adj list

function hasEdge2(adjList,u,v){
   return adjList[u].includes(v);
}

console.log(hasEdge2(buildAdjList(n, edges),1,3)) //O(n because traverse list linearly)

// solution  , create list with set so that we can use .has() to check if connection exist in O(n)



```

```ts


// create adj list with set to get value in O(1) with has()

function createadjListWithset(n){
    let adj=[];
    for(let i=0;i<n;i++){
        adj[i]=new Set();
    }
    return adj;
}

console.log(createadjListWithset(n))


function buildAdjlistWithSet(n,edges){
    let adj=createadjListWithset(n);
    for(let [u,v] of edges){
        adj[u].add(v);
        adj[v].add(u);
    }
    return adj
}


console.log(buildAdjlistWithSet(n,edges))


function  hasEdge(adjlistWithSet,u,v){
    return adjlistWithSet[u].has(v);
}


console.log(hasEdge(buildAdjlistWithSet(n,edges),1,3))

function dfsStackMatrix(adjMatrix){
   let visited=new Set();
   let result=[];
   let stack=[]
   visited.add(0);
   stack.push(0);

   while(stack.length){
    let node = stack.pop();
    result.push(node);

    for(let i=0;i<adjMatrix.length;i++){
      if(adjMatrix[node][i]==1 && !visited.has(i)){
         visited.add(i);
         stack.push(i)
      }
    }
   }

   return result;
}
```







