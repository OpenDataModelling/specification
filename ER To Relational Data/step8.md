**Step 8 Mapping of Specialization types.**

There are three ways of implementing superclasses and subclasses and it depends on the application which will be the most suitable.
Only the first method is a true reflection of the superclasses and subclasses and if either of the other methods is preferential then the model should not have subclasses.

1) One relation for the superclass and one relation for each subclass.

2) One relation for each subclass.

3) One relation for the superclass.

**Example**

<img src ="http://i.imgur.com/rFD9zUc.png">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;8) Superclass/Subclass mapping example

**1) One relation for the superclass and one relation for each subclass:**

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Staff(staff_no, name, address, dob)**
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Manager(staff_no, bonus)** 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Secretary(staff_no, wp_skills)**
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Sales_personnel(staff_no, sales_area, car_allowance)**

The primary key of the superclass is mapped into each subclass and becomes the subclasses primary key. This represents most closely the EER model. However it can cause efficiency problems as there needs to be a lot of joins if the additional information is often needed for all staff.

**2) One relation for each subclass:**

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Manager(staff_no,name,address,dob,bonus)** 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Secretary(staff_no,name,address,dob,wp_skills)**
 &nbsp;**Sales_personnel(staff_no,name,address,dob,sales_area, car_allowance)**

All attributes are mapped into each subclass. It is equivalent to having three separate entity types and no superclass.

It is **useful** if there are no overlapping entities and there are no relationships between the superclass and other entity types.

 It is **poor** if the subclasses are not disjoint as there is data duplication in each relation which can cause problems with consistency.

**3) One relation for the superclass:**

**Staff(staff_no,name,address,dob, bonus, wp_skills, sales_area, car_allowance)**

This represents a single entity type with no subclasses.

This is **not good** if the subclasses are not disjoint or if there are relationships between the subclasses and the other entities. In addition, there will be many null fields if the subclasses do not overlap a lot. 

However, **it avoids** any joins to get additional information about each member of staff.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src ="http://i.imgur.com/6BUIDu0.png">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;8) ER diagram representation( EMPLOYEE is the superclass)



