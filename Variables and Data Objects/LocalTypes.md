
### Creating Local Variable TYPES

````Abap
TYPES gty_type1 TYPE c LENGTH 10.
DATA gv_num1 TYPE gty_type1 VALUE '21'.
WRITE gv_num1.

````
## CONSTANTS variable

````Abap
CONSTANTS gv_const TYPE I VALUE 25.

````

## Data Declarations

- Example 1
````Abap
PARAMETERS pa_num TYPE i. 
DATA gv_num TYPE i.
DATA gv_result TYPE i. "" Global variable

DATA lv_result TYPE i. "" Local variable

gv_num = 1.
MOVE pa_num TO gv_result. "" Moving input value to global data

lv_result = gv_result.

ADD 1 TO lv_result. 

WRITE : 'Global Variable :' , gv_result.
NEW-LINE. "" It gives a space line.
WRITE : 'Local Variable :' , lv_result.

````
- Example 2
````Abap
TYPES : BEGIN OF gty_address,
          city   TYPE text30,
          region TYPE text30,
        END OF gty_address.

DATA : gs_address TYPE gty_address,
      gs_address2 LIKE gs_address.

gs_address-city = ' ANKARA'.
gs_address-region = 'Çankaya'.

MOVE CORRESPONDING gs_address TO gs_address2.

````
