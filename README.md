# Python-Keylogger

# What is a Keylogger
A keylogger is a program that monitors and records your keyboard inputs to ensure that every keystroke is captured. It can be used with malicious softwate  by stealing passwords, credit card numbers, or sensitive data.

# How it works 
The Python script used in this  is a basic keylogger that records every key pressed on the keyboard and saves it to a file called keyfile.txt. It uses the keyboard module to detect key presses in real-time.
When a key is pressed, the script logs the key’s name (like a, enter, shift, etc.).
The keylogger keeps running until manually stopped.
The purpose of this script is for educational and ethical hacking practice only.

# Key Terms to Know
-Keylogger: A program or device that records the keystrokes made by a user. Often used for monitoring or debugging, but can be misused if deployed maliciously.

-Keyboard Module: A Python library that allows programs to interact with the keyboard (e.g., detect key presses).

-Event: In programming, an action or occurrence (like a key press) that the program can detect and respond to.

-Threading: A method of running tasks in the background, so the program can listen for keystrokes while doing other things if needed.

-Listener: A function or process that waits for a specific event (in this case, a key press) and triggers an action when it happens.


# How the code works
This script is a basic keylogger written in Python. It uses the keyboard module to detect key presses and logs them to a file named keyfile.txt
import keyboard
import threading
The keyboard module allows the script to monitor and react to keyboard events, such as when a user presses a key. The threading module is included to support running tasks in the background. Although it’s not currently used in this script, it could be helpful if we wanted to run the keylogger alongside other tasks without blocking the main program.Next, we define a function called keyPressed(). This function handles each key press event. When a key is pressed, the keyboard module triggers this function and passes in an event object that contains information about the key that was pressed. Inside the function, we open (or create) a file called keyfile.txt in append mode. We then write the name of the key that was pressed into this file, followed by a newline character. If any error occurs during this process—such as the file being inaccessible—a message is printed to the console with details of the error.This function first tells the program to call keyPressed() every time a key is pressed by using keyboard.on_press(). Then, it uses keyboard.wait() to keep the program running indefinitely, so it can continue listening for key events. Again, if any errors occur while setting up the keylogger, they are caught and printed to the console.

Finally, the script checks if it is being run directly (as opposed to being imported by another script.If the script is being run directly, it will call start_keylogger() to begin logging key presses. Note that in your original version, there was an attempt to use keyboard.Listener, but this does not exist in the keyboard module. That line seems to be copied from the pynput library, which uses a different API. To keep this script working correctly with the keyboard module, we use on_press() and wait() as shown.
