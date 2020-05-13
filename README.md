# Collections-in-java
Collection framework in java


05/13 -

Need of Collections in java:

Think of situation where we need to store 10000 values, we cannot go for variable declaration approach and it reduces readabilty and its not a good practice to declare more varaibles.

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


 



