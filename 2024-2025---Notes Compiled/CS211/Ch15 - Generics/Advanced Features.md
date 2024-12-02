
---

Resizing when necessary - ie. real arraylist wont throw exception, it'll modify itself to be the new length

however - constructing new arrays not very space efficient - thus you should instead double the size of the array. 
even though the initial call to copy everything over might be expensive, it's far better than, for example, if the size it at 1000 which is its capacity and someone tries to add something new, you would have to resize the array 4 times instead of just once

iterator class - keep track of the position 