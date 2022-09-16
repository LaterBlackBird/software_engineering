# SOLID
****
## **Single Responsibility** 
each class/function should do one thing, and one thing well.  _Fragment out what a function is doing in to smaller more managable chunks._  Instead of having all code ran by one function or returned by one component - separate these out so they can be reused or modified more easily.

## **Open / Closed** 
each class/function should be open to extension, but closed to modification from other classes/functions.  _Make big components from small ones._  Avoid 'tight-coupling' between components (AKA: making one component able to break another).  This is mostly taken care of if we adhere to atomic design.

## **Liskov Substitution**
	Not Used In Modern React
When extending a class, make sure the base class is as generic as needed to be a true representation of every subclass.  A subclass should be interchangable with the parent class without affecting functionality.  The parent class should not have methods that do not pertain to a child class ( ex of bad code = vehicle class has engine type, but bicycle extends vehicle ).

## **Interface Segregation**
*Only pass props that a component needs, and nothing else.*  technically the pricinciple states that you shouldn't force a user to use a certain type of interface, but this can be translated in to making a function use a speific version of a class or object.  Instead of passing in a books object prop, and making the component use book.title, we should really just send bookTitle as a prop because if the book object changes in the future, the child component will break.

## **Dependency Inversion**
Introduce abstraction with high level code, so that low level code is not mixed in.  "Hide the wiring behind the walls".  Ties is well is Single Responsibility.  For instance, we should separate out calls to the backend, manipulating data, and rendering components.