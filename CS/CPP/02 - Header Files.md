**Relevant Tags:** [[02 - Preprocessor Directives]]

----
End with .h, can be included with # include "filename.h" - useful so you don't have to forward declare everything at the top of your main.cpp file.

 Basically, when you include a header file, everything in the header file gets copied - however you don't want to define/run code in your header file as this often results in duplicate function names/namespace collision. Instead, you want to write your functions in a cpp file, then in your header file forward declare your functions - for example an add.h file might just have the forward declaration "int add(int x, int y);" to forward declare an add function. Then, you want a cpp file with the same name (add.cpp) with the actual function itself, taking the x and y parameters - that way when you # include "add.h" in your main file, it'll just forward declare the add function, which will also be compiled with your code.

Generally, it's good practice to include your header file in the corresponding code file as well so the compiler can catch any bugs such as return type mismatch.

Header guards/include guards are usually included in header files using preprocessor directives.

The way this works is by using an # ifndef to check if something has been defined - if not define it, insert the code, and then wrap with an end if. That way, if the code has already been defined in a header, it won't be redefined and the code will be skipped - otherwise it will be defined and the code will be included.

Conventionally, your header guards should be set to the name of your header file typed in all caps - for example file square.h would become SQUARE_H, and the header guard would ifndef square_h, define square_h, and then endif.

However - instead you can literally just type # pragma once at the top of the header and apparently this does the same thing 99% of the time.
