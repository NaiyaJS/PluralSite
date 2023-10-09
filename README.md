# PluralSite
Java Lists inherit from a Collection

#Collection Interface
you must implement certine methods to be called a collection
ex.add(), remove(), size(), contains() etc
2 subgroups of many collections List and Set

#Set
A group of unique values without an index
Collections are a grouping of general Java Objects

#List
An ordered group of values that are indexed numerically

List is also an interface, so it implements methods of a collection as well as its own list of methods
ex: add() at index, set(), remove() at index, indexOf(), sublist(), set() etc
Cannot instantiate a list directly so we either build our own list or use Javas implemented nonabstract list like
ArrayList, LinkList, Vector, Stack
Make the variable a general List on the left to be more flexible.
Can change the type of list throughout the code without having to change the variable on the left later.
List can hold any type of object

#Adding elements to a List

List<string> languages = new ArrayList<>();
languages.add("Java");
languages.add("Python");
languages.add("JavaScript");
languages.add("Go");</string>

System.out.println(languages());
//outputs 4
#Iterating through Elements in a List
use a for each loop to print out the elements

for (String language : languages)
System.out.println(language);

/*Output
Java
Python
JavaScipt
Go
*/

#index and Value
need to get an index of a specific value or a value of a specific index
can use .indexof() or .get()
ex.
System.out.println(languages.indexOf("Python"));
or
System.out.println(languages.get(2));

if you need to remove elements on the list you can use .remove() using wither index or value
ex:
languages.remove("Python");
languages.remove(2);
#ProbelmsWithArrays
they don't resize

#HowListSolvesProblem
convert a List into an array

#ReturnAnArrayOfObjects
Object[] langsArray = languages.toArray()

#ReturnAnArrayOfStrings
String[] langsArray = languages.toArray(new String[0]);

#subList()
List<string> someLangs = languages.subList(0,3);</string>
subList() returns a view of the list. setting a value in the sublist will change the Original List as well.
someLangs.set(2, "Groovy"); will change the 3rd element/ 2nd indext number to Goovy in the original languages ArrayList
#need to learn LearnTryCatch
