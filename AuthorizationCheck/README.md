
# How to do authority check in **ABAP**?
---

- ### The SAP system is a very large and integrated system that can access all modules, so we need to define certain privileges for users. In other words authorization check. 

*** 
* ### For example, user X has permission to view data with CARR_ID value 'AA' in the SCARR table. CARR_ID may not be authorized to see data with 'AZ' value.

 ### Let's see this with an example. 

 ### I am going to try to explain athority check with images.

---

* ### First of all , we should know that in this section we will use **three transaction code** to create authorization control.

 ### 1. su20 tcode
 ### 2. su21 tcode
 ### 3. pfcg tcode 

*** 

## 1. Creating Authorization Field with su20

---

![](images/1.JPG)

### First we creat a authorization field , after we clicked it we saw a page like as follow.
![](images/2.JPG)

 >  ### In here we defined a authorization field that starts with 'Z' (because we are creating it..)
>
> ### Second one is to define data element. We choose S_CARRID because we check if user has athority to access this data element or not. 
>
> ### Lastly we choose the control table and then save the field. 

 ![](images/3.JPG)

 ---

 ![](images/4.JPG)

 ---

![](images/5.JPG)

---

> ### As we can see in pictures above after we save the field we created it the system asks us to save it into a ** package ** we created before.
> ### After save the package then system asks us to save it into a request too. In here I took a new request but if you want you can use old one as well. Finally we saved the request too , we will see our field we created but it is empty for now as we can see. 

## 2. Creating authorization object with su21

---

![](images/6.JPG)

> ### First we should create an ** Authorization Object Class ** before authorization object.

![](images/7.JPG)

* ### You can give any name start with 'Z' to your class and don't forget to describe your class too.

* ### After save that The system ask us to save it into a package and request too as we did before in creating authorization field. 

+ ### Next step is to create an Authorization Object.

![](images/8.JPG)

---
### We create an authorization object name start with 'Z' again. After describe it as follows. We define class that we create before. Lastly , of course we indicate our package name. 

---
![](images/9.JPG)

* ### After we saved the object we should see a screen like picture above.

 ![](images/10.JPG)

* ### We describe the authorization field (ZCARRID_22) we created beginning of the program with tcode su20. Activity field allows us to choose authority . 

![](images/11.JPG)

 * ### We clicked the pencil next to the ACVTY field we can see a screen. We choose Display activity and authorization value is '03'.

## 3. Creating Role with pfcg tcode

![](images/12.JPG)
 
 * ### We create a role starts with 'Z' and then click the single role. 

![](images/13.JPG)

* ### After we saved the role we will see a screen like above. We should write a description. 

+  ### We are selecting "**Authorizations** " section and then click Change Authorization Data to edit it. We will see a pop up , we should choose don't select template .


![](images/14.JPG)

---
### We should define our authorization Object **Manually**.

--- 
![](images/15.JPG)

- ### when we go to the lowest layer in the hierarchy , we saw field we defined before. 

- ### First ACTVY field should define and save after that ZCARRID_22 should define and save .

![](images/16.JPG)
![](images/17.JPG)

* ### After we defined the fields we should save and generate it. Generate button is red and white color also left side of the delete button object.

> # congratulations !!!! 
>
> # you create the object.

![](images/18.JPG)

---
* ### How we can call it in our program ?  Let's see...

* ### First we click the "Pattern" button. After we should see a select pattern screen and there is Authorıty-check button there. When we write our authorization object name then we can see that its codes will come to the program.  

![](images/19.JPG)

---

* ### This field we just change p_carrid and ACTVY field value "03" .  ( p_carrid is our parameter . We are searching from this)





