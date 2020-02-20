# Graph layering and classification: 
Graph databases do not support subgraphs or multilayers, which will require a programmatic abstraction to implement over the database.

- Classifying graphs into groups that may overlap.
- Layering graphs allowing connections between them, kind of aggregating connections according to specific needs. 
- multi-layer views (Subgraphs) of a target unit/node. 
  - Changing representation of the graph according to the dimension model used with the target node. e.g. timescale dimension, where the target node is and entity and restricted to events relationship.
  - representing multiple units in relations to each other, or classified by one another. Diffenent algorithms to merge nodes into view: mutually inclusive, nested / included by one another, side by side, etc.
  - Cross relationships can be applied between the graph layers. 
- Allowing to restrict to a target relationship types.
