Download Link: https://assignmentchef.com/product/solved-cse241-homework-1
<br>
You are going to implement an interactive program which enables user to play the game <em><sub>mastermind</sub></em>. The idea of the game is, one side holds a secret number and the other side(user) proposes numbers and gets useful hints at each turn. The aim of the user is to guess the secret number.

<h1>The Rules of The <em>Mastermind</em></h1>

<ul>

 <li>A digit is an integer in the range <sub>[0,9]</sub></li>

 <li>A valid number is defined to be an <sub>N </sub>digit number (N <em><sub>≤ </sub></em>9) where the high-most (leftmost) digit cannot be <sub>0</sub></li>

</ul>

and <strong>any digit appears only once in the number</strong>.

<ul>

 <li>Your program chooses a valid number (secret number).

  <ul>

   <li>First option is to generate a random number (it must be a valid number)</li>

   <li>Second option is to use a given number (a number will be provided as a command-line argument)</li>

  </ul></li>

 <li>(At each turn) the code breaker (user) proposes a valid number. Turns are counted (Starting with 1).</li>

 <li>As response to the proposal, the code maker(your program) provides two counts:

  <ul>

   <li><strong><sub>First count </sub></strong>(C<sub>exact</sub>): The count of digits of the proposed number that match in place of the secret number.</li>

   <li><strong><sub>Second count </sub></strong>(C<sub>misplaced</sub>): The count of digits of the proposed number which do exist in the secret number but are not in place.</li>

  </ul></li>

 <li>A C<sub>exact </sub>value of <sub>N </sub>stops the game and the turn-count is recorded; otherwise the game continues with accepting user proposals.</li>

</ul>

<h1>Expectations</h1>

<h2>Input</h2>

<ul>

 <li>Your program will take command-line arguments.

  <ul>

   <li>The first argument is either <sub>-r </sub>or <sub>-u</sub>.</li>

   <li>If the first argument is <sub>-r</sub>, user has to provide another argument <sub>N</sub>: The number of digits. Your program will create a random number which has <sub>N </sub></li>

   <li>If the first argument is <sub>-u</sub>, user has to provide another argument which will be used as a secret number.</li>

  </ul></li>

 <li>At each turn user enters a number, your program has to capture the number correctly, compare it with the secret and print hints.</li>

</ul>

<h2>Output</h2>

<ul>

 <li>At each iteration, print hints.</li>

 <li>If the user input perfectly matches with the secret number, print the <sub>FOUND </sub>message and number of iterations and exit.</li>

</ul>

<h1>Example Run</h1>

Suppose that your source file is <sub>mysource.cpp</sub>. First, it will be compiled:

g++ -std=c++11 mysource.cpp -o mastermind

Then your program can be called like the following: mastermind -r 6

With this call, user is expected to enter a <sub>6 </sub>digit number. If user enters a number which has more or less than <sub>6 </sub>digits, your program should print the following error message and exit.

E1

If the user enters something but not an integer, your program should print the following error:

E2

If the user enters a valid number your program should return the hints in the following format:

<table width="711">

 <tbody>

  <tr>

   <td width="126">mastermind -r 6</td>

   <td width="586">——&gt; Assume that your program generates secret 130456</td>

  </tr>

  <tr>

   <td width="126">123456</td>

   <td width="586">——&gt; User enters 123456</td>

  </tr>

  <tr>

   <td width="126">4 1</td>

   <td width="586">——&gt; First count is 4, Second count is 1 (separated by a space)</td>

  </tr>

  <tr>

   <td width="126">132456</td>

   <td width="586">——&gt; User enters 132456</td>

  </tr>

  <tr>

   <td width="126">5 0</td>

   <td width="586">——&gt; First count is 5, Second count is 0 (separated by a space)</td>

  </tr>

  <tr>

   <td width="126">130456</td>

   <td width="586">——&gt; User enters 130456</td>

  </tr>

  <tr>

   <td width="126">FOUND 3</td>

   <td width="586">——&gt; User found the number in 3 iterations, program exits. (separated by a space)</td>

  </tr>

 </tbody>

</table>

If the user cannot find in <sub>100 </sub>iterations, print the following message and exit the program:

FAILED

Your program can also be called like the following: mastermind -u 12345

If this happens, your program will use 12345 (the given argument) as the secret number. The rest of your code will not change.

<h1>Error Checking</h1>

Check for any errors in program call. If there is any error, print the following and exit:

E0

Errors in program call include the following:

<ul>

 <li>Missing parameters.</li>

 <li>Wrong parameters.</li>

 <li>Undefined parameters.</li>

 <li>Negative value or <sub>0 </sub>value following the <sub>-r </sub></li>

 <li>Digits of the number followed by <sub>-u </sub>are not unique.</li>

</ul>

The other errors are specified in the <sub>Example </sub>section.

<h1>Remarks</h1>

<ul>

 <li>Error checking is important.</li>

 <li>Your program should be immune to the whitespace before any user input.</li>

 <li>Do not submit your code without testing it with several different scenarios.</li>

 <li>Write comments in your code. Extensive commenting is required. Comment on every variable, constant, function and loop. (<sub>10pts</sub>)</li>

 <li>Do not use <sub>#Define </sub>and define macros. Instead use <sub>constant </sub>keyword and define constant variables. If you use macros, you will loose <sub>5 </sub>points for each of them.</li>

 <li>Do not create an output file. Everything happens through <sub>stdin </sub>and <sub>stdout</sub>.</li>

 <li>Be very careful about the input and output format. Don’t print anything extra(including spaces).</li>

</ul>

<strong>Turn in:</strong>

<ul>

 <li>Source code of a complete C++ program. Name of the file should be in this format: <sub>&lt;full_name&gt;_&lt;id&gt;.cpp</sub>. If you do not follow this naming convention you will loose <sub>-10 </sub></li>

 <li>Example: <sub>cpp</sub>. Please do not use any Turkish special characters.</li>

 <li>You don’t need to use an IDE for this assignment. Your code will be compiled and run in a command window.</li>

 <li>Your code will be compiled and tested on a Linux machine(Ubuntu). GCC will be used.</li>

 <li>Make sure you don’t get compile errors when you issue this command : <sub>g++ -std=c++11 &lt;full_name&gt;_&lt;id&gt;.cpp</sub>.</li>

 <li>A script will be used in order to check the correctness of your results. So, be careful not to violate the expected output format.</li>

 <li>Provide comments unless you are not interested in partial credit. (If I cannot easily understand your design, you may loose points.)</li>

 <li>You may not get full credit if your implementation contradicts with the statements in this document.</li>

</ul>