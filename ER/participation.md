### Participation Constraints (Optionality)

* Specifies if the existence of an entity depends on it being related to another entity via relationship.
* Specifies minimum number of relationship instances each entity can participate in.
* The two types of participation are: Total and Partial

       &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src ="http://i.imgur.com/kL5xdVc.png" >
* <u>Example</u>: If a company policy says that every employee must work for the department then the participation of employees in **work-for** is **total**.

<img src ="http://i.imgur.com/YEVmO1W.png" >

* However in a relationship between employees and department: **MANAGE** , we cant say that every employee must **MANAGE** a department. Hence the relationship in this case is **partial**.

<img src ="http://i.imgur.com/Z1UGoNH.png">

* **Total partcipation** is indicated by a **double line** and **Partial partcipation** is indicated by a **single line**.
* As shown in the above example **relationships can also have attributes**. For example relationship **MANAGES** has an attribute **Start-date**.