
## Standart variable types in ABAP...

## Complete types

- Date (D)
 
```` Abap
DATA gv_date TYPE D.
gv_date = 20221112.

DATA gv_date2 TYPE D.
gv_date2 = sy-datum.  "" It gives current date.
````
- Time (T)

```` Abap
DATA gv_time TYPE T.
gv_time = 102305.

DATA gv_time2 TYPE T.
gv_time2 = sy-uzeit. "" It gives current time.

````
- Integer and Float types (I) - (F)

```` Abap
DATA gv_num1 TYPE decfloat16.
DATA gv_num2 TYPE int1. ""Maximum length is 3.
DATA gv_num3 TYPE int2. " Maximum length is 5.
DATA gv_num4 TYPE int4. " Maximum length is 10.


````
- String (S)

````Abap
DATA gv_var1 TYPE String.
gv_var1 = 'Hello World!' .

````

## Uncomplete Types

- CHAR (C)
- Numerical character (N)
- Byte (X)
- Decimal ,packed Number (P)

```` Abap

DATA : gv_city TYPE C LENGTH 12,
       gv_perc TYPE P LENGTH 3 DECIMALS 2.
       
gv_city = 'TURKEY'.
gv_perc = 32,12. "" Declaring variables

````









