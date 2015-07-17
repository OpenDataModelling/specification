

**Step 9: Mapping of Union Types**

For mapping a category whose defining superclass have different keys, it is customary to specify a new key attribute, called a surrogate key, when creating a relation to correspond to the category.

In the **example** below we can create a relation OWNER to correspond to the OWNER category and include any attributes of the category in this relation. The **primary key** of the **OWNER** relation is the **surrogate key**, which is called **OwnerId**.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src ="http://i.imgur.com/jKAqrKb.png">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src ="http://i.imgur.com/apa78Hm.png">

9) Union of OWNER with PERSON, BANK and COMPANY( Separate relation for OWNER &nbsp;&nbsp;&nbsp;&nbsp;created) 