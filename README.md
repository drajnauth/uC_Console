# Micro Controller PC Console
This is a python program that provided a smart console for Microcontrollers

It allows data to be captured in a csv file for analysis or allows data to be plotted directly from the Microcontroller.  

You Microcontroller will send to send commands that start with special characters that will allow numerical data to be captured.
Any data without the preceeding special character will be ignored

The program is written in Python 3.9.4 and developed using Visual Studio Code. The program requires Python to be installed (https://www.python.org/downloads/).  You need to understand how to run a Python program.


Usage: 
======
python uC_Console_TKv0.1b.py

Microcontroller Setup:
======================
Numbers that start with # will be captured by the python program provided you indicated that its to be captured.  Currently it can capture
data set as follows

Single data points (float or integer) that will be plotted in real time
\#1<br />
\#2.2222<br />
\#0.1234<br />

X and Y data point that will be ploted once the "|" character is sent
\#1,1<br />
\#2,4.110<br />
\#3,9<br />
\#4,16.001<br />
\|<br />

Line X, Y series.  For each Z values a X,Y line will be generated (e.g. Transistor Curve Trace).  A new Z series will be captures what a "=" character is recived and the the capture will end and plot generated when the "|" character is received.
\#1,1,1<br />
\#2,2,1<br />
\#3,3,1<br />
\#4,4,10<br />
\=<br />
\#1,1,2<br />
\#2,4.110,2<br />
\#3,9,2<br />
\#4,16.001,2<br />
\=<br />
\#1,1,3<br />
\#2,8,3<br />
\#3,27,3<br />
\#4,256,3<br />
\=<br />
\|<br />

Python Program Running on PC:
=============================
The python program is faily easy to use.  
Steps are:
1. Select com port and baud rate, then click on the "Connect" check box.  To disconnect from the com port, clear the checkbox. 

When the program first starts it enumerates and display all com ports available.

2. Once connected, you next select the type of data capture from the drop down. You can capture single values "y" or two values "x,y" or three values "x,y,z".  There is also a choice to capture and plot data in real time "Live".  Choices available in dropdown are:
x,y
x,y,x
y
Live x,y
Live y

3. Check the "Plot" checkbox to generate a plot and/or check the "Save CSC" checkbox to save to a Excel CSV file.  Once the "Save CSV" option is selected a dialog is presented to select directory to save the file. You also need to enter the file name that will be created.  Once either of these are selected, the Microcontoller does the test.

4. At the Top of the Window, under "Command Entry" you can enter text that will be transmitted to the Microcontroller (e.g. command to generate data). Press the green "Enter" button to transmit the text to the Microcontroller. 

5. The is a large text window under the "uC Output" that displays all text received from the Microcontroller.  Any text that is red is an error.  Black text is data that is captured.  If a "." is displayed, a non printable character was received and could not be processed.

Written by Dave Rajnauth (VE3OOI) and licensed under Creative Commons. No commercial use permitted.
