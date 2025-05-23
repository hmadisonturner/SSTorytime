
# pathsolve

This is an experimental tool for finding contiguous paths between node sets.

For now, you can get started by trying the examples, e.g.
<pre>
$ cd examples
$ make
$ ../src/pathsolve -begin A1 -end B6 

mark% go run pathsolve.go -begin a1 -end b6 

 Paths < end_set= {B6, b6, } | {A1, } = start set>

     - story path: 1 * A1  -(forwards)->  A3  -(forwards)->  A5  -(forwards)->  S1
      -(forwards)->  B1  -(forwards)->  B4  -(forwards)->  B6

    Linkage process: -(+leads to)->  -(+leads to)->  -(+leads to)->  -(+leads to)->  -(+leads to)->  -(+leads to)-> . 


     - story path: 2 * A1  -(forwards)->  A3  -(forwards)->  A5  -(forwards)->  S2
      -(forwards)->  B2  -(forwards)->  B4  -(forwards)->  B6

    Linkage process: -(+leads to)->  -(+leads to)->  -(+leads to)->  -(+leads to)->  -(+leads to)->  -(+leads to)-> . 


     - story path: 3 * A1  -(forwards)->  A3  -(forwards)->  A6  -(forwards)->  S2
      -(forwards)->  B2  -(forwards)->  B4  -(forwards)->  B6

    Linkage process: -(+leads to)->  -(+leads to)->  -(+leads to)->  -(+leads to)->  -(+leads to)->  -(+leads to)-> . 


     - story path: 4 * A1  -(forwards)->  A2  -(forwards)->  A5  -(forwards)->  S1
      -(forwards)->  B1  -(forwards)->  B4  -(forwards)->  B6

    Linkage process: -(+leads to)->  -(+leads to)->  -(+leads to)->  -(+leads to)->  -(+leads to)->  -(+leads to)-> . 


     - story path: 5 * A1  -(forwards)->  A2  -(forwards)->  A5  -(forwards)->  S2
      -(forwards)->  B2  -(forwards)->  B4  -(forwards)->  B6

    Linkage process: -(+leads to)->  -(+leads to)->  -(+leads to)->  -(+leads to)->  -(+leads to)->  -(+leads to)-> . 

 *
 *
 * PATH ANALYSIS: into node flow equivalence groups
 *
 *

    - Super node 0 = {A1,}

    - Super node 1 = {A3,A2,}

    - Super node 2 = {A5,A6,}

    - Super node 3 = {S1,}

    - Super node 4 = {S2,}

    - Super node 5 = {B1,}

    - Super node 6 = {B2,}

    - Super node 7 = {B4,}

    - Super node 8 = {B6,}
 *
 *
 * FLOW IMPORTANCE:
 *
 *

    -Rank (betweenness centrality): 1.00 - B4,A1,B6,

    -Rank (betweenness centrality): 0.80 - A5,

    -Rank (betweenness centrality): 0.60 - S2,B2,A3,

    -Rank (betweenness centrality): 0.40 - A2,B1,S1,

    -Rank (betweenness centrality): 0.20 - A6,

</pre>

Or the adjoint path search:

<pre>

$ go run pathsolve.go -begin B6 -end A1 -bwd

</end>