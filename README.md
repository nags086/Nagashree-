# Nagashree-
TO - DO LIST APPLICATION
class ToDoList:
    def __init__(self):
        self.tasks = []

    def add_task(self, task):
        self.tasks.append(task)
        print(f"Task '{task}' added successfully!")

    def delete_task(self, task):
        if task in self.tasks:
            self.tasks.remove(task)
            print(f"Task '{task}' deleted successfully!")
        else:
            print(f"Task '{task}' not found in the list.")

    def mark_completed(self, task):
        if task in self.tasks:
            print(f"Task '{task}' marked as completed!")
            self.delete_task(task)
        else:
            print(f"Task '{task}' not found in the list.")

    def display_tasks(self):
        if self.tasks:
            print("Tasks:")
            for index, task in enumerate(self.tasks, start=1):
                print(f"{index}. {task}")
        else:
            print("No tasks to display.")

def main():
    todo_list = ToDoList()
    while True:
        print("\nChoose an option:")
        print("1. Add task")
        print("2. Delete task")
        print("3. Mark task as completed")
        print("4. Display tasks")
        print("5. Exit")

        choice = input("Enter your choice: ")

        if choice == "1":
            task = input("Enter task to add: ")
            todo_list.add_task(task)
        elif choice == "2":
            task = input("Enter task to delete: ")
            todo_list.delete_task(task)
        elif choice == "3":
            task = input("Enter task to mark as completed: ")
            todo_list.mark_completed(task)
        elif choice == "4":
            todo_list.display_tasks()
        elif choice == "5":
            print("Exiting program.")
            break
        else:
            print("Invalid choice. Please enter a number from 1 to 5.")

if __name__ == "__main__":
    main()
