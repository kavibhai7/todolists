# todolists

tasks = []

def show_menu():
   
    print("\nMenu:")
    print("1. View Tasks")
    print("2. Add Task")
    print("3. Remove Task")
    print("4. Exit")

def view_tasks():
    
    if not tasks:
        print("list khali h.")
    else:
        print("\nYour To-Do List:")
        for i, task in enumerate(tasks, 1):
            print(f"{i}. {task}")

def add_task():
  
    task = input("Enter a task: ")
    tasks.append(task)
    print(f"Task '{task}'added to the list.")

def remove_task():
   
    if not tasks:
        print("kux h hi nhi nikalne k lie")
        return
    
    try:
        task_number = int(input("Enter the task number to remove: "))
        if 0 < task_number <= len(tasks):
            removed_task = tasks.pop(task_number - 1)
            print(f"Task '{removed_task}'  list s bahar.")
        else:
            print("dimag kam ba ka")
    except ValueError:
        print("enter a  valid no.")

def main():
   
    while True:
        show_menu()
        choice = input("kya krna h choose kr : ")

        if choice == '1':
            view_tasks()
        elif choice == '2':
            add_task()
            view_tasks()    
        elif choice == '3':
              view_tasks()
              remove_task()
        elif choice == '4':
            print("here, is ur tasks")
            view_tasks()
            print("chlo niklo ab")
            break
        else:
            print("dhyan se , kya dal ra h.")

if __name__ == "__main__":
    main()
