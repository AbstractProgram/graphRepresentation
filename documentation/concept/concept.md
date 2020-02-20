# Graph Concepts: 
_Graph / Node Relationship Graph / Nested Unit Tree / Trees / Herarchies / Nested Treemaps_

- Graphs can represent any collection of objects having some kind of pairwise relationship (conveying of relational information). Many realworld systems and problems can be modeled using a graph.
- Generally speaking, there isn't really a concept of mutable state in abstract algebra (of which Graph Theory is a part). Only existence/non-existence. Graphs have a static state, and cannot be mutable in common Graph Theory concepts. Any 'change' indicated would be another distinct graph.

### Definitions: 
- **Multiedge/Parallel edges**: Multiple connections between 2 verticies/nodes.
- **Self edges**: Loop allowed graph.
- **Node** _(Vertex / ReusableNestedUnit / Unit)_ - e.g. a node references a single data item that should be used or consumed in specific way. 
- **Edge** _(Relationship / Connection)_ - Edges could be directed with 'ingoing'/'outgoing' direction.
    - Source/destination nodes - are nodes that make up the edges of a connection. _Or start/end nodes_
    - connectionKey / pathPointerKey
    - weighted graph: edges have values.

# Other features missing in graph databases:
- Support for graph document store (nested fields as node properties), which Neo4j said they were looking into it, but it seems they won't apply it as it "encourages bad graph modeling".

### In-memory storage structure & requirements:
- Example of algorithms / data structures for graph storage: 
    - Adjancency Matrix representation - using matrix array to store edeges for nodes. 
    - Adjacency list
- Data items to be processed are stored as part of the graph. Each data item can be referenced/connected by multiple nodes (isn' strictly boudn to a single node).
- Handling multiple graphs in memory which are separated and traversals or caching are not shared. e.g. a graph for Middleware, another for Condition, Template, etc.
