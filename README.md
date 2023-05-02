Download Link: https://assignmentchef.com/product/solved-comp90041-assessment
<br>
In this assignment, you will write a simple console drawing program that implements some simplified features of a popular graphic application such as Microsoft Paint. Specifically, given some parameters (e.g., side length, alignment settings), the program draws isosceles right-angled triangles and squares on a drawing canvas. The program will also have a certain capability to implement some simple transformations like rotation and zooming and perform simple error checking. This assignment is designed in such a way that we can evaluate your knowledge on the following topics: 1) basic class design and implementation, 2) control flow structures (e.g., if-then-else, loops), and 3) basic I/O (e.g., Scanner class, formatted printing).

<ul>

 <li><strong>Your Task</strong></li>

</ul>

Go to <em>https://classroom.github.com/a/RAVaxEzI </em>and accept the assignment. For details on how to check out the repository, make sure to consult the Lab 3 Materials<a href="#_ftn1" name="_ftnref1"><sup>[1]</sup></a>. Once you have cloned the repository, you will find four classes in it:

ConsoleDrawing.java

DrawingCanvas.java

Triangle.java

Square.java

ConsoleDrawing.java will be the main application containing your main() method. The other three classes will contain methods for setting up the drawing canvas, handling user inputs (e.g., information of the shapes to be drawn), and drawing the supported shapes. All these .java files are almost empty and you are asked to add constructors, instance variables, and methods to complete the program. See the application walk-through to understand the required features of the program.

<strong>For this assignment, all user inputs will be assumed to be the correct data types; such that if a String is expected then it is assumed a string will be entered, and the same for an integer. No error control for incorrectly entered data types are required… as of yet! </strong>.

<strong>3       Application Walk-through</strong>

<ol>

 <li>Your program must take three arguments which will be used to set up the initial drawing canvas. For example, the following command starts your program with a 10×6 drawing canvas and the background character is the minus sign.</li>

</ol>

java ConsoleDrawing 10 6 –

<strong>Note that this is a console drawing app so instead of using one pixel, we use one character as the measurement unit. A 10×6 drawing canvas is like a table with 6 rows and 10 columns in which each cell has enough space for only one printable character</strong>. Following is an example of a 10×6 canvas on which a 5×5 “square” has been drawn.

AAAAA—–

AAAAA—–

AAAAA—–

AAAAA—–

AAAAA—–

———-

<ol start="2">

 <li>Your program will begin by displaying a welcome message. It will then display the initial drawingcanvas settings as given in the program arguments.</li>

</ol>

—-WELCOME TO MY CONSOLE DRAWING APP—Current drawing canvas settings:

<ul>

 <li>Width: 10</li>

 <li>Height: 6</li>

 <li>Background character: –</li>

</ul>

<ol start="3">

 <li>The program will then display the main menu with a list of options for 1) drawing isosceles rightangled triangles, 2) drawing squares, 3) updating the drawing canvas, and 4) exiting the program.</li>

</ol>

Please select an option. Type 4 to exit.

<ol>

 <li>Draw triangles</li>

 <li>Draw squares</li>

 <li>Update drawing canvas settings</li>

 <li>Exit</li>

</ol>

<ol start="4">

 <li>If an invalid option is provided, say the user types “5” and presses Enter, an error message will bedisplayed and the main menu is listed again.</li>

</ol>

Unsupported option. Please try again!

Please select an option. Type 4 to exit.

<ol>

 <li>Draw triangles</li>

 <li>Draw squares</li>

 <li>Update drawing canvas settings</li>

 <li>Exit</li>

</ol>

<ol start="5">

 <li>If the first option (“Draw triangles”) is selected, by typing “1” and then pressing Enter, theprogram should call a corresponding method of the Triangle class to accept more user inputs and draw triangles accordingly. Specifically, it should first ask for the side length of an isosceles rightangled triangle, the printing character (which will be drawn inside the triangle on the canvas), and its alignment. Regarding error handling, you need to check if the canvas is big enough for the triangle. In case of alignment options, if an invalid one is selected, say “a” or “b”, the default choice should be left alignment. Your program will then draw a triangle on the canvas if all settings are valid.</li>

</ol>

Please select an option. Type 4 to exit.

<ol>

 <li>Draw triangles</li>

 <li>Draw squares</li>

 <li>Update drawing canvas settings</li>

 <li>Exit</li>

</ol>

1

Side length: 8

Error! The side length is too long (Current canvas size is 10×6). Please try again. Side length:

5

Printing character:

A

Alignment (left, middle, right):

left AAAAA—–

AAAA——

AAA——-

AA——–

A———

———-

Please find below the program output if middle or right alignment has been selected. You can see that the triangles look the same but their positions on the canvas are different. If we use a tuple <strong>(row index, col index)</strong>, where the indexes start from 1, to specify the top-left position of a shape on the drawing canvas, for all alignment settings, row index equals 1. It means that all shapes should be drawn from the first row. The following formulas show how you should calculate the column index. Note that the same rule applies to squares.

Left alignment: col_index = 1

Middle alignment: col_index = (canvas_width – side_length) / 2 + 1

Right alignment: col_index = canvas_width – side_length + 1

(middle alignment)

–AAAAA—

–AAAA—-

–AAA—–

–AA——

–A——-

———-

(right alignment)

—–AAAAA

—–AAAA-

—–AAA–

—–AA—

—–A—-

———-

<ol start="6">

 <li>Your program will then ask if the user want to do some rotations by typing R (for a 90-degreeclockwise rotation) or L (for a 90-degree anticlockwise rotation) and then pressing Enter. Note that the selection is case insensitive (i.e. R/r and L/l are accepted).</li>

</ol>

Type R/L to rotate clockwise/anti-clockwise. Use other keys to continue.

The following figures show the initial position of a left-aligned triangle and its new positions after being rotated 90 degrees, 180 degrees, 270 degrees, and 360 degrees, respectively. The same transformation rules apply to middle-aligned and right-aligned triangles. <strong>Note that all transformations should not change the current alignment setting i.e. if a triangle or a square is left-aligned, the rotated triangle or the zoomed square must also be left-aligned</strong>.

(A isosceles right triangle T at its initial position)

AAAAA—–

AAAA——

AAA——-

AA——–

A———

———-

(90 degrees clockwise rotation of T)

AAAAA—–

-AAAA—–

–AAA—–

—AA—–

—-A—–

———-

(180 degrees clockwise rotation of T)

—-A—–

—AA—–

–AAA—–

-AAAA—–

AAAAA—–

———-

(270 degrees clockwise rotation of T)

A———

AA——–

AAA——-

AAAA——

AAAAA—–

———-

(360 degrees clockwise rotation of T — T is drawn at its initial position)

AAAAA—–

AAAA——

AAA——-

AA——–

A———

———-

<ol start="7">

 <li>When users stop rotating the triangle, by typing any characters other than R and L and thenpressing Enter, your program will ask if they want to draw another triangle.</li>

</ol>

Draw another triangle (Y/N)?

If Y is selected, the program should accept user inputs and draw another triangle. If N is selected, it should go back to the main menu. Otherwise, an error message should be displayed. Note that the selection is also case insensitive.

Draw another triangle (Y/N)?

A

Unsupported option. Please try again!

Draw another triangle (Y/N)?

N

Please select an option. Type 4 to exit.

<ol>

 <li>Draw triangles</li>

 <li>Draw squares</li>

 <li>Update drawing canvas settings</li>

 <li>Exit</li>

</ol>

<ol start="8">

 <li>In the main menu, if the second option (Draw squares) is selected, the program will follow a similarworkflow when the first option (Draw triangles) is selected except that zooming (in and out) will be supported instead of rotations. <strong>Note that each time a square is zoomed in/out, its side length will be increased/decreased by one character. Once the square reaches its limit i.e. its side length equals to </strong>min(canvas width, canvas height) <strong>or 1, users cannot make it bigger or smaller, respectively. If they try to do so, nothing changes</strong>.</li>

</ol>

Please select an option. Type 4 to exit.

<ol>

 <li>Draw triangles</li>

 <li>Draw squares</li>

 <li>Update drawing canvas settings</li>

 <li>Exit</li>

</ol>

2

Side length:

5

Printing character:

B

Alignment (left, middle, right):

middle –BBBBB—

–BBBBB—

–BBBBB—

–BBBBB—

–BBBBB—

———-

<h1><a name="_Toc14110"></a>Type I/O to zoom in/out. Use other keys to continue.</h1>

I

–BBBBBB–

–BBBBBB–

–BBBBBB–

–BBBBBB–

–BBBBBB–

–BBBBBB–

Type I/O to zoom in/out. Use other keys to continue.

O

–BBBBB—

–BBBBB—

–BBBBB—

–BBBBB—

–BBBBB—

———-

Type I/O to zoom in/out. Use other keys to continue.

O

—BBBB—

—BBBB—

—BBBB—

—BBBB—

———-

———-

Type I/O to zoom in/out. Use other keys to continue.

Q

Draw another square (Y/N)?

<ol start="9">

 <li>The third option in the main menu is for changing the current canvas settings. Once the settings have been changed, your program will print out a confirmation message and the newest settings.</li>

</ol>

Please select an option. Type 4 to exit.

<ol>

 <li>Draw triangles</li>

 <li>Draw squares</li>

 <li>Update drawing canvas settings</li>

 <li>Exit</li>

</ol>

3

<h1><a name="_Toc14111"></a>Canvas width: 20</h1>

<h1><a name="_Toc14112"></a>Canvas height: 20</h1>

<h1><a name="_Toc14113"></a>Background character: +</h1>

<h1><a name="_Toc14114"></a>Drawing canvas has been updated!</h1>

Current drawing canvas settings:

– Width: 20

<h1><a name="_Toc14115"></a>– Height: 20</h1>

– Background character:


Please select an option. Type 4 to exit.

<ol>

 <li>Draw triangles</li>

 <li>Draw squares</li>

 <li>Update drawing canvas settings</li>

 <li>Exit</li>

 <li>To exit the program, users can choose the fourth option from the main menu. And the program should display a goodbye message.</li>

</ol>

Please select an option. Type 4 to exit.

<ol>

 <li>Draw triangles</li>

 <li>Draw squares</li>

 <li>Update drawing canvas settings</li>

 <li>Exit</li>

</ol>

4 Goodbye!

<strong>4       Example execution</strong>

Note that in the following example execution, we show both the input and output of the program. In the given test cases, the input and output are stored in different files. See Section 7 (Testing Before Submission) for more details.

—-WELCOME TO MY CONSOLE DRAWING APP—Current drawing canvas settings:

<ul>

 <li>Width: 10</li>

 <li>Height: 6</li>

 <li>Background character: –</li>

</ul>

Please select an option. Type 4 to exit.

<ol>

 <li>Draw triangles</li>

 <li>Draw squares</li>

 <li>Update drawing canvas settings</li>

 <li>Exit</li>

</ol>

5

Unsupported option. Please try again!

Please select an option. Type 4 to exit.

<ol>

 <li>Draw triangles</li>

 <li>Draw squares</li>

 <li>Update drawing canvas settings</li>

 <li>Exit</li>

</ol>

1

Side length:

20

Error! The side length is too long (Current canvas size is 10×6). Please try again. Side length:

5

Printing character:

A

Alignment (left, middle, right):

left AAAAA—–

AAAA——

AAA——-

AA——–

A———

———-

Type R/L to rotate clockwise/anti-clockwise. Use other keys to continue.

R

AAAAA—–

-AAAA—–

–AAA—–

—AA—–

—-A—–

———-

Type R/L to rotate clockwise/anti-clockwise. Use other keys to continue.

R

—-A—–

—AA—–

–AAA—–

-AAAA—–

AAAAA—–

———-

Type R/L to rotate clockwise/anti-clockwise. Use other keys to continue.

R

A———

AA——–

AAA——-

AAAA——

AAAAA—–

———-

Type R/L to rotate clockwise/anti-clockwise. Use other keys to continue.

R

AAAAA—–

AAAA——

AAA——-

AA——–

A———

———-

Type R/L to rotate clockwise/anti-clockwise. Use other keys to continue.

L

A———

AA——–

AAA——-

AAAA——

AAAAA—–

———-

Type R/L to rotate clockwise/anti-clockwise. Use other keys to continue.

L

—-A—–

—AA—–

–AAA—–

-AAAA—–

AAAAA—–

———-

Type R/L to rotate clockwise/anti-clockwise. Use other keys to continue.

L

AAAAA—–

-AAAA—–

–AAA—–

—AA—–

—-A—–

———-

Type R/L to rotate clockwise/anti-clockwise. Use other keys to continue.

L

AAAAA—–

AAAA——

AAA——-

AA——–

A———

———-

Type R/L to rotate clockwise/anti-clockwise. Use other keys to continue.

A

Draw another triangle (Y/N)?

Y

Side length:

6

Printing character:

B

Alignment (left, middle, right):

right —-BBBBBB

—-BBBBB-

—-BBBB–

—-BBB—

—-BB—-

—-B—–

Type R/L to rotate clockwise/anti-clockwise. Use other keys to continue.

L

—-B—–

—-BB—-

—-BBB—

—-BBBB–

—-BBBBB-

—-BBBBBB

Type R/L to rotate clockwise/anti-clockwise. Use other keys to continue.

L

———B

——–BB

——-BBB

——BBBB

—–BBBBB

—-BBBBBB

Type R/L to rotate clockwise/anti-clockwise. Use other keys to continue.

L

—-BBBBBB

—–BBBBB

——BBBB

——-BBB

——–BB

———B

Type R/L to rotate clockwise/anti-clockwise. Use other keys to continue.

A

Draw another triangle (Y/N)?

N

Please select an option. Type 4 to exit.

<ol>

 <li>Draw triangles</li>

 <li>Draw squares</li>

 <li>Update drawing canvas settings</li>

 <li>Exit</li>

</ol>

2

Side length:

8

Error! The side length is too long (Current canvas size is 10×6). Please try again. Side length:

4

Printing character:

C

Alignment (left, middle, right):

middle —CCCC—

—CCCC—

—CCCC—

—CCCC—

———-

———-

Type I/O to zoom in/out. Use other keys to continue.

I

–CCCCC—

–CCCCC—

–CCCCC—

–CCCCC—

–CCCCC—

———-

Type I/O to zoom in/out. Use other keys to continue.

I

–CCCCCC–

–CCCCCC–

–CCCCCC–

–CCCCCC–

–CCCCCC–

–CCCCCC–

Type I/O to zoom in/out. Use other keys to continue.

I

–CCCCCC–

–CCCCCC–

–CCCCCC–

–CCCCCC–

–CCCCCC–

–CCCCCC–

Type I/O to zoom in/out. Use other keys to continue.

O

–CCCCC—

–CCCCC—

–CCCCC—

–CCCCC—

–CCCCC—

———-

Type I/O to zoom in/out. Use other keys to continue.

O

—CCCC—

—CCCC—

—CCCC—

—CCCC—

———-

———-

Type I/O to zoom in/out. Use other keys to continue.

O

—CCC—-

—CCC—-

—CCC—-

———-

———-

———-

Type I/O to zoom in/out. Use other keys to continue.

O

—-CC—-

—-CC—-

———-

———-

———-

———-

Type I/O to zoom in/out. Use other keys to continue.

O

—-C—–

———-

———-

———-

———-

———-

Type I/O to zoom in/out. Use other keys to continue.

O

—-C—–

———-

———-

———-

———-

———-

<a href="#_Toc14110">Type I/O to zoom in/out. Use other keys to continue.                                                                                                                               </a>

<a href="#_Toc14111">Canvas width:                                                                                                                                                                                                         10</a>

<a href="#_Toc14112">Canvas height:                                                                                                                                                                                                        10</a>

<a href="#_Toc14113">Background character: *                                                                                                                                                                                         </a>

<a href="#_Toc14114">Drawing canvas has been updated!Current drawing canvas settings:- Width:                                                                           10</a>

<a href="#_Toc14115">– Height:                                                                                                                                                                                                                    10</a>




A

Draw another square (Y/N)?

N

Please select an option. Type 4 to exit.

<ol>

 <li>Draw triangles</li>

 <li>Draw squares</li>

 <li>Update drawing canvas settings</li>

 <li>Exit</li>

</ol>

3

– Background character: *

Please select an option. Type 4 to exit.

<ol>

 <li>Draw triangles</li>

 <li>Draw squares</li>

 <li>Update drawing canvas settings</li>

 <li>Exit</li>

</ol>

2

Side length:

6

Printing character:

E

Alignment (left, middle, right):

right ****EEEEEE

****EEEEEE

****EEEEEE

****EEEEEE

****EEEEEE

****EEEEEE

**********

**********

**********

**********

Type I/O to zoom in/out. Use other keys to continue.

A

Draw another square (Y/N)?

N

Please select an option. Type 4 to exit.

<ol>

 <li>Draw triangles</li>

 <li>Draw squares</li>

 <li>Update drawing canvas settings</li>

 <li>Exit</li>

</ol>

<ul>

 <li>Goodbye!</li>

 <li><strong>Important Notes</strong></li>

</ul>

Automatic tests will be conducted on your program by compiling, running, and comparing your outputs for several test cases with generated expected outputs. The automatic test will deem your output wrong if your output does not match the expected output, even if the difference is just having an <strong>extra space or missing a colon</strong>. Therefore, it is crucial that <strong>your output follows exactly the same format</strong>

<strong>shown in the examples above.</strong>

Also, use <strong>ONLY ONE </strong>Scanner object throughout your program. Otherwise the automatic tests may cause your program to generate exceptions and terminate. The reason is that in the automatic test, multiple lines of test inputs are sent all together to the program. As the program receives the inputs, it will pass them all to the currently active Scanner object, leaving the rest of the Scanner objects nothing to read and hence cause a run-time exception. Therefore, it is important that <strong>your program has only one Scanner object. </strong>Arguments such as “It runs correctly when I do the manual test, but fails under the automatic test” will not be accepted.

<ul>

 <li><strong>Assessment</strong></li>

</ul>

This project is worth 15% of the total marks for the subject.

Your Java program will be assessed based on correctness of the output as well as quality of code implementation.

<ul>

 <li><strong>Testing Before Submission</strong></li>

</ul>

You will find all input files and the expected output files in the Projects page on Canvas for you to use on your own. <strong>In this assignment, markers will use the same set of test data for marking</strong>. You should use them to test your code carefully and then submit your code on GitHub. Note that each commit you make is recorded in your GitHub repository. Details of how the submission works can be found in Section 8.

To test your code by yourself:

<ol>

 <li>Check your Java code files, and make sure you have the test input data files ready (e.g.,“txt”).</li>

 <li>Open a console, navigate to your project directory (where your .java classes reside), and run compileyour program: javac *.java (this command will compile all your java file in the current folder).</li>

 <li>Run command: java ConsoleDrawing 10 6 – &lt; input1.txt &gt; my-output1.txt (it runs the ConsoleDrawing using contents in “txt” as input and write the output to my-output1.txt). Note that the exact arguments “10 6 -” must be passed to the program because the given output files (e.g., output1.txt, output2.txt) were captured with the same arguments.</li>

 <li>Inspect the file my-output1.txt as it contains any errors your program execution may have encountered.</li>

 <li>Compare your result with the provided output file txt. Fix your code if they are different.</li>

 <li>Repeat steps 3-5 for all given input and output pairs. When you are satisfied with your project,commit your changes to GitHub.</li>

</ol>

<strong>Please follow the instructions in Lab-3 documentation if you want to use IDEs like</strong>

<strong>Eclipse.</strong>

<a href="#_ftnref1" name="_ftn1">[1]</a> https://canvas.lms.unimelb.edu.au/courses/105405/assignments/200112