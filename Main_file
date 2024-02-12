def read_data():
    #Creating main_list to hold my matrix
    main_list = []
    #opening file and reading contents
    read_file = open('nutrition_data.csv', 'r')
    file_contents = read_file.readlines()
    #starting a while loop to append to the main_list by index. Removing the \n and spliting
    #results by the ","
    index = 0
    while index < len(file_contents):
        file_content = file_contents[index].strip("\n")
        file_content_parts = file_content.split(",")
        main_list.append(file_content_parts)
        index += 1
    #closing and returning the file
    read_file.close()
    return main_list

def create_separate_list(main_list, user_choice):
    #making a list for each main option
    dairy = []
    meat = []
    vegetable = []
    fruit = []
    grains = []
    #appending the list by the 0 index of the main_list with items in the same category
    for lines in main_list:
        if lines[0] == "Dairy":
            dairy.append(lines)
        elif lines[0] == "Meat":
            meat.append(lines)
        elif lines[0] == "Vegetables":
            vegetable.append(lines)
        elif lines[0] == "Fruit":
            fruit.append(lines)
        else:
            grains.append(lines)

    #returning correct list by user input
    if user_choice == 1:
        return dairy
    elif user_choice == 2:
        return meat
    elif user_choice == 3:
        return vegetable
    elif user_choice == 4:
        return fruit
    else:
        return grains

def display_menu():
    #display of menu
    print("Nutrition by Food Group")
    print("1. Dairy")
    print("2. Meat")
    print("3. Vegetables")
    print("4. Fruit")
    print("5. Grains")
    print()

def main():

    #starting a loop
    while True:
        #calling display
        display_menu()
        # calling read_data function to get main_list
        main_list = read_data()
        #getting user input
        user_choice = int(input("Enter your food group choice: (1-5): "))
        #data validation to check if the user placed a number 5 or less and returning an error if
        #number was above 5 then resending them to the display_menu function
        if user_choice > 5:
            print("Your choice must be between 1 and 5. Please try again")
            print()
            continue
        else:
            #if user input is correct sending information to the create_separate_list to return correct list then sorting list
            food_list = create_separate_list(main_list, user_choice)
            food_list.sort()
           #output display
            print("Name                                Amount          Calories")
            print("---------------------------------------------------------------")
            #looping through the list and printing the results.
            for food in food_list:
                food.pop(0)
                name = food.pop(0)
                amount = food.pop(0)
                calories = food.pop(0)
                print(f'{name:<35}  {amount:<15}  {calories:<15}')

            print()
        #asking user if they want to go again
        go_again = input("Would you like to preform another conversion? (y/n): ")
        print()
        if go_again == "n":
            print("Thanks, bye")
            break

main()
