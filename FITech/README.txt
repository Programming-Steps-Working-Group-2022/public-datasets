Programming process data in adjusted Progsnap2-format
https://cssplice.github.io/progsnap2/


## Data description ##

The data is from an online introductory programming course using Dart language.
The students have varied backgrounds and study from distance. The course is
available at https://fitech101.aalto.fi/fitech101/introduction-to-programming/
in Finnish. For the same reason the programs in this data are likely to include
e.g. variable and function names in Finnish.

The published data includes
* 2 assignments, see TaskDescription-A*.txt
* 5 students in A79 assignment
* 20 students in A81 assignment

The process data was annotated with expert interventions to facilitate learning
according to the intervention guideline created in the programming steps
working group at ITiCSE'22 conference.
https://dl.acm.org/...TODO


## Data pre-processing ##

The collected data included every keystroke and other action from the online
IDE where students worked on the assignments. First, code states at every step
were reconstructed from the individual keystrokes. Second, to accommodate human
analysis we filtered the steps to token-level i.e. steps where parsing produced
incomplete tokens were removed.


## Format adjustment ##

The v6 format specification was violated in dropping two required columns.

* ToolInstances: Every event is from the one described tool & environment and
                 this column was dropped as redundant repetition.
* CodeStateID: For human analysis the short code states were direcly included
               as a column in the main table, see X-CodeState.


## User-defined columns ##

* X-CodeState: the code state i.e. current source code in the editor
* X-ElapsedTime: seconds elapsed since task started
* X-Intervene: Y = Intervention, two experts agreed
               D = Intervention, two experts separately disagreed
               R = No intervention, expert agreed run test results suffice
* X-Why: A reason to intervene from the intervention guide
         compiler = Compiler error (unaddressed)
         semantic = Semantic error
         logical = Logical error (automated test results not included or R)
         deviation = Deviation from specification
         trial = Trial and Error behaviour
         hint = Hint or Feedback request
         subgoal = Subgoal completion
         backward = Removing useful concepts in code
* X-How: A suggested message to the learner


This work is licensed under a Creative Commons Attribution-ShareAlike 4.0 International License
http://creativecommons.org/licenses/by-sa/4.0/
