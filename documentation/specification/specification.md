# Specification: 
- Graph representation of the program's control flow, as instructions directed to the traverser.
- **Graph type**: Usually the Graph that is used is Directed, Acyclic or cyclic, Weighed, Sparsed _(few edges in comparison to complexity analysis)_, & immediately-processed graph (created to be processed during traversal).

## Graph Elements:
The graph traversal chain (a single recursive traversal call) could traverse nodes in an independent way, where each node traversal awaits only it's own nested and siblings traversals, or it could be executed in a manner where each node can control the entire chain iterator and await any other node, even if it is not nested or part of the same port group of nodes.

- **Stage nodes**: are node traverser positions that guide the traverser to perform actions involving adverse effects or returning results.
- **Procss nodes** _/ DataItem / Record node_: are responsible for data process, performing actions and optionally returning a result. Each Process node uses it's own properties and traversal information to result in an action/effect, depending on the implementation being used.
Execute will process the node taking into consideration graph data and parameters, and Pipe will allow for further processing of the result of the main process.
    - a node as a resource of data to be executed by a processing implementation. e.g. { Type: ‘reference’, importModuleName: ‘’, processNode: ‘’ }
- **Resource node**: Resource record. The RESOURCE relationship holds the context type `filsystemReference` or `applicationReference`, and the resource node could be of different types following a convention used by the app.
    e.g. A File node that has { type: 'file', path: '' } with a resource relation context of `filesystemContext`, as the File node holds references to a specific path & module in the filesystem context. Other RESOURCE nodes could be references to the variables in the application logic context.

#### Classification of node types/labels: 
- Entrypoint/Root nodes: are nodes that can be traversed, and provided as an entrypoint to the graph. 
    _Stage, Reroute_
- Nested/Supplement nodes/Instruction nodes: are nodes which are nested to other nodes and provide features for the traversal. The traversion could not start from these nodes. 
    _Port, Configuration, Process_
- Reference/Reroute nodes: 
    _Reroute, Switch_

## Programming concepts implemented in the graph:

- Command execution in sequence and in parallel.
- Conditionals / logical operations: 
    - Switch multiple cases
    - Switch boolean cases
    (Both of the above could be represented as a special type of Stage node) 
    - AND logical operator
    - OR logical operator 
    (Both of the above can be represented as a propagation implementation in a port with several next stages traversed.)
- Nodes type depict traversal instruction: 
    - Each node gives instructions to traverser and returns a specific return type that is used in the integration layer (core layer) of the graph traversal module.
    - Each node type has plugable implementations.
    - Nodes have connections which determine the traversal propagation implementation. 
- Ports control the traverser propagation order to the next Stage nodes (propagation control), in addition to grouping the Stages into meaningful groups that could be used in the aggregator implementations.
    - Selective/restricted port/Channel concepts: a port/Channel that propages according to a set of rules or conditions. Ports can be chained to further filter the Stages in the returned iterator.
        - Iteration limit: Each port/Channel returns an iteration of nodes. A property on the node called 'iterationLimit' could be used to limit the number of returned nodes during iteration next calls. `∞` (Infinity in javascript) value could be representing an unlimited number of iterations, while a number is used to specify the amount of iterations returning a node before finishing the iterator with marking it as done.
        - Conditional progation / Switch case concept - Allows traversing the grpah selectively, picking the nodes required for the next traversal using conditions or logical decision making algorithms. e.g. Switch Case port where it checks if a condition is met, then picks a single matching node and returns it in the iterator.
- **Lazy execution during traversal** - on each node reached the traversal could be halted or continued and a processing implementation could be executed before continuing traversing or have a side effect during execution.
- **Node & edge filter** - some implementations can filter specific nodes through conditions.
- Dynamic traverser configuration - The traverser in each current position can change behavior according to the evaluation of the node. i.e. the traverser may change modes controlled by each stage node. Stage nodes could be also thought as `traverser controller` nodes that give the traverser in the current position, instrcutions to follow and changes it's behavior. 
