# 1. Commands
*Enter commands in MATLAB to perform calculations and create variables.*

Session 1: Enter Commands \\
*   'Enter' runs a command
*   Semicolon stops answer being displayed in the command window after command is executed
* An unspecified output variable gives a default variable ```ans```
* Workspace shows all active variables
* Can recall previous commands to the current command line using the up arrow

Session 2: Name Variables \\
* Variable names **must** start with a letter and only contain letters, numbers and/or underscores

Session 3: Save and Load Variables \\
* Can save variables in the workspace to a MAT-file using the command ```save``` (syntax: ```>> save filename.mat```)
* To load a MAT-file use command ```load``` (```>> load filename.mat```)
* To clear workspace use command ```clear```
* To clear command window but keep variables in the workspace use command ```clc```
* Can view the contents of a variable by entering its name into the command window (```>> myvariable ```)
* To load and save specific variables use ```load``` and ```save``` with extra inputs. Example: To save a specific variable *myvar* (```>> save filename.mat myvar```) and to load (```>>load filename.mat myvar```)

Session 4: Use Built-In Functions and Constants \\
* MATLAB contains built-in constants (e.g. Pi ```pi```, i ```i```)
* MATLAB contains built-in functions (e.g. Sine ```sin```, absolute value ```abs```, Eigenvalues ```eig```, Square Root ```sqrt```)
* Pass inputs to functions using parentheses ```sin(x)```
* Command window output shows four decimal places, use ```>> format long myvar``` to display more or ```>> format short myvar``` to display default


# 2. MATLAB Desktop and Editor
*Write and save your own MATLAB programs.*

Session 1: MATLAB Desktop and Editor \\
* A live script can be used to organise a sequence of commands and run many outputs at once
* 'New Live Script' can be found in the toolbar
* Script features options for text and code (like Colab!)
* Saving a live script saves the code, output, and descriptions

Session 2: The MATLAB Editor \\
* Grey box is for input
* Output is shown in the right-hand box after running script

Session 3: Run Scripts \\
* Section breaks can be used to create sections which can be run seperately

Session 4: Debug MATLAB Code
* Errors and warnings are displayed in the left margin of the code and are also highlighted in red and yellow respectively within the code


# 3. Vectors and Matrices
*Create MATLAB variables that contain multiple elements.*

Session 1: Manually Enter Arrays \\
* All MATLAB variables are arrays. So, each numeric variable can contain multiple numbers. You can store related data in one variable by using an array.
* Therefore, scalars are represented by a 1x1 array
* Arrays with multiple elements can be made using square brackets ```[]```, (```x = [3 5]```)
* Numbers in rows are seperated by spaces, columns are seperated by semicolons
```x = [1 2]``` or ```x = [1; 2]```
* Combining spaces and semicolons allows matrices to be inputted
* Calculations can be performed within square brackets

Session 2: Create Evenly Spaced Vectors \\
* If creating a long vector with all elements equally spaced e.g. ```x = [1 2 3 4 5]```, a more efficient method of input is to use a colon ```>> x = 1:5``` (note square brackets are not needed for this method)
* To specify the interval between elements use format ```x = start number:interval size:end number``` e.g. ```>> x = [1:3:10]``` >>> ```x = [1 4 7 10]```
* If you know the number of elements you want in a vector (instead of the spacing between each element), you can use ```linspace``` (linearly spaced) as ```>> x = linspace(first, last, number_of_elements)```
* To do the above points for a column vector, use the transpose function ```'``` as ```>> x = (1:3:10)'``` (note parentheses are needed for this) or the sequence ```>> x = linspace(first, last, number_of_elements); >> x = x'```

Session 3: Create Arrays with Functions
* MATLAB contains many functions that create commonly used matrices, such as matrices of random numbers ```>> x = rand(rows, columns)``` e.g. ```>> x = rand(3, 4)``` creates a 3x4 matrix, x
* Other useful functions: ```>> x = zeros(n, m)``` creates a matrix of zeroes, ```>> x = ones(n, m)``` creates a matrix of ones
* To determine the size of a matrix, use ```>> size(x)```
* To create a new matrix with the same size as another, you can use ```size``` within a function e.g. ```>> y = rand(size(x))```


# 4. Array Indexing and Modification
*Use indexing to extract and modify rows, columns, and elements of MATLAB arrays.*

Session 1: Indexing \\
* Indexing describes referring to an element(s) in an array, and aids with extracting and modifying specific values
* Position of an element within an array is its index e.g. ```x = [2 4 6 8 10]``` positions' ```[1 2 3 4 5]``` therefore the 2nd element of x is 4, 3rd is 6 etc.
* To call a specific element use ```>> x(n)``` with n referring to the index of the element desired
* A called index can be reassigned a value using the operator ```=``` e.g. ```>> x(2) = 5``` will change the 2nd element to the value 5
* A range of values can be extracted using a colon ```>> x(first:last)``` e.g. ```>> x(2:5)``` will extract the 2nd through to the 5th element
* In a matrix, to extract a single element use ```>> x(row, column)```
* To extract entire rows or columns a colon can be used ```>> x(:, column)``` for an entire column or ```>> x(row, :)``` for an entire row
* Variables can be assigned extractions using ```>> myvar = arrayvar(row, col)```

Session 2: Index into Arrays \\
* ```end``` references the last element in a row or column e.g. ```>> x = A(end, 2)``` extracts the element in the final row of column 2 from matrix A and assigns it to variable x
* Arithmetic can be used with ```end``` to describe elements of end-n value e.g. ```>> x = A(end-1, end-4)``` to find the values second to last and fourth from last
* If using only one index to extract an element from a matrix, MATLAB will by default count through each column until it reaches the specified index e.g. ```>> A = [1 2 3; 4 5 6]; >> A(4)``` will return ```5```
* Variables can also be used as an index e.g. ```>> myvar = 3; >> A(myvar)``` will extract the third element of A

Session 3: Extract Multiple Elements \\
* Colons extract entire rows or columns
* Colons used between values extract a range of elements e.g. ```>> A(3:6, :)``` extracts all columns in rows 3 to 6
* Ranges can be used for a single index when extracting elements from matrices e.g. ```>> A(1:8)``` will extract the range of elements 1 to 8 by counting through the columns of A
* Indices can also be non-consecutive numbers e.g. ```>> A([1 3 5])``` will return the first, third and fifth elements (note the use of square brackets within the parentheses)

Session 4: Change Values in Arrays \\
* Elements can be changed in a vector by combining indexing with assignment e.g. ```>> A(n) = newvalue``` changes the nth element to a new value. This can be used with any type of indexing
* Indexing and assignment can be combined e.g. ```>> A(1) = A(2)``` changes the value of the first element to the same as the second


# 5. Array Calculations
*Perform calculations on entire arrays at once.*

Session 1: Perform Array Operations on Vectors
* Scalar values can be added to all elements of an array e.g. ```>> x = [n m p]; >> y = x + 2``` >>> ```y = [n+2 m+2 p+2]```
* Two arrays of the same size can also be added ```>> z = x + y``` >>> ```z = [2n+2 2m+2 2p+2]```
* Division and multiplication operators can also be applied this way ```>> y = 2*x``` or ```>> y = x/2```
* Basic statistical functions can also be applied to vectors for a single output e.g. ```>> A_max = max(A)``` will determine the maximum value
* Mathematical operations can be performed on entire arrays such as ```sqrt``` and ```round```
* The operator ```*``` performs **matrix** multiplication, therefore will display an error if used to multiply two equally sized arrays (for example (n-by-m) * (n-by-m)). To perform an **element-wise** multiplication use ```.*```
* There are many compatible sizes of arrays (above examples showing two arrays of the same size and a scalar * array), for example ```x = [1 2; 3 4; 5 6; 7 8].*[1;2;3;4]``` is a compatible multiplication


# 6. Function Calls
*Call functions with multiple outputs.*

Session 1: Request Multiple Outputs in Function Calls
* Recall that the size of an array can be assigned to a variable e.g. ```>> sizeA = size(A)```
* This can include receiving two outputs using format ```>> [xrow, xcol] = size(X)```
* Using this same set-up, the max value of an array and its index can be extracted using format ```>> [xMax, xIndex] = max(X)```
* A tilde ```~``` to ignore outputs in functions e.g. ```>> [~, xcol] = size(X)``` returns only the column size


# 7. Documentation
*Use the MATLAB documentation to learn more about MATLAB features.*

Session 1: MATLAB Documentation \\
* The MATLAB documentation contains information about MATLAB functions and capabilities
* Documentation can be found in the MATLAB application under the help button

Session 2: Use MATLAB Documentation \\
* Documentation can also be found by using the function ```doc``` in the format ```>> doc functionname ```
* Phrases can also be used in this e.g. ```>> doc uniformly distributed numbers```


# 8. Plots
*Visualize variables using plotting functions.*

Session 1: Plot Vectors \\
* Two vectors of the same length can be plotted against each other using ```>> plot(x, y)```
* Colour, line style and marker of the plot can be specified in double quotes as an input into the plot function ```>> plot(x, y, "colour line style marker")```
* Graphs can be plotted on top of each other using ```hold on``` e.g. ```>> plot(x1, y1); >> hold on; >> plot(x2, y2)```
* To stop plotting graphs together use ```hold off```
* You can optionally set properties using one or more name-value arguments, which consist of an argument name and an associated value e.g. ```>> plot(x, LineWidth = 3)``` setting the line width to 3
* This can be used in addition to colour, line style and marker in format ```>> plot(x, y, "colour linestyle marker", Name = value)```
* ```plot``` creates line graphs, however there are other functions to create different types of graph e.g. ```histogram```
* Note, for versions of MATLAB older than R2021a, use commas to separate each name and value, and enclose ```Name``` in quotes e.g. ```>> plot(x, y, "LineWidth",3)``` instead of ```>> plot(x, y, LineWidth = 3)```

Session 2: Annotate Plots
* Annotations can be added to plots using plot annotation functions e.g. ```>> title("Title Name")```
* Axes can be labelled using ```>> xlabel("X Label")``` and ```>> ylabel("Y Label")```
* Legends can be added using ```>> legend("a", "b", "c", ... , "n")```


# 9. Data Imports
*Bring data from external files into MATLAB.*

Session 1: Import Tool \\
* MAT, jpeg, csv and txt files can be imported into MATLAB
* If importing csv files, missing data entries are automatically filled with NaN (Not a Number)

Session 2: Import Data as a Table \\
* To extract a variable from a table, use dot notation e.g. ```>> table.VariableName```
* If you are working with a table, you might want to keep related data together. Instead of creating separate variables, you can append the result of a calculation to a table e.g. ```>> data.HeightMeters = data.HeightYards*0.9144```
* If the variable ```HeightMeters``` doesn't already exist, MATLAB will create a new vaiable ```HeightMeters``` in the table ```data```
* You can interact with tables (for example, sorting A-Z) in the output pane of a live script
* To save these table modifications use the 'Update Code' button
* Dot notation is used to extract table variables. For extracting rows use regular array indexing e.g. ```>> myvar = table(row, col)```


# 10. Logical Arrays
*Use relational operators and logical indexing to extract elements of interest from MATLAB arrays.*

Session 1: Logical Indexing
* Relational operators, such as >, <, ==, and ~= perform comparisons between two values. The outcome of a comparison for equality or inequality is a boolean (either 1 (true) or 0 (false))
* Questions posed using relational operators can be assigned to a variable e.g. ```>> x = a < b``` returns ```x = 0``` (false) or ```x = 1``` (true)
* Can compare arrays to single scalar values (i.e. a comparison of each value in the array to the scalar) which returns a logical array of equal size
* A logical array can be used as an array index, where array elements whose corresponding index is 1 (true) can be extracted e.g. ```>> myvar = array(array </>/==/=~ n)```
* Logical indexing can also be used for two different arrays ```>> myvar = array1(array2 </>/==/=~ n)```
* Logical indexing can be used to reassign values in an array ```>> array(array </>/==/=~ n) = m```
* Logical comparisons can be combined using logical operators AND ```&``` or OR ```|``` e.g. finding elements inbetween two values ```>> myvar = array(array < n & array > m)``` or finding values that fit two seperate conditions ```>> myvar = array(array < n | array > m)```


# 11. Programming
*Write programs that execute code based on specified conditions.*

Session 1: Programming Constructs \\
* Recall scripts allow us to execute commands in chronological order, from beginning to end
* Programming edits the behaviour of a script, allowing certain commands to be run for certain conditions
* If, else, elseif, and for statements can control which commands are executed for specified conditions

Session 2: Decision Branching \\
* ```If``` blocks execute only if the condition specified is true
* If the condition is not true an ```else``` block can be added to execute alternative code
* ```end``` is used to end any statements' blocks
* More conditions can be added to the ```if``` block using ```elseif```

Session 3: For Loops \\
* ```for``` can be used to execute code that is reliant on a loop counter
* This can be used in the format ```>> for counter = 1:n; >> commands; >> end```
* If ```n``` is unknown, the function ```length(vector_name)``` can be used
* ```drawnow``` updates plots after each iteration of a ```for``` loop and allows for playback of the plot animation


# 12. Final Project - See Worksheets

* Stellar Motion
> * Calculating and plotting the wavelength of different star's spectrums, locating the hydrogen alpha line, calculating the redshift of the star

* Compare Stellar Spectra
> * Calculating all stars' spectra at once using programming, plotting onto one graph
