# Specification: 
- Graph representation of the program's control flow, as instructions directed to the traverser.
- **Graph type**: Usually the Graph that is used is Directed, Acyclic or cyclic, Weighed, Sparsed _(few edges in comparison to complexity analysis)_, & immediately-processed graph (created to be processed during traversal).

# Executable Graph Traversal
- similar concept to abstract semantic graph only intended for execution.
- Abstract Program Graph: The program is "abstract" in the sense that it deals with abstractions of a lower level program.
- Executable Graph
An immediately executed graph traversal, where nodes instruct on performing actions in customizable implementations. It hands back control to the client allowing to manipulate the traversal propagation and node data processing logic.
- On each traversal a node data can be processed/executed, taking into account precedence constraints.
- Created for graph where the node's data is the main subject, & traversal rules/configs of a relational graph, are used to decide on the way to deal with multiple processings of the nodes's data - i.e. processing logic & combination of results.
- Immediately Graph Traversal: allows to move the control flow logic of the program to an in-memory graph. In addition to defining the flow of program, it controls the integration logic/algorithm between the procedure/actions of the program - which could be used for different use cases. Describing the algorithm used to handle processes/steps/procedures of the program.
- Graphs allow to create a visual layer for the program control flow, and allow realtime changes to a running program, in which different presentation elements could be defined to display the program in a sumerized compact manner. The visual representation doesn't necessarily represent the exact graph database structure, rather it adds a level of abstraction.
- There is one node for each abstract procedure in the program. 
- highly abstract software language
- Eagerly executed, promise and iterators based.
- The graph traversal module is callback & Proxy based, which hands overcontrol to concrete functions and returns an iterator of results that the proxy implementation can decide what to do with. Permitting highly configurable traversal behavior.
- The core code of the module is separate from the plugin implementations and largely involved in the integration between the plugin implementations.

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
