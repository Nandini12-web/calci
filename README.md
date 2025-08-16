# calculator
def calculate():

    print("Welcome to the Simple Calculator!")

    try:
        num1 = float(input("Enter the first number: "))
        num2 = float(input("Enter the second number: "))
    except ValueError:
        print("Invalid input. Please enter valid numbers.")
        return

    print("\nSelect an operation:")
    print("1. Addition (+)")
    print("2. Subtraction (-)")
    print("3. Multiplication (*)")
    print("4. Division (/)")

    operation_choice = input("Enter your choice (1/2/3/4): ")

    if operation_choice == '1':
        result = num1 + num2
        print(f"Result: {num1} + {num2} = {result}")
    elif operation_choice == '2':
        result = num1 - num2
        print(f"Result: {num1} - {num2} = {result}")
    elif operation_choice == '3':
        result = num1 * num2
        print(f"Result: {num1} * {num2} = {result}")
    elif operation_choice == '4':
        if num2 == 0:
            print("Error: Division by zero is not allowed.")
        else:
            result = num1 / num2
            print(f"Result: {num1} / {num2} = {result}")
    else:
        print("Invalid operation choice. Please select 1, 2, 3, or 4.")

if __name__ == "__main__":
    calculate()

#password generator
import random
import string

def generate_strong_password():
    """Generates a strong, random password based on user-specified length."""

    while True:
        try:
            length = int(input("Enter the desired password length (minimum 6): "))
            if length < 6:
                print("Password length must be at least 6 characters.")
            else:
                break
        except ValueError:
            print("Invalid input. Please enter a number.")


    lowercase = string.ascii_lowercase
    uppercase = string.ascii_uppercase
    digits = string.digits
    special_characters = string.punctuation


    password_characters = []
    password_characters.append(random.choice(lowercase))
    password_characters.append(random.choice(uppercase))
    password_characters.append(random.choice(digits))
    password_characters.append(random.choice(special_characters))


    all_characters = lowercase + uppercase + digits + special_characters


    for _ in range(length - len(password_characters)):
        password_characters.append(random.choice(all_characters))


    random.shuffle(password_characters)


    generated_password = "".join(password_characters)

    print(f"Generated Password: {generated_password}")

if __name__ == "__main__":
    generate_strong_password()

