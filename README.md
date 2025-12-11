# passwordchecker
simple Python code for checking the how the password is strong.

import re

def check_password(password):
    # Minimum length check
    if len(password) < 8:
        return "Weak (Password must be at least 8 characters long)"

    # Regex checks
    if not re.search(r"[A-Z]", password):
        return "Weak (Password must contain at least one uppercase letter)"
    if not re.search(r"[0-9]", password):
        return "Weak (Password must contain at least one number)"
    if not re.search(r"[!@#$%^&*(),.?\":{}|<>]", password):
        return "Weak (Password must contain at least one special character)"

    return "Strong Password!"

# Main Program
user_pass = input("Enter your password: ")

print(check_password(user_pass))
