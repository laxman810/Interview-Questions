# Programming Multiple Choice Questions

```
1. How will you free the allocated memory ?
A. remove(var-name);
B. free(var-name);
C. delete(var-name);
D. dalloc(var-name);
ANSWER: Option B
```

```
2. What is the similarity between a structure, union and enumeration?
A. All of them let you define new values
B. All of them let you define new data types
C. All of them let you define new pointers
D. All of them let you define new structures
ANSWER: Option B
```

```
3. What is (void*)0?
A. Representation of NULL pointer
B. Representation of void pointer
C. Error
D. None of above
ANSWER: Option A
```

```
4. Can you combine the following two statements into one?
   char *p; p = (char*) malloc(100);
A. char p = *malloc(100);
B. char *p = (char) malloc(100);
C. char *p = (char*)malloc(100);
D. char *p = (char *)(malloc*)(100);
ANSWER: Option C
```

```
5. How many bytes are occupied by near, far and huge pointers (DOS)?
A.	near=2 far=4 huge=4
B.	near=4 far=8 huge=8
C.	near=2 far=4 huge=8
D.	near=4 far=4 huge=8
ANSWER: Option A
```

```
6. If a variable is a pointer to a structure, then which of the following operator is used to access data members of the structure through the pointer variable?
A.	.
B.	&
C.	*
D.	->
ANSWER: Option D
```

```
7. What do the following declaration signify?
int (*pf)();
A.	pf is a pointer to function.
B.	pf is a function pointer.
C.	pf is a pointer to a function which return int
D.	pf is a function of pointer variable.
ANSWER: Option C
```

```
8. Which of the following is the correct order of evaluation for the below expression?
z = x + y * z / 4 % 2 - 1
A.	* / % + - =
B.	= * / % + -
C.	/ * % - + =
D.	* % / - + =
ANSWER: Option A
```

```
9. What will be the output of the following C code?
    #include <stdio.h>
    union u
    {
        struct
        {
            unsigned char x : 2;
            unsigned int y : 2;
        }p;
        int x;
    };
    int main()
    {
        union u u;
        u.p.x = 2;
        printf("%d\n", u.p.x);
    }
a) Compile time error
b) 2
c) Undefined behaviour
d) Depends on the standard
ANSWER: b
```

```
10. Comment on the output of following code:
  #include <stdio.h>
    main()
    {
        char *p = 0;
        *p = 'a';
        printf("value in pointer p is %c\n", *p);
    }
a) It will print a
b) It will print 0
c) Compile time error
d) Run time error
ANSWER:d
```

```
11. What is the output of this C code?
 #include <stdio.h>
    main()
    {
        int n = 0, m = 0;
        if (n > 0)
            if (m > 0)
                printf("True");
        else 
            printf("False");
    }
a) True
b) False
c) No Output will be printed
d) Run Time Error
ANSWER:c
```

```
12. What will be the output of the following C code?
#include <stdio.h>
    main()
    {
        int a = 1;
        printf("size of a is %d, ", sizeof(++a));
        printf("value of a is %d", a);
    };
a) size of a is 4, value of a is 1
b) size of a is 4, value of a is 2
c) size of a is 2, value of a is 2
d) size of a is 2, value of a is 2
ANSWER: a
```

```
13. What will be the output of the following C code?
   #include <stdio.h>
   printf("%d", sizeof(strlen("HELLOWORLD")));
a) Output, 4
b) Output, 10
c) Output, 16
d) Error, sizeof cannot evaluate size of a function
ANSWER: a
```

```
14. What will be the output of the following C code?
    #include <stdio.h>
    int x = 5;
    void main()
    {
        int x = 3;
        printf("%d", x);
        {
            int x = 4;
        }
        printf("%d", x);
    }
a) 3 3
b) 3 4
c) 3 5
d) Run time error
ANSWER: a
```

```
15. What could be the worst case height of an AVL tree?
A - 0.97 log n
B - 2.13 log n
C - 1.44 log n
D - n2 log n
ANSWER : C
```

```
16. What is the worst case time complexity of linear search algorithm?
A - Ο(1)
B - Ο(n)
C - Ο(log n)
D - Ο(n2)
ANSWER : D
```

```
17. Graph traversal is different from a tree traversal, because
A  trees are not connected.
B  graphs may have loops.
C  trees have root.
D  None is true as tree is a subset of graph.
ANSWER : C
```

```
18. Which among the below specified condition is applicable if the Queue is non - empty? 
a. rear > front
b. rear < front
c. rear = front
d. Unpredictable
ANSWER: A
```

```
19. Second most used data structure after array is
A Queue
B Stack
C Hash table
D Linked List
ANSWER D.
```

```
20. Which of the following statements is true for the dirty page in a page table? 
a. Helps to maintain LRU information
b. Allows only read on a page
c. Helps to avoid unnecessary writes on paging device
d. None of the above
ANSWER: C
```

```
21. Which of the following statements are true? 
a. Shortest remaining time first scheduling may cause starvation
b. Starvation may be caused by preemptive scheduling.
c. In terms of response time robin round is better than FCFS
d. All of the above statements are true
ANSWER: D
```

```
22. Which of the following type of class allows only one object of it to be created?
A.	Virtual class
B.	Abstract class
C.	Singleton class
D.	Friend class
ANSWER: Option C
```

```
23. Which of the following statements is correct?
A.	Base class pointer cannot point to derived class.
B.	Derived class pointer cannot point to base class.
C.	Pointer to derived class cannot be created.
D.	Pointer to base class cannot be created.
ANSWER: Option B
```

```
24. Which of the following is not the member of class?
A.	Static function
B.	Friend function
C.	Const function
D.	Virtual function
ANSWER: Option B
```

```
25. Which of the following is the correct way of declaring a function as constant?
A.	const int ShowData(void) { /* statements */ }
B.	int const ShowData(void) { /* statements */ }
C.	int ShowData(void) const { /* statements */ }
D.	Both A and B
ANSWER: Option C
```

```
26. Which of the following concepts is used to implement late binding?
A.	Virtual function
B.	Operator function
C.	Const function
D.	Static function
ANSWER: Option A
```

```
27. Which of the following statement is correct?
A.	C++ allows static type checking.
B.	C++ allows dynamic type checking.
C.	C++ allows static member function be of type const.
D.	Both A and B.
ANSWER: Option D
```

```
28. Which of the following keyword is used to overload an operator?
A.	overload
B.	operator
C.	friend
D.	override
ANSWER: Option B
```

```
29. What will happen if a class is not having any name?
A.	It cannot have a destructor.
B.	It cannot have a constructor.
C.	It is not allowed.
D.	Both A and B.
ANSWER: Option D
```

```
30. Which of the following provides a reuse mechanism?
A.	Abstraction
B.	Inheritance
C.	Dynamic binding
D.	Encapsulation
ANSWER: Option B
```

```
31. An expression A.B in C++ means ____
A. A is member of object B
B. B is member of Object A
C. Product of A and B
D. None of these
ANSWER : Option B
```

```
32. Which of the following statement is correct about the references?
A.	A reference must always be initialized within functions.
B.	A reference must always be initialized outside all functions.
C.	A reference must always be initialized.
D.	Both A and C.
ANSWER: Option C
```

```
33. The part of machine level instruction, which tells the central processor what has to be done, is
A.	Operation code
B.	Address
C.	Locator
D.	Flip-Flop
E.	None of the above
ANSWER: Option A
```

```
34. To avoid the race condition, the number of processes that may be simultaneously inside their critical section is
A.	8
B.	1
C.	16
D.	0
E.	None of the above
ANSWER: Option B
```

```
35. A system program that combines the separately compiled modules of a program into a form suitable for execution
A.	assembler
B.	linking loader
C.	cross compiler
D.	load and go
E.	None of the above
ANSWER: Option B
```

```
36. A relation is in this form if it is in BCNF and has no multivalued dependencies:
A.	second normal form.
B.	third normal form.
C.	fourth normal form.
D.	domain/key normal form.
ANSWER: Option C
```

```
37. The primary key is selected from the:
A.	composite keys.
B.	determinants.
C.	candidate keys.
D.	foreign keys.
ANSWER: Option C
```

```
38. What is the time complexity to count the number of elements in the linked list?
a) O(1)
b) O(n)
c) O(logn)
d) None of the mentioned
ANSWER: b
```

```
39. In circular linked list, insertion of node requires modification of?
a)	One pointer
b)	Two pointer
c)	Three pointer
d)	None
ANSWER: B
```

```
40.	The postfix form of A*B+C/D is?
a)	*AB/CD+
b)	AB*CD/+
c)	A*BC+/D
d)	ABCD+/*
ANSWER: b
```