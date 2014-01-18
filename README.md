`kruskal.js`
==========

A simple implementation of Kruskal's algorithm to find the minimum spanning tree of a graph.

This implementation needs only the edge list, not the whole adjacency matrix, so could be more
efficient for sparser graphs.

[Kruskal's Algorithm](http://en.wikipedia.org/wiki/Kruskal%27s_algorithm)


Usage
=====

Here is an example of finding the minimum spanning tree given in the example directory:

![alt tag](https://raw2.github.com/abetusk/kruskal.js/master/example/kruskalExample.jpg)

See 'example/example.js' for a full example.  Here is an abridged version:

    // vertices hold data that will be used in the distance metric function
    var verticies = [ 
      [0.38503426988609135,0.5090362404007465],
      [0.19520984776318073,0.786977760726586],
      ...
    ]

    // edges are vertex position pairs
    var edges = [ 
      [8,6], [8,12], [6,12], ...
    ];

    function metric_dist( a, b )
    {
      var dx = a[0] - b[0];
      var dy = a[1] - b[1];
      return dx*dx + dy*dy;
    }

    var Kruskal = require("../kruskal.js");
    var edgeMST = Kruskal.kruskal( vertices, edges, metric_dist );

    // Print minimum spanning tree
    for (var ind in edgeMST)
    {
      var u = edgeMST[ind][0];
      var v = edgeMST[ind][1];

      console.log( verts[u][0] + " " + verts[u][1] );
      console.log( verts[v][0] + " " + verts[v][1] );
      console.log("");

    }



License
=======
GPLv3

