Structs
--------

Mainly about structure and grouping data together. Fields are public.

```c++
// declare
struct Name {
    type field1;
    type field2;
};

//instantiate (option 2)
Name var;
var.field1 = value;
var.field2 = value;

// instantiate (option 2)
Name var = { 
    value, // field1
    value, // field2
};
```

Objects/classes
--------

About structure + functionality. If you find yourself adding lots of functionality to a struct, make it a class instead.

```c++
// in Name.h
#ifndef _NAME_H_  // this is the header guard
#define _NAME_H_

// declare
class Name {
    public:
        Name(); // constructor, no args
        Name(type arg1, type arg2);  // constructor, two args

        void MethodDeclaration();  // method, no args
        int OtherMethodDeclaration(type arg1);  // method, 1 arg

        type get_field() { return field_; }  // getter declared in line

    private:
        type field_; //private fields should end in an underscore
};

#endif  // end _NAME_H_ header guard


// in Name.cpp

#include "Name.h"


// no arg constructor
Name::Name() {
    field1_ = value;  // for example
}

// 2 arg constructor
Name::Name(type arg1, type arg2) {
    ...
}

void Name::MethodDeclaration() {
    // if you need to access a field, inside an object, use:
    // field_
    // this->field_
    ...
}

int Name::OtherMethodDeclaration(type arg1) {
    ...
}

// don't need to include the getter, already implemented in the header


// Insantiations
Name n();  // not a pointer
Name n2(arg1, arg2);  // using the 2 arg constructor
n.MethodDeclaration();  // use "." if the object variable isn't a pointer

Name * n3 = new Name(); // pointer!
n3->MethodDeclaration();  // use "->" if the object variable is a pointer (follow the arrow)
```



