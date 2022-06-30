# Keypad-using-stm32
## A software that display a number on a seven-segment display after pressing a button on a keypad.
## - Contains the following:
### Keypad.h that contains the declarations for the keypad manager APIs.
### Keypad.c that contains the implementations for the keypad driver APIs.
### Main.c that contains the implementation of the required application.
### The implemented GPIO driver shall be used by the Keypad driver APIs.
### Keypdad_init
* Function does not take any arguments. It will be used to initialize the internal
keypad driver variable(s).

### Keypad_manage
* Function does not take any arguments.
* Function is called periodically from the infinite loop in main function.
* Function scans all keys to check which one is pressed.
* Once a valid key press detected, function does the following:
* Store the pressed key value.
* Call a function “KeypadCallouts_KeyPressNotificaton” and does not pass
any arguments to it.
* After the key press, the value of the stored key is not be changed until the
key is released and Keypad_GetKey function is called.
* Function uses lookup table implementation to define the value of the
pressed key.
### Keypad_GetKey
* Function is called by application to get the last stored key.
