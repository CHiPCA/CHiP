
CHiP: Configurable Hybrid Parallel Covering Array Constructor

CHiP is a covering array constructor which both uses CPU and GPU (specifically NVIDIA GPU). The configurable name comes from the ability to let the user choose in one of the versions for construct covering arrays; faster (fast), having smaller size (quality) or between those options (balanced). CHiP lets the user to choose the any of these three versions. 

Configuration Spaces
* Configuration space models have the .configModel extension.
* Input explanations for each line of the file:
  1) Name of the output file for the computed covering array.
  2) Experiment id. This id is used for automated testing. 
  3) Number of options. Option enumeration starts with 0, i.e., first option is the 0th option.
  4) Number of values for each option can take. Value enumeration for an option starts with 0. Currently, tool support max number of 4 values for an option.
  5) Number of constraints. Constraints are defined as invalid tuples. Note that a group of invalid tuples may infer new invalid tuples a.k.a. implicit invalid tuples. Our tool identifies implicit invalid tuples, too and report the total number of constraints.
  Following line 5, next lines describe the constraints if there exist any. Each 2 lines indicate a single constraint. First line is the length of constraint (invalid tuple), and the next line is the invalid tuple. They are ordered as option and values pairs. For example, consider that 2 constraints are given as follows.

  2  
  1 0 2 1  
  3  
  2 2 1 1 5 0  
  
  They indicate that the tuples (o1=0∧o2=1) and (o2=2∧o1=1∧o5=0) are forbidden to be appear in any configurations of computed covering array, i.e., they are invalid tuples.
* A sample configuration space model as well as a set of configurations space models for benchmarking are provided.
* With a given configuration model, CHiP computes both a 2-way and a 3-way CA and reports the timings, seperately.

Dependencies
* CUDA programming model, https://developer.nvidia.com/. We tested CHiP with CUDA 5, therefore any version aobve that should be enough. The device also must support having 32 threads in a warp (old devices have 16 threads).
* Sugar: a SAT-based Constraint Solver, http://bach.istc.kobe-u.ac.jp/sugar/
* ACTS, http://www.flossic.com/ACTS/
  
How to build
* Currently we do not provide the source code.

How to run
* ./CHiP {fast|balanced|quality} sample.configModel sugarPath actsPath
* Providing CHiP version is optional, default value is balanced.
* sugarPath and actsPath are the paths of the Sugar and ACTS, respectively.  
E.g.,   
./CHiP fast sample.configModel /some/path/acts.jar /some/path/sugar

Note: This is the first release of the tool, so please send any errors that you encounter or any suggestions and questions about the tool to hanefimercan@sabanciuniv.edu

The paper about CHiP is currently under review, therefore we can not give detail about the algorithm and share the source code of the CHiP for the moment.
