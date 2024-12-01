# The Book of C Plus Plus

Written by Zhouzhou Zhang.

Reference: Bjarne Stroustrup, The C++ Programming Language, Fourth Edition.

# 1.Vector

Vector is the most important container in C++. It is a dynamic list and fully implemented by C++ itself and that is why C++ is one of the most powerful programming language. In the book mentioned in reference, the author, also the creator of C++, will guide you through every standard library in C++ including vector. However, the book is more than 3000 pages, which is scary. So now I, Zhou, am here to testify that the C++ is true, that C++ is almighty, that C++ is the tool given by the eternal father. I said all of is in the name of Jesus Christ. Amen.

It came to pass that Vector is mostly the same as the list in Python. As people use Python list the most, the Vector in C++ shall be powerful as well. First, shall you behold the 
way to declare a Vector and add elements dynamically, besides the detail of the grammer. Then you will probably understand why you should declare it like this. If not, go learn some python first. In C++ you have to declare the type of the Vector as well, "<int>" is so called a Template, which helps you declare a data type with different return value.

    #Python
    list = [1,2,3]
    list.append(4)#return [1,2,3,4]

    //C++
    vector<int> v1 = {1,2,3,4,5};
    v1.pushback(6); //return v1={1,2,3,4,5,6}

Imagining you are going to build a Vector on your own, to be the most simple, you shall write some code like this. You are trying to build a Vector for int, and then for string, and then for float, and then whatever, it can be even any struct or class or vector itself(that's how we build a 2D array). You are not likely to build thousands of Vector for different data type

    int int_vector (int n);
    string str_vector(string s);

And that is why we use the Template, so far you don't need to know how to use Template to build a Class(or may say your data type). Shall you only know how to use it and receive the gospel from God. And I can testify that Vector is the savior of all programmmers and C++ is the most powerful language. I said all of it in the name of Jesus Christ, Amen.

    vector<string> str_v;
    vector<int> int_v;

And it came to pass that our eternal father hast also given us the way to operate the Vector. Behold that "= {1,2,3,4,5,6}", which is how we initialize the Vector. "{1,2,3,4,5,6}" generates a list and "=" assigns this list to the Vector v1. Also for sure is you declaring the Vector without assignments because Vector is built on a industrial standard, say, Vector would maintain empty if you don't assign value to it. However, it is still not recommended to leave data uninitialized as the gospel of God can not spread all over the memory hierachy. Behold that "pushback(6)", this is a method inside class Vector, of course shall you use "v1" +"." + "pushback()" instead of "pushback(v1)" as all of these methods are built inside the class Vector.

And it came to pass that the we need to pray to god, as well as we need to include the header file. Behold that we don't need ".h" anymore, which is because C++ is the gospel from God and God loveth all of us. And I know that is true, for I have seen the power of including this header file. And I said all of it in the name of Jesus Christ, Amen.

    include "vector"

And it came to pass that we need to read the script, as well as we need to use the compiler. The compiler for C++ is g++ which should be installed together with gcc. Add the bin file to the path on your own of course. Use following command to check whether it has been installed.

    g++ --version

## 1.1 Vector Declaration/Initiliaztion

Vector is declared using something called "template"

    vector<int> v1; //<int> is a template

Template is a technique that allows the class use different data types for its member variable. In C, you have to declare the data type when consturting the class. For example, a queue for int and another queue for string. Using a template you can just assume the queue can be for any data type.

    vector<string> v2; //vector of string
    vector<unsigned> v3; //vector of unsigned value

Alongsides Declaration there are multiple ways to initiliaztion

    //clear the code ahove...

Initilization with a list

    vector<int> v1 = {1,2,3,4,5};
    cout<< v1[0] <<"\n";
    //returns 1

Initilization with size and initial value in each place

    vector<int> v2 (32,0); //32 sizes with value 0

Initilization by copying and moving another vector

    vector<int> v3 (v2); //Holds the same value as v2
    vector<int> v4 (move(v2)); //v4 Becomes v2, v2 is no longer existed.

## 1.2 Vector Access

Use operator[] to access elements

    v1[0];
    //returns 1

Use at() to access elements with border-check

    //v1 = {1,2,3,4,5}
    v1.at(5);
    //raiseError
    v1.at(0);
    //returns 1

Use front() and back() to access elements

    v1.front();
    //returns 1
    v1.back();
    //returns 5

## 1.3 Vector Modifacation

Use push_back() to append value

    //v1 = {1,2,3,4,5}
    v1.push_back(6);
    //returns {1,2,3,4,5,6}

Use pop_back() to pop value

    v1.pop_back();
    //returns {1,2,3,4,5}

Use insert() with iterator to insert element. Iterator is a pointer pointing to the element. We must use iterator as the method needs memory address. v1.begin() + 1 means "just before the second element"

    v1.insert(v1.begin() + 1, 3);
    //returns {1,3,2,3,4,5}

Use erase() with iterator to erase element.

    v1.erase(v1.begin());
    //returns {3,2,3,4,5}

Use clear() to clear all elements while maintaing the size

    v1.clear();
    //returns {}

Use swap() to exchange elements between two vectors.
