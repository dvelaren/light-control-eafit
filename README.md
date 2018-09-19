# Light Control EAFIT
Light system with Proportional, Integral and Derivative (PID) controller that adapts brightness based on the environment conditions. This repository includes Datalogger application installer, which allows to establish a serial communication with Arduino. This application sends a desired setpoint to Arduino and it reads the Measured signal from Arduino into the application. It plots setpoint and measurement and allows to export the data that was acquired during the execution. Windows, Linux and Mac installers are available.

## Example: A light control system with feedback
![alt text](https://raw.githubusercontent.com/tidusdavid/light-control-eafit/master/Resources/Architecture.png)
![alt text](https://raw.githubusercontent.com/tidusdavid/light-control-eafit/master/Resources/Device.jpg)

This example allows to implement a PID Light Controller using Arduino, Matlab, Datalogger App, LDR Sensor and Power LED Hardware.

## Testing

First copy all the required libraries to My Documents / Arduino / libraries.

In order to test this project follow the next steps:
1. First install Datalogger application.
2. Upload Arduino codes/arduinoMatlab/arduinoMatlab.ino to Arduino MEGA and edit code header to match the current pins of the device (LDR is connected to A0, Power LED is connected to PWM 2).
3. Open Datalogger application.
4. Select COM port where Arduino MEGA is connected.
5. Click on Start button.
6. Put a 512 Setpoint value.
7. Verify that Power LED turns on to 50% aprox of brightness and that Datalogger app shows the LDR measurement in the plot.
8. Click on Stop.
9. Click on Export and check that Dataset is accurate according to what you monitored in Datalogger app.
10. Using Matlab, the previous dataset and System Identification Toolbox (ident), acquire a first order plus dead time model for the system (FOPDT)
11. Tune a PID controller using PID Tune toolbox.
12. Upload Arduino codes/arduinoMatlabCtrl/arduinoMatlabCtrl.ino to Arduino MEGA and edit code header to match current pins of device (LDR is connected to A0, Power LED is connected to PWM 2) and also edit the control constants kp, ki and kd.
13. Test that the controller adapts depending on context situations.
