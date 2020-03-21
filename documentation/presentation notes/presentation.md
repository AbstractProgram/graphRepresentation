# Presentation: max 3 mins. 

| Points        | Scene           |
| ------------- |:------------- |
| 1 | External with screens in the background.
| 2-4 | Title with an example control flow graph.|
| 5 | Side-by-side text and visual programming approaches |
| 6-7 | Graph with arrow pointing to an interpreter |
| 8-9 | Supervisor program (traverses, interprets, & executes) with an inpur program graph and used interpretation algorithms. |
| 10-13 | Browser screencast of repositories |


## Points: 
_1. introduction about the project:_ 
- about presentation. 
- Closest term "abstract program"

_Explain the concept:_

2. High-level Graph-based programming.
3. Visual & text-based approaches integration.
4. Represent part of a program in graph. 
5. Use existing text-based development tools and incrementally build graphical toolset. 
6. Explain abstract term & interpreter of the program. 
7. Split sequence from logic.

_How does it work in a nutshell ?_

8. Supervisor program - interpret and execute.
9. Interpretation algorithms for different use cases. 

_Present repositories:_

10. Specification & implementation repos.
11. Graph theory concepts repository. 
12. Supervisor program Implementation of the spec.
13. Use cases. 
14. Graphical representation designs.
15. Technical implementation details and architecture.
16. pros & conss

___

## Actual script: 
بِسْمِ اللَّـهِ الرَّحْمَـٰنِ الرَّحِيمِ

``` 
This is an overview of abstract program concept. A project I've been working on, allowing to execute programs represented as graph data strutures. 
I came up with my own concept of how I envision programming to be, instead of writting code, the developer would deal with visual abstractions and the program would be represented as a graph which would be compiled directly into a low level language. 
Now, there is always place to improve and rethink the concept, only that it would require deeper knowledge and a lot of time to implement. So I ended up combinning both text-based programming with graph-based programming.

___

Abstract program is a high-level graph-based program which is interpreted on runtime by a supervisor program. 
This Graph program concept creates an additional layer of abstraction, where it doesn't deal with specifics of the algorithms, instead only describing the control flow of the program, hence the term abstract program. 
In other words, it allows for splitting up the sequence of steps from the logic processed on each step. 
This is where a supervisor program comes into place. The supervisor program is provided with the graph data as input, in which it interprets the graph on-the-fly, and executes the steps in the graph during each traversal. The graph can reference external resources & functionalities which will be used during interpretation.
For example, functions maybe referenced in the graph by name, and the interpreter program would decide how to resolve & call the functions in the graph. 
So, the same graph can be executed with different interpretation algorithms to match specific use-cases.
 
I created a specification describing the concept and the graph models 
& this repository of a working implementation in Nodejs, that I actually use in my projects. 
Where the interpretation algorithms are provided as external plugins to the impleminting module.
Also I've described some additional graph theory concepts, not supported by graph databases, so I had to implement some of them in the application layer. 

Let's look at different programming patterns that are better represented as graphs.

- Build & Deployment pipelines
  Task runners are good use cases, like in a build system. In this example the build command will load the graph data representing the build pipeline, and run the tasks when traversing the graph. So, each task matches a group of nodes in the graph that include the resources required for execution.
Another usages in this case for production servers are:    
- Request routing with complex logical conditions (Request Routing with logical conditions). 
- Template systems to generate custom web documents (Template compositions & rendering).
- Handling api data (Data schema verification for api requests).
and 
- implementation of middleware pattern (Sever middleware). 

For example, in this sample web application, the server components are loaded into a memory database, ready to be traversed on each client request.
Invoking the server will load the webapp, responding in this case with asset files. Where for each request a new traversal of the graph with it's own context is invoked. 

Now if we look at the graph program in the database there are separate graphs for the services of the app. The graph in this example, is made up of a subgraph for middleware chain and another subgraph for template trees, which are linked together. 
Those subgraphs are executed in the same traversal session, but are configured to use different interpretation algorithms. Therefore, when the traverser crosses the connection between the subgraphs, it interprets each with a different logic, one for the middleware downstream & upstream pattern, and the other for the templates composition & rendering. 


Representing programs in graph data structures, instead of code files, opens up a variety of possiblities for improving the development experience, mainly concerning creating visual tools, which was my initial focus from developing programs as graphs.
Rather than taking an entire visual representation approach, integrating graph with text-based programming, allows to incrementally improve graphical tools without giving up current existing text-based development tools.

The main purpose is to be able to program the same way we contruct a mental model of the program, or a least to program closer to the way we think & imagine by. I've found that some program patterns are easier to grasp when displayed graphically. Not necessarily viewing the program in a visual manner in terms of squares and lines, but in an abstract manner. 
This assists in understanding or reasoning about the temporal aspect - i.e. the expected timing of the procedures executions, and the spatial aspect - capturing the placement relations of program procedures relative to each other.

Graphical representation of programs is known to be bulky and take a lot of space, but it shouldn't be necessarily the case, when the purpose is to show abstractions of the program focusing on the control flow rather than the actual specific procedures. In this case a compact and summerized design can developed. 
I think this is one of the main reasons why visual programming languages never catched on in professional progamming, while it is used in graphics field with flow-based models or in occasional non-professional programming.

On top of this core implementation, can be built systems that are altered in realtime using graphical interfaces. I think of building a platform or software -as-a-service (PaaS or SaaS) for creating advanced webapps leveraging visual programming approach.

```

