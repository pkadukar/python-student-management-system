# Student Management System

## Project Overview

The Student Management System is a menu-driven Python application created to maintain, retrieve, update, and remove student records efficiently. The application allows users to perform several operations on student data, including adding students, searching records, updating information, generating reports, and sorting records.

Student information is stored persistently in a CSV file, allowing records to remain available between program executions. I built this project to strengthen my Python programming skills while learning to design reusable software using modular functions, input validation, separation of concerns, and clean code architecture.

## Features

* Add new student records
* View all student records
* Search for students by first, middle, or last name
* Perform case-insensitive name searches
* Update a student’s name, age, or both
* Remove a selected student record
* Handle multiple matching search results through numbered selection
* Calculate the average student age
* Find the youngest and oldest students
* Count students above or below a specified age
* Display student records sorted by age
* Generate a summary report
* Store and retrieve records using a CSV file
* Validate names, ages, and numbered menu choices

## Technologies Used

* Python
* Google Colab
* CSV file storage
* Google Drive
* Git
* GitHub

## Project Structure

The application is organized into logical sections based on responsibility:

### Data Persistence

Functions responsible for loading student records from the CSV file and saving changes back to it.

* `load_students()`
* `save_students()`

### Validation Helpers

Reusable functions that validate user input before it is converted or used.

* `valid_name()`
* `valid_age()`
* `valid_choice()`
* `is_empty()`

### Search and Selection Helpers

Functions that centralize repeated student-search logic.

* `find_matching_students()`

### Student Management Operations

Functions that perform the main create, read, update, and delete operations.

* `add_student()`
* `view_students()`
* `update_student()`
* `remove_student()`
* `search_student()`

### Reports and Analysis

Functions that calculate statistics and summarize student records.

* `average_age()`
* `youngest_student()`
* `oldest_student()`
* `count_students_above_age()`
* `count_students_below_age()`
* `view_students_sorted()`
* `student_report()`

### Menu System

The program uses a metadata-driven menu to connect menu choices with their corresponding functions. Menu metadata also identifies whether an operation changes student data and therefore requires the CSV file to be updated.

* `menu`
* `run_menu()`

## Important Design Decisions

### Reusable Search Logic

The `find_matching_students()` helper centralizes student-search logic so that searching does not need to be rewritten inside multiple functions.

### Separation of Concerns

Each function has a focused responsibility. For example, validation functions return whether input is valid, search helpers return matching data, and menu functions control program flow.

### Guard Clauses

Invalid or empty cases are handled early using patterns such as:

```python
if is_empty(students):
    return
```

This keeps the main logic easier to read.

### Input Validation

User input is validated before conversion and use:

```text
Input
↓
Validate
↓
Convert
↓
Use
```

This prevents invalid names, ages, and menu selections from crashing the application.

### Object References

The project uses Python dictionary references when updating selected students. A selected student refers to the same dictionary stored in the main student list, allowing updates to modify the original record directly.

### Persistent Storage

Student records are stored in a CSV file so that changes remain available after the notebook or program is restarted.

## How to Run the Project

1. Open the project notebook in Google Colab.
2. Connect Google Drive if the CSV file is stored there.
3. Update `FILE_PATH` if necessary.
4. Run the notebook cells in order.
5. Load the student records:

```python
students = load_students()
```

6. Start the application:

```python
run_menu(students)
```

7. Select an option from the displayed menu.

## Example Menu

```text
Choose an option:

1. Add Student
2. View Students
3. Find Topper
4. Update Student
5. Remove Student
6. Search Student
7. Youngest Student
8. Average Age
9. Count Students Above an Age
10. Exit Program
11. Count Students Below an Age
12. Student Summary Report
13. View Students Sorted by Age
```

## Concepts Demonstrated

This project helped me practice and understand:

* Python functions and parameters
* Return values
* Lists and dictionaries
* Loops and conditional statements
* File reading and writing
* CSV-based data persistence
* Input validation
* Helper functions
* Guard clauses
* CRUD operations
* Partial and case-insensitive searching
* Sorting with key functions
* Object references
* Mutation versus reassignment
* Separation of concerns
* Reusable software architecture
* Metadata-driven menus
* Code organization and refactoring

## Lessons Learned

The most important lesson from this project was learning to think beyond making individual lines of code work. I began thinking about how the complete application should be organized, how repeated logic could be centralized, and how functions could be designed with clear responsibilities.

This project also strengthened my understanding of Python references. I learned the difference between modifying an existing dictionary and reassigning a variable to a different object.

## Possible Future Improvements

* Replace CSV storage with a relational database
* Add unique student identification numbers
* Build a graphical user interface
* Add more academic fields such as grades and courses
* Add automated tests
* Convert the notebook into a standalone Python application
* Add data visualizations and more advanced reports

## Project Status

**Version 1 completed**

The current version includes the planned student-management operations, validation, persistent CSV storage, reports, sorting, reusable helpers, and an organized menu system.

