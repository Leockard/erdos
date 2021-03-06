Title: Adjacency Lists
Category: Representations
Date: 2016-06-26
Position: 1
Summary: Graphs can be represented by lists defining the adjacencies of every node.
Disqus_identifier: 2f2822f5-graphs-can-be-represented-by-lists-defining-the-adjacencies-of-every-node

{% include "context_header.md" %}

In the previous problems, we read a graph from a file which listed each
edge in one line. Now, we are going to represent a graph in a different,
more succint way. For every node `u`, we want to create a list defining the
nodes adjacent to `u`.

Adjacency List[](#adjacency-list)
: Given a node `u`, the **adjacency list** of `u` is a list of all nodes
that `u` is connected to. If the graph is directed, the list contains
either all the nodes connecting to `u`, or all the nodes receiving edges
from `u`, but not both.

Consider a graph with $n$ nodes and $m$ edges. In our previous
representation, the file contained one line to define the number of nodes
and edges, $n$ and $m$, and one line for each edge, $m + 1$ lines in
total. In the new representation, our file will still need one line for $m$
and $n$, but only $n$ lines will follow, one for each node's adjacencies.

As we [saw before]({filename}/challenges/graphs/density.md), an undirected
graph can hold up to $n(n+1)/2$ edges in total. This means that, if the
graph is moderately dense, we will have $n < m \approx n(n+1)/2$, and
therefore, our new graph representation will in general have fewer lines
than the previous one.

{% include "problem_header.md" %}

For this challenge, you need to read a file representing a graph in the
previous, long, format, and output it in the new, shorter one.

The input is a file where the first line contains two integers, $n$ and
$m$, defining the number of nodes and edges, respectively. The next $m$
lines each contain two integers, representing two nodes that are joined by
an edge. Assume undirected edges.

Write $n$ lines, where each line holds a list of space-separated integers,
representing the adjacencies of every node. As before, assume that nodes
are labeled from `0` to `n-1`. Write the lines in ascending order of node
label, e.g., the first line of the output should contain the adjacencies of
node `0`, the second line should contain the adjacencies of node `1`,
etc. Print each adjacency list in ascending order.

{% include "input_header.md" %}

```
4 4
0 1
0 2
1 3
3 0
```

{% include "output_header.md" %}

```
1 2 3
0 3
0
0 1
```

{% include "solutions_header.md" %}

The solution to this challenge is hosted on
[Github](https://github.com/leotrs/erdos/blob/master/solutions/reprs/adjlist.py).
