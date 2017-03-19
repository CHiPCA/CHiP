
#CHiP
CHiP: Configurable Hybrid Parallel Covering Array Constructor

Configuration Spaces

    There are 2 or 3 (if there exist constraint) files for each configurations space.

    inputs.txt: Describes the configuration space model. More detail information can be found in the file.

    settings.txt: Keeps the number of settings for each option in order.

    constraints.txt: Keeps the constraints if there exist any. First number in the file tells the length of the constraint and in the next line, options and their settings are placed next to each other. For example, 2 constraints are given as follows.

    2
    1 0 2 1
    3
    2 2 1 1 5 0

They indicate that the tuples (o1=0∧o2=1) and (o2=2∧o1=1∧o5=0) are forbidden to be appear in any configurations of computed covering array, i.e., they are invalid tuples.

    Note that one can define other configuration space models with the same format.
    A sample configuration space model as well as a set of configurations space models for benchmarking are provided.

Dependencies

    NVIDIA GPUs Tool uses CUDA programming model. So, without having NVIDIA GPUs and its driver, the code will not work.
    Sugar: a SAT-based Constraint Solver, http://bach.istc.kobe-u.ac.jp/sugar/
    ACTS (optional), http://www.flossic.com/ACTS/
    If ACTS is provided, CHiP may compute the covering arrays faster.

How to build

    Currently we do not provide the source code.

How to run

    Put input.txt, settings.txt and constraints.txt (if any) files into same folder with the binary format of CHiP.
    Executable Sugar and ACTS (if desired) have to be in the same folder as well.
    Run the executable file
    ./CHiP

Note: This is the first release of the tool, so please send any errors that you encounter or suggestions and questions about the tool to hanefimercan@sabanciuniv.edu

The paper about CHiP is currently under review, therefore we can not give more detail how the algorithm work and share the source code of the CHiP for the moment.
