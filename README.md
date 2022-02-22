# SAT-solver
DPLL based SAT solver for cnf: CS202 
## How to use the code:
-copy the cnf file to same folder
-type python3 -u SATsolver.py /*cnf_file_name*/.cnf in the terminal
- wait for some time , if the cnf is sat then output will be sat followed by any one model
- if the cnf is unsat the output in terminal is unsat
## IMPLEMENTATION
This SAT solver uses DPLL algorithm for solving the cnf
DPLL is backtracking based search algorithm.
For understanding the algorithm we need to know these terms:
- Unit literal: A literal that appears in a singleton clause
Ex:
- Pure literal: A symbol that always appears with same sign
Ex: in {{a -b c}{-c d -e}{-a -b e}{d b}{e a -c}} here d appears only with one
sign so it is a pure literal here
DPLL enhances over the backtracking algorithm by the eager use of the following rules at
each step:
- Unit propagation : this clause can only be satisfied by assigning the necessary value to make
this literal true.
- Pure literal elimination: A pure literal can always be assigned in a way that makes all clauses
containing it true.When assigned that way that literal can be removed and there will be no
effect on satisfiability of unsatisfiability of cnf.
Unsatisfiability can be detected by by empty clause.
Further exhaustive backtracking is implemented if there are remaining clauses.
Time complexity analysis :
Best case : when all the clauses contain
## ASSUMPTION
We have assumed input to be in cnf form.
## LIMITATION
In Worst case we would have to run complete backtracking which leads to O(2n) where n is the
number of and for our machines for large value of n is the number of literals. So this can take lot
of time to run completely.
