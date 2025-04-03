# week-4-File-handling-
Step 1: Get the Filename from the User
First, ask the user to input the filename:
Python
filename = input("Enter the filename: ")
Step 2: Handle Errors When Opening the File
Use a try-except block to handle errors when opening the file:
Python
try:
    with open(filename, 'r') as file:
        content = file.read()
except FileNotFoundError:
    print(f"Sorry, the file {filename} does not exist.")
    exit()
except PermissionError:
    print(f"Sorry, you do not have permission to read the file {filename}.")
    exit()
except Exception as e:
    print(f"An error occurred: {e}")
    exit()
Step 3: Modify the Content
Modify the content as needed. For example, let's convert the text to uppercase:
Python
modified_content = content.upper()
Step 4: Write the Modified Content to a New File
Write the modified content to a new file:
Python
with open('modified_' + filename, 'w') as new_file:
    new_file.write(modified_content)
Step 5: Print a Success Message
Print a success message:
Python
print(f"Modified content written to modified_{filename}")
Here's the complete code:
Python
filename = input("Enter the filename: ")

try:
    with open(filename, 'r') as file:
        content = file.read()
except FileNotFoundError:
    print(f"Sorry, the file {filename} does not exist.")
    exit()
except PermissionError:
    print(f"Sorry, you do not have permission to read the file {filename}.")
    exit()
except Exception as e:
    print(f"An error occurred: {e}")
    exit()

modified_content = content.upper()

with open('modified_' + filename, 'w') as new_file:
    new_file.write(modified_content)

print(f"Modified content written to modified_{filename}")
