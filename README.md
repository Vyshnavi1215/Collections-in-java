## Learning log for Collections-in-java
# Collection framework in java

#### 05/13 

## Need of Collections in java:

- **Problem** storing thousands of strings in a program
- Individual String declaration is hard, reduces readbility, not a convention
- We can use array for it ``` Employee emp[] = new Employee[10000]; ```
- But in array we need to declare size, what if we need it dynamically
- **Collections** are used for this.

- Think of situation where we need to store 10000 values, we cannot go for variable declaration approach as it reduces readabilty and its not a good practice to declare more variables.
Hence we go for Array approach.In array we can store all the values by defining a single variable.
for example ``` Employee emp[] = new Employee[10000]; ``` this works well as the size is defined initially.But what happens if we need to store more than 10000????

## There are some limitations in Arrays:
1. The size should be known in prior.
2. Only Homogeneous data elements allowed in arrays.
3. Underlying data structure in not in arrays

> Point 2-Homogeneous data element means ``` emp[0] = new Employee(); ``` -> this is valid.
- But ```emp[1] = new Customer();``` this is invalid -> compiler throws an error stating incompatible type.
- The above problem can be solved by using Object arrays.
```
Object obj[] = new Object();

Now we can add heterogenous data elements to obj.
obj[0] = new Employee();   -> valid.
obj[1] = new Customer();   -> valid.
```
## Underlying Data structure.
- In array if we need to search anything we need to write the code manually to search it or if we need to sort the data then we need to 
write the program for sorting as well.(no readymade method support)
- but this is not the case in collections.
- Collections have some built in functions to do these operations like contains().
- Collections are growable in nature, allows both homogeneous and heterogeneous data elements, this have the readymade method support to work on different functionalities.

#### 05/25

## Differences between arrays and collections :
- Collections are growable in nature based on our requirement.
- Collections concepts are not up to the mark based on performance wise

### Differences between array and collections
Arrays | Collections
---------------------------------------------------------------- | -----------------------------------------------------------------
Arrays are Fixed in size | Collections are growable in size.
Arrays are not good for Memory management | Collections are good for memory management 
Performance wise this is good | Not good by performance wise.
holds only homogeneous data | holds both homogeneous and heterogeneous data
readymade method support is not available | readymade methods are available(ex-to find the elements)
Arrays can be used to store primitive and objects | Collections store only objects
 
## Collection and Collection Framework
 
- Collection is a group of individual objects represented as a single entity.
 
## What is collection framework?
- It defines several classes and interfaces which are used to define a collection.
- Collection is not a new concept, it is also present in other languages
- In java it is collection and in C++ it is Container
- Java- Collection framework and in C++ STL(Standard Template Library).[Library means a group of classes and interfaces].
 
## **9** Key interfaces in Collection Framework
 
### First Interface is **Collection**
1. Collection-defines the most common methods applicable for all the the collections like addd, isempty etc.
2. In general collection interface is considered as the root interface for collection.
 
> Note : There is no concrete class that implements the collection interface directly.
 
### Diff between Collection and Collections :
- Collection - interface, collections -class, this will have pre defined methods to work on collections
- For example think of an arraylist we dont have any method to sort which means it is not defined in arraylist.
- but we can use as ``` Collections.sort(ArrayList) ``` to sort it.
- This is present in java.util.package.

### Second Interface - List.(1.2)
- duplicates are allowed.
- Insertion order to be preserved.
- Implementation classes of List are ArrayList(1.2), LinkedList(1.2), Vector[1.0] and Stack[1.0](Vector and stack are called as Legacy classes as they exist from 1.0 Version) All others are from 1.2V(Collection, List,ArrayList,LinkedList)
> The classes that exists from older versions are called as Legacy classes.

### Third Interface is Set(1.2)
- Duplicates are not allowed.
- Insertion not preserved
- Implementation classes Hashset(1.2V) and LinkedHashset(1.4V)

### Diff between List and Set
List | Set
---------------------------------- | ------------------------------------------
Dupicates are allowed | Dupicates not allowed.
Insertion order preserved | Insertion Set-not preserved.

### Fourth Interface -Sorted set(1.2V)
- This is the child interface of Set(1.2V), when there is a requirement in which the duplicates are not allowed and insertion order need to be preserved then we go for Sortedset.

### Fifth Interface -Navigable Set(1.6V)
- It is the child interface of Sorted Set and it defines several navigation methods.
- Implementation of the Navigable set is Treeset(1.2V)

### Sixth Interface is Queue(1.5V)
- Implementation classes of Queue are Priority Queue(1.5V) and Blocking Queue(1.5V) and Blocking Queue have two more implementation classes
- Linked Blocking Queue(1.5V) and Priority Blocking Queue(1.5V)

> All the above collection Interfaces are used to represent as group of  individual objects 

- Queue is best used when we need to do any operation in First In First Out Order.
- Before processing if we want to store a group of individual objects, then we go for Queue.
- For example consider a message to be sent for 100 people then the recepients should be stored in prior before sending then we can use Queue interface.

> If we want to represent a group of objects as Key value pairs then we got for **Map Interface**.

#### 05/26

### Seventh Interface - Map
- Map is not the child interface of collections-
- **Implementation classes:** Map(1.2V) implementation classes 1.HashMap (1.2V) 2. WeakHashMap(1.2V) 3.IdentityHashMap(1.4V) 4.Hashtable
Linked HashMap(1.4V) is the child interface of HashMap                                                       
- child class of Hashtable is properties, Hashtable comes from Old Legacy class Dictionary
- Dictionay,HashTable and Properties classes are from version 1.0 and so they are called as Legacy classes.

### Eighth Interface Sorted Map(1.2V)
- This is a child interface of map, This is mainly used when we want to represent a group of objects as key value pairs according to some sorting order then we go for Sorted Map.

### Ninth Interface
- Navigable Map(1.6V) is child interface of sortedmap
- It defines several utility methods for navigation purpose.Implementation of navigable map is tree map(1.2V) 

#### 05/29
- Overview of collection framework
### What is the difference between comparable and comparator?
Comparable | Comparator
------------------------------------------ | --------------------------------------------
Used for sorting order | Customised sorting order

> To get the collection objects one by one we have some interfaces.

## Cursors is the concept

- How many cursors are there in java?
 - Enumeration
 - Iterator
 - ListIterator
- All the above are used to get the collection objects one by one.

### Utility classes
1. Collections -defines serveral utility methods for collection object.
2. Arrays - defines several utility methods for Arrays object.

#### 05/30
## Collection framework-Collection Interface
- In the collection interface we will have the most common methods applicable for any collection object.
 -	```add(Object o)``` this is used whenever we need to add an object from the collection.
 -	```addAll(Collection c)``` this is used to add the group of objects from the collection.
 -	```remove(Object o)``` this is used whenever we need to remove an object from the collection.
 -	```removeAll(Collection c)``` this is used to remove the group of objects from the collection.
 -	```clear()``` to remove the entire objects in collection.
 -	```retailAll(Collection c)``` Except a group of objects all the other objects are to be removed then we should use ```retainAll()``` method.

-	To check whether the collection is empty or not then we should use ```isEmpty()```.
-	To get the size of the collection ```size()```.
-	To check whether a particular object is available or not in that collection ``` contains(Object o)```.
-	To check whether a group of particular objects are available or not ```containsAll(Collection c)```.

### Coverting a collection to array
``` Object a[] =c.toArray() ```
- To iterate all the objects in the collection use Iterator which returns the iterator object.
> Collection interface doen't contain any method to retrieve objects as ther is no concrete class which implements the colletion class directly.

## List Interface
- List is child interface of collection.
- Index play an important role in List.
- Index - used to differentiate the duplicates and to preserve the insertion order.
### Methods specific to list interface.
-	To add an element at particular index ``` add(int index, Object o) ```
-	To add group of objects from a specified index ``` addAll(int index Collection c) ```
-	To remove an element at a particular index ``` remove(int index) ```
-	To find a particular element in the ``` list.indexOf(Object o) ```
-	To find the last occurence of that particular element in the ``` list-list.lastIndexOf(Object o) ```
-	To iterate the list we use ``` ListIterator() ```
-	To get the value at particular ``` index get(int index) ```
-	To replace the element at the specified index ``` set(int index, Object o) ```

> From the above we can notice that list interface have its own methods in addition to the methods that are getting from the collection.

> Index play very important role in list interface.
  
### Implementation classes of List
### ArrayList
#### Main features of ArrayList
-	underlying data structure for arraylist - resizable or growable array.
-	insertion order is preserved.
-	duplicates are allowed.
-	heterogeneous objects are allowed.
-	null insertion is also allowed.
- Heterogeneous objects are allowed in collection except in Treeset and TreeMap-this is because in this collection classes the objects are stored in sorting order. also, to sort any object, the other should be of same type.hencce heterogeneous objects are not allowed in treeset and treemap.

### Constructors
``` ArrayList al = new ArrayList(); ```
- whenever we create a arraylist its default capacity is 10. But if we add 11th element then the compiler will create the new capacity arraylist by copying all the elements from the initially created arraylist and the old arraylist will be moved to garbage collection.
- Coming to the size of newly created arraylist- capacity is calculated as - (current capacity *3/2)+1

``` ArrayList al = new ArrayList(int initialcapacity) ```
- With the first constructor, if the sixe increases based on requirement the processing will be too slow, since all the elements have to be copied to the newly created list.
- But if we know the capacity in prior then we can use this second constructor with initial capacity.

- if we want to convert any collection object to arraylist then we can use this.
``` ArrayList al = new ArrayList(Collection c) ```
- purpose of collection- to hold the objects and transfer the objects accross the network.
- first to transfer the object it must be serialized, so every collection class by default use serializable interface.
- once after sending the object the reciever takes it and creates an exact copy of the object - which is called cloning because if anything happens to the recieved object then it cannot be regained.so cloning is must.
- hence every collection class implements cloneable interface.

> ArrayList and Vector collection classes implements RandaomAccess Interface. With this the data in that particular index can be obtained very soon. If our frequent operation is retrieval then we can go for ArrayList..

### RandomAccess
- It is a marker interface and doesn't contain any methods
- ArrayList is the best choice if our frequent operation is retrieval.
- But if our operations are adding in middle or removing an element arraylist doesn't suit, as it lags performance.

#### 05/31

### Differences between arraylist and vector
Arraylist | Vector
-------------------------------------------- | --------------------------------------------
Methods are non-synchronised | Methods are synchronised.
Not threadsafe | Thread safe.
Performance is good in arraylist | Performance but low in vector.
Non legacy class, as it is introduced in 1.2 | Legacy class as it is introduced in 1.0

### How to get synchronised version of ArrayList-
- We have a method in collections class to make the arraylist as syncronized.
```
ArrayList al= new ArrayList(); //To make it as synchronized-
List l1=Collections.synchronisedList(al);
```
> This will give us the synchronised arraylist.

```
public static List synchronizedList(List al)
// similarly we can get the synchronised version of map and set like above.
public static Set synchronizedSet(set s)
public static Map synchronizedMap(Map m)
```

## LinkedList
- Second interface class of collections-
- If the main requirement is to add/remove the elements then we can go for linkedList. if our frequent operation is retrieval it is not the best option.
### Properties:
1. Underlying Data structure is Doubly Linked List.
2. Insertion order is preserved.
3. Duplicates are allowed.
4. Null values are allowed.
5. Heterogeneous data types are allowed.

- This implements both serializable and cloneable interfaces.
- LinkedList used to implement stacks and queues.
- To implement these LinkedList have 6 methods which are used only in LinkedList class but not anywhere.

```
	void addFirst(Object o)
	void addLast(Object o)
	Object getFirst()
	Object getLast()
	Object removeFirst()
	Object removeLast()
```

### Constructors
``` LinkedList l1= new LinkedList(); ```
- To allow the inter conversion from one collection to other collection--
``` Linkedlist L1 = new LinkedList(Collection c) ```
- Set method is used to replace.
- Differences between ArrayList and LinkedList
- Arraylist underlying data structure - resizeable or growable array, Linked List-underlying data structure- double linked list.

## Vector class
- Vector is synchronised, which is thread safe
### Vector methods
- to add the element ``` addElement(Object O) ```
- to remove the element ``` removeElement(Object o) , removeAllElements(),removeElementsAt(int Index) ```
- to retrieve elements ``` Object elementAt(int index), Object get(int index) ,Object FirstElement(), Object LastElement() ```

### Constructors
- default initial capacity is 10
``` 
Vector  v = new Vector();
Vector v = new Vector(100) ;-specify the capacity as per our need.
```
- if we have 101st element the capcity will increase as below. ``` new capacity = 2* current capcity ```
- but if we dont want all the memory locations we can specify the increment value as per our need.
``` 
Vector v = new Vector(int initialcapacity, int incremental capacity)
Vector v= new Vector(Collection c)<-- to convert any collection class to vector
```

## Stack class
- This is the child class of vector class
- This is specially designed for last in first out (LIFO) order.
### Constructor
``` Stack s = new Stack(); ```
### Methods of stack
- ```push(Object o)``` to insert an element into stack
- ```pop()``` to remove and return the top of the stack.
- ```peek()``` to return the top of the stack without removing the element
- ```empty()``` to check whether the stack is empty
- ```search()``` to search an element in the stack and this returns offset

### now what is offset??
- consider a stack with three elements

[x] C -1
[x] B -2
[x] A -3

- In the above stack if we perform search as search of A
- ```search("A")``` it returns 3
- ```search("Z")``` it returns -1
- so when the element is not found it returns -1
- Offset means a value in general

- Cursors in Java--If we want to retrieve objects from collection one by one then we should go for cursors in Java.
- There are three cursors in java

1. Enumeration
2. Iterator
3. ListIterator

#### 06/01

## Enumeraion
- Enumeration can be created by using elements of vector class.
``` 
Enumeration e =v.elements();
// Methods
public boolean hasMoreElements()
public Object nextElement()
```

#### 06/02
## Iterator
- Enumeration-Applicable for legacy classes only and not an universal cursor, can perform only read operation
- Iterator is universal cursor and can be performed on any collection class, by using iterator we can perform both read and remove operations
- We can create iterator obbject by using the methods of collection interface.
```
public Iterator iterator();
Iterator itr= c.iterator(); //where c is any collection object
// Methods of Ierator
public boolean hasNext();
public Object next();
public void remove();
```

### Limitations
- Forward direction cursors- only next elements will be checked.
- only read and remove, no replace operations

## ListIterator
- This is a bidirectional cursor.
- by using this we can read, remove, replace or add new items as well.
- this is the child interface of Iterator-
- how to get the listIterator object--
```
public ListIterator listIterator();
ListIterator ltr =l.listIterator(); //where l is any list object
// This has 9 methods
# Forward Direction

public boolean hasNext();
public Object next();
public int nextIndex();

# Backward Direction -

public boolean hasPrevious();
public Object previous();
public int nextPrevious();

# Other methods -

public void remove();
public void set(Object obj);
public void add(Object new);
```

- Limitation - applicable for only for list objects and not the universal cursor.

#### 06/05

- Differences between Three cursors

#### 06/06
### Comparision between three cursors based on some properties :

### Property-Applicable for:
1. Enumeration applicable only for legacy classes.
2. Iteration applicable for any collection class.(also called as Universal Cursor)
3. ListIterator applicable only for List classes.
### Property- Movement:
1. Enumeration -only forward(single direction)
2. Iterator - only forward(Single direction)
3. ListIterator - both directions(bidirectional)
### Property- Accessibility
1. Enumeration -only read operation.
2. Iterator- both read and remove.
3. ListIterator, Read, remove, replace and add elements
### Property - How we can get this cursors ?
1. Enumeration -elements method of vector class.
2. Iterator- iterator method of collection Interface.
3. ListIterator - by using listIterator() method of List Interface
### Property - methods in cursors
1. Enumeration - two methods ``` hasNextElement(), nextElement()```.
2. Iterator - three methods ``` hasNext(),next(),remove()```.
3. List Iterator- 9 methods.
### Propery -legacy.
1. Enumeration- Yes Legacy class(1.0)
2. Iterator- No 1.2V
3. List Iterator- No 1.2 V
> Interfaces references can be used to hold interface class objets
> We can print implemented class of interface by using ``` .getClass().getName(); ```

## Set
- Set Interface doesn't contain any new methods, we have to use the methods that are coming from collection Interface as set is the child interface of Collection
### HashSet()
- Underlying data structure - HashTable
- Duplicates are not allwoed.
- Insertion order not preserved, but it is based on Hashcode.
- Heterogeneous objects are allowed.
- Null Insertion is allowed.
- implements serializable and cloneable.
- Hashset is the best choice if the frequent operation is search operation
### Constructors of HashSet()
- ``` Hashset h = new HashSet(); ```
	- create an empty Hashset with default capacity 16 and load factor -0.75(fillratio)
	- fill ratio determines determines at which point the new Hashset to be created when for the given capacity of the hashset.
- ```HashSet h = new Hashset(int initialcapacity); ```
	- creates an Hashset Object with the initial capacity
- ``` Hashset h = new Hashset(int initialcapacity float fillRatio) ```
	- creates the hashset with the specified capacity and the fillratio after which new Hashset to be created.
- ``` Hashset h = new Hashset(Collection c) ```
	- To convert any collection to Hashset above constructor is used.
> Insertion in hashset is based on hashcode.

### LinkedHashset
### Properties
- Insertion order is preserved.
- Duplicates are not allowed.
- Underlying datastructure is Hashtable + Linked List
- Introduced in 1.4 version.
### Usage of LinkedHashSet-
- Cache based applications
### SortedSet Details
- If we want to store group of objects according to some sorting order then we need to go for SortedSet
- Sorted set specific methods are applicable on Sortedset implementation classes- TreeSet
```
Object first() //returns the first element of the object.
Object last () //returns the first element of the object.
sortedSet headSet(Object obj) // returns the sortedSet whose elements are less than obj
sortedSet tailSet(Object obj) // returns the SortedSet ehole elements are >= obj.
sortedSet Subset(Object obj1, Object obj2) // returns the SortedSet whole elements are >=obj1 and <obj2
comparator() //return comparator object that describes the underlying sorting technique, if we are using default sorting order then this will return null.
```
> Default sorting order for numbers is ascending order and for strings it is alphabetical order.
### TreeSet
### Properties
- Underlying data structure is Balanced tree
- It doesnot allow heterogeneous data elements
- Null allowed only once.
### Constructors 
- ```TreeSet t = new TreeSet();```
	- default empty treeset will be created with default natural sorting order
- ```TreeSet t = new TreeSet(Comparator C)```
	- treeset will be created with the customised sorting order
- ```TreeSet t = new TreeSet(Collection C)```
	- to convert any collection to Treeset.
- ``` TreeSet t = new TreeSet(SortedSet S)```
	- to convert given sortedset to treeset.
### Null acceptance in Treeset-
- If we are going to add null as first element in the empty treeset then it is allowed, else we will get nullpointer exception
- Null cannot be added in non empty treeset

- If we are depending on natural sorting order then the objects should be homogeneos and comparable, otherwise we will get ClassCastException at runtime.
- An object is said to be comparable if and only if the corresponding class implements java.lang.comparable Interface.

### Comparable Interface -
- This interface is present in java.lang package, contains only one method
```
compareTo(Object obj)
public int compareTo(Object obj)
obj1.coompareTo(obj2)
returns
-1 iff obj1 has to come before obj2
 1 iff obj1 has to come after obj2
 0 iff both are equal
 ```
 - If we are depending on default natural sorting order internally JVM will call compareTo() method while inserting elements in to the TreeSet.Hence the objects should be homogeneous and comparable.
- Comparable meant for default natural sorting order where as Comparator meant for the customised sorting order.
 
#### 06/07
- If we are not satisfied with default natural sorting order or if we want customised sorting order then we have to go for Comparator 
- Comparator interface is present in java.util package
- It defines two methods **compare** and **equals**
- compare works same as compareTo
- For a class implemeting Comparator it should define only the logic for Compare Method, equal method is optional.
- Consider an example
```
 class myComparator implements Comparable
{
public int compare(){
	}
} 
```
- Here any class is the child class of Object class, since object class contains the implementation of equal method, and every class is inherited from Object, the implementation will be present already
> Comparator- to implemet our own sorting techniques

#### 06/08

### Treeset details
- How to add string buffer objects in to treeset
- We need to use toString Method to convert String buffer to String while comparing.
- If we are defining our own objects by comparator then the objects need not to be comparable.
#### 06/10
- If we are depending on default natural sorting order then the objects should be homogeneous and comparable else will get classcastexception
- If we are defining our own natural sorting order then the objects can be non comparable and heterogeneous as well
#### 06/13
### Difference between Comparable and Comparator Interface
- For predefined comparable classes, default sorting is already available, if we are not satisfied with the default sorting order then we can for comparator.
- For predefined non comparable classes like String Buffer  default natural sorting is not available, hence comparator should be used.
- Consider an own class, the person who is going to write the functionality of the class is responsible for writing the logic for default natural sorting order.
- If the person who is going to use this class is not satisfied by this default natural sorting order then that person should implement   sorting order based on the requirement using comparator.

Comparable | Comparator
--------------------------------------------------------------|----------------------------------------------------
Default natural sorting order | Meant for customised sorting order
Present in java.lang | Present in java.util
Only one methid present ```compareTo()``` | Methods present are ```compare() , equals()```
Implemented classes are All wrapper classes and String | Implemented classes are Collator and Rule Based Collators

### Map
- Map 
- HashMap    
- Linked HashMap(1.4)
- IdentityHashMap(1.4)
- WeakHashMap
- SortedMap
- NavigableMap(1.6)
- TreeMap
- Remaining all in the version 1.2
- We have Hashtable concepts in Map, Hashtable comes from Dictionary and implementation class of Hashtable is Properties(All are legacy classes)
### Map
> Map is not interface of collection
- If we want any group of objects as key value pairs then we go for Map concept
- Each key value pair is called Entry, hence map is a collection of entry objects

### Map Interface Methods

- put method used in Map
```
object put(Object key, Object value)
```
1. To add one key value pair to the mail
2. If the key is already present, them old value will be replaced with new value and returns old value.
```
m.put(101, "Durga")
m.put(102, "Shiva")
m.put(101, "Ravi")
```
- Now Durga will be replaced with Ravi
```
void putAll(Map m) // To add group of key value pairs
Object get(Object key) // return the value associated with specified key
Object.remove(Object key) // removes the entry associated with specified key
boolean containsKey(Object key)
boolean containsValue(Object value)
boolean isEmpty()
int size()
void clear();
Set KeySet() // to return only keys and keys wont be duplicate
Collection values() //values of that particular keys
set entrySet() //to obtain set of entries.
```
- The above three methods are considered as Collection view of Map since we are applying on a map but retrieving a collection
### Entry Interface
- A map is a group of key value pairs and each key value pair is called as an entry
- Hence Map is considered as a collection of entry objects 
- without existing the map object  there is no chance of existing entry object
- Hence Entry interface is defined inside Map Interface
```
interface Map
{
interface entry
{
Object getKey()
Object getValue()
Object setValue(Object newO)
}
}
```
- The above three methods are entry specific and can be applied on Entry object

### HashMap
- Underlying data structure -Hashmap
- Insertion order is not preserved and it is based on Hashcode of Keys
- Duplicate Keys are not alloed, but values can be duplicate.
- Heterogeneous objects are allowed for both key and value.
- Null insertion is allowed for key that too only once, but allowed as many times for values
- Hashmap implements serializable and cloneable interfaces but not Random Access
- Hashmap is the best choice if the frequent operation is searching
### Constructors
```
Hashmap m = new HashMap() // initial capacity 16 and loadfactor -0.75
Hashmap m = new HashMap( int initialcapacity)
Hashmap m = new HashMap(int initialcapacity float loadfactor)
HashMap m = new HashMap(Map m) // to convert any map object to Hashmap
```
### Differences between HashMap and HashTable
- HashMap - Every method present in HashMap is not synchronised, not threadsafe, performance is high, null  key and values allowed, introduced in version 1.2
- HashTable - synchronised, threadsafe, performance is low, null concept n/a, legacy class(1.0V)
- How to get synchronised version of HashMap object
- By default  HashMap is non synchronised, but  we can get synchronised version of HashMap by using synchronisedMap method of Collections Class
```
Hashmap m = new HashMap()
Map m1 = Collections.synchronisedMap(m);
//m is non synchronised amd m1 is synchrnised.
```
#### 06/16
- LinkedHashMap -child class of HashMap, exactly same as HashMap(including methods and constructors)
- LinkedHashMap - Underlying data structure is LinkedList and HashTable, Insertion order is preserved, introduced in 1.4V
- HashMap -Underlying data structure is Hashtable, Insertion order is not preserved and is based on hashcode of Keys, introduced in 1.2V
- LinkedHasSet and LinkedHashMap are commonly used for developing Cache based applications.
- Difference between == and .equals()
	- In general == operator meant for reference comparision(address comparision) where as .equals() method meant for content comparision
```
Interger I1 = new Integer(10);
Integer I2 = new Integer(10);
S.O.P(I1 ==I2) //false  I1->10, I2->10
S.O.P(I1.equals(I2)); //true    content is same
```
### IdentityHashMap -
- It is exactly same as HashMap(including methods and constructors) except the follwoing difference
- In the case of normal HashMap JVM will use .equals() method to identify the dupilcate keys, which is meant for content comparision.
- But in the case of IdentityHashMap JVM will use == operator to identify the duplicate keys which is meant for reference comparision(address comparision)

### Example
```
HashMap m = new HashMap()
Integer i1= new Integer(10);
Integer i2 = new Integer(10);

m.put(i1, "Test");
m.put(i2, "Example);
s.o.p(m)
```
- The output we get here us {10= example} since the JVM uses .equals method to find the duplicate keys and the value will be replaced with new value.
- but if we use LinkedHashMap we will get as {10= Test, 10= Example} //i1==i2 return false
### WeakHashMap
- Just before destroying an object garbage collector calls finalize method to do the clean up activities
- It is exactly same as HashMap except the following difference
- In the case of HashMap, eventhought the object doesn't have any reference it is not eligible for GC if it is associated with the HashMap i.e HashMap dominates garbage collector
- but in the case of weakHashMap, if the object doesn't contain any references it is eligible gc eventhough object associated with WeakHashMap i.e gc dominates weakhashMap.

#### 06/17
### SortedMap
- It is the child interface of Map, if we want to represent a group of key value pairs according to some sorting order of keys then we should go for SortedMap
- Sorting is based on key but not based on value
- Sorted  map defines the following specific methods
```
Object firstKey();
Object lastKey()
SortedMap headMap(Object key);
SortedMap tailMap(Object key);
sortedMap subMap(Object key1, Object key2);
Comparator comparator();
```
#### Example 
```
101->A
103->B
104->C
107->D
125->E
136->F

Object firstKey();-101
Object lastKey(); -136
SortedMap headMap(107);-{101=A,103=B,104=C}
SortedMap tailMap(107);{107=D125=E,136=F}
sortedMap subMap(104, 136};{104=C,107=D,125=E}
Comparator comparator();
```
### TreeMap
- Underlying data structure is red black tree
- Insertion is not preserved and it is based on some sorting order of keys
- Duplicate keys are not allowed, but values can be duplicated.
- If we are depending on default natural sorting order then keys should be homogeneous and comparable, otherwise we will get runtimeexception mentioning ClassCastException.
- If we are defining our own sorting by comparator then keys need not be homogeneous and comparable, we can take heterogeneous non comparable objects also
- Whether we are default natural sorting order or customised sorting order values have no restriction, we can take non comparable heterogeneous objects also

### Null acceptance
- For non empty tree map if we are trying to insert an entry with null key then we will get Run time exception saying NPE
- For an empty tree map, as the first entry with null key is allowed but after inserting that entry if we are trying to insert any other entry then we will get run time exception saying NPE
> The above null acceptance rule applicable until 1.6V only from 1.7 version onwards null is not allowed for key. but for values we can use null any no.of times, there is no restriction whether it is 1.6V or 1.7V

### Constructors
```
TreeMap t = new TreeMap() // inserts elements in to the map based on the default sorting order of the keys
TreeMap t = new TreeMap(Comparator c) // this is used for customised sorting order based on the comparator object we pass sorting will be done
TreeMap t = new TreeMap(SortedMap m) // to convert sorted map to TreeMap
TreeMap t = new TreeMap(Map m) //to convert any map object to TreeMap
```
#### 06/18
### Hashtable
### Constructors 
```
Hashtable h = new Hashtable() //creates an empty hashtable object with default initial capacity 11 and default fill ratio 0.75
Hashtable h = new Hashtable(int initialcapacity)
Hashtable h = new Hashtable(int initialcapacity float fillratio);
Hashtable h = new Hashtable(Map m) //interconversion between map objects
```
#### 06/19
- In Hashtable values will set based on hashcode
- the way on ehivh the output we get is from top to bottom and if the bucket contains more values then the printing order is from right to left
- Refer the images in Info folder for further clarification

### Properties
- In our program if anything which changes frequently like username , password, mailid, mobe number etc are  ot recommended to hardcode in java program because if there is any change, to reflect that change recompilation, rebuild, redeploy application are required even sometimes server restart also required which creates a big business impact to the client
- We can overcome this problem by using the properties file, such type of variable things we have to configure in the properties file
- From that properties file we have to read in to Java program and we can use those properties.
- The main advantage of this approach is if there is a change in properties file to reflect that change just redloyment is enough which wont create any business impact to the client
- We can use java properties object to hold properties which are coming from properties file
- In normal map like HashMap HashTable TreeMap key and value can be any type, but in the case of properties key and value should be string typr "only".
### Constructor
```
Properties p = new Properties();
```
### Methods
```
String setProperty(String pname, String pvalue) // to set a new property
//If the specified property already available then the old value will be replaced with new value and returns old value
String getProperty(String pname) // to get the vlaue associated with specified property
//If the specified property then the above method returns null
Enumeration propertynames() // returns all property names present in Properties object
```

### 2 another methods
```
voild load(InputStream is) //to laod the properties from the properties file in to java properties object
void store(OutputStream os , String comment) //to store properties from java properties object to properties file.
```
### Queue
- 1.5 Version enhancements(Queue interface)
- It is the child interface of Collection
### Queue -priorityqueue and blocking queue
- blocking queue is again divided into priorityblockingqueue and linkedblockingqueue
- If we want to represent a group of individual objects prior to processing then we should go for queue.
- For example before sending a sms message all mobile numbers should be stored in some data structure, in which order we added mobile numbers in the same order only message should be sent.for this fifo requirement queue is the best choice
- Usually queue follows first on first out order but based on our rewuirement we can implement our own priority order also(priority queue)
- from 1.5v onwards linked list class also implements Queue Interface.
- linkedlist based implementation of queue always follows fifo order

### Queue interface specific methods
```
boolean offer(Object o) // to add an object in to queue
Object peek() // to return head head element of the queue without deleting, if queue is empty this returns null
Object Element() // return the head eleament of the queue without deleting, but run time exception occurs if queue is empty. RE-NoSuchElementException
Object poll() // to remove and return the head element of the element, if queue is empty then returns null,
Object remove() // to remove and retun the head element of the queue, but run time exception occurs if queue is empty.RE-NoSuch ElementException
```

### properties
- default and customised sorting order allowed(priority can be both)
- insertion order not preserved and based on some priority
- null insertion not allowed, even as the first element also
- duplicates not allowed.


### 1.6V Enhancements
- Navigableset(I)
- Navigable Map(I)
> The above two are introduced are part of 1.6V

### NavigableSet -
- It is child interface of SortedSet and it defines several methods for navigation purposes
- Methods in NavigableSet:
```
floor(e) // returns the lowest element which is <=e
lower(e) // returns the lowest element which is <e
ceiling(e) // returns the highest element which is >=e
higher(e) // returns the highest element which is >e
pollFirst() // remove and return the first element 
pollLast() // remove and return last element.
descendingSet() // returns NavigableSet in reverse order
```

### NavigableMap -
- It is the child interface of Sorted Map which is introduced in 1.6V
- It defines several methods for navigation purposes
- Navigable Map defines the following methods
```
floorKey(e) // returns the lowest key which is <=e
lowerKey(e) // returns the lowest key which is <e
ceilingKey(e) // returns the highest key which is >=e
higherKey(e) // returns the highest key which is >e
pollFirstEntry() // remove and return the first entry 
pollLastEntry() //remove and return last entry.
descendingMap() // returns NavigableMap in reverse order
```

### Utility Classes
- Collections class defines several utilty methods for collection objects like Sorting, Searching, reversing etc 

### Sorting elements of list:

- Collections class defines the following two sort methods 
- ```public static void sort(List l)``` To sort based on default natural sorting order In this case list should compulsory contain homogeneous and comparable objects otherwise we will get runtime exception saying ClassCastException
- List should not contain null values, if it contains null, while comparing we will get null pointer exception
- ```public static void sort(List l, comparator C)``` to sort based on Customised sorting order

## Searching Elements of List-
### Collections defines the following binary search methods
- ```public static int binarySearch(List l, Object target)``` If the list is sorted according to default natural sorting order then have to use this method
- ```public statuc int binarySearch(List l, Object target, Compararator c)``` we have to use this method if the list is sorted according to customised sorting order

### Conclusions:
- The above search methods internally will use binary search algorithm 
- Successful search returns index.
- Unsuccessful search returns insertion point
- Insertion point is the location where we can place the target element in sorted list.
- Before calling binary search method compulsory list should be sorted otherwise we will get unpredictable results
- If the list is sorted according to comparartor , then at the time of search operation also we have to pass same comparartor object
otherwise we will get unpredictable results.
- For the list of n elements in the case of binary search methods 
	1. successful search resukt range is 0 to (n-1)
	2. Unsuccessful search result range is -(n+1) to -1
	3. Total result range is -(n+1) to (n-1)


### Reversing elements of List

``` public static void reverse(List l)```
- reverse() vs reverseOrder()
- We can use reverse method to reverse order of elements of list whereas we can use reverseOrder method to get reversed Comparator
```Comparator c1= Collections.reverseOrder(Comparator c)```
- Another utilty class present in Collections is Arrays()
- Arrays class is an utility class to define several utility methods for array objects

### Sorting elements of Array
- Arrays class defines the following sort methods to sort elements of primitive and object type arrays
```
public static void sort(Primitive[] p) // to sort according to natural sorting order
public static void sort(Object[] o) // to sort according to natural sorting order.
public static void sort(Object[] o, Comparator c) //to sort according to customised sorting order.
```
> We can sort primitive arrays only based on default natural sorting order but for objects we can do both sorting i.e default natural sorting order or customised sorting order

### Searching the elements of Array
- Arrays class deines the following binarySearch methods
```
public static int binarySearch(primitive[] p, primitive target)
public static int binarySearch(Object[] a, Object target)
public static int binarySearch(Object[] p, Object target, Comparator c)
```
> All rules Arrays class binary search methods are exactly same as BinarySearch methods

### Conversion of array to list

``` public static list asList(Object o) ```
- Strictly speaking this method wont create an independent list object
- For the existing array we are getting list view
- By using array reference if we perform any change automatically that change will be reflected to the list similarly by using list reference if we perform any change that change will be reflected automatically to the array
- By using list reference we cant perform any operation which varies the size otherwise we will get runtime expection saying UnsupportedOperationException
- By using list reference we are not allowed  to replace with heterogeneous objects otherwise we will get runtime exception saying ArrayStoreException
					###### End of Collections
