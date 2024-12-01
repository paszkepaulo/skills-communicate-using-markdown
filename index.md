# to je duży tekst h1

``` python
def get_number(prompt):
    while True:
        try:
            return int(input(prompt))
        except ValueError:
            print("Please provide valid numbers only (1-4)!")



def menu(l_choice, l_taskList):
    while True:
        if l_choice == 1:
            i = 0
            l_taskList.append(input("Enter the task: "))
            l_taskList.append("   Pending")
            print(f"Task added: '{l_taskList[-2]} with status:{l_taskList[-1]}'\n\n")
            return l_taskList
        

        elif l_choice == 2:
            viewTask(l_choice, l_taskList)
            
            
        elif l_choice == 3:
            while True:
                if l_taskList:
                    l_choice = get_number("Which task would you like to mark as complete (select number and press enter)\n\n") 
                    i = 2*(l_choice - 1)
                    taskList[i + 1] = "   Complete"
                    print(f"Task '{l_taskList[i]}' has been marked as complete!\n")
                    break
                else:
                    print("No tasks to view yet. Select '1' in the main menu to add tasks.\n")
                    l_choice = 0
                    break
                   
        elif l_choice == 4:
            print("Goodbye!")
            return l_choice
        else:
            print("Please select numbers 1-4 to move around menu\n")
            break
    return l_taskList



def viewTask(l_choice, l_taskList):
        while True:
            if not l_taskList:
                print("No tasks to view yet. Select '1' in the main menu to add tasks.\n")
                break
            else:
                print("\nCurrent Tasks:\n")
                for i in range(0, len(l_taskList) - 1, 2):
                    index = (i + 1)//2
                    print(f"{index + 1}. {l_taskList[i]} {l_taskList[i + 1]}\n")
                    break
taskList = []

while True:

    print("Welcome to To-Do List Manager!")           

    choice = get_number("What would you like to do?\n1. Add Task\n2. View Task\n3. Mark a Task as Complete\n4. Exit\n\nEnter your choice: ")

    taskList = menu(choice, taskList)
    if choice == 4:
        break



```


![Image of Yaktocat](https://octodex.github.com/images/yaktocat.png)
