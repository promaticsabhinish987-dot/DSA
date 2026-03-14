## 1. BFS graph traversal


steps

1. start from node 0
2. make it visited
3. push it into the queue
4. repeat until queue become empty.

```ts


// implement BFS with queue

// for adj list

function bfs(graph){
let visited=new Set();
let queue=[0];
visited.add(0)
let result=[]

while(queue.length){
let node=queue.shift(); // get front node
result.push(node);

for(let children of graph[node]){
   if(!visited.has(children)){
      visited.add(children);
      queue.push(children)
}
}
}
return result;
}


console.log(bfs(buildAdjList(n, edges))); //[ 0, 1, 3, 2 ] (n)



// with adj matrix

function bfsMatrix(matrix){
   let n=matrix.length;
   let visited=new Set();
   let queue=[0];
   let result=[];
   visited.add(0);

   while(queue.length){
      let node=queue.shift();
      result.push(node);
      // we have n children so we visit all for each node if connected its 1
      for(let children = 0;children<n;children++){
      if(matrix[node][children]==1 && !visited.has(children)){
         visited.add(children);
         queue.push(children)
      }
      }
   }

return result
}

console.log(bfsMatrix(buildAdjMatrix(n, edges)));

// traverse the immediate friend , at each level, order may change of nodes.

```


DFS 

1. what about disconnected graph traversal and cyclic graph traversal?
2. DFS doesnt mean choose the first neighbor.
3. move to any visited neighbor.
4. continue deeper at each level.
5. backtrack when you visited all neighbor.



```ts


//DFS 
// it uses stack
//stack can be a recursive stack or explicit stack
// traverse from index 0
// recursive stack automaptically pop, unwind



function dfs(adjsList,start,visited,result){
visited.add(start);
result.push(start);
for(let children of adjsList[start]){
   if(!visited.has(children)){
      dfs(adjsList,children,visited,result)
   }
}
return result
}


function traverseDFS(adjsList){
let visited=new Set();
let result=[]
return dfs(adjsList,0,visited,result);
}

console.log("====================");
console.log(traverseDFS(buildAdjList(n, edges))) // adj list







console.log("====================");

function dfsAdjMatrix(adjMatrix,start,visited,result){
visited.add(start);
result.push(start);

for(let i=0;i<adjMatrix.length;i++){
   if(adjMatrix[start][i]==1 && !visited.has(i)){
  dfsAdjMatrix(adjMatrix,i,visited,result)
   }
}

return result;
}


function traverseAdjMatrix(adjMatrix){
const visited=new Set();
let result=[];

return dfsAdjMatrix(adjMatrix,0,visited,result)

}

console.log("==============DFS matrix===============");
console.log(traverseAdjMatrix(buildAdjMatrix(n, edges)));
// console.log(traverseAdjMatrix(buildAdjMatrix(n, edges)));




// stack solution 


// function dfsStack(adjList){
// let visited=new Set();
// let stack=[]
// let result=[];
// visited.add(0);
// stack.push(0)

// while(stack.length){
//    let node = stack.pop();
//    result.push(node)
//    for(let children of adjList[node]){
//      if(!visited.has(children)){
//       stack.push(children);
//       visited.add(children)
//      }
//    }
// }

// return result
// }

function dfsStack(adjList){

  const visited = new Set()
  const stack = []
  const result = []

  stack.push(0)
  visited.add(0)

  while(stack.length){

    const node = stack.pop()
    result.push(node)

    for(const child of adjList[node]){

      if(!visited.has(child)){
        visited.add(child)
        stack.push(child)
      }

    }

  }

  return result
}

console.log("dfsStack============");

// console.log(traverseDFS(dfsStack(n, edges))) // adj list
console.log(dfsStack(buildAdjList(n, edges))) // adj list

```
