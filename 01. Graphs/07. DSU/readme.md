# Disjoint Set and Union

- A graph can be visualized a series of node sets. These sets may or maynot be connected . Like the image below. 

- A disjoint-set has mainly 2 operations `union` and `find`.

- In `Union` operation we take 2 disjoint sets and merge them, in the below example joining nodes `2` and `4` would merge the two sets.

- In `Find` operation we have to find root node of a given node.

- In both these operations the whole game becomes about `root` nodes. For each node we define a root node for example in the image below `0,9,4,5` can be considered root nodes for other nodes in the graph. 

- We can figure if two nodes belong to same graph if `Root(Node1) == Root(Node2)` i:e if root of two nodes are same then they must belong to same set.

- The union problem can be solved trivially by defining `node2.Root = node1`. This is not an optimised way though.

- <img width="640" alt="Screenshot 2023-03-24 at 10 23 46 AM" src="https://user-images.githubusercontent.com/122880563/227427802-80b76a64-60e4-47f4-93e8-a48fe1d7b6bd.png">

## Representation

- The above Graph can be represented as `[0,0,0,1,4,5,5,5,4,9]` where the `array index` is the node and `array value for the index` is the root.

- To find root of a node `i` we have to do something like. 
```python
while arr[i] != i :
  i=arr[i]
```

- To union two nodes n1 and n2 we have to set root of n2 to n1
 
```python
rootN2 = find(n2)
arr[rootN2]= n1
```


## Flavors of Disjoint set and union

### Quick Find

- This is optimised for find. In quick-find time-complexity of find is `O(1)`.

- This is like a flattenned graph where each node is directly connected to the root. So we dont have to traverse multiple nodes to find root like in the find algo mentioned above. It can be represented as (for node n)
```python
def find(node,arr):
  return arr[node]
  
```

- Union is not optimised. For each union we have traverse through the array and mark root of each node in the joined set to root of current set. For union worst case can be `O(N)` where N is number of nodes.


### Quick Union

### Union by Rank



