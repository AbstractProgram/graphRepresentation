# Abstract Program representation in graphs برنامج مُـخَطَط 

An abstract program (or control graph or flowchart schema) depicts the control structure of the program, leaving much of the detail to be specified in an interpretation. To put it differently, it helps to distinguish between the sequence of processing steps and the algorithms applied at each step. This allows one to change the control module, for instance by reprogramming it or by treating the abstract program as the input of a supervisor program which does not change. The supervisor executes processing steps in the sequence  specified by the abstract program whose statements are read in as the data of the supervisor.

A concept of graph assisted programming, immediately executed graph. and an implementation module of such concept. Similar to program analysis graphs which displays all possible paths a program can take, only that it is used for runtime execution. A graph representing the control flow of the program.

###### Other terminology: _Abstract Program Graph / Executable Graph / Control Flow Graph / Graph-assisted program / Call Graph_


# Contents links: 

- [Specification for abstract program representation in graph datastructure](/documentation/specification/specification.md)
- [Graph concepts for extending the data structure](/documentation/concept/concept.md)
- [Graphical presentation of the graph data](/documentation/graphical/graphical.md)
- [Resource links](/documentation/resource.md)

# The role of Immediately Executed Graphs in program design:
Separates the program units or logic or functions from the control flow of program execution. Allowing to focus on developing needed functionality in separate modules, and then placing them in a graph to architect the interactions between them. Immediately Executed Graphs are like an integration layer and control flow for applications, where the program functions are considered abstract units that are referenced in the graph. Therefore it could be called Abstact Visual Programming, because it allows for coding the program with all language features, and integrating it in a visual manner.
- this is different to "a system could be modeled visually, the program code would be generated from the models, and any changes to the code could be pushed back to the model."

#### A program requires 2 structures:

    - Actions/procedures - performing calculations, etc.
    - Sequence - combines the actions to be executed on runtime. These are control structures, this is what the graph is intended to take the role of - sequences the actions of the program.
        subdevided into the following fundumental control structures: 
            - compound/sequence & parallelism: executed unconditionally. (a body of a function is considered a compound structure)
            - conditional/selection: if condition, if else, if else if, nested if else, switch case (multi-way selection).
            - loop/iteration: while, do while, for loop.
  
  _The loop and conditional structures could be represented in the graph, and the statements/steps/actions are represented in modules/functions/procedures/subroutine._

# Applications / Usages: 
Different applications may use this module:
- Build systems with package dependencies - make a topological sort to know which library should be built first.
- Creating pipelines to manipulate data. e.g.  [CI/CD pipelines](https://docs.gitlab.com/ee/ci/pipelines.html). 
    - Execution pipelines for code building.
    - Task/command runner with ability for synchronous or async execution.
- Task schedualing - which task should procede which one. 
- AST representation in NoSQL database.
- Template system for creating complex templates:
    _A better terminology whould be "document", as it may represent a collection of template & configs/parameters._
    Web documents (or documents) are composed of templates, represented as graphs. 
    Templates require a rendering algorithm/engine to deal with marked points in them, and produce rendered content. Templates can be nested and each nested template should be redered as well.
    Redering algorithm could involve:
        - Only replacement of marked points in the template.
        - Executionng of code logic and replacement of points with content produced by that code.
- Server request handling with on the fly middleware chain compisition.
- etc.
