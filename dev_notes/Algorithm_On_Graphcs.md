...menustart

 - [Algorithm On Graphs](#311ad33f7584ac17012490ce8852f7e8)
     - [Week1](#3c88e16de2066fa3ce3055a55a3e473b)
         - [Representing Graphs](#030495a245248ce0deed9c13f9576cd0)
         - [Exploring Graphs](#6d620d4a966ddb637a736ea4670b6782)
             - [Explore , starting from a Node](#78f63ae6b311ad607db08a56dd79649a)
             - [DFS](#c1bb62b63c65be3760b715faad0bdf8d)
         - [Connectivity](#9bd9d0ebc081bd74f5bef4e136bb1aed)
             - [Connected Components](#8a4d6dec35ad6f01d54531c509cf7d37)
         - [Previsit and Postvisit Orderings](#cb7d104acd7ef78260476fb96e632beb)
             - [Previsit and Postvisit Functions](#c190b4dd3a865a419b7d42ecdded4b14)
     - [Week2](#687c054c8abba26ef7b123d19d29bee7)
         - [Directed Acyclic Graphs](#7a53b8f5717213d05b5a349b30218b27)
             - [Directed DFS](#82842893b1046ac7ea43887a7d4c6c97)
             - [Cycles](#d3240659659cbfa93d781d1510717a66)
             - [DAGs](#1f979bae5ccfb6a193fde8d275355540)
         - [Topological Sort](#3f9c4755d1b2c530f17ce3f80a0fb896)
             - [Finding Sink](#2f1d4122555c30fa41c0390bd028ef60)
             - [TopologicalSort Algorithm](#7325cfd5224854fdee2a8cd7f046a1f6)
         - [Strongly Connected Components](#670190ac033bf942d8013492dc8f8b0f)
             - [Metagraph](#cd4755489eca8e682b00937d8e695b98)
         - [Computing Strongly Connected Components](#b3a7569c9a7d363bd55ee91cf45641f9)
             - [Sink Components](#80d29df79dc221a3cd1b8e554a6a3828)
             - [Finding Sink Components](#57c30fe3a2297ed1dfa107e753e2752e)
                 - [Reverse Graph Components](#509d136ac9a437456bbe67dd6b003890)
             - [Algorithm](#4afa80e77a07f7488ce4d1bdd8c4977a)
     - [Week4 Fastest Route](#81f77ede3fa5efdc0417b37ade6871a6)
         - [Naive Algorithm](#b7d8dac92149c1cdc7a8e81befdfb08b)
             - [Optimal substructure](#57942cdc67d1172d4aff18d81651ba69)
             - [Edge relaxation](#f1800f07c216d493e8e9ff2761ccfc33)
             - [Naive approach](#cc6cc606f58f43f4ddfafcf6043ba8ce)
             - [Correct distances](#b34e2384a9cd203b59f2660349fdb5fe)

...menuend


<h2 id="311ad33f7584ac17012490ce8852f7e8"></h2>

-----
-----

# Algorithm On Graphs

<h2 id="3c88e16de2066fa3ce3055a55a3e473b"></h2>

-----

## Week1

<h2 id="030495a245248ce0deed9c13f9576cd0"></h2>

-----

### Representing Graphs

 - Edge List
    - egdes: (A, B), (A, C), (A,D), (C,D) 
    - A,B,C,D are vertices
 - Adjacency Matrix
    - Entries 1 if there is an edge, 0 if there is not.
 - Adjacency List
    - For each vertex, a list of adjacent vertices.
    - A adjacent to B, C,D
    - B adjacent to A
    - C adjacent to A,D
    - D adjacent to A, C
    - can be implemented by a dictionary 
 
 - Defferent operations are faster in defferent representations
 - for many problems , want adjacency list .

Op | Is Edge? | List Edge | List Nbrs 
--- | --- | --- | ---
Adj. Matrix | Θ(1) |  Θ( &#124;V&#124;²) |  Θ(&#124;V&#124;)
Edge List | Θ(&#124;E&#124;) | Θ(&#124;E&#124;) |  Θ(&#124;E&#124;)
Adj. List | Θ(deg) | Θ(&#124;E&#124;) | Θ(deg)


<h2 id="6d620d4a966ddb637a736ea4670b6782"></h2>

-----

### Exploring Graphs

 - Visit Markers
    - To keep track of vertices found: Give each vertex boolean visited(v).
 - Unprocessed Vertices
    - Keep a list of vertices with edges left to check.
    - This will end up getting hidden in the program stack
 - Depth First Ordering
    - We will explore new edges in Depth First order. 

<h2 id="78f63ae6b311ad607db08a56dd79649a"></h2>

-----

#### Explore , starting from a Node

 - Need adjacency list representation!

```python
def Explore(v):
    visited(v) ← true
    for (v, w) ∈ E:
        if not visited(w):
            Explore(w)
```

<h2 id="c1bb62b63c65be3760b715faad0bdf8d"></h2>

-----

#### DFS

```python
def DFS(G):
    for all v ∈ V : mark v unvisited
    for v ∈ V :
        if not visited(v):
            Explore(v)
```

---

<h2 id="9bd9d0ebc081bd74f5bef4e136bb1aed"></h2>

-----

### Connectivity

<h2 id="8a4d6dec35ad6f01d54531c509cf7d37"></h2>

-----

#### Connected Components

 - Explore(v) finds the connected component of v
 - Just need to repeat to find other components.
 - Modify DFS to do this.
 - Modify goal to label connected components

```python
def Explore(v):
    visited(v) ← true
    CCnum(v) ← cc
    for (v, w) ∈ E:
        if not visited(w):
            Explore(w)

def DFS(G):
    for all v ∈ V mark v unvisited
    cc ← 1
    for v ∈ V :
        if not visited(v):
            Explore(v)
            cc ← cc + 1
```

---

<h2 id="cb7d104acd7ef78260476fb96e632beb"></h2>

-----

### Previsit and Postvisit Orderings

 - Need to Record Data
    - Plain DFS just marks all vertices as visited.
    - Need to keep track of other data to be useful.
    - Augment functions to store additional information

<h2 id="c190b4dd3a865a419b7d42ecdded4b14"></h2>

-----

#### Previsit and Postvisit Functions


```python
def Explore(v):
    visited(v) ← true
    previsit(v)
    for (v, w) ∈ E:
        if not visited(w):
            Explore(w)
    postvisit(v)
```

 - Clock
    - Keep track of order of visits.
    - Clock ticks at each pre-/post- visit.
    - Records previsit and postvisit times for each v.

![](../imgs/algr_on_graph_previst_clock_example.png)

 - Computing Pre- and Post- Numbers
 - Initialize clock to 1.

```python
def previsit(v):
    pre(v) ← clock
    clock ← clock + 1
def postvisit(v):
    post(v) ← clock
    clock ← clock + 1
```

 - Previsit and Postvisit numbers tell us about the execution of DFS.
 - Lemma
    - For any vertices u, v the intervals pre(u), post(u)] and [pre(v), post(v)] are either **nested** or **disjoint**.
        - nested: eg.  (1,8) , (2,5)
        - disjoint: eg.  (1,8) , (9,12)
    - that is , Interleaved (not possible) 
        - eg. ( 1, 8 ) , ( 5, 9  )

---

<h2 id="687c054c8abba26ef7b123d19d29bee7"></h2>

-----

## Week2 

<h2 id="7a53b8f5717213d05b5a349b30218b27"></h2>

-----

### Directed Acyclic Graphs

 - Directed graphs might be used to represent:
    - Streets with one-way roads.
    - Links between webpages.
    - Followers on social network.
    - Dependencies between tasks.


<h2 id="82842893b1046ac7ea43887a7d4c6c97"></h2>

-----

#### Directed DFS

 - Can still run DFS in directed graphs.
    - Only follow **directed** edges
    - explore(v) finds all vertices **reachable** from v.
    - Can still compute pre- and postorderings.

<h2 id="d3240659659cbfa93d781d1510717a66"></h2>

-----

#### Cycles

 - A **cycle** in a graph G is a sequence of vertices v1, v2, . . . , vn so that
 - (v1, v2),(v2, v3), . . . ,(vn−1, vn),(vn, v1) are all edges.
 - ![](../imgs/algorithm_on_graph_cycles.png)
 - Theorem
    - If G contains a cycle, it cannot be linearly ordered.

<h2 id="1f979bae5ccfb6a193fde8d275355540"></h2>

-----

#### DAGs

 - A directed graph G is a **Directed Acyclic Graph** (or DAG) if it has no cycles.
 - Theorem
    - Any DAG can be linearly ordered


<h2 id="3f9c4755d1b2c530f17ce3f80a0fb896"></h2>

-----

### Topological Sort


 - Last Vertex
    - Consider the last vertex in the ordering. It cannot have any edges pointing out of it
    - ![](../imgs/algorithm_on_graph_last_vertex.png)
 - Sources and Sinks
    - A **source** is a vertex with no incoming edges.
    - A **sink** is a vertex with no outgoing edges
        - ![](../imgs/algorithm_on_graph_sinks_in_dag.png)

<h2 id="2f1d4122555c30fa41c0390bd028ef60"></h2>

-----

#### Finding Sink

 - Question: How do we know that there is a sink?
 - Follow path as far as possible v1 → v2 → . . . → vn. Eventually either:
    - Cannot extend (found sink).
    - Repeat a vertex (have a cycle).

<h2 id="7325cfd5224854fdee2a8cd7f046a1f6"></h2>

-----

#### TopologicalSort Algorithm

```python
TopologicalSort(G)
    DFS(G)
    sort vertices by reverse post-order
```


<h2 id="670190ac033bf942d8013492dc8f8b0f"></h2>

-----

### Strongly Connected Components

 - Two vertices v, w in a directed graph are **connected** if you can reach v from w and can reach w from v.
 - Theorem
    - A directed graph can be partitioned into **strongly connected components** where two vertices are connected if and only if they are in the same component.
    - ![](../imgs/algorithm_on_graph_SCC.png)

<h2 id="cd4755489eca8e682b00937d8e695b98"></h2>

-----

#### Metagraph

 - We can also draw a **metagraph** showing how the strongly connected components connect to one another 
    - ![](../imgs/algorithm_on_graph_metagraph.png)
 - Theorem
    - The metagraph of a graph G is always a DAG.
 
How to compute the strongly connected components of a graph. ?


<h2 id="b3a7569c9a7d363bd55ee91cf45641f9"></h2>

-----

### Computing Strongly Connected Components

 - Problem
    - Input: A directed graph G
    - Output: The strongly connected components of G. 

<h2 id="80d29df79dc221a3cd1b8e554a6a3828"></h2>

-----

#### Sink Components

 - Idea: 
    - If v is in a sink SCC, explore(v) finds vertices reachable from v. This is exactly the SCC **of v**.
        - 因为SCC的性质，无论你从SCC中的任何一个点node开始，你都是 explore 真个SCC
    - that also means, you will get different SCC, if you start from different node.
 - Need a way to find a sink SCC.
    - why ? 
    - if you start from a source SCC, you many visit the whole graph, it won't help you.


<h2 id="57c30fe3a2297ed1dfa107e753e2752e"></h2>

-----

#### Finding Sink Components

 - Theorem
    - If C and C' are two strongly connected components with an edge from some vertex of C to some vertex of C' , 
    - then largest post in C bigger than largest post in C'.
 - Conclusion
    - The vertex with the largest postorder number is in a source component!
    - Problem: We wanted a sink component

<h2 id="509d136ac9a437456bbe67dd6b003890"></h2>

-----

##### Reverse Graph Components

 - Let Gᴿ be the graph obtained from G by reversing all of the edges.  
    - ![](../imgs/algr_on_graph_reverse_graph.png)
 - Gᴿ and G have same SCCs.
 - Source components of Gᴿ are sink components of G.  
 - Find sink components of G by running DFS on Gᴿ .
    - The vertex with largest postorder in Gᴿ is in a sink SCC of G.

<h2 id="4afa80e77a07f7488ce4d1bdd8c4977a"></h2>

-----

#### Algorithm

```python
def SCCs(G):
    run DFS(Gᴿ)
    for v ∈ V in reverse postorder:
        if not visited(v):
            Explore(v)
            # mark the learder node as that SCC
            mark visited vertices as new SCC
```

 - Runtime
    - Essentially DFS on Gᴿ and then on G.  
    - Runtime O(|V| + |E|).


<h2 id="81f77ede3fa5efdc0417b37ade6871a6"></h2>

-----

## Week4 Fastest Route 

<h2 id="b7d8dac92149c1cdc7a8e81befdfb08b"></h2>

-----

### Naive Algorithm

<h2 id="57942cdc67d1172d4aff18d81651ba69"></h2>

-----

####  Optimal substructure

 - Observation
    - Any subpath of an optimal path is also optimal.
 - Proof
    - Consider an optimal path from S to t and two vertices u and v on this path. If there were a shorter path from u to v we would get a shorter path from S to t.
    - ![](../imgs/algr_on_graph_substructure_proof.png)
 - Corollary
    - If S → . . . → u → t is a shortest path from S to t, then d(S,t) = d(S, u) + w(u,t) 
        - u is the previous node on that path
        - w means weight



<h2 id="f1800f07c216d493e8e9ff2761ccfc33"></h2>

-----

#### Edge relaxation

 - dist[v] will be an upper bound on the actual distance from S to v.
    - it store our **estimation** distance from the origin to this particular node v.
 - The edge relaxation procedure for an edge (u, v) just checks whether going from S to v through u improves the current value of dist[v].

```python
def Relax((u, v) ∈ E):
    if dist[v] > dist[u] + w(u, v):
        dist[v] ← dist[u] + w(u, v)
        prev[v] ← u
```

 - if both dist[v]=∞ and dist[u]=∞ , and w(u,v)=5, should the edge(u,v) be relaxed ?
    - NO! 



<h2 id="cc6cc606f58f43f4ddfafcf6043ba8ce"></h2>

-----

#### Naive approach

```python
def Naive(G, S):
    for all u ∈ V :
        dist[u] ← ∞
        prev[u] ← nil
    dist[S] ← 0
    do:
        relax all the edges
    while at least one dist changes
```

<h2 id="b34e2384a9cd203b59f2660349fdb5fe"></h2>

-----

#### Correct distances

 - Lemma
    - After the call to Naive algorithm all the distances are set correctly.





