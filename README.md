Download Link: https://assignmentchef.com/product/solved-kit205-week6-tutorial
<br>
In this tutorial you will be implementing quicksort for strings.  In addition, you will practice some string functions and input redirection, which can help with testing.

<h1>Strings</h1>

<table width="170">

 <tbody>

  <tr>

   <td width="170"><em>This typedef is not required, we could just continue using </em><em>char*</em><em>However, when we make </em><em>an array of strings, this would become </em><em>char**</em><em>, which can get confusing. </em><em>Instead of </em><em>char**</em><em>, we can now write </em><em>String*</em><em>, which is more readable </em></td>

  </tr>

 </tbody>

</table>

<ol>

 <li>Create a new empty project</li>

 <li>Add a file called <em>c</em> with a <em>main</em> method 3. Add the following typedef typedef char *String;</li>

 <li>Add a variable called <em>strings</em> that is a <em>String</em> pointer that can be used to store an array of strings</li>

 <li>Add a variable called <em>buffer</em> that is large enough to store a 100 character string</li>

 <li>Add some code to prompt the user for the number or strings and store the result in a variable, <em>n</em></li>

 <li>Initialise the <em>strings</em> array so that it has size <em>n</em></li>

 <li>Add a for loop that reads <em>n</em> strings into <em>buffer</em></li>

 <li>Now add the following code (within the for loop) to copy from the buffer into the array</li>

</ol>

strings[i] = (String)malloc(strlen(buffer) + 1);  strcpy(strings[i], buffer);

<ol start="10">

 <li>Finally, add another loop to print the array.</li>

</ol>

Make sure that you test and understand this string code before continuing.

<ol start="11">

 <li>Add a loop to free memory for all of the strings and the string array</li>

</ol>

<h1>Input Redirection</h1>

We want to test our sorting code with a large number of strings.  Like these 100 for example:

sausage blubber pencil cloud moon water computer school network hammer walking violently mediocre literature chair two window cords musical

zebra

xylophone penguin home dog final ink teacher fun website banana uncle softly mega ten

awesome

attatch blue internet bottle tight

zone

tomato prison hydro cleaning telivision send frog cup book zooming falling evily gamer lid juice moniter captain bonding loudly thudding guitar shaving hair soccer water racket table late media desktop flipper club flying smooth monster purple guardian bold hyperlink presentation world national   comment element magic lion sand crust toast jam hunter forest foraging

silently           tawesomated joshing

pong sponge rubber




<ol start="12">

 <li>Choose <em>Add New Item </em>from the <em>Project</em> menu (or right click in the <em>Solution Explorer</em> pan). Select <em>C++|Utility|Text File (.txt)</em> as the type and change the name to <em>txt</em>.  Click <em>Add</em>.</li>

 <li>Copy the words above into the file and on a new line at the beginning of the file add the number of words: 100. Save the file.</li>

 <li>Open the <em>Project Properties</em> dialog (accessed from the <em>Project</em> menu). Go to Configuration <em>Properties|Debugging</em> and add <em>&lt;“$(ProjectDir)input.txt”</em> to the <em>Command Arguments</em> Click <em>Apply</em>.</li>

 <li>Now run your program again.</li>

</ol>

You should see that the program now runs without any input from you.  The <em>&lt;</em> redirects standard input so that it comes from the file, instead of from the keyboard.

<h1>Quicksort</h1>

Next we are going to write a quicksort function for strings.  The function prototype will be: void quicksort(String *a, int first, int last);

<em>a</em> is the array of strings, <em>first</em> is the first index to be sorted and <em>last</em> is the last index to be sorted.  Initially the indices will be 0 and n-1 for an n element array.

<ol start="16">

 <li>Implement the quicksort function using the following <em>pseudo-code</em> as a guide</li>

</ol>

(remember that you will need to use the <em>strcmp</em> function in your implementation):

quicksort(a,first,last):      if (first&lt;last):

// use last element as a pivot            i=first; j=last-1          while i&lt;j:                    while i&lt;last and a[i]&lt;a[last]:

i


while j&gt;=first and a[j]&gt;a[last]:

j–                if i&lt;j:

swap(a[i],a[j])

swap(a[i],a[last])            quicksort(a,first,j)      quicksort(a,i+1,last)




<ol start="17">

 <li>Modify you main method so that the quicksort function is called after reading the strings and before printing them. Check that the result is correct.</li>

 <li>Now modify your code so that it uses the median-of-three method for choosing a pivot.</li>

 <li>If you get time, modify your code so that it switches to insertion sort when the number of elements is less than some threshold.</li>

</ol>





