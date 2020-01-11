# Graphs

Created By: Chris Trinh
Last Edited: Dec 24, 2019 5:01 PM

- What is a graph?
    - Any collection of nodes and edges
    - Unlike trees, they may lack a root node, have cycles, and an unlimited number of edges leaving the node
- Make a mental model of a GraphNode class
    - Graph Nodes have unlimited neighbors in an array

        class GraphNode {
            constructor(val) {
                this.val = val;
                this.neighbors = [];
            }
        }
        
        let a = new GraphNode('a');
        let b = new GraphNode('b');
        let c = new GraphNode('c');
        let d = new GraphNode('d');
        let e = new GraphNode('e');
        let f = new GraphNode('f');
        a.neighbors = [b, c, e];
        c.neighbors = [b, d];
        e.neighbors = [a];
        f.neighbors = [e];

- What is an adjacency matrix?
    - Used to represents connecting nodes in a graph. Columns and rows are identified by the values and the array value( true/false) represents whether it is connected or not.

        let matrix = [
        /*          A       B       C       D       E       F   */
        /*A*/    [true,  true,   true,   false,  true,   false],
        /*B*/    [false, true,   false,  false,  false,  false],
        /*C*/    [false, true,   true,   true,   false,  false],
        /*D*/    [false, false,  false,  true,   false,  false],
        /*E*/    [true,  false,  false,  false,  true,   false],
        /*F*/    [false, false,  false,  false,  true,   true]
        ];

- What is an adjacency list?
    - Hash map matrix that has each node as a key and its adjacent nodes as a value in the array.
    - Uses at most n^2 space
- What is a weighted graph vs unweighted?
    - Weighted graphs has edges that contain values or information
- When would we use weighted graphs?
    - Allows the capture of real world scenarios to associate the cost of moving from one entity to another

    Say each node is a city and each weight is the flight cost between two cities:

    - How can we want to travel from city `a` to `e` and save as much money as possible?
    - How can we travel from city `a` to `e` with as little stops in between?
- What does Dijkstra's Algorithm do?
    - Finds the shortest path between two nodes in a graph

- Explain in code, Dijkstra's algorithm
- What is the time complexity of Dijkstra's?

    O(n^2) where n is the number of nodes in the graph

    - n is the number of nodes in the graph
    - The while loop will iterate once for every node, so in isolation it contributes O(n) steps
    - The `minDistanceNode` helper iterates through every unvisited node, so in isolation it contributes O(n) steps
    - The helper call is nested in the while loop, so combined they contribute **O(n2)**
    - Over the course of the whole algorithm, the inner for loop will iterate once for every edge of the graph. The number of edges in a graph of n nodes is guaranteed to be less than n. So this loop does not contribute to the overall complexity.
- What is a heap?
    - A binary tree but not a binary search tree
    - partially ordered data structure where the maximum (max heap) or minimum (min heap) be the root of the tree
- What is a max heap invariant?
    - Given any node, its children must be less than or equal to the node
    - There is no guarantee order among siblings in a heap
- What is a complete tree?
    - Every complete tree is a balanced tree, but not every balanced tree is complete
    - All levels have maximal number of nodes except the bottom level
    - Bottom level of nodes has nodes filled to the far left as possible
- When wold you use a heap?
    - When problems ask you to partially sort data
        - calculating the smallest or largest n numbers of a collection
    - eg. Find the largest 5 numbers in an array in linear time
- What is a general conceptualization to implement a heap?
    - Use an array and each index of the array will represent a node with the root being at index 1. Index 0 will not be used so that the math works out a little better
    - index `i` represents a node in the heap
    - the left child of node `i` can be found at index `2 * i`
    - the right child of code `i` can be found at index `2 * i + 1`
- Explain a MaxHeap class and its major functions

        class MaxHeap {
            constructor() {
                this.array = [null];
            }
        
            getParent(idx) {
                return Math.floor(idx / 2);
            }
        
            getLeftChild(idx) {
                return idx * 2;
            }
        
            getRightChild(idx) {
                return idx * 2 + 1;
            }
        
            // ...
        }

- How does insertion work in a heap and what is siftUp?
    - We insert data into a heap at the bottom leaf node at the far left as possible but sometimes the value could be greater than the parent
    - Sift up is when we continuously swap the parent with the child until we meet the property that states that a node must be greater than its children
- Translate the insertion conceptualization above into array operations
    - push the new value into the end of the array and swap until the heap property is true.
    - Code

            class MaxHeap {
                // ...
                insert(val) {
                    // add the new node to the bottom level, far-left 
                    this.array.push(val);
                    
                    // then, sift that value up the heap to restore heap property
                    this.siftUp(this.array.length - 1);
                }
                
                siftUp(idx) {
                    // if the node is already at the root, there's no further we can sift up
                    if (idx === 1) return;
                    
                    let parentIdx = this.getParent(idx);
            
                    // if the node is bigger than it's parent, we are breaking heap property...
                    if (this.array[parentIdx] < this.array[idx]) {
                        // so swap the node with it's parent
                        [ this.array[parentIdx], this.array[idx] ] = [ this.array[idx], this.array[parentIdx] ];
            
                        // and continue to sift it up recursively
                        this.siftUp(parentIdx);
                    }
                }
                // ...
            }