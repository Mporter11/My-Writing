
| Description | Command |
| --- | --- |
| Import the functions, classes and variables of the random function | `import random` |
| Define character sets for letters, <br>numbers and symbols | `letters = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z', 'A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 'I', 'J', 'K', 'L', 'M', 'N', 'O', 'P', 'Q', 'R', 'S', 'T', 'U', 'V', 'W', 'X', 'Y', 'Z']`<br>`numbers = ['0', '1', '2', '3', '4', '5', '6', '7', '8', '9']`<br>`symbols = ['!', '#', '$', '%', '&', '(', ')', '*', '+']`</br> |
| Display user welcome message | `print("Welcome to the Random Password Generator!")` |
| User input for the amount of letters, numbers and symbols | `nr_letters = int(input("How many letters would you like in your password?\n"))`<br>`nr_symbols = int(input(f"How many symbols would you like?\n"))`<br>`nr_numbers = int(input(f"How many numbers would you like?\n"))`</br> | 
| Initialize empty string to store password | `password = ""` |
| Set a loop to randomly generate password according to user input | `for char in range(1, nr_letters + 1):
    password += random.choice(letters)`<br>Test test test`</br>  |
| Display password to user | `print(f"Your password is: {password}")` | |
