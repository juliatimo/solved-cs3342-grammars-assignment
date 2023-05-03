Download Link: https://assignmentchef.com/product/solved-cs3342-grammars-assignment
<br>


 <noscript>

  &lt;strong&gt;We’re sorry but Markdown View doesn’t work properly without JavaScript enabled. Please enable it to continue.&lt;/strong&gt;

 </noscript>

5/5 - (1 vote)

<header></header>

<nav></nav>







This file contains two questions. The first has 2 parts, the second has 7.

For all but questions 2.3 and 2.5 you’ll answer questions by editing this file. Your answers will appear in the Ax.y section after each question, replacing the placeholders.

For question 2.3, you’ll need to add an image file to the repository (.png or .pdf) and put its file name as the answer.

For question 2.5, you’ll write one or more source code files and add them to the repository. You will then show the command used to run the files in the answer. Do <em>not</em> upload any binary files for this section.

Please do not edit anything outside the answers sections.

<h1 id="q1mrfussybuildsapath">Q1: Mr Fussy Builds a Path</h1>

<h1 id="q1">Q1</h1>

Mr Fussy wants to build a path using a row of large square pavers. His path is one paver wide and an odd number of pavers long. Pavers come in three colors: red, green, blue.

Mr Fussy has a rule: the sequence of colors must be symmetrical across the length of the path: the last paver must be the same color as the first, the second to last the same color as the second, and so on.

This is a valid path: rgbgr So is this: rrr

This is not: rgb This is not: rggr (it must be an odd length)

<h2 id="q115points">Q1.1 (5 points)</h2>

Write a Chomsky type 2 grammar that describes any valid path containing at least one paver. Use <code>S</code> as the start state, and <code>r</code>, <code>g</code>, <code>b</code> as terminals that represent the tiles.

<h2 id="a11">A1.1</h2>

S -&gt; r | g | bS -&gt; r S rS -&gt; g S gS -&gt; b S b

<h2 id="q121pointfortheoanswer2forthesentence">Q1.2 (1 point for the O() answer, 2 for the sentence)</h2>

Using big-O notation, what is the likely memory requirement for a parser that can validate a particular path configuration, where <code>n</code> is the number of tiles? In one sentence, explain why.

<h2 id="a12">A1.2</h2>

O(1), the parser uses the same quantity of memory to keep track of where it is in the path and make comparisons regardless of the length of the path.

<h1 id="q2">Q2</h1>

A simple sentence structure might be

<pre><code>"the" (zero or more adjectives) noun verb (optional adverb)</code></pre>

Adjectives are “lazy” or “smelly”

Nouns are “dog” or “cat”

Verbs are “ate” and “ran”

Adverbs are “slowly” and “noisily”

The following are examples of valid sentences:

<ul>

 <li>The smelly dog ran.</li>

 <li>The smelly dog ran slowly.</li>

 <li>The cat ate noisily.</li>

</ul>

<h2 id="q217points">Q2.1 (7 points)</h2>

Write the BNF (not EBNF) description for this language.

<h2 id="a21">A2.1</h2>

 ::= “lazy” | “smelly” ::=   | “” ::= “dog” | “cat” ::= “ate” | “ran” ::= “slowly” | “noisily” | “” ::= “the”    

<h2 id="q225points">Q2.2 (5 points)</h2>

Write this grammar using EBNF with common extensions

<h2 id="a22">A2.2</h2>

 ::= “lazy” | “smelly” ::= “dog” | “cat” ::= “ate” | “ran” ::= “slowly” | “noisily” ::= “the” {}   []

<h2 id="q236points">Q2.3 (6 points)</h2>

Draw a diagram for an FSM which recognizes these sentences. Use EOI as the event that occurs at the end-of-input. Start with a state named S0. Receiving the word “the” in that state will transition to state S1. Name the final state END.

You can hand draw it and snap a picture, or use a drawing tool. Either way, upload the image, and put the file name in the answer below.

(Hint: my answer has seven states including the start and end states)

<h2 id="a23">A2.3</h2>

«replace this with your answer»

<h2 id="q246points">Q2.4 (6 points)</h2>

Convert this diagram into a table of the form:

<table>

 <thead>

  <tr>

   <th>Current state</th>

   <th>Next word</th>

   <th>Next state</th>

  </tr>

 </thead>

 <tbody>

  <tr>

   <td>S0</td>

   <td>the</td>

   <td>S1</td>

  </tr>

  <tr>

   <td>S1</td>

   <td>. . .</td>

   <td>. . .</td>

  </tr>

 </tbody>

</table>

(hint: my version has 13 entries. Yours <em>might</em> be different)

<h2 id="a24">A2.4</h2>

<table>

 <thead>

  <tr>

   <th>Current State</th>

   <th>Next Word</th>

   <th>Next State</th>

  </tr>

 </thead>

 <tbody>

  <tr>

   <td>S0</td>

   <td>the</td>

   <td>S1</td>

  </tr>

  <tr>

   <td>S1</td>

   <td>lazy</td>

   <td>S1</td>

  </tr>

  <tr>

   <td>S1</td>

   <td>smelly</td>

   <td>S1</td>

  </tr>

  <tr>

   <td>S1</td>

   <td>dog</td>

   <td>S2</td>

  </tr>

  <tr>

   <td>S1</td>

   <td>cat</td>

   <td>S2</td>

  </tr>

  <tr>

   <td>S2</td>

   <td>ate</td>

   <td>S3</td>

  </tr>

  <tr>

   <td>S2</td>

   <td>ran</td>

   <td>S3</td>

  </tr>

  <tr>

   <td>S3</td>

   <td>slowly</td>

   <td>S4</td>

  </tr>

  <tr>

   <td>S3</td>

   <td>noisily</td>

   <td>S4</td>

  </tr>

  <tr>

   <td>S3</td>

   <td>EOI</td>

   <td>END</td>

  </tr>

  <tr>

   <td>S4</td>

   <td>EOI</td>

   <td>END</td>

  </tr>

 </tbody>

</table>

<h2 id="q2512points">Q2.5 (12 points)</h2>

Translate this table into a programming language of your choice. Then write a function that takes a list of words (ending “EOI”) and runs the list through the state machine. If the state machine cannot find a transition for a word when in a given state, return false. If the state machine runs out of words and the state is not “END” then return false. Otherwise return true.

Then write some unit tests that exercise your function, making sure that it recognizes valid sentences and rejects invalid ones.

The answer should appear in one or more source files in the same directory as this file. If I need to do anything more that type a single command to run your code, include a script or makefile that will do the job.

<h2 id="a25">A2.5</h2>

<code>g++ FSM.cpp -o FSM &amp;&amp; ./FSM</code>

<h2 id="q263points">Q2.6 (3 points)</h2>

How many valid sentences are there in this language?

<h2 id="a26">A2.6</h2>

Potentially infinite. The two adjectives can be strung together endlessly to create sentences of arbitrary length.

<h2 id="q271pointforthelevel2forthesentence">Q2.7 (1 point for the level, 2 for the sentence)</h2>

Which is the simplest Chomsky grammar level for this language? In one sentence, explain why.

<h2 id="a27">A2.7</h2>