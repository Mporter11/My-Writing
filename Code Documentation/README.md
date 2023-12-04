# 100 Days of Code: The Complete Python Bootcamp Project #

## Background
During May-December 2023 I completed the ["100 Days of Code: The Complete Python Bootcamp"](https://www.udemy.com/course/100-days-of-code/) course on [Udemy.com](https://www.udemy.com/). One of the beginner level lessons involved creating a random password generator. It was the first time I felt like a 'real' python developer, and not out of my programming league since I didn't have to stop and puzzle out Google searches to complete it. As someone who is self-taught in IT, it was a proud and special moment. I also find this project quite useful since I frequently add or update passwords for professional and personal environments. Therefore, I picked this brief exercise to practice documenting code in couple of different ways.

## Concept
- The random password generator takes into account a user's character length requirements to generate a random password using letters, numbers, and symbols.
- The below table describes the purpose of each command of the script.
- Click [here](https://github.com/Mporter11/My-Writing/blob/main/Rest%20API%20Documentation/Random%20Password%20Generator/) to view the code file with comments and docstrings.
<br><br>

| Description | Command |
| --- | --- |
| Import the functions, classes and variables of the random function | `import random` |
| Define character sets for letters, numbers, and symbols | `letters = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z', 'A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 'I', 'J', 'K', 'L', 'M', 'N', 'O', 'P', 'Q', 'R', 'S', 'T', 'U', 'V', 'W', 'X', 'Y', 'Z']`<br>`numbers = ['0', '1', '2', '3', '4', '5', '6', '7', '8', '9']`<br>`symbols = ['!', '#', '$', '%', '&', '(', ')', '*', '+']`</br> |
| Display user welcome message | `print("Welcome to the Random Password Generator!")` |
| User input for the amount of letters, numbers, and symbols | `nr_letters = int(input("How many letters would you like in your password?\n"))`<br>`nr_symbols = int(input(f"How many symbols would you like?\n"))`<br>`nr_numbers = int(input(f"How many numbers would you like?\n"))`</br> | 
| Initialize empty string to store password | `password = ""` |
| Set a loop to randomly generate password according to user input | `for char in range(1, nr_letters + 1):`<br>`   password += random.choice(letters)`<br><br>`for char in range(1, nr_symbols + 1):`<br>`    password += random.choice(symbols)`<br><br>`for char in range(1, nr_numbers + 1):`<br>`    password += random.choice(numbers)`  | |
| Display password to user | `print(f"Your password is: {password}")` | |
