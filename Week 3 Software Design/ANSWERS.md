# Week 3 Software Design

**Introduction**

**Motivating the need for software design**

**Problem 1**

Which is NOT an essential difficulty of building software?

Complexity

Changeability

Visibility -correct

Conformity

Answer
Correct: Visibility would be great! But unfortunately, “invisibility” is an essential difficulty because we cannot “see” software in the same way we see other engineering artifacts.

**Problem 2**

What is modeling (in the context of designing software)?

Identifying concepts and their relationships -correct

Identifying design patterns and their data structures

Identifying design patterns and their relationships

Refactoring architecture as necessary

Answer
Correct: Although the other operations can be part of the software design process, modeling refers to creating a “model” of our domain that can then be converted into a design.

**Problem 3**

What is NOT true about software design?

Good software design produces code that is easy to understand

Good software design produces the shortest pieces of code -correct

Good software design produces code that is easy to change

Software design is the process of converting requirements into a software artifact (code).

Answer
Correct: Understandability and changeability are certainly desirable qualities of software, and good design seeks to produce them. However, shorter pieces of code are not necessarily the aim of software design, since shorter code may, for instance, be hard to understand.

**Domain Modelling**

Problem 1

In grammatical parsing, which of the following is NOT a valid role assignment?

Noun: class

Adjective: subclass

Verb: attribute -correct

Noun: attribute

Answer
Correct: Verbs should be operations, not attributes.

**Problem 2**

A professor gives 10 lectures in a semester. Her students attend one or more lectures, and attendance is taken at the start and end (for latecomers) of every lecture. The lectures each focus on one topic and comes with a corresponding reading assignment. Using grammatical parsing, should the noun lecture be a class or attribute?

Class with subclasses such as LectureTopic, LectureAssignment, LectureAttendance.

Class with attributes such as topic, reading assignment, list of students attended and operations like updating attendance. -correct

Attribute: a Map from lecture topics (Strings) for the Professor class to attendance lists.

Attribute: a list of lectures (Strings) that a student attended.

Answer
Correct: It should be a class because it is its own entity and not part of another class. And things like topic, homework assignment, etc. should be attributes and not subclasses since they comprise the lecture and are not specific types of lectures.

**Representing a design with UML**

**Problem 1**

In Java, a Realization

“extends” an interface

“extends” a concrete class

“implements” an interface -correct

“implements” an abstract class

Answer
Correct: A Realization relationship means that the thing being realized cannot be instantiated on its own. In Java, this means that it is an interface or an abstract class. Keep in mind that in Java we “extend” an abstract class and “implement” an interface.

**Problem 2**

In Java, a Generalization

“implements” an interface

“implements” an abstract class

“extends” a concrete class -correct

“extends” an interface

Answer
Correct: A Generalization relationship means that both classes can be instantiated (i.e., are concrete) and that one is a specialization of the other.

**Problem 3**

A composition is a “has-a” relationship, where:

One class is part of another and can exist independently

One class is part of another but cannot exist independently -correct

One class is a specialized form of the other and provides additional behavior/attributes

One class is a generalized form of the other and provides additional behavior/attributes

Answer
Correct: Option #1 is “aggregation”. Options #3 and #4 are more related to “generalization.”

**Detailed UML class diagrams**

**Problem 1**

How do you describe 0 or more objects that can be used in an association? (Multiplicity 0 or more)

 n

 0 .. n

 0

 ** single asterisk -correct

Answer
Correct: The asterisk or “Kleene star” means “zero or more.”

**Problem 2**


If Dog is a specialization of Pet with an attribute breed, and the Pet UML specifies some methods and the attributes owner and name, how do you translate this relationship into Java?

Dog has a field of type Pet.

Dog extends Pet, which is an interface.
correct
Pet extends Dog, which is an abstract class. 

Dog extends Pet, which is an abstract class. -correct

Explanation:
Dog should definitely extend Pet, since Pet is a generalization of Dog. But we cannot “extend” an interface, so the only option would be to extend an abstract class.

**Software Quality**

**Problem 1**

“External” software quality refers to the quality of:

the code as human-readable text.

the code compiled into machine instructions. 

an executable program running on hardware in some environment. -correct

an executable program as human-readable text.

Explanation:
For external quality, we care about the properties of the software as it is actually executing. This is different from internal quality, which relates to the code as text that someone sees and reads.

 
**Problem 2**


What is NOT one of the four aspects of internal quality?

Reliability -correct

Analyzability

Changeability

Testability

Answer
Correct: Reliability is an aspect of external quality, not internal.

**Problem 3**

What does it mean for software to have stability?

Increased confidence that software is working. -correctly

The code is tolerant of changes to other parts of the code correct.

Changes in one part of the code require changes in other parts.

A programmer can easily incorporate new code.

Answer
Correct: When we think of software as “stable,” that means it is not easily affected by things that change elsewhere.

**Software Design Concepts**

**Problem 1**

How does the Monolith approach harm internal software quality?

Changeability: hard to know whether a change in one part will necessitate changes elsewhere.

Analyzability: hard to find the code you want to change.

Testability: hard to find the bug if something goes wrong.

All of the above -correct

Answer
Correct: When all of the code is in one place, its internal quality suffers!

**Problem 2**


You are creating an application that will allow users to (1) search data, (2) summarize it, or (3) exit out of the program. They can input their choices into a command line prompt, and the data that can be searched or summarized is stored in a text file. How would you design this software using the three-tier architecture?

Divide the program into the 3 major features specified (search, summarize, exit).

Divide the program into the user interface (here, command line), operations (search, summarize, exit), and the retrieval of data. -correct

Divide the program into the user inputs, the operations (search, summarize, exit), and the outputs.

Divide the program into the user interface, the user inputs, and the operations which produce outputs.

Answer
Correct: In the three-tier architecture, we always have a tier/layer for the user interface, one for the operations, and one for dealing with the storage of data.

**Problem 3**


What is the difference between modularity and functional independence?

They are synonyms

Functional independence is achieved by making sure each component addresses a single part of the functionality; 

modularity ensures that components have minimal dependence on other components.

Modularity ensures that each component addresses a single part of the functionality; functional independence is achieved by making sure components can use other components with minimal knowledge of the details of their implementation. 

Modularity ensures that each component addresses a single part of the functionality; functional independence is achieved by making sure components have minimal dependence on other components. -correct

Explanation:
These concepts are often confused with each other but modularity refers to the organization into modules, and functional independence refers to the fact that they don’t depend on each other too much.

**Modularity**

**Problem 1**

Which of the following is NOT an aspect of internal quality that is improved by modularity?

Analyzability: leads to smaller pieces of code, each of which is easier to understand.

Testability: being able to test individual pieces makes it easier to find and fix bugs.

Changeability: easy to find the code that needs to be change.

Stability: pieces of code can be reused in this application or other applications. -correct

Answer
Correct: Stability is not necessarily related to reuse of modules, but rather the effect that a change in one part of the code has on other parts. It is not improved by modularity, because the code can still be unstable, even if there are modules.

**Problem 2**

What is cohesion?

The extent to which the different classes in a program “go together”

The extent to which the modules “go together”

The extent to which the parts of a module (class) “go together” -correct

The extent to which the methods in a program “go together”

Answer
Correct: Cohesion is a property of a module itself, and whether the things in that module belong together.

**Functional Independence**

**Problem 1**

When viewing a UML class diagram, an indication of a problem with functional independence is demonstrated by:

A class being dependent on more than one other class.

A cyclic dependency in which classes are dependent on each other. -correct

A class having more than one field.

Two classes both being dependent on the same other class.

Answer
Correct: When there is a cyclic dependency, this means the classes are not independent and rely on each other.

**Problem 2**

Which of the following is necessarily an example of “tight coupling”?

Class Dog depends on class Toy. i
Class Dog depends on class Cat, and both extend class Animal.

Class Dog depends on class Person, which also depends on class Dog. -correct

Class Dog extends class Animal, which depends on class Person.

Explanation:
When two classes depend on each other, that is a form of tight coupling that indicates a problem with the design.


**Problem 3**

A class called CourseEnrollment maintains a list of all students who are enrolled in a course. A Student class consists of the student’s name, date of birth, and grade point average. If another class wants to get the students’ names from CourseEnrollment to include in a report, CourseEnrollment should:

have a method that returns all of the Student objects

have a method that returns a Student object, given the Student’s name

make the list of Student objects public

have a method that returns only the names of the students -correct

Answer
Correct: Although returning all the Student objects or making the list of Student objects public may seem okay, part of the idea of functional independence is only exposing the minimum amount of data necessary, and CourseEnrollment should only expose the students’ names, and nothing else. Therefore, a method that returns only the names is best.

**Abstraction**

**Problem 1**

A key concept in understanding abstraction is:

“Each module should only have one reason for changing.”

“Program to an interface, not an implementation.” -correct

“Do the simplest thing that works.”

“Separate how an object is created from how it is used.”

Answer
Correct: The goal of abstraction is that the user of a piece of code knows what it does (its interface) and not how it does it (its implementation).

**Problem 2**

You are creating a class to keep track of all the books in a library, and are defining a method to return the titles of all the books. The user of this method does not care about the order in which the books are stored. From an abstraction standpoint, the best return type for this method would be:

Set -correct

HashSet

TreeSet

LinkedList

Explanation:
By returning the most generic type (Set), you are able to hide the underlying representation so that the caller knows what this code does/returns without needing to know how.

**The Law of Demeter**

**Problem 1**

The Law of Demeter is related to which software design principle?

Modularity

Functional Independence

Abstraction -correct

Reliability

Answer
Correct: The law relates to the fact that a component should know what other components do but not how.

**Problem 2**

On which lines of the following code is the Law of Demeter violated? 

2, 3, 4, and 5

3 and 4 only

4 and 5 only -correct

3, 4, and 5 only

Answer
Correct: Lines 2 and 3 are not violations, because it is okay to call methods on the parameter “p.” However, line 4 is a violation because “l” is not an object created in this method, or a parameter, or a field. And line 5 is clearly a violation because we see the “message chain” of calling methods.

**Problem 3**

The goal of the Hide Delegate pattern is to:

improve abstraction

fix violations of the Law of Demeter

make it possible to change a class’ implementation and dependencies without needing to change the code that uses that class

all of the above -correct

Answer
Correct: Although the Hide Delegate pattern increases the number of methods in our design, it helps with abstraction by hiding the details of a class’ dependencies.

