def add(num1, num2):
    """Calculates the sum of two numbers."""
    return num1 + num2

def subtract(num1, num2):
    """Calculates the difference between two numbers."""
    return num1 - num2

def multiply(num1, num2):
    """Calculates the product of two numbers."""
    return num1 * num2

def divide(num1, num2):
    """Calculates the quotient of two numbers. Includes zero-division check."""
    if num2 == 0:
        return "Error: Division by zero is not allowed."
    return num1 / num2

def main():
    print("=== Modular Calculator Mini-Program ===\n")
    
    try:
        first_number = float(input("Enter the first number: "))
        second_number = float(input("Enter the second number: "))
    except ValueError:
        print("Invalid input. Please enter numerical values.")
        return

    print("\nAvailable Operations:")
    print("1. Add (+)")
    print("2. Subtract (-)")
    print("3. Multiply (*)")
    print("4. Divide (/)")
    choice = input("Choose an operation (1/2/3/4): ").strip()

    result = None
    operation_symbol = ""

    if choice == '1':
        result = add(first_number, second_number)
        operation_symbol = "+"
    elif choice == '2':
        result = subtract(first_number, second_number)
        operation_symbol = "-"
    elif choice == '3':
        result = multiply(first_number, second_number)
        operation_symbol = "*"
    elif choice == '4':
        result = divide(first_number, second_number)
        operation_symbol = "/"
    else:
        print("Invalid operation choice.")
        return

    print("\n--- Result ---")
    if isinstance(result, str):
        print(result) 
    else:
        print(f"{first_number} {operation_symbol} {second_number} = {result}")

if __name__ == "__main__":
    main()
