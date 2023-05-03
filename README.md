Download Link: https://assignmentchef.com/product/solved-cs-461-artificial-intelligence-homework-2
<br>
Feel free to use any programming language as long as any of you can, if requested, give a demo using your notebook computer.

In this homework, you’ll solve a <u>variant</u> of the 15-puzzle, something I would like to call the E15puzzle because it is easier to solve. (It is well-known that the 15-puzzle is difficult to solve; Wikipedia notes that lengths of optimal solutions can be as large as 80 moves.) The first figure below is the goal state for the (classical) 15-puzzle. The second figure below is the goal state for the E15-puzzle. It is clear that due to the repeated tiles, the E15-puzzle should take fewer moves to solve in general.

<strong>15-puzzle (goal state) </strong>







<table width="248">

 <tbody>

  <tr>

   <td width="61"><strong>1 </strong></td>

   <td width="63"><strong>2 </strong></td>

   <td width="61"><strong>3 </strong></td>

   <td width="63"><strong>4 </strong></td>

  </tr>

  <tr>

   <td width="61"><strong>2 </strong></td>

   <td width="63"><strong>3 </strong></td>

   <td width="61"><strong>4 </strong></td>

   <td width="63"><strong>5 </strong></td>

  </tr>

  <tr>

   <td width="61"><strong>3 </strong></td>

   <td width="63"><strong>4 </strong></td>

   <td width="61"><strong>5 </strong></td>

   <td width="63"><strong>5 </strong></td>

  </tr>

  <tr>

   <td width="61"><strong>4 </strong></td>

   <td width="63"><strong>5 </strong></td>

   <td width="61"><strong>5 </strong></td>

   <td width="63"><strong> </strong></td>

  </tr>

 </tbody>

</table>




<strong>E15-puzzle (goal state)</strong>

(colors are just to emphasize the duplicate tiles)




<strong>Now implement the A* search algorithm (no other algorithm is acceptable) and use it to solve a given instance of the E15-puzzle <u>optimally</u>, that is, with a minimum number of moves.</strong> (Winston covers A* in chapter 5. It is up to you to add the dynamic programming part; no points will be deducted for lack of it. On the other hand, you must definitely implement loopchecking.)

As you know, A* requires <u>admissible</u> heuristics. The following are used in solving the 15-puzzle and with some modifications (if necessary) should work for the E15-puzzle, too. The admissibility proofs given below within parentheses are for the 15-puzzle though.

<ul>

 <li>h1: number of misplaced tiles</li>

</ul>

(h1 is an admissible heuristic for the 15-puzzle, since every tile that is out of position must be moved at least once.)

<ul>

 <li>h2: sum of Manhattan distances of the tiles from their proper positions</li>

</ul>

(h2 is an admissible heuristic for 15-puzzle, since in every move, one tile can only move closer to its goal by one step and the Manhattan distance is never greater than the number of steps required to move a tile to its proper position.)

Here’s what you should do:

<ul>

 <li>Write a ‘puzzle generator’ first. Starting from the goal state of the E15-puzzle (cf.</li>

</ul>

preceding figure), the generator returns a reasonably garbled initial state (S) by randomly shuffling the puzzle 10 times. This means that starting with the goal state, you ‘move’ the blank tile (up, down, left, or right) 10 times in succession, each move being decided by a call to a pseudo-random number generator. <strong>Notice that the puzzle generator thus guarantees that this (initial state) S will be solvable.</strong>

<ul>

 <li>Run your generator as many times as necessary to obtain a dozen <u>distinct</u> initial states of the E15-puzzle. For the benefit of a reader (e.g., our TAs), clearly print these states and give them names, viz. S1, S2, …, S12.</li>

 <li>Solve each Si, where i is between 1 and 12, via A*. In your A* implementation, you’ll use admissible heuristics similar to h1 or h2 (see presently).</li>

</ul>

A submission consists of:

<ul>

 <li>Listing of your program code with a clear <u>indication</u> of what parts, if any, of it are borrowed from elsewhere. (It is best if you write your own original code because points will definitely be deducted for code heavily borrowed from another source.) To explain your program, you should include comments. It is crucial that you give, in the beginning of your program and in block comments, a characterization of the heuristic you’re using and an admissibility proof for it.</li>

</ul>

<em>(HINT: Do the duplicate tiles in the E15-puzzle pose a problem re: the admissibility of h1 or h2?)</em>

<ul>

 <li>The list of a dozen initial states.</li>

 <li>For two of your initial states (you are free to pick them arbitrarily), a graphical <u>solution</u> <u>sequence</u> starting with the initial state and ending with the goal, fully tracing the moves of your program. <strong>See the part typeset in </strong><strong>dark red below for details.</strong></li>

 <li>A graph showing the queue size for the <u>remaining</u> 10 states. The x-axis of your graph should have the names of the states. The y-axis should indicate the maximum number of paths in the queue at any time for a particular state.</li>

</ul>




<strong>It is of utmost importance that a solution sequence is shown graphically.</strong> The drawings need not be sophisticated or in color, etc. Just to give you an example of what I’ve in mind, consider the following solution sequence for the 8-puzzle:







<strong>Thus, I expect two drawings like this from you but, needless to say, for the E15-puzzle</strong>