Title: Triangles and Transitivity
Category: Measures
Date: 07/25/2016
Position: 20
Summary: Triangles describe network transitivity.
Disqus_identifier: d2615dde-triangles-describe-network-transitivity


{% include "context_header.md" %}


When two nodes in a network are joined by an edge, we think of them as
sharing a relationship of some sort. Two people on a social network are
joined by an edge if there is a friendship between them. Two websites on
the WWW are joined by an edge if one of them links to the other. This
relationship is in fact what defines the graph, as it dictates which edges
are present.

Just as we study the concrete objects that make up the graph, its nodes and
edges, we can study this relationship too. One way to do it is by measuring
its level of transitivity. In the following, we write `u ~ v` to mean that
nodes `u` and `v` are adjacent.

Network Transitivity[](#network-transitivity)
: Network **transitivity** measures the extent to which `u ~ v` and `v ~ w`
imply `u ~ w`.

Read out loud, transitivity keeps track of the cases when, for three nodes
`u`, `v`, and `w`, if there are at least two edges among them, then there
is also a third one. In the social network example, three nodes with two
edges among them means three different people with two
friendships. Therefore, network transitivity in a social network measures
the cases when one person's friends are also friends to each other.

{% from 'img_desc.html' import img_desc %}
{{ img_desc("triangles.svg", "Are my friends themselves friends?")}}

As the picture should make clear, transitivity simply measures the
occurrence of triangles in a network. If the network relation is highly
transitive, then many of its *connected triads* will form *triangles*.

Connected triad[](#connected-triad)
: If three nodes `u`, `v`, and `w` have at least two edges among them, they
are called a **connected triad**.

Triangle[](#triangle)
: A **triangle** in a graph is a triad of nodes where each one is
connected to the other two. Every triangle is a connected triad.


{% include "problem_header.md" %}


For this challenge, you need to count the number of triangles in a network.

The input is a file which contains one line with a single integer $n$, the
number of nodes in the network. The following $n$ lines each contain one
row of the adjacency matrix of the network, where each entry is separated
by a space.

Output the number of triangles in the network.

Hint
: Since you will be given the adjacency matrix, think how it would reflect
the presence of a triangle. If `u`, `v` and `w` form a triangle, what can
be said about the entries $a_{uv}$, $a_{vw}$, $a_{wu}$ of the adjacency
matrix?


{% include "input_header.md" %}

```
10
0 1 1 0 1 0 0 1 0 0
1 0 0 0 0 0 1 1 1 0
1 0 0 1 0 0 0 0 1 0
0 0 1 0 0 0 1 0 1 1
1 0 0 0 0 0 0 0 1 0
0 0 0 0 0 0 1 0 0 1
0 1 0 1 0 1 0 0 0 0
1 1 0 0 0 0 0 0 0 0
0 1 1 1 1 0 0 0 0 0
0 0 0 1 0 1 0 0 0 0
```

{% include "output_header.md" %}

```
2
```


{% include "solutions_header.md" %}


[Solution](https://github.com/leotrs/erdos/blob/master/solutions/measures/triangles.py).


{% include "question_header.md" %}


1. In an undirected network, a triad of nodes can only have one, two or
   three edges among them. What patterns can a triad form in a directed
   network? Discuss the meaning of these patterns in a directed social
   network (like Twitter), and the WWW.

2. How many patterns can four nodes form in a directed or undirected
   network? Would counting the occurrence of these patterns also be useful
   as a measure for network transitivity?


{% include "answers_header.md" %}

The *patterns* formed by *undirected* graphs with three and four nodes can be
found [here](https://oeis.org/A000088/a000088a.gif).

The *patterns* formed by *directed* graphs with three nodes are
[here](http://mathworld.wolfram.com/SimpleDirectedGraph.html).

The *number* of *undirected* graphs with $n$ nodes can be found
[here](https://oeis.org/A000088).

The *number* of *directed* graphs with $n$ nodes can be found
[here](https://oeis.org/A000273).


1. The patterns formed by three nodes in a directed social network
   represent all the possible distinct ways that three people can follow
   each other, without taking into account who follows whom.

2. The occurrence of 4-vertex patterns is less useful for measuring
   transitivity, as its definition as a measure involves three nodes, not
   four.  The occurrences of these patterns might or might not be useful in
   measuring other graph properties.
