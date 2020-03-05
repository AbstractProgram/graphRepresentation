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

Abstract program is a high-level graph-based program which is interpreted on runtime by a supervisor program. This Graph program concept creates an additional layer of abstraction, it doesn't deal with specifics of the algorithms, only representing the module units or name references of functions, hense the term abstract program.

I've created a specification which is an aggregation of notes and drawings for the graph models & this repository of a working implementation in Nodejs, that I actually use in my projects. Also I've described some additional graph theory concepts, not supported by graph databases, so I had to implement some of them in the application layer. 

Initially the purpose was to be able to program the same way we contruct a mental model map of the program, or a least closer to the way we think & imagine by. I've found that some program patterns are easier to grasp when displayed graphically. Not necessarily viewing the program in a visual manner in terms of squares and lines, but in an abstract manner.
For example creating a visual program map that takes into consideration the placement of procedures relative to each other and the expected timing of the different procedure executions in the program. 
This assists in understanding or reasoning about the temporal aspect - timing of the program procedures, and the spatial aspect - capturing the position relations of the elements in the program.

Representing programs in a graph data structure, instead of code files, opens up a variety of possiblities for improving the development experience, mainly concerning creating visual tools, which was my initial focus from developing programs as graphs.
Graphical representation of programs is known to be bulky and take a lot of space, but it shouldn't be necessarily the case, when the purpose is to show abstractions of the program focusing on the control flow rather than the actual specific procedures. In this case a compact and summerized design can developed. I think this is one of the main reasons why visual programming languages never catched on in professional progamming, while it is used in graphics field, king of flow-based programming or occasional programming, so in a non-professional way.

Back to the concept - Basically it is a way to represent part of the program in a graph data structure. This allows for integrating visual & text-based programming approaches, so that visual programming could be used, without giving up current development tools. Rather than taking an entire visual representation approach, using both visual & text, allows for integration with current existing text-based development tools, and incrementally build graphical tools.

An abstract program, it is abstract in the sense that it describes the control flow of the program, leaving the details of the algorithms for an interpreter. In other words, it allows for splitting up the sequence of steps from the logic to be processed on each step.
This is where a supervisor program comes into place. The supervisor program is provided with the graph data as input, in which it traverses the graph, interprets it, and executes the steps in the graph on runtime during each traversal. The same graph can be executed with different interpretation algorithms to match specific use-cases.

Let's breifly look into different use cases:
- Build pipelines
- Sever middleware. 
- Routing with logical conditions. 
- Template compositions and rendering.

Future plan to build a SaaS or PaaS.
```

