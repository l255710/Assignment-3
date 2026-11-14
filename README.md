# Assignment 3: Student Management Portal.

\[Iram Jehangir\] \[25L-5710\]  
\[Simra Anees\] \[25L-5072\]

---

## Features

- Login with a limit of 3 attempts  
- Add a student (ID, name, course, marks)  
- Search students by ID or part of a name  
- Update a student's marks  
- Delete a student  
- View all students in a table  
- Generate a report (total, average, highest, lowest, grade distribution) and save it  
- **Own feature:** rank students from highest to lowest marks (bubble sort)

## Python concepts demonstrated

| Concept | Where it is used |
| :---- | :---- |
| Functions (def) with parameters and return | user\_login(), add\_record(), search\_record(), generate\_report(), and others |
| Loops (while, for) | while True main menu loop; for loops for loading, searching, reporting and ranking |
| File handling (read, write, append) | load\_students(), save\_students(), append\_student(), save\_report() |
| Exception handling (try, except, finally) | FileNotFoundError, PermissionError, ValueError handled so the program never crashes |

## Repository contents

| File | Description |
| :---- | :---- |
| Assignment 3 | Jupyter Notebook with all the code, explanations and sample test runs |
| README | This file |

**Default login:** username admin, password admin123

## Menu options

```
--- STUDENT PORTAL ---
1. Add student
2. Search student
3. Update marks
4. Delete student
5. View all students
6. Generate report
7. Exit
8. Show ranking
```

## Data file format

Each line holds one record. Fields are separated by the pipe character \|, because names can contain commas.

students.txt

```
S1|Ayesha|PAI|88.5
S2|Bilal|PAI|62.0
S3|Hamza|PAI|95.0
```

users.txt

```
admin|admin123
```

## Error handling

| Problem | How it is handled |
| :---- | :---- |
| Data file missing | Starts with empty data and creates the file when saving |
| Users file missing | Creates a default admin account |
| No permission to read or write a file | Prints a message and continues |
| Letters typed instead of marks | Asks again (ValueError caught in a while loop) |
| Marks outside 0-100 | Rejected, asks again |
| Damaged line in a data file | Line is skipped with a warning |
| Empty fields or \` | \` in input |
| Invalid menu choice | Message shown, menu repeats |

## Sample output

Report (menu option 6):

```
===== STUDENT REPORT =====
Total students : 3
Average marks  : 81.83
Highest        : Hamza (95.0)
Lowest         : Bilal (62.0)
Grades         : A=2 B=0 C=1 D=0 F=0
```

Ranking (menu option 8):

```
1 Hamza 95.0
2 Ayesha 88.5
3 Bilal 62.0
```

## Limitations and future work

- Passwords are stored as plain text to keep the code basic; a real system should hash them.  
- A graphical or web frontend (Tkinter, Streamlit) could replace the terminal menu.  
- A database would suit larger amounts of data better than text files.
