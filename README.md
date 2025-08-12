# Password-Strength-Checker-Python-

This Python script checks the stregth of a given password based on multiple criteria such as length, use of uppercase/lowercase letters, number, and speical characters. 

# Technlogies Used 
-Python 3.x

-Tkinter (GUI Library)

-ttk (Themed Tkinter widgets)

-string (Python standard libray for punctuation detection)

# Features 
-Checks minimum length requirement.

-Detects uppercase & lowercase letters.

-Checks for numbers and special characters.

-Provides feedback on how to make your password stronger.

-Simple CLI interface.


 # GUI & Theme Changes
  -The apply_theme(scorce) function changes:
  -Background color
  -Displayed text and style
  -themes are linked to password strength
  

  # User Interaction
  -Enter password in the input field
  -Click Check Password
  -See streght score and suggestions
  -Visual theme updates based on score


  # How It Works
-The script assigns points based on:

-Length of the password

-Use of uppercase and lowercase letters

-Inclusion of numbers

-Inclusion of special characters


The final score determines whether your password is:

-Weak

-Moderate

-Strong


# Example

- Use of uppercase and lowercase letters.

- Inclusion of numbers.
   Output:
  - Strength: Moderate
  - Suggestions: "Increase passowrd length for better security."
  - GUI Theme; Pink
- Inclusion of special characters.

- The final score determines if your password is Weak, Moderate, or Strong.


 #  Installation & Requirements

 Requiments:

''' Python 3.x'''
'''tkinter'''

# Installation Steps:

1. Clone the repository:

'''git clone https://github.com/yourusername/Password-Strength-Checker-Python.git
cd Password-Strength-Checker-Python'''


2. Install required packages:

'''pip install -r requirements.txt'''

3. Run the application:

'''python password_checker.py'''





