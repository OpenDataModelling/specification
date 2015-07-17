**Step 4 Mapping of Binary 1: N Relationship Types.**

To map 1:N relationships, the **primary key on the '1 side'** of the relationship **is added to 'N side' as a foreign key.**

**Example**

<img src ="http://i.imgur.com/7vpQVdC.png">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;4) Mapping 1:N relationship ‘course-student’

* Assuming that the entity types have the following attributes:
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Course(course_no, c_name)**
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Student(matric_no, st_name, dob)**

* Then **after mapping**, the following relations are produced:
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Course(course_no, c_name)**
&nbsp;&nbsp;&nbsp; **Student(matric_no, st_name, dob, course_no)**

* If an entity type participates in several 1:N relationships, then you apply the rule to each relationship, and add foreign keys as appropriate.
