# Calculator1
My first complete calculator that I coded myself

#Imported Tkinter for GUI and imported math for pi, squaring, and square root
from tkinter import *
import math
#Initializing the first value and command to use for global variables
value1 = 0
command = ""
#Pressing the number will add the value on to the end of the label display
def num0():
    value = int(lbl_value["text"])
    lbl_value["text"] = f"{value}0"
def num7():
    value = int(lbl_value["text"])
    lbl_value["text"] = f"{value}7"
def num8():
    value= int(lbl_value["text"])
    lbl_value["text"] = f"{value}8"
def num9():
    value= int(lbl_value["text"])
    lbl_value["text"] = f"{value}9"
def num4():
    value= (lbl_value["text"])
    lbl_value["text"] = f"{value}4"
def num5():
    value= int(lbl_value["text"])
    lbl_value["text"] = f"{value}5"
def num6():
    value= int(lbl_value["text"])
    lbl_value["text"] = f"{value}6"
def num1():
    value= int(lbl_value["text"])
    lbl_value["text"] = f"{value}1"
def num2():
    value= int(lbl_value["text"])
    lbl_value["text"] = f"{value}2"
def num3():
    value= int(lbl_value["text"])
    lbl_value["text"] = f"{value}3"
def deci():
    value=int(lbl_value["text"])
    lbl_value["text"] = f"{value}."
def multiply():
    global value1
    value1=float(lbl_value["text"])
    lbl_value["text"] = "0"
    global command
    command = "x"   
def add():
    global value1
    value1=float(lbl_value["text"])
    lbl_value["text"] = "0"
    global command
    command = "+"
def subtract():
    global value1
    value1=float(lbl_value["text"])
    lbl_value["text"] = "0"
    global command
    command = "-"
def division():
    global value1
    value1=float(lbl_value["text"])
    lbl_value["text"] = "0"
    global command
    command = "÷"
def sqrt():
    global value1
    value1=float(lbl_value["text"])
    global command
    command = "√"
def sqr():
    global value1
    value1=float(lbl_value["text"])
    global command
    command = "x²"
def equal():
    global value1
    global command
    if command == "+":
        value=float(lbl_value["text"])
        lbl_value["text"] = value1+value
        command = ""
    if command == "x":
        value=float(lbl_value["text"])
        lbl_value["text"] = value*value1
        command = ""
    if command == "÷":
        value=float(lbl_value["text"])
        lbl_value["text"] = value1/value
        command = ""
    if command == "-":
        value=float(lbl_value["text"])
        lbl_value["text"] = value1-value
        command = ""
    if command == "√":
        value=float(lbl_value["text"])
        lbl_value["text"] = math.pow(value,.5)
        command = ""
    if command == "x²":
        value=float(lbl_value["text"])
        lbl_value["text"]= value**2
        command = ""
def clear():
    lbl_value["text"] = "0"
    global value1
    value1 = "0"    
def pi():
    global value1
    lbl_value["text"] = math.pi
window = Tk()
#Below are the buttons, named by their text
btn_7 = Button(master=window, text="7", command=num7)
btn_7.grid(row=1, padx = 5, pady = 5, column=0)

btn_8=Button(master=window, text="8", command=num8)
btn_8.grid(row=1, padx = 5, pady = 5, column=1)

btn_9 = Button(master=window, text="9", command=num9)
btn_9.grid(row=1, padx = 5, pady = 5, column=2)

btn_4=Button(master=window, text="4", command=num4)
btn_4.grid(row=2,padx = 5, pady = 5, column=0)

btn_5=Button(master=window, text="5", command=num5)
btn_5.grid(row=2,padx = 5, pady = 5, column=1)

btn_6=Button(master=window, text="6", command=num6)
btn_6.grid(row=2,padx = 5, pady = 5, column=2)

btn_1=Button(master=window, text="1", command=num1)
btn_1.grid(row=3,padx = 5, pady = 5, column=0)

btn_2=Button(master=window, text="2", command=num2)
btn_2.grid(row=3,padx = 5, pady = 5, column=1)

btn_3=Button(master=window, text="3", command=num3)
btn_3.grid(row=3,padx = 5, pady = 5, column=2)

btn_0=Button(master=window, text="0", command=num0)
btn_0.grid(row=4, padx=5, pady=5, column=0)

btnx=Button(master=window, text="x", command=multiply)
btnx.grid(row= 1,padx = 5, pady = 5, column=4)

btnadd = Button(master=window, text="+", command=add)
btnadd.grid(row= 2,padx = 5, pady = 5, column=3)

btneql = Button(master=window, text="=", command=equal)
btneql.grid(row= 3,padx = 5, pady = 5, column=3)

btnsub = Button(master=window, text="-", command=subtract)
btnsub.grid(row= 1,padx = 5, pady = 5, column=3)

btndiv = Button(master=window, text="÷", command=division)
btndiv.grid(row=2,padx = 5, pady = 5, column=4)

btnClr = Button(master=window, text="C", command=clear)
btnClr.grid(row=3,padx = 5, pady = 5, column=4)

btnsqrt = Button(master=window, text="√", command= sqrt)
btnsqrt.grid(row=4, padx=5, pady=5, column = 3)

btnsqr = Button(master=window, text="x²", command= sqr)
btnsqr.grid(row=4, padx=5, pady=5, column = 2)

btnpi = Button(master=window, text="π", command=pi)
btnpi.grid(row=4, padx=5, pady=5, column = 4)

btndeci=Button(master=window, text=".", command=deci)
btndeci.grid(row=4, padx=5, pady=5, column =1)

lbl_value = Label(master=window, text="0")
lbl_value.grid(row=0, padx = 5, pady = 5, column=0, columnspan = 5, sticky="e")

window.mainloop()
