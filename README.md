Download Link: https://assignmentchef.com/product/solved-cs1331-homework-12-pokemon-the-sequel
<br>
<h1>Problem Description</h1>

Having now solved the Pokemon health crisis, word of your programming ability quickly spreads throughout the land like a cool seed in The Game of Life. One day, you receive an email:

Hello there! Welcome to the world of POKEMON! My name is OAK! People call me the POKEMON PROF!

This world is inhabited by creatures called POKEMON! For some people, POKEMON are pets. Others use them for fights. Myself…I study POKEMON as a profession.

You soon learn that Oak is a professor at “Georgia Tech University”, which, he assures you, is a well known school. He wants you to help him write software to catalog and organize Pokemon so he can better research them. At first you’re skeptical, but once he promises you meal swipes, you promptly get to programming.

<h1>Solution Description</h1>

For this assignment, create the following files:

<ul>

 <li>java</li>

 <li>java</li>

 <li>java</li>

</ul>

<strong>PokemonSpecies Class:</strong>

In the world of Pokemon – all species of Pokemon (the equivalent of animals in this world) have been assigned a number for ease of reference and sorting. This representation of a PokemonSpecies, therefore, should implement the <a href="https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/lang/Comparable.html">Comparable interface</a>. A PokemonSpecies is “greater” when it has a higher speciesNumber; a PokemonSpecies is “lesser” when it has a lower speciesNumber.

<em>Variables</em>:

<ul>

 <li>speciesNumber, an int that represents the specific species of a given PokemonSpecies. Once set, this should not be changeable outside this class.</li>

 <li>speciesName, a String holding the name of the species. Once set, this should not be changeable outside this class.</li>

 <li>speciesNickname a String holding the nickname of the PokemonSpecies</li>

 <li>description a String holding a description of the PokemonSpecies.</li>

</ul>

<em>Constructors</em>:

<ul>

 <li>PokemonSpecies(String speciesName, int speciesNumber, String speciesNickname, String description)

  <ul>

   <li>Sets speciesName, speciesNumber, speciesNickname, and description</li>

  </ul></li>

 <li>PokemonSpecies(String speciesName, int speciesNumber)

  <ul>

   <li>Sets speciesName and speciesNumber. speciesNickname and description should be set to null.</li>

  </ul></li>

</ul>

<em>Methods</em>:

<ul>

 <li>int compareTo(PokemonSpecies other)</li>

 <li>boolean equals(Object other) PokemonSpecies are considered equal if they have the same speciesName and speciesNumber.</li>

 <li>int hashCode() Write a proper hashCode for PokemonSpecies that considers the proper fields (Hint: Look at equals)</li>

 <li>String toString() Should return “[speciesNumber]: [speciesName], the [speciesNickname] Pokemon.</li>

</ul>

[speciesDescription].”

<ul>

 <li>Getters for all fields.</li>

 <li>Setters for speciesNickname, description.</li>

</ul>

<strong>AbstractDex Class:</strong>

This class should be generic. The generic type should be bounded such that you can perform searching and sorting operations on a List of any generic type that can be sorted. We will refer to the generic as T but you can name it what you want as long as you follow the proper conventions. Because this simply serves as a base of reusable code for any type of dex, it should be abstract.

<em>Instance Variables</em>:

<ul>

 <li>ArrayList&lt;T&gt; entries An ArrayList of objects that are comparable to each other.</li>

 <li>boolean sorted A boolean value storing whether or not entries have already been sorted by the dex.</li>

</ul>

<em>Constructors</em>:

<ul>

 <li>AbstractDex() Initializes entries to an empty ArrayList <em>Methods</em>:</li>

 <li>void insertionSort() sorts entries using the insertionSort() algorithm taught in class. Sets sorted to true</li>

 <li>void selectionSort() sorts entries using the selectionSort() algorithm taught in class. Sets sorted to true.</li>

 <li>int binarySearch(T element) searches entries for the passed in element using the binary search algorithm taught in class, returning its index if found or -1 if not found or sorted is false. DO NOT USE JAVA’S BUILT IN indexOf() METHOD.</li>

 <li>void addToDex(T newElement) If there is not already an equivalent element in entries, as determined by compareTo(), add newElement to the end of entries and set sorted to false.</li>

 <li>boolean equals(Object other) Write a proper equals method for AbstractDex. Two AbstractDex objects are considered equal if they have the same entries. For comparison, you can use ArrayList’s equals() method.</li>

 <li>int hashCode() Write a proper hashCode for a AbstractDex, using only the proper fields. (Hint: look at equals). You can use ArrayList’s hashCode() method.</li>

 <li>String toString() Should loop through each entry and call it’s toString(). Separate the outputs with newline characters. An example of what this should look like can be found in the sample tests.</li>

 <li>Getters for entries and sorted.</li>

 <li>Setter for entries.</li>

</ul>

<strong>Pokedex Class:</strong>

Is a concrete subclass of AbstractDex which holds PokemonSpecies only (Hint: how can we extend AbstractDex to only allow PokemonSpecies) <em>Constructors</em>:

<ul>

 <li>Pokedex() initializes entries to an empty ArrayList</li>

 <li>Pokedex(ArrayList&lt;PokemonSpecies&gt; initialEntries) initializes entries with the elements in the passed in List.</li>

</ul>

<strong>Testing your code:</strong>

If you want to test out your own code before submitting we recommend creating a separate java file and implementing a main method there. You can then create new animals and test your methods. Below is some sample testing code. <strong>These tests are not comprehensive!</strong>

<table width="632">

 <tbody>

  <tr>

   <td width="632">Pokedex myPokedex = <strong>new </strong>Pokedex();PokemonSpecies carl = <strong>new </strong>PokemonSpecies(“Carl”, 1, “Head TA”,“Its Mixtapes are said to be too hot for the average listener”); System.out.println(carl);<em>// 1: Carl, the Head TA Pokemon. Its Mixtapes are said to be too hot for the average listener.</em>PokemonSpecies karl = <strong>new </strong>PokemonSpecies(“Karl”, 2, “Spooky TA”,“It is said Karl can be found lurking in Klaus during spooktober”);PokemonSpecies qarl = <strong>new </strong>PokemonSpecies(“Qarl”, 3, “Checkstyle TA”,“Qarl likes to remind students to checkstyle their work”);System.out.println(qarl.compareTo(karl));<em>// positive number </em>myPokedex.addToDex(karl); myPokedex.addToDex(qarl); myPokedex.addToDex(carl); myPokedex.insertionSort();System.out.println(myPokedex.binarySearch(carl));<em>// 0</em>System.out.println(myPokedex.binarySearch(karl));<em>// 1</em>System.out.println(myPokedex.binarySearch(qarl));<em>// 2</em>Pokedex secondPokedex = <strong>new </strong>Pokedex();secondPokedex.addToDex(qarl); secondPokedex.addToDex(carl); secondPokedex.addToDex(karl); secondPokedex.selectionSort();System.out.println(myPokedex.binarySearch(carl));<em>// 0</em>System.out.println(myPokedex.binarySearch(karl));<em>// 1</em>System.out.println(myPokedex.binarySearch(qarl));<em>// 2</em>System.out.println(myPokedex.equals(secondPokedex));<em>// true</em>System.out.println(myPokedex);<em>/*</em><em>1: Carl, the Head TA Pokemon. Its Mixtapes are said to be too hot for the average listener.</em><em>2: Karl, the Spooky TA Pokemon. It is said Karl can be found lurking in Klaus during spooktober.</em><em>3: Qarl, the Checkstyle TA Pokemon. Qarl likes to remind students to checkstyle their work. */</em></td>

  </tr>

 </tbody>

</table>

Feel free to create your own tests in the main method! Try to write tests for the remaining methods in the file!

<h1>Rubric</h1>

<ul>

 <li>[35] PokemonSpecies

  <ul>

   <li>[5] Correct Fields</li>

   <li>[5] Correct Constructors</li>

   <li>[5] equals(Object)</li>

   <li>[5] compareTo(PokemonSpecies)</li>

   <li>[5] hashCode()</li>

   <li>[5] toString()</li>

   <li>[5] Getters and Setters</li>

  </ul></li>

 <li>[60] AbstractDex

  <ul>

   <li>[5] Generic with correct type bounds</li>

   <li>[4] Correct Constructor</li>

   <li>[1] Correct Field</li>

   <li>[10] insertionSort()</li>

   <li>[10] selectionSort()</li>

   <li>[10] binarySearch(T element)</li>

   <li>[5] addToDex(T element)</li>

   <li>[5] equals(Object)</li>

   <li>[5] hashCode()</li>

   <li>[5] toString()</li>

  </ul></li>

 <li>[5] Pokedex

  <ul>

   <li>[5] Correct Constructors</li>

  </ul></li>

</ul>

<h1>Allowed Imports</h1>

<ul>

 <li>To prevent trivialization of the assignment, you are only allowed to import the following class:</li>

</ul>

<strong>– </strong>java.util.ArrayList

<h1>Javadocs</h1>

For this assignment, you will be commenting your code with Javadocs. Javadocs are a clean and useful way to document your code’s functionality. For more information on what Javadocs are and why they are awesome, the <a href="http://www.oracle.com/technetwork/java/javase/documentation/index-137868.html">online overview</a> for them is extremely detailed and helpful.

You can generate the javadocs for your code using the command below, which will put all the files into a folder called javadoc:

$ javadoc *.java -d javadoc

The relevant tags that you need to include are @author, @version, @param, and @return. Here is an example of a properly Javadoc’d class:

<table width="632">

 <tbody>

  <tr>

   <td width="632"><strong>import </strong>java.util.Scanner;<em>/**</em>*       This class represents a Dog object<em>.</em>*       <strong>@author </strong>George P<em>. </em>Burdell*       <strong>@version </strong><em>1.0</em><em>*/ </em><strong>public class </strong>Dog {<em>/**</em>*       Creates an awesome dog <em>(</em>NOT a dawg<em>!) */</em></td>

  </tr>

  <tr>

   <td width="632"><strong>public </strong>Dog() { …}<em>/**</em>* This method takes in two ints and returns their sum* <strong>@param a </strong>first number* <strong>@param b </strong>second number <em>* </em><strong>@return </strong>sum of a and b<em>*/</em><strong>public </strong>int add(int a, int b) {…}}</td>

  </tr>

 </tbody>

</table>

A more thorough tutorial for Javadocs can be found <a href="https://cs1331.gitlab.io/cs1331-style-guide.html">here</a>. Take note of a few things:

<ol>

 <li>Javadocs are begun with /** and ended with */.</li>

 <li>Every class you write must be Javadoc’d and the @author and @verion tag included. The comments for a class should start with a brief description of the role of the class in your program.</li>

 <li>Every non-private method you write must be Javadoc’d and the @param tag included for every method parameter. The format for an @param tag is @param &lt;name of parameter as written in method header&gt; &lt;description of parameter&gt;. If the method has a non-void return type, include the @return tag which should have a simple description of what the method returns, semantically.</li>

</ol>


