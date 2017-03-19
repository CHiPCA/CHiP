
CHiP: Configurable Hybrid Parallel Covering Array Constructor

Configuration Spaces
* Configuration space models have .configModel extension.
* Input explanations for each line of file:
  1) Name of the output file for the computed covering array.
  2) Experiment id. This id is used for automated testing. 
  3) Number of options.
  4) Number of values for each option can take.
  5) Number of constraints.   
After line 5, next lines describe the constraints if there exist any. Each 2 lines indicate a single constraint. First line is the length of constraint (invalid tuple), and the next line is the invalid tuple. They are ordered as option and values pairs. For example, consider that 2 constraints are given as follows.

  2  
  1 0 2 1  
  3  
  2 2 1 1 5 0  
  
They indicate that the tuples (o1=0∧o2=1) and (o2=2∧o1=1∧o5=0) are forbidden to be appear in any configurations of computed covering array, i.e., they are invalid tuples.

* Note that one can define other configuration space models with the same format.
* A sample configuration space model as well as a set of configurations space models for benchmarking are provided.

Dependencies
* An NVIDIA GPU device and CUDA programming model. The device should have 32 threads in a warp (Old devices have 16 threads).
* Sugar: a SAT-based Constraint Solver, http://bach.istc.kobe-u.ac.jp/sugar/
* ACTS, http://www.flossic.com/ACTS/
  
How to build
* Currently we do not provide the source code.

How to run
* ... TODO

Note: This is the first release of the tool, so please send any errors that you encounter or any suggestions and questions about the tool to hanefimercan@sabanciuniv.edu

The paper about CHiP is currently under review, therefore we can not give more detail how the algorithm work and share the source code of the CHiP for the moment.
