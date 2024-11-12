# C++: A LeetCode Approach
Written by Zhouzhou Zhang.

Reference: Bjarne Stroustrup, The C++ Programming Language, Fourth Edition.

## 1. Vector

The list in Python is just like the vector in C++

    #Python
    list = [1,2,3]
    list.append(4)#return [1,2,3,4]

    //C++
    vector<int> v1 = {1,2,3,4,5};
    v1.pushback(6); //return v1={1,2,3,4,5,6}

The header file should always be included. Note the header file no longer has ".h" than C

    include "vector"

This header file is included in the standard libaray, which means you can always include it with a compiler

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