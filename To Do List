import json

def load_todo_list():
    try:
        with open('todo_list.json', 'r') as file:
            return json.load(file)
    except FileNotFoundError:
        return []

def save_todo_list(todo_list):
    with open('todo_list.json', 'w') as file:
        json.dump(todo_list, file)

def display_todo_list(todo_list):
    if not todo_list:
        print("Your to-do list is empty.")
    else:
        print("Your to-do list:")
        for index, task in enumerate(todo_list, start=1):
            print(f"{index}. {task}")

def add_task(todo_list, task):
    todo_list.append(task)
    print(f"Task '{task}' added to your to-do list.")

def update_task(todo_list, index, new_task):
    if 1 <= index <= len(todo_list):
        todo_list[index - 1] = new_task
        print(f"Task {index} updated to '{new_task}'.")
    else:
        print("Invalid task index.")

def main():
    todo_list = load_todo_list()

    while True:
        print("\n1. Display to-do list")
        print("2. Add task")
        print("3. Update task")
        print("4. Save and exit")

        choice = input("Enter your choice (1-4): ")

        if choice == '1':
            display_todo_list(todo_list)
        elif choice == '2':
            task = input("Enter the task: ")
            add_task(todo_list, task)
        elif choice == '3':
            index = int(input("Enter the task index to update: "))
            new_task = input("Enter the new task: ")
            update_task(todo_list, index, new_task)
        elif choice == '4':
            save_todo_list(todo_list)
            print("To-do list saved. Exiting.")
            break
        else:
            print("Invalid choice. Please enter a number between 1 and 4.")

if __name__ == "__main__":
    main()
