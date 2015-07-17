
**Step 3 Mapping of Binary 1 : 1 Relationship Types.**

There are three possibilities while mapping a binary 1:1 relation. The relationship maybe

a) Mandatory at both ends.

b) Mandatory at one end and optional at the other.

c) Optional at both ends.

**a)** If the relationship is mandatory at both ends it is often possible to subsume one entity type into the other.

* The choice of which entity type subsumes the other depends on which is the more important entity type (more attributes, better key, semantic nature of them).

* The result of this amalgamation is that all the attributes of the `swallowed up' entity become attributes of the more important entity.

* The key of the subsumed entity type becomes a normal attribute.

* If there are any attributes in common, the duplicates are removed.

* The primary key of the new combined entity is usually the same as that of the original more important entity type.

**When not to combine**

There are a few reason why you might not combine a 1:1 mandatory relationship:

* the two entity types represent **different entities in the `real world'.**

* the entities participate in **very different relationships** with other entities.

* **efficiency considerations** when fast responses are required or different patterns of updating occur to the two different entity types.


**If not combined**

If the two entity types are kept separate then the association between them must be represented by a foreign key.

* The primary key of one entity type comes the foreign key in the other.

* It does not matter which way around it is done but you should not have a foreign key in each entity.

**Example**

* Consider two entity types; staff and contract.

* Each member of staff must have one contract and each contract must have one member of staff associated with it.

* It is therefore a mandatory relations at both ends.

<img src ="http://i.imgur.com/8Z4swCS.png">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;3.a) Mandatory relation at both ends.

* These two entity types could be **amalgamated into one.**

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Staff(emp_no, name, cont_no, start, end, position, salary)**

* **OR** they can be  kept apart and a foreign key (**in Staff**) is used

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **Staff(emp_no, name, contract_no)**
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Contract(cont_no, start, end, position, salary)**

* **OR** they can be  kept apart and a foreign key (**in Contract**) is used

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Staff(emp_no, name)**
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Contract(cont_no, start, end, position, salary, emp_no).**

**b)** If the relationship is **mandatory at one end and optional at the other** it is often  possible                                                                   to **subsume the entity type of the optional end into the mandatory end.**

It is better **NOT** to subsume the mandatory end into the optional end as this will create null entries. 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src ="http://i.imgur.com/XGSKLvL.png">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;3.b) 1:1 mapping with one end optional

If we add to the specification that **each staff member may have at most one contract** (thus making the relation optional at one end). 

* Map the foreign key into Staff - the key is null for staff without a contract.
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Staff(emp_no, name, contract_no)**
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Contract(cont_no, start, end, position, salary)**

* Map the foreign key into Contract - emp_no is mandatory thus never null.
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Staff(emp_no, name)**
  **Contract(cont_no, start, end, position, salary, emp_no)**

Here we have **NOT SUBSUMED** and kept the entries separate.

**When to subsume?**

The reasons for not subsuming are the same as before with the following additional reason.


* very few of the entities from the mandatory end are involved in the relationship. This could cause a lot of wasted space with many blank or null entries.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src ="http://i.imgur.com/77MNlPH.png">


&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;3.b) One end optional

* If only a few lecturers manage courses and Course is subsumed into Lecturer then there would be many null entries in the table.

 **Lecturer(lect_no, l_name, cno, c_name, type, yr_vetted, external)**

* It would be better to keep them separate.

 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Lecturer(lect_no, l_name)**
 **Course(cno, c_name, type, yr_vetted, external, lect_no)**

**Summary**

So for 1:1 optional relationships, **take the primary key from the `mandatory end' and add it to the `optional end' as a foreign key.**

**c.**  If the relationship is **optional at both ends** they **cannot** be amalgamated as you could not select a primary key. Instead, they are kept separate and one foreign key is used as before.

**Example**

<img src ="http://i.imgur.com/5g167MP.png">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;3.c) Both ends optional

* Each staff member may lease up to one car

* Each car may be leased by at most one member of staff

* If these were combined together...
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Staff_car(emp_no, name, reg_no, year, make, type, colour)**

what would be the primary key?

* If emp_no is used then all the cars which are not being leased will not have a key.

* Similarly, if the reg_no is used, all the staff not leasing a car will not have a key.

* A compound key will not work either.

Hence it is in the best interest to **keep the two entities separate and use a foreign key in one of the relations.**