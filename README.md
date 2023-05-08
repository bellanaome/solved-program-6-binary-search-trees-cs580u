Download Link: https://assignmentchef.com/product/solved-program-6-binary-search-trees-cs580u
<br>
<h3><u>Driver Code and Test Input Files</u></h3>

<h3>●       Provided Files</h3>

<ul>

 <li><a href="https://drive.google.com/open?id=1TbdYMIzWGmLufNoCYUKNl49jGc3zwwC2">c</a> //Driver Code</li>

</ul>

<h3><u>Grading Rubric</u></h3>

<strong><em>TOTAL: 30 points</em></strong>

<h2>●       Part 1,2,3:</h2>

<h2>○       Test 1 – Initialize the BST (1 point)</h2>

<h2>○       Test 2 – Insert into the BST (1 point)</h2>

<h2>○       Test 3 – Insert Duplicates(1 point)</h2>

<h2>○       Test 4 – Sorted data (3 points)</h2>

<h2>○       Test 5 – Search data (2 points)</h2>

<h2>○       Test 6 – Search for Missing data (2 points)</h2>

<h2>○       Test 7 – Clone and Compare trees (3 points)</h2>

<h2>○       Test 8 – Remove a value not found (1 points)</h2>

<h2>○       Test 9 – Remove Leaf (2 points)</h2>

<h2>○       Test 10 – Remove 1 child node  (2 points)</h2>

<h2>○       Test 11 – Remove 2 child node with leaf (2 points)</h2>

<h2>○       Test 12 – Remove 2 child node with short circuit (2 points)</h2>

<h2>○       Test 13 – Remove 2 child root (2 points)</h2>

<h2>○       Test 14 – Remove 1 child root (2 points)</h2>

<h2>○       Test 15 – Remove Leaf root (1 points)</h2>

<h2>○       Test 16 – Clean up memory. Delete all trees (3 points)</h2>

<h2>●       Style Guidelines and Memory Leaks</h2>

<h2>○       <em>You will lose significant points for the following:</em></h2>

<h2>■       Makefile does not have requested format and labels (-10 points)</h2>

<h2>■       Does not pass Valgrind Tests (-5 points)</h2>

<h2>■       Does not follow requested program structure and submission format (-10 points)</h2>

<h3><u>Guidelines</u></h3>

This is an individual assignment. You must do the vast majority of the work on your own. It is permissible to consult with classmates to ask general questions about the assignment, to help discover and fix specific bugs, and to talk about high level approaches in general terms. It is not permissible to give or receive answers or solution details from fellow students.




You may research online for additional resources; however, you may not use code that was written specifically <em>to</em> solve the problem you have been given, and you may not have anyone else help you write the code or solve the problem. You may use code snippets found online, providing that they are appropriately and clearly cited, within your submitted code.

<em> </em>

<em>By submitting this assignment, you agree that you have followed the above guidelines regarding collaboration and research.</em>




<em> </em>

<em> </em>




<h1>Part 1: BST</h1>




<ul>

 <li>Create a link based Binary Search tree composed of a Node and Tree struct. You should have a header file, bst.h, with the following:

  <ul>

   <li>Node struct containing left, right, and parent pointers, in addition to holding a Data struct value.</li>

   <li>Tree struct containing a pointer to the root of the tree.</li>

   <li>A function declaration for a function that allocates a tree, and initializes the root to NULL;</li>

   <li>A function declaration for a function that takes a Data struct as a parameter, allocates a node, and initializes the left, right, parent fields to NULL.</li>

  </ul></li>

 <li>You should also have a source file, bst.c, that implements the two declared functions:

  <ul>

   <li>Tree * newTree();</li>

   <li>Node * newNode(Data d, Node * parent);</li>

  </ul></li>

 <li>Test your functions and structure to ensure everything is initialized correctly by creating a Tree and adding a root to it.</li>

</ul>

<h1>Part 2: BST Operations</h1>

<ul>

 <li>Alter your tree struct declaration in your header file to contain the function pointers for insert, search, removeData. Implement the operations in your BST.c file.</li>

 <li>INSERT:

  <ul>

   <li>Create a function, Data * (*insert)(Tree * bst, Data value), that inserts into the tree – Helpful hints:

    <ul>

     <li>Return a pointer to the Data value inserted into the tree</li>

     <li>Make sure you check for the special case of an empty tree [if(bst-&gt;root == NULL)],</li>

     <li>After checking for the root, use a separate helper function to insert a value into the tree, Data * insertNode(Node * node, Data value), that you can use for the recursive call</li>

     <li>If the value is already in the tree, return NULL</li>

    </ul></li>

   <li>SEARCH:

    <ul>

     <li>Create a function, Data * (*search)(Tree * bst, Data value), that searches for a value in the tree. Return a pointer to the Data object if found – Helpful hints:

      <ul>

       <li>Make sure you check for the special case of an empty tree [if(bst-&gt;root == NULL)],</li>

       <li>After checking for the root, use a separate helper function to search the tree, Node * searchNode(Node * node, Data value), that you can use for the recursive call</li>

      </ul></li>

     <li>REMOVE:

      <ul>

       <li>Create a function, void (*removeData)(Tree * bst, Data value), that removes a value from the tree – Helpful hints:

        <ul>

         <li>Use your (hopefully) working search auxiliary function to find the node you need to delete

          <ul>

           <li>Your auxiliary search function can return a node pointer, and you primary search function returns the data from that pointer.</li>

          </ul></li>

         <li>You will have 3 cases requiring 3 separate functions:

          <ul>

           <li>remove a leaf node : void removeLeaf(Tree * bst, Node * d_node);</li>

           <li>remove a node with 1 branch: void shortCircuit(Tree * bst, Node * d_node)</li>

           <li>remove a node with 2 branches: void promotion(Tree * bst, Node * d_node)</li>

          </ul></li>

         <li>You will need to use your removeLeaf() and shortCircuit() functions in your promotion function, so make sure they are working before starting on the promotion function.</li>

        </ul></li>

      </ul></li>

    </ul></li>

  </ul></li>

</ul>

Part 3: Testing Your Tree

<ul>

 <li>In the driver code provided below, we do the following to test your tree:

  <ul>

   <li>Using your insert function, insert the following values into your tree (in this order)

    <ul>

     <li>5,3,10,4,8,2,1,7,9,6,12,11,13</li>

    </ul></li>

   <li>The following will be tested:

    <ul>

     <li>Insertion of the above value set</li>

     <li>Search on each value</li>

     <li>Search on a value not in the tree</li>

     <li>Deletion of each value using the following algorithms

      <ul>

       <li>Delete leaf</li>

       <li>Delete 1 child</li>

       <li>Delete 2 child</li>

       <li>Delete root</li>

       <li>Delete 1 child root</li>

       <li>Delete leaf root</li>

      </ul></li>

     <li>You will also need to implement the following:

      <ul>

       <li>Tree * (*clone)(Tree*): Takes a tree and uses preorder traversal algorithm to return a clone of the tree</li>

       <li>int (*compare)(Tree*, Tree*): Takes a tree and uses preorder traversal algorithm to determine if the trees are equal</li>

       <li>void (*sort)(Tree *, Data *): Takes a tree and a data array buffer as parameters, and fills the buffer with the tree data in sorted order using the inorder traversal algorithm.</li>

       <li>void (*delete)(Tree * bst): Add a post-order deleteTree() function that deletes all nodes and the tree

        <ul>

         <li>Remember, post order only deletes leafs, so you need only call deleteLeaf()</li>

        </ul></li>

       <li><em>Hint: Each of the above functions is easier to implement if you use an auxiliary recursive function</em></li>

      </ul></li>

    </ul></li>

  </ul></li>

</ul>




Part 4 – Submission




<ul>

 <li>Required code organization:

  <ul>

   <li>c – contains the driver code, and executable program code</li>

   <li>c/h – Your header file should have (at minimum) the following function declarations:

    <ul>

     <li>Data struct

      <ul>

       <li>value (int)</li>

      </ul></li>

     <li>Node struct

      <ul>

       <li>data (Data)</li>

       <li>left (Node *)</li>

       <li>right (Node *)</li>

      </ul></li>

     <li>Tree struct

      <ul>

       <li>root (Node *)</li>

       <li>Data * (*insert)(Tree *, Data);</li>

       <li>Data * (*search)(Tree * bst, Data value);</li>

       <li>void (*sort)(Tree *, Data *);</li>

       <li>int (*compare)(Tree *t, Tree * copy);</li>

       <li>Tree * (*clone)(Tree *t);</li>

       <li>void (*delete)(Tree * bst);</li>

       <li>void (*removeData)(Tree * bst, Data value);</li>

      </ul></li>

     <li>Node * newNode(Data d, Node * parent);</li>

     <li>Tree * newTree();</li>

     <li>makefile

      <ul>

       <li><em>You must have the following labels in your makefile:</em>

        <ul>

         <li>all – to compile all your code to an executable called ‘<strong>program6</strong>’ (no extension). <strong>Do not run</strong>.</li>

         <li>run – to compile if necessary and run</li>

         <li>checkmem – to compile and run with valgrind</li>

         <li>clean – to remove all executables and object files</li>

        </ul></li>

       <li>While inside your program 6 folder, create a zip archive with the following command

        <ul>

         <li>zip -r &lt;yourid&gt;_program6 &lt;files to include&gt;

          <ul>

           <li>This creates an archive of all file and folders in the current directory called &lt;yourid&gt;_program6.zip</li>

           <li><strong>Do not zip the folder itself, only the files required for the program</strong></li>

          </ul></li>

         <li>Submit the program as done for previous assignments.</li>

        </ul></li>

      </ul></li>

    </ul></li>

  </ul></li>

</ul>