def calculate_bmi(weight_kg, height_m):
    """Calculate Body Mass Index."""
    if height_m <= 0:
        raise ValueError("Height must be greater than 0.")
    bmi = weight_kg / (height_m ** 2)
    return round(bmi, 2)

def classify_bmi(bmi):
    """Return BMI classification based on value."""
    if bmi < 18.5:
        return "Underweight"
    elif 18.5 <= bmi < 24.9:
        return "Normal weight"
    elif 25 <= bmi < 29.9:
        return "Overweight"
    else:
        return "Obesity"

def main():
    print("BMI Calculator")
    try:
        weight = float(input("Enter your weight in kilograms: "))
        height = float(input("Enter your height in meters: "))
        bmi = calculate_bmi(weight, height)
        category = classify_bmi(bmi)
        print(f"\nYour BMI is: {bmi}")
        print(f"Category: {category}")
    except ValueError as e:
        print(f"Error: {e}")

if __name__ == "__main__":
    main()
