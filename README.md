Expense Tracker
A desktop expense tracker built in Java with Swing. Add, edit, and delete expenses in a table, see your running total, and have everything saved automatically between sessions.
Features
Add an expense with an amount and a description
Edit an existing expense: select a row, type the new values, and click Edit
Delete the selected expense
Summary button that shows the total of all expenses
Automatic saving: data is written to expenses.ser after every add, edit, or delete, and loaded again on startup
Input validation: empty fields, non-numeric amounts, and missing row selections show clear error dialogs
Project structure
File
Role
Expense.java
Data class holding an amount and a description. Implements Serializable so it can be saved to disk.
ExpenseManager.java
Business logic: stores the list of expenses, handles add/update/remove, calculates the total, and saves/loads the list using Java object serialization.
ExpenseTrackerGUI.java
Swing user interface (JFrame, JTable, buttons). Contains the main method.


The GUI is kept separate from the data logic, so ExpenseManager could be reused with a different interface.
Requirements
Java Development Kit (JDK) 11 or newer
Running
The source files use the package main.expenseTracker. From the src folder:

javac main/expenseTracker/*.java

java main.expenseTracker.ExpenseTrackerGUI

Or open the project in IntelliJ IDEA and run ExpenseTrackerGUI.

The app creates expenses.ser in the folder you run it from. Delete that file to start with an empty list.
How to use
Type an amount and a description, then click Add.
To change an entry, click its row, enter the corrected amount and description in the fields, then click Edit.
To remove an entry, click its row and click Delete.
Click Summary to see the total.
Concepts demonstrated
Object-oriented design with separated data, logic, and UI classes
Swing event handling with lambda expressions
Java serialization (ObjectOutputStream / ObjectInputStream) for persistence
Exception handling for bad input and missing files
Possible improvements
Dates and categories for each expense
Filtering and sorting
Pre-filling the input fields when a row is selected
Storing data in a portable format such as CSV or JSON instead of Java serialization
