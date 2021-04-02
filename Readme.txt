Virtual Environments, and External Packages

Tutorial viewed at: https://channel9.msdn.com/Series/Intro-to-Python-Development/Python-for-Beginners-35-of-44-Demo-Virtual-environments-packages

This sample project involved working with packages, and installing local environments so that there are no version issues when packages are installed globally.
The goal will be to create a program that calls a package that will make an error message red and a sample message green.
1. Create a local environment
```Terminal
python -m venv venv #The first venv asks for a local environment, the second creates the folder w/name 'venv'
```
2.Create a text file that has the package dependancies.  Call the file requirements.txt, and put colorama in the text file (This is a package that allows changing color of text)
3. Install the colorma package in the local environment using the requirements text file.
```Terminal
pip install -r requirements.txt # -r is telling pip install there is a requirements file.
```
4. Create a file called helpers.py and type the following code in:
```
from colorama import init, Fore #required syntax is available by googling colorama package

def display(message, is_warning=False): #This sets a default of warning to False
        if is_warning:
            print(Fore.RED + message)
        else:
            print(Fore.GREEN + message)
```
5. Create a main program file called demos.py and type in the following code:
```
import helpers #importing the package this way requires you to use do notation to call the function
helpers.display('Sample message', True)

from helpers import display #importing the package this way you can just call display; alternatively you could call it with import helpers *
display('Sample message')
```