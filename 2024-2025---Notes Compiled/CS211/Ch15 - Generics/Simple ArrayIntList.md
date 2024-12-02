
---
Goal is to create a class that has one mutator method that is able to add values to the list as well as an accessor method that can display the contents of the list

Declare two variables: one for size, one for capacity 

Generally the size of the list = index of last vacant element

add method, increase the size so it doesn't keep adding to the same index of the array

add parameter so they can specify the size of the list/vacant slots

precondition: size must be less than capacity - otherwise you will attempt to store a variable at an index that doesn't exist

to add methods - create checkcapacity method, call it with size + 1