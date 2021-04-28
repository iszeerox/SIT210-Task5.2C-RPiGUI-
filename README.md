# SIT210-Task5.2C-RPiGUI-
import tkinter.font
from time import sleep
import RPi.GPIO as GPIO
from gpiozero import LED
from tkinter import *
GPIO.setmode(GPIO.BCM)


red = LED(22)
blue = LED(17)
yellow = LED(27)
                                             


window = Tk()
window.title("LED BLINKER")
myFont = tkinter.font.Font(family = 'Arial', size = 20, weight = "bold")


def yellowLedToggle():
    if yellow.is_lit:
        yellow.off()
        yellowLedButton["text"] = "Turn the YELLOW LED on"
    else:
        yellow.on()
        yellowLedButton["text"] = "Turn the YELLOW LED off"
        
def redLedToggle():
    if red.is_lit:
        red.off()
        redLedButton["text"] = "Turn the RED lED on"
    else:
        red.on()
        redLedButton["text"] = "Turn the RED LED off"

def blueLedToggle():
    if blue.is_lit:
        blue.off()
        blueLedButton["text"] = "Turn the BLUE LED on"
    else:
        blue.on()
        blueLedButton["text"] = "Turn the BLUE LED off"


redLedButton = Button(window, text = 'Turn the RED LED On', font = myFont, command = redLedToggle, bg = 'red', height = 2, width = 30)
redLedButton.grid(row=1,column=0)

yellowLedButton = Button(window, text = 'Turn the YELLOW LED On', font = myFont, command = yellowLedToggle, bg = 'yellow', height = 2, width = 30)
yellowLedButton.grid(row=2,column=1)

blueLedButton = Button(window, text = 'Turn the BLUE LED On', font = myFont, command = blueLedToggle, bg = 'blue', height = 2, width = 30)
blueLedButton.grid(row=3,column=2)
