Scientific Calculator GUI Functionality

Overview

The scientific calculator is implemented as a graphical user interface (GUI) in MATLAB. It allows users to perform a variety of mathematical operations, including basic arithmetic and advanced functions like trigonometric calculations, logarithms, and more. The interface is designed to be user-friendly, with buttons for each operation and a display area for showing results.

Components

Figure Window:

The main window of the calculator is created using uifigure, which sets the title and dimensions of the window. The background color is set to a light blue for a pleasant visual experience.

Display Area:

At the top of the window, there is a display field (uieditfield) that shows the current expression being entered and the result of calculations. This field is set to be non-editable by the user to prevent direct input, ensuring that all input comes from button presses.

Angle Mode Switch:

A switch is provided to toggle between degrees and radians for trigonometric functions. This allows users to choose their preferred angle measurement, which is crucial for accurate calculations.

Buttons:

The calculator features a grid of buttons for numbers (0-9), operations (addition, subtraction, multiplication, division), and functions (sin, cos, tan, log, etc.). Each button is created using uibutton, and they are arranged in a grid layout for easy access.
Each button is assigned a callback function (handleButtonPress) that is triggered when the button is pressed.

Functionality

Button Press Handling:

When a button is pressed, the handleButtonPress function is called with the current figure, display field, and the label of the pressed button.
The function retrieves the current expression stored in the application data and checks the angle mode (degrees or radians).

Calculating Results:

If the "=" button is pressed, the function attempts to evaluate the expression:
It modifies the expression based on the angle mode. If degrees are selected, it converts trigonometric functions (sin, cos, tan) to their degree equivalents using sind, cosd, and tand.
The expression is then evaluated using MATLAB's eval function.
If the evaluation is successful, the result is displayed in the display field, and the expression is updated to show the result.
If an error occurs during evaluation (e.g., invalid input), the display shows "Error," and the expression is cleared.

Clearing Input:

If the "C" button is pressed, the display field is cleared, and the stored expression is reset to an empty string.

Building Expressions:

For all other buttons (numbers and operations), the label of the pressed button is appended to the current expression. The updated expression is then displayed in the display field.

Conclusion:

The scientific calculator GUI provides a comprehensive tool for performing mathematical calculations in a user-friendly manner. It supports both basic and advanced functions, allowing users to switch between angle modes and handle complex expressions. The design ensures that users can easily input their calculations and receive immediate feedback on their results.
