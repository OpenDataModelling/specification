## **Superclass and Subclass**
* An entity type may have additional meaningful sub groupings of its entities.

* For example: EMPLOYEE may be further grouped into SECRETARY, ENGINEER, MANAGER, TECHNICIAN, SALARIED_EMPLOYEE, HOURLY_EMPLOYEE etc.
 
* In the above example, each of these groupings is a subset of EMPLOYEE entity and are called the **subclass** of EMPLOYEE. On the other hand, EMPLOYEE is the **superclass** of each of these **subclasses**  

* The relationship among them is called **superclass/subclass** relationships. For example EMPLOYEE/SECRETARY, EMPLOYEE/TECHNICIAN.
* The relationship is represented as: &nbsp;&nbsp;&nbsp;&nbsp;<img src ="http://i.imgur.com/YMny2IE.jpg">

* They are also called **IS-A relationship**. For example SECRETARY IS-A EMPLOYEE, TECHNICIAN IS-A EMPLOYEE.

<img src ="http://i.stack.imgur.com/13y38.jpg">

## **Specialisation**

* An entity that is a member of a subclass **inherits** all **attributes** of the entity as a member of the superclass. It also **inherits** all the **relationships**

* **Specialization** constructs the lower level entity set that are subsets of a higher level entity set. It is the process of defining a set of subclasses of a superclass. 
* The set of subclasses is based on some distinguishing characteristics of the entities in the superclass. Example: {SECRETARY, ENGINEER, TECHNICIAN} is a specialization of EMPLOYEE based upon job type. 

<img src="http://i.imgur.com/5OBKltd.jpg">

