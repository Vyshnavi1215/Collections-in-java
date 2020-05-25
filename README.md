# Collections-in-java
Collection framework in java


05/13 -

Need of Collections in java:

Think of situation where we need to store 10000 values, we cannot go for variable declaration approach asit reduces readabilty and its not a good practice to declare more varaibles.

Hence we go for Array approach.In array we can store all the values by defining a single variable.

for example Employee emp[] = new Employee[10000]; this works well as the size is defined initially.But what happens if we need to store more than 10000????

There are some limitations in Arrays:

1.The size should be known in prior.
2.Only Homogeneous data elements allowed in arrays.
3.Underlying data structure in not in arrays

Point 2----Homogeneous data element means emp[0] = new Employee(); -> this is valid.

But emp[1] = new Customer();this is invalid -> compiler throws an error stating incompatible type.

But this above problem can be solved by using Object arrays.

Object obj[] = new Object();

Now we can add heterogenous data elements to obj.
obj[0] = new Employee();   -> valid.
obj[1] = new Customer();   -> valid.

Point 3--- Underlying Data structure.

In array if we need to search anything we need to write the code manually to search it or if we need to sort the data then we need to 
write the program for searching as well.(no readymade method support)

but this is not the case in collections.

Collections have some built in functions to do these operations like contains().

Collections are growable in nature, allows both homogeneous and heterogeneous data elements, this have the readymade method support to work on different functionalities.

05/25--

Differences between arrays and collections :

Collections are growable in nature based on our requirement.

collections concepts are not up to the mark based on performance wise

Differences 


               Arrays                                                           Collections
 1. Fixed in size                                                          1. Grpwable in nature.
 2.Arrays are not good for Memory management                               2.Collections are good for memory management.
 3.Performance wise this is good                                           3.Not good by performance wise.
 4.only homogeneous data                                                   4.holds both homogeneous and heterogeneous data
 5.readymade method support is not available                               5. readymade methods are available(ex-to find the elemnts)
 6.Arrays can be used to store primitive and objects                       6.Collections store only objects
 
 
 Collection and Collection Framework--
 
 Collection is a group of individual objects represented as a single entity.
 
 What is collection framework ??
 
 It defines several classes and interfaces which are used to define a collection.
 
 Collection is not new concepts, it is alo there in other languages
 
 In java it is collection and in C++ it is Container
 Java- Collection framework and in C++ STL(Standard Template Library).[Library means a group of classes and interfaces].
 
 
 9 Key interfaces in Collection Framework --
 
 First is collection
 
 1.Collection-defines the most common methods applicable for all the the collections like addd, isempty etc.
 2.In general collection interface is considered as the root interface for collection.
 
 Note : There is no concrete class that implements the collection interface directly.
 
 Diff between Collection and Collections :
 
 
Collection - interface, collections -class, this will have pre defined methods to work on collections

For example think of an arraylist we cdont have any method to sort which means its not defined in arraylist.

but we can use as Collections.sort(ArrayList) to sort it.

This is present in java.util.package.

Second - List



 
 
 
 
 
 
 
 













