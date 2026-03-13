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
