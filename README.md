# Stepper-Motor-Control-using-ArduinoUNO

## Project Overview
This project implements a stepper motor control system using an Arduino UNO microcontroller, an A4998 motor driver, and an LCD display for interactive feedback. The system allows precise control of the stepper motor, operating in two modes:

Degree Mode (DEG): Rotate the motor to a specific angle at a user-defined speed (RPM).
RPM Mode: Continuously rotate the motor at a set speed (RPM).

Key features include microstepping, digital and analog input adjustments, dynamic updates on an LCD display, and user-friendly navigation using push buttons.

## Components Used
Microcontroller: Arduino UNO
Motor Driver: A4998 Stepper Motor Driver
Stepper Motor: Standard Bipolar Stepper Motor
LCD Display: 20x4 LiquidCrystal I2C

## Input Devices:
Push Buttons: For input adjustments and navigation
Potentiometer: For analog input calibration
Power Supply: External power source for motor operation
## Miscellaneous:
Resistors, connecting wires, breadboard, etc.

## Features
### Control Modes:

Degree Mode: Enter desired rotation angle and speed in RPM.
RPM Mode: Specify the motor speed, and it runs continuously until stopped.
Interactive LCD Display:

Displays real-time updates for:
  Analog and Digital Input values
  Resolution settings
Motor operation mode and direction
Current RPM and degree rotation
### Microstepping: Enhanced motor precision with configurable microstepping factors.

### Calibration: Analog input calibration for precise speed control.

### User-Friendly Navigation:

Increment and decrement digital input values.
Switch between RPM and DEG modes.
Start/stop motor operations with simple button presses.

### Functional Workflow
1. Initialization
LCD initializes with a splash screen displaying the project title and team name.
Motor driver is prepared with predefined settings for microstepping and acceleration.
2. Operation Modes
a) Degree Mode (DEG)
Enter desired angle of rotation.
Enter desired speed (RPM).
Motor rotates to the specified angle at the defined speed.
Displays "DONE" upon completion and awaits further instructions.
b) RPM Mode
Enter desired RPM value.
Motor rotates continuously at the specified speed.
Displays "DONE" when stopped and awaits further instructions.
3. Input Calibration
Analog Input: Adjusted using a potentiometer; values mapped from 30 to 3000.
Digital Input: Increment or decrement via push buttons, with customizable resolution settings.
4. Real-Time Updates

### LCD continuously updates with:
Analog Input (AI)
Digital Input (DI)

### Resolution settings
Required RPM or degree values
Motor direction (Clockwise or Anti-clockwise)

### Hardware Connections
Arduino Pin	Component	Description
2	Power Button	Enables/disables motor power
3	Type of Rotation Button	Switch between DEG and RPM modes
4	Rotation Direction Button	Sets rotation direction (CW/ACW)
5	Increment Button	Increase digital input value
6	Decrement Button	Decrease digital input value
8	DIR Pin (A4998)	Controls motor direction
9	STEP Pin (A4998)	Sends step pulses to the driver
10	Enter Button	Proceeds to the next operational step
13	Resolution Button	Adjusts resolution settings
A0	Potentiometer	Reads analog input for speed control

### Software Features
Libraries Used
LiquidCrystal_I2C.h: For LCD interaction.
AccelStepper.h: For advanced stepper motor control.
Key Functions

### LCD Update Functions:
update_lcd_m(value1, value2): Updates mode and direction.
update_lcd_a(): Updates analog input value.
update_lcd_d(value): Updates digital input value.
update_lcd_r(value): Updates net required value.
update_lcd_deg(value): Updates degree value in DEG mode.
update_lcd_rpm(value): Updates RPM value.

### Motor Control:
Converts user inputs to step pulses and speed using:
deg * (200.0 / 360.0) * msf (DEG mode)
(rpm) * (200.0 / 60.0) * msf (RPM mode)
Uses stepper.setSpeed() and stepper.runSpeed() for smooth operation.

### Calibration:
Maps potentiometer input using map() function for better control.

## Usage Instructions
1. Setup the hardware as per the connections table.
2. Upload the code to Arduino UNO.
3. Use push buttons to:
      Switch between modes.
      Enter required RPM or degree values using analog and digital imputs.
      Start/stop the motor.
4. Observe real-time updates and results on the LCD screen
