## **Entity** 
* It is a **real world** item/concept that can exist on it's own.
*  It may be an object with **physical existence** (person, house) 
   or it may be an object with **conceptual existence** (company,
   job, university course).
### Entity Type
* It is a collection of entities with same attributes.
* It is defined in the database according to its **name** and **attribute**.
* **Entity instance** is single occurrence of an entity type. 
* Entity type is a represented as a rectangle enclosing the type name which is a **singular noun**.
![enter image description here](http://i.imgur.com/jWbv08J.png)

## **Strong and Weak Entities**

* Entity type that doesn’t have a key attribute on it's own is called **weak entity** and regular entity type that have key value are called **strong entity**.
* Entity belonging to weak entity type is identified by being related to specific entities from another entity type in combination with one of their attribute value.
* Weak entities have always a **total participation constraint** because they cannot be identified without an owner entity.
* The weak entities are represented by a **double lined rectangle (entity)** connected via a **double lined arrow (total participation constraint)** to a **double lined diamond (relationship)**.
<br>
  <img src ="http://i.imgur.com/KnSBVfg.png">
  
* In the example above **EMPLOYEE** is a **strong entity** and **DEPENDANTS** is a **weak entity**.