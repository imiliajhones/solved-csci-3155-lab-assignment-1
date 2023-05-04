Download Link: https://assignmentchef.com/product/solved-csci-3155-lab-assignment-1
<br>
The purpose of this assignment is to warm-up with Scala and to refresh preliminaries from prior courses.

Form your team of 8-10 persons in your lab section. Then, find a partner from your team for this lab assignment. You will work on this assignment closely with your partner. However, note that <strong>each student needs to submit </strong>and are individually responsible for completing the assignment.

You are welcome to talk about these questions beyond your teams. However, we ask that you code in pairs. Also, be sure to acknowledge those with which you discussed, including your partner and those outside of your pair.

Recall the evaluation guideline from the course syllabus.

<em>Both your ideas and also the clarity with which they are expressed matter—both in your English prose and your code!</em>

<em>We will consider the following criteria in our grading:</em>

<ul>

 <li>How well does your submission answer the questions? <em>For example, a common mistake is to give an example when a question asks for an explanation. An example may be useful in your explanation, but it should not take the place of the explanation.</em></li>

 <li>How clear is your submission? <em>If we cannot understand what you are trying to say, then we cannot give you points for it. Try reading your answer aloud to yourself or a friend; this technique is often a great way to identify holes in your reasoning. For code, not every program that “works” deserves full credit. We must be able to read and understand your intent. Make sure you state any preconditions or invariants for your functions (either in comments, as assertions, or as </em><em>require clauses as appropriate).</em></li>

</ul>

Try to make your code as concise and clear as possible. Challenge yourself to find the most crisp, concise way of expressing the intended computation. This may mean using ways of expression computation currently unfamilar to you.

Finally, make sure that your file compiles and runs on COG. A program that does not compile will <em>not </em>be graded.

1

<strong>Submission Instructions.                 </strong>Upload to the moodle exactly three files named as follows:

<ul>

 <li>Lab1-<em>YourIdentiKey</em>.pdf with your answers to the written questions (scanned, clearly legible handwritten write-ups are acceptable).</li>

 <li>Lab1-<em>YourIdentiKey</em>.scala with your answers to the coding exercises.</li>

 <li>Lab1-<em>YourIdentiKey</em>.jsy with a challenging test case for your JAVASCRIPTY</li>

</ul>

Replace <em>YourIdentiKey </em>with your IdentiKey (e.g., for me, I would submit Lab1-bec.pdf and Lab1-bec.scala). Don’t use your student identification number. To help with managing the submissions, we ask that you rename your uploaded files in this manner.

Submit your Lab1.scala file to COG for auto-testing. We ask that you submit both to COG and to moodle in case of any issues.

Sign-up for an interview slot for an evaluator. To fairly accommodate everyone, the interview times are strict and <strong>will not be rescheduled</strong>. Missing an interview slot means missing the interview evaluation component of your lab grade. Please take advantage of your interview time to maximize the feedback that you are able receive. Arrive at your interview ready to show your implementation and your written responses. Implementations that do not compile and run will not be evaluated.

<strong>GettingStarted. </strong>Clone the code from the Githup repository <a href="https://github.com/bechang/pppl-labs">https://github.com/bechang/ </a><a href="https://github.com/bechang/pppl-labs">pppl-labs</a> and follow the instructions in the README.md.

A suggested way to get familiar with Scala is to do some small lessons with Scala Koans <a href="http://www.scalakoans.org/">(</a><a href="http://www.scalakoans.org/">http://www.scalakoans.org/</a><a href="http://www.scalakoans.org/">)</a>. For this lab, we suggest that you consider looking at the AboutAsserts, AboutLiteralBooleans, AboutLiteralNumbers, AboutLiteralStrings, AboutMethods, AboutRecursion, AboutTuples, AboutCaseClasses, and AboutPatternMatching koans.

<ol>

 <li><strong>Feedback</strong>.. Complete the survey linked from the moodle after completing this assignment. Any non-empty answer will receive full credit.</li>

 <li><strong>Scala Basics: Binding and Scope</strong>. For each the following uses of names, give the line where that name is bound. Briefly explain your reasoning (in no more than 1–2 sentences).</li>

</ol>

(a) Consider the following Scala code.

<em>1          </em><strong>val </strong>pi = 3.14 <em>2      </em><strong>def </strong>circumference(r: Double): Double = { <em>3         </em><strong>val </strong>pi = 3.14159 <em>4     </em>2.0 * pi * r

<em>5                </em>}

<h1><em>6          </em><strong>def </strong>area(r: Double): Double = <em>7                      </em>pi * r * r</h1>

The use of pi at line 4 is bound at which line? The use of pi at line 7 is bound at which line?

(b) Consider the following Scala code.

<h1><em>1          </em><strong>val </strong>x = 3 <em>2                  </em><strong>def </strong>f(x: Int): Int =</h1>

<ul>

 <li>x <strong>match </strong>{</li>

 <li><strong>case </strong>0 <strong>=&gt; </strong>0</li>

 <li><strong>case </strong>x <strong>=&gt; </strong>{</li>

 <li><strong>val </strong>y = x + 1 <em>7 </em>({ <em>8               </em><strong>val </strong>x = y + 1</li>

</ul>

<em>9                                                    </em>y

<h1>                       <em>10                                                      </em>} * f(x – 1))</h1>

<ul>

 <li>}</li>

 <li>}</li>

</ul>

<h1>                       <em>13                         </em><strong>val </strong>y = x + f(x)</h1>

The use of x at line 3 is bound at which line? The use of x at line 6 is bound at which line? The use of x at line 10 is bound at which line? The use of x at line 13 is bound at which line?

<ol start="3">

 <li><strong>ScalaBasics: Typing</strong>. In the following, I have left off the return type of function g. The body of g is well-typed if we can come up with a valid return type. Is the body of g well-typed?</li>

</ol>

<h1><em>1 </em><strong>def </strong>g(x: Int) = { <em>2                     </em><strong>val </strong>(a, b) = (1, (x, 3)) <em>3    </em><strong>if </strong>(x == 0) (b, 1) <strong>else </strong>(b, a + 2)</h1>

<em>4                </em>}

If so, give the return type of g and explain how you determined this type. For this explaination, first, give the types for the names a and b. Then, explain the body expression using the following format:

<em>e </em>: <em>τ </em>because <em>e</em><sub>1 </sub>: <em>τ</em><sub>1 </sub>because

…

<em>e</em><sub>2 </sub>: <em>τ</em><sub>2 </sub>because

…

where <em>e</em><sub>1 </sub>and <em>e</em><sub>2 </sub>are subexpressions of <em>e</em>. Stop when you reach values (or names).

As an example of the suggested format, consider the plus function:

<strong>def </strong>plus(x: Int, y: Int) = x + y

Yes, the body expression of plus is well-typed with type Int.

<h1>x + y : Int because x : Int y : Int</h1>

<ol start="4">

 <li><strong>Run-Time Library</strong>. Most languages come with a standard library with support for things like data structures, mathematical operators, string processing, etc. Standard library functions may be implemented in the object language (perhaps for portability) or the meta language (perhaps for implementation efficiency).</li>

</ol>

For this question, we will implement some library functions in Scala, our meta language, that we can imagine will be part of the run-time for our object language interpreter. In actuality, the main purpose of this exercise is to warm-up with Scala.

<h1>(a) Write a function abs <strong>def </strong>abs(n: Double): Double</h1>

that returns the absolute value of n. This a function that takes a value of type Double and returns a value of type Double. This function corresponds to the JavaScript library function Math.abs. <strong>Instructor Solution</strong>: 1 line.

<h1>(b) Write a function xor <strong>def </strong>xor(a: Boolean, b: Boolean): Boolean</h1>

that returns the exclusive-or of a and b. The exclusive-or returns <strong>true </strong>if and only if exactly one of a or b is <strong>true</strong>. For practice, do not use the Boolean operators. Instead, only use the <strong>if</strong>–<strong>else </strong>expression and the Boolean literals (i.e., <strong>true </strong>or <strong>false</strong>).

<strong>Instructor Solution</strong>: 4 lines (including 1 line for a closing brace).

<ol start="5">

 <li><strong>Run-Time Library: Recursion</strong>.</li>

</ol>

<h1>(a) Write a recursive function repeat <strong>def </strong>repeat(s: String, n: Int): String</h1>

where repeat(s, n) returns a string with n copies of s concatenated together. For example, repeat(“a”,3) returns “aaa”. This function corresponds to the function goog.string.repeat in the Google Closure library.

<strong>Instructor Solution</strong>: 4 lines (including 1 line for a closing brace).

(b) In this exercise, we will implement the square root function—Math.sqrt in the JavaScript standard library. To do so, we will use Newton’s method (also known as Newton-Raphson).

Recall from Calculus that a root of a differentiable function can be iteratively approximated by following tangent lines. More precisely, let <em>f </em>be a differentialable function, and let <em>x</em><sub>0 </sub>be an initial guess for a root of <em>f </em>. Then, Newton’s method specifies a sequence of approximations <em>x</em><sub>0</sub>,<em>x</em><sub>1</sub>,… with the following recursive equation:<a href="#_ftn1" name="_ftnref1"><sup>[1]</sup></a>

<em>f </em>(<em>x<sub>n</sub></em>)

<em>x</em><em>n+</em>1 <em>= x</em><em>n − </em><em>f </em><em>0</em>(<em>x</em><em>n</em>) .

The square root of a real number <em>c </em>for <em>c &gt; </em>0, written <em>pc</em>, is a positive <em>x </em>such that <em>x</em><sup>2 </sup><em>= c</em>. Thus, to compute the square root of a number <em>c</em>, we want to find the positive root of the function: <em>f </em>(<em>x</em>) <em>= x</em><sup>2</sup><em>−c </em>.

Thus, the following recursive equation defines a sequence of approximations for <em>pc</em>:

<em>= − x<sup>n</sup></em><sup>2 </sup><em>−c x</em><em>n+</em>1 <em>x</em><em>n </em><sub>2<em>x</em></sub><em><sub>n </sub></em>.

<h1>i. First, implement a function sqrtStep <strong>def </strong>sqrtStep(c: Double, xn: Double): Double</h1>

that takes one step of approximation in computing <em>pc </em>(i.e., computes <em>x<sub>n</sub></em><em>+</em>1 from <em>x<sub>n</sub></em>).

<h1><strong>Instructor Solution</strong>: 1 line. ii. Next, implement a function sqrtN <strong>def </strong>sqrtN(c: Double, x0: Double, n: Int): Double</h1>

that computes the <em>n</em>th approximation <em>x<sub>n </sub></em>from an initial guess <em>x</em><sub>0</sub>. You will want to call sqrtStep implemented in the previous part.

Challenge yourself to implement this function using recursion and no mutable variables (i.e., <strong>var</strong>s)—you will want to use a recursive helper function. It is also quite informative to compare your recursive solution with one using a <strong>while </strong>loop. <strong>Instructor Solution</strong>: 7 lines (including 2 lines for closing braces and 1 line for a require). iii. Now, implement a function sqrtErr

<h1><strong>def </strong>sqrtErr(c: Double, x0: Double, epsilon: Double): Double</h1>

that is very similar to sqrtN but instead computes approximations <em>x<sub>n </sub></em>until the approximation error is within <em>ε </em>(epsilon), that is,

<em>|x</em><em>n</em>2 <em>−c|&lt;ε </em>.

You can use your absolute value function abs implemented in a previous part. A wrapper function sqrt is given in the template that simply calls sqrtErr with a choice of x0 and epsilon.

Again, challenge yourself to implement this function using recursion and compare your recursive solution to one with a <strong>while </strong>loop.

<strong>Instructor Solution</strong>: 5 lines (including 1 line for a closing brace and 1 line for a require).

<ol start="6">

 <li><strong>Data Structures Review: Binary Search Trees</strong>.</li>

</ol>

In this question, we will review implementing operations on binary search trees from Data Structures. Balanced binary search trees are common in standard libraries to implement collections, such as sets or maps. For example, the Google Closure library for JavaScript has goog.structs.AvlTree. For simplicity, we will not worry about balancing in this question.

Trees are important structures in developing interpreters, so this question is also critical practice in implementing tree manipulations.

A binary search tree is a binary tree that satisfies an ordering invariant. Let <em>n </em>be any node in a binary search tree whose data value is <em>d</em>, left child is <em>l</em>, and right child is <em>r</em>. The ordering invariant is that all of the data values in the subtree rooted at <em>l </em>must be <em>&lt; d</em>, and all of the data values in the subtree rooted at <em>r </em>must be <em>≥ d</em>.

We will represent a binary trees containing integer data using the following Scala <strong>caseclass</strong>es and <strong>case object</strong>s:

<strong>sealed abstract class </strong>IntTree <strong>case object </strong>Empty <strong>extends </strong>IntTree

<strong>case class </strong>Node(l: IntTree, d: Int, r: IntTree) <strong>extends </strong>IntTree

A IntTree is either Empty or a Node with left child l, data value d, and right child r.

For this question, we will implement the following four functions.

<h1>(a) The function repOk <strong>def </strong>repOk(t: IntTree): Boolean</h1>

checks that an instance of IntTree is valid binary search tree. In other words, it checks using a traversal of the tree the ordering invariant. This function is useful for testing your implementation. A skeleton of this function has been provided for you in the template.

<strong>Instructor Solution</strong>: 7 lines (including 2 lines for closing braces).

<h1>(b) The function insert <strong>def </strong>insert(t: IntTree, n: Int): IntTree</h1>

inserts an integer into the binary search tree. Observe that the return type of insert is a IntTree. This choice suggests a functional style where we construct and return a new output tree that is the input tree t with the additional integer n as opposed to destructively updating the input tree.

<strong>Instructor Solution</strong>: 4 lines (including 1 line for a closing brace).

<h1>(c) The function deleteMin <strong>def </strong>deleteMin(t: IntTree): (IntTree, Int)</h1>

deletes the smallest data element in the search tree (i.e., the leftmost node). It returns both the updated tree and the data value of the deleted node. This function is intended as a helper function for the delete function. Most of this function is provided in the template.

<strong>InstructorSolution</strong>: 9 lines (including 2 lines for closing braces and 1 line for a require).

(d) The function delete

<h1><strong>def </strong>delete(t: IntTree, n: Int): IntTree</h1>

removes the first node with data value equal to n. This function is trickier than insert because what should be done depends on whether the node to be deleted has children or not. We advise that you take advantage of pattern matching to organize the cases.

<strong>Instructor Solution</strong>: 10 lines (including 2 lines for closing braces).

<ol start="7">

 <li><strong>JavaScripty Interpreter: Numbers</strong>.</li>

</ol>

JavaScript is a complex language and thus difficult to build an interpreter for it all at once. In this course, we will make some simplifications. We consider subsets of JavaScript and incrementally examine more and more complex subsets during the course of the semester. For clarity, let us call the language that we implement in this course JAVASCRIPTY.

For the moment, let us define JAVASCRIPTY to be a proper subset of JavaScript. That is, we may choose to omit complex behavior in JavaScript, but we want any programs that we admit in JAVASCRIPTY to behave in the same way as in JavaScript.

In actuality, there is not one language called JavaScript but a set of closely related languages that may have slightly different semantics. In deciding how a JAVASCRIPTY program should behave, we will consult a reference implementation that we fix to be Google’s V8 JavaScript Engine. We will run V8 via Node.js, and thus, we will often need to write little test JavaScript programs and run it through Node.js to see how the test should behave.

In this lab, we consider an arithmetic sub-language of JavaScript (i.e., an extremely basic calculator). The first thing we have to consider is how to represent a JAVASCRIPTY <em>program as data </em>in Scala, that is, we need to be able to represent a program in our object/source language JAVASCRIPTY as data in our meta/implementation language Scala.

To a JAVASCRIPTY programmer, a JAVASCRIPTY program is a text file—a string of characters. Such a representation is quite cumbersome to work with as a language implementer. Instead, language implementations typically work with trees called <em>abstract syntax trees</em>

(ASTs). What strings are considered JAVASCRIPTY programs is called the <em>concrete syntax </em>of JAVASCRIPTY, while the trees (or <em>terms</em>) that are JAVASCRIPTY programs is called the <em>abstract synatx </em>of JAVASCRIPTY. The process of converting a program in concrete syntax (i.e., as a string) to a program in abstract syntax (i.e., as a tree) is called <em>parsing</em>.

For this lab, a parser is provided for you that reads in a JAVASCRIPTY program-as-a-string and converts into an abstract syntax tree. We will represent abstract syntax trees in Scala using <strong>case class</strong>es and <strong>case object</strong>s. The correspondence between the concrete syntax and the abstract syntax representation is shown in Figure 1.

(a)

<strong>Interpreter 1. </strong>Implement the eval function <strong>def </strong>eval(e: Expr): Double

that evaluates a JAVASCRIPTY expression e to the Scala double-precision floating point number corresponding to the <em>value </em>of e.

Consider a JAVASCRIPTY program <em>e</em>; imagine <em>e </em>stands for the concrete syntax or text of the JAVASCRIPTY program. This text is parsed into a JAVASCRIPTY AST e, that is, a Scala value of

<strong>sealed abstract class </strong>Expr

<strong>case class </strong>N(n: Double) <strong>extends </strong>Expr

N(<em>n</em>) <em>n</em>

<strong>case class </strong>Unary(uop: Uop, e1: Expr) <strong>extends </strong>Expr

Unary(<em>uop</em>,<em>e</em><sub>1</sub>) <em>uope</em><sub>1 </sub><strong>case class </strong>Binary(bop: Bop, e1: Expr, e2: Expr) <strong>extends </strong>Expr

Binary(<em>bop</em>, <em>e</em><sub>1</sub>) <em>e</em><sub>1</sub><em>bope</em><sub>2</sub>

<strong>sealed abstract class </strong>Uop <strong>case object </strong>Neg <strong>extends </strong>Uop

Neg <em>−</em>

<strong>sealed abstract class </strong>Bop <strong>case object </strong>Plus <strong>extends </strong>Bop

Plus <em>+</em>

<strong>case object </strong>Minus <strong>extends </strong>Bop

Minus <em>−</em>

<strong>case object </strong>Times <strong>extends </strong>Bop

Times <em>∗</em>

<strong>case object </strong>Div <strong>extends </strong>Bop

Div /

Figure 1: Representing in Scala the abstract syntax of JAVASCRIPTY. After each <strong>caseclass </strong>or <strong>caseobject</strong>, we show the correspondence between the representation and the concrete syntax.

type Expr. Then, the result of eval is a Scala number of type Double and should match the interpretation of <em>e </em>as a JavaScript expression. These distinctions can be subtle but learning to distinguish between them will go a long way in making sense of programming languages.

At this point, you have implemented your first language interpreter!

<a href="#_ftnref1" name="_ftn1">[1]</a> The following link is a refresher video on this algorithm: <a href="https://www.youtube.com/watch?v=1uN8cBGVpfs">http://www.youtube.com/watch?v=1uN8cBGVpfs</a><a href="https://www.youtube.com/watch?v=1uN8cBGVpfs">, </a>January 2012