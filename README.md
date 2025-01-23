# coding-samurai-project

(1)Build a command-line to-do list application where
users can add, delete, and view tasks.
• Skills: Lists, loops, user input, file handling.

import os
# Define a file to store the tasks
TODO_LIST_FILE = "todo_list.txt"


def load_tasks():
    """Load tasks from the file."""
    if not os.path.exists(TODO_LIST_FILE):
        return []
    
    with open(TODO_LIST_FILE, "r") as file:
        tasks = file.readlines()
    
    return [task.strip() for task in tasks]


def save_tasks(tasks):
    """Save tasks to the file."""
    with open(TODO_LIST_FILE, "w") as file:
        for task in tasks:
            file.write(f"{task}\n")


def add_task(task):
    """Add a new task."""
    tasks = load_tasks()
    tasks.append(task)
    save_tasks(tasks)
    print(f"Task '{task}' added.")


def delete_task(task_number):
    """Delete a task by its number."""
    tasks = load_tasks()
    if task_number < 1 or task_number > len(tasks):
        print("Invalid task number.")
        return

    deleted_task = tasks.pop(task_number - 1)
    save_tasks(tasks)
    print(f"Task '{deleted_task}' deleted.")


def view_tasks():
    """Display the list of tasks."""
    tasks = load_tasks()
    if not tasks:
        print("No tasks to show.")
        return
    
    print("Your To-Do List:")
    for idx, task in enumerate(tasks, 1):
        print(f"{idx}. {task}")


def main():
    """Main function to run the application."""
    while True:
        print("\n--- To-Do List Application ---")
        print("1. View tasks")
        print("2. Add task")
        print("3. Delete task")
        print("4. Exit")
        
        choice = input("Enter your choice (1-4): ").strip()
        
        if choice == "1":
            view_tasks()
        elif choice == "2":
            task = input("Enter the task to add: ").strip()
            add_task(task)
        elif choice == "3":
            try:
                task_number = int(input("Enter task number to delete: ").strip())
                delete_task(task_number)
            except ValueError:
                print("Please enter a valid number.")
        elif choice == "4":
            print("Exiting the application. Goodbye!")
            break
        else:
            print("Invalid choice. Please enter a number between 1 and 4.")
if __name__ == "__main__":
    main()

    OUTPUT
--- To-Do List Application ---
1. View tasks
2. Add task
3. Delete task
4. Exit
Enter your choice (1-4): 2
Enter the task to add: Github
Task 'Github' added.

--- To-Do List Application ---
1. View tasks
2. Add task
3. Delete task
4. Exit
Enter your choice (1-4): 2    
Enter the task to add: Coding Samurai
Task 'Coding Samurai' added.

--- To-Do List Application ---
1. View tasks
2. Add task
3. Delete task
4. Exit
Enter your choice (1-4): 2
Enter the task to add: Python Developement
Task 'Python Developement' added.

--- To-Do List Application ---
1. View tasks
2. Add task
3. Delete task
4. Exit
Enter your choice (1-4): 2
Enter the task to add: internship
Task 'internship' added.

--- To-Do List Application ---
1. View tasks
2. Add task
3. Delete task
4. Exit
Enter your choice (1-4): 1
Your To-Do List:
1. omkar ghadge
2. python samurai
3. apna collage
4. Github
5. Coding Samurai
6. Python Developement
7. internship

--- To-Do List Application ---
1. View tasks
2. Add task
3. Delete task
4. Exit
Enter your choice (1-4): 3
Enter task number to delete: 1
Task 'omkar ghadge' deleted.

--- To-Do List Application ---
1. View tasks
2. Add task
3. Delete task
4. Exit
Enter your choice (1-4): 3
Enter task number to delete: 3
Task 'Github' deleted.

--- To-Do List Application ---
1. View tasks
2. Add task
3. Delete task
4. Exit
Enter your choice (1-4): 1
Your To-Do List:
1. python samurai
2. apna collage
3. Coding Samurai
4. Python Developement
5. internship

--- To-Do List Application ---
1. View tasks
2. Add task
3. Delete task
4. Exit
Enter your choice (1-4): 4
Exiting the application. Goodbye!


 (2) Create a simple calculator that can perform basic
     operations like addition,subtraction, multiplication, and division.
    • Skills: Basic syntax, user input, conditionals.

def add(x, y):
    return x + y

def subtract(x, y):
    return x - y

def multiply(x, y):
    return x * y

def divide(x, y):
    if y == 0:
        return "Error: Division by zero is not allowed."
    return x / y

def main():
    print("Simple Command-Line Calculator")
    

    while True:
        print("Operations:")
        print("1. Addition")
        print("2. Subtraction")
        print("3. Multiplication")
        print("4. Division")
        print("5. Quit")

        choice1 = input("Enter your choice (1-5): ")

        if choice1== "5":
            print("Goodbye!")
            break

        elif choice1 in ["1", "2", "3", "4"]:
            try:
                num1 = int(input("Enter the first number: "))
                num2 = int(input("Enter the second number: "))

                if choice1 == "1":
                    print(f"{num1} + {num2} = {add(num1, num2)}")
                elif choice1 == "2":
                    print(f"{num1} - {num2} = {subtract(num1, num2)}")
                elif choice1 == "3":
                    print(f"{num1} * {num2} = {multiply(num1, num2)}")
                elif choice1 == "4":
                    print(f"{num1} / {num2} = {divide(num1, num2)}")

            except ValueError:
                print("Invalid input. Please enter a number.")

        else:
            print("Invalid choice. Please try again.")

if __name__ == "__main__":
    main()


    OUTPUT -
  
Simple Command-Line Calculator
Operations:
1. Addition
2. Subtraction
3. Multiplication        
4. Division
5. Quit
Enter your choice (1-5): 1
Enter the first number: 10
Enter the second number: 20
10 + 20 = 30     
Operations:      
1. Addition      
2. Subtraction   
3. Multiplication
4. Division      
5. Quit
Enter your choice (1-5): 2
Enter the first number: 50
Enter the second number: 20
50 - 20 = 30
Operations:
1. Addition
2. Subtraction
3. Multiplication
4. Division
5. Quit
Enter your choice (1-5): 3
Enter the first number: 500
Enter the second number: 100
500 * 100 = 50000
Operations:
1. Addition
2. Subtraction
3. Multiplication
4. Division
5. Quit
Enter your choice (1-5): 4
Enter the first number: 1000
Enter the second number: 200
1000 / 200 = 5.0
Operations:
1. Addition
2. Subtraction
3. Multiplication
4. Division
5. Quit
Enter your choice (1-5): 5
Goodbye!
    
