# Ex. No: 6 Creating Cursors using PL/SQL
## DATE:8/9/23
### AIM: To create a cursor using PL/SQL.

### Steps:
1. Create employee table with following attributes (empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);
2. Create a cursor named as employee_cursor
3. Using cursor read each record and display the result
4. Close the cursor

### Program:
```SQL> CREATE TABLE employs (
  2  empid NUMBER,
  3    empname VARCHAR(10),
  4    dept VARCHAR(10),
  5    salary NUMBER
  6  );
```

### Create employee table
![Ex 6 table](https://github.com/BalaSathiesh/Ex-no-6-Creating-Cursors-using-PL-SQL/assets/128462891/d27acd3e-fdfa-4d79-ad9b-1acd65df7f97)


```
SQL> DECLARE
  2  CURSOR employs_cursor IS
  3  SELECT empid, empname, dept, salary
  4  FROM employs;
  5  emp_id NUMBER;
  6  emp_name VARCHAR(15);
  7  emp_dept VARCHAR(15);
  8  emp_salary NUMBER;
  9  BEGIN
 10  OPEN employs_cursor;
 11  LOOP
 12  FETCH employs_cursor INTO emp_id, emp_name, emp_dept, emp_salary;
 13  EXIT WHEN employs_cursor%NOTFOUND;
 14  DBMS_OUTPUT.PUT_LINE('EMPID: ' || emp_id);
 15  DBMS_OUTPUT.PUT_LINE('EMPNAME: ' || emp_name);
 16  DBMS_OUTPUT.PUT_LINE('DEPT: ' || emp_dept);
 17  DBMS_OUTPUT.PUT_LINE('SALARY: ' || emp_salary);
 18  END LOOP;
 19  CLOSE employs_cursor;
 20  END;
 21  /

PL/SQL procedure successfully completed.
```
### PLSQL Cursor code
![Ex 6 procedure](https://github.com/BalaSathiesh/Ex-no-6-Creating-Cursors-using-PL-SQL/assets/128462891/e9c9677c-1dbd-4752-90a8-c214abfcf5dc)

### Output:
![Ex 6 output](https://github.com/BalaSathiesh/Ex-no-6-Creating-Cursors-using-PL-SQL/assets/128462891/34026896-6edd-4c07-941e-69b340851fb2)

### Result:
          Thus, To create a cursor using PL/SQL completed successfully.
