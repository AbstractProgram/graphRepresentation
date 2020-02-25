# Presentation: max 3 mins. 

| Points        | Scene           |
| ------------- |:------------- |
| 1-4 | Title with an example control flow graph.|
| 5 | Side-by-side text and visual programming approaches |
| 6-7 | Graph with arrow pointing to an interpreter |
| 8-9 | Supervisor program (traverses, interprets, & executes) with an inpur program graph and used interpretation algorithms. |
| 10-13 | Browser screencast of repositories |


## Points: 
_Explain the concept:_
1. Closest term "abstract program"
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
16. pros & cons

___

## Actual script: 

```
This is an overview of abstract program concept. A high-level graph-based program which depends on another program to be interpreted. Representing programs in a graph data structure, instead of code files, opens up a variety of possiblities for improving development experience, mainly creating visual tools.

Basically it is a way to represent part of the program in a graph data structure. This allows for integrating visual & text-based programming approaches, so that visual programming could be used, without giving up current development tools. Rather than taking an entire visual representation approach, using both visual & text, allows for integration with current existing text-based development tools, and incrementally build graphical tools.

An abstract program, it is abstract in the sense that it describes the control flow of the program, leaving the details of the algorithms for an interpreter. In other words, it allows for splitting up the sequence of steps from the logic to be processed on each step.

So, a supervisor program is provided with the graph data as input, in which it traverses the graph, interprets it, and executes the steps in the graph on runtime during each traversal. The same graph can be executed with different interpretation algorithms to match specific use-cases.


Here is the specification & this is the implementation of it in Nodejs.

I've found that some program patterns are easier to grasp when displayed graphically (Not necessarily in a visual manner (in terms of squares and lines), but in an abstract manner), which assist in understanding both time and spatial relations. 
Graphical representation of programs is known to be bulky and take a lot of space, but it shouldn't be necessarily the case, when the purpose is to show abstractions of the program focusing on the control flow rather than the actual procedures. In this case a compact and summerized design can developed.

Let's look at different use cases:
- Build pipelines
- Sever middleware. 
- Routing with logical conditions. 
- Template compositions and rendering.
```

