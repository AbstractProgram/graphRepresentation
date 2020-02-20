# node extension / inheritance
_(subnode-supernode / node extension/inheritance)_

- Node that extends another node, in a way that any changes of the parent node is retained by the child node. (Newer nore: this seems to be a similar concept to the reroute node `extends` relationship).
- extends: will allow to create instances of another subgraph with different manipulation parameters.
- This is a better implementaiton for tree templates (extending an existing node tree without changing it) that used pathPointer or connectionPathSequence to reach the desired position for adding nodes inthe nested subtree/subnodes.
    - override connection - node that extends/inherit from another node and overrides a specific connection of the supernode, if the supernode connectionKey is removed then the overriding connection of the subclass will be ignored.
- Nodes that extend other nodes.
