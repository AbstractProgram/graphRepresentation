# Reroute / Reference nodes:
_Reusable Subgraph Template / Subgraph template node / Node reference / or will be refered shortly as “subgraph”_

- A part of a directed graph with a root node, representing the entrypoint to the subgraph. The subgraph could be referenced by nodes in the graph, and could be extended by other “subgraph templates”. Extending a subgraph allows to insert additional nodes to the subgraph in desired positions or paths (traversal chain or sequence of edges). Much in the sense of externally mapping the same target graph into other different graphs, without changing the original target graph. 
- A function which takes a graph (subgraph) as an input and maps to another graph dependent on that input.
- Nodes that are treated as a placement for other nodes (referencing other nodes). Reroute node also allows to divide a graph into subgraphs by pointing to a root node  and storing information about the subgraph.

### Placement references / Node placement in subgraph / Additional children/edges conecpt:
- A way to insert nodes into a subgraph. 
- Marks an entrypoint to a graph, and allows for adding external nodes to it. 
- Where a graph can be used (traversed) through a proxy without manipulating it directly. Related to insertion points concept - adding nodes in insertion points in the graph. Each edge has a position/arrangement property that defines the order and a placement (in case it is an additional connection to be traversed). e.g. `pathPointerKey`/`connectionKey` could be an additional conenction that is added to the existing conenctions for traversal purposes.
- Where the reference nodes are meant to be placed into a target subgraph (e.g. added into the next relatioship of a stage).

### External reference: 
- Holding reference information to a node that exist in another location, when imported to an existing graph database, a connection will be created to the referenced graph.
- It may also create a new interface to the target graph, where it specifies possible connection positions or ports to map it to the external graph.
- Referencing nodes from an external source, that will be available when imported to the database. 

### Replacement reference / Node replacement positions: 
- Replaces the current position with another node.
- Where the position node is ment to be replaced with the target node (referenced node).

___

# Resources: 
- https://www.worldscientific.com/doi/abs/10.1142/9789812384720_0001