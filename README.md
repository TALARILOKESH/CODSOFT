# CODSOFT
#PASSWORD GENERATOR
import random
import string 
def generate_password(length,complexity):
    if complexity =='low':
        characters=string.ascii_lowercase
    elif complexity =='medium':
        characters=string.ascii_letters
    elif complexity =='high':
        characters=string.ascii_letters+string.digits
    elif complexity =='very high':
        characters=string.aacii_letters+string.digits+string.punctuation
    else:
        raise ValueError("Invalid complexity level")
    password = ''.join(random.choice(characters) for _ in range(length))
    return password
def main():
    while True:
        try:
            length=int(input("Enter the desired length of the password:"))
            if length<1:
                print("PLease enter a positive integer.")
            else:
                break
        except ValueError:
                print("Please enteer a valid integer.")
    complexity =input("Enter the desired complexity (low,medium,high,very high):").lower()
    try:
        password=generate_password(length,complexity)
        print(f"Generated Password:{password}")
    except ValueError as e:
        print(e)
if __name__=="__main__":
    main()
