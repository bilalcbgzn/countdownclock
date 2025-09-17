import datetime
from tkinter import *

root = Tk()
root.title("Countdown Clock")



def countdown():
    delta = datetime.datetime(2025,1,1,0,0) - datetime.datetime.now()
    days = delta.days
    hours , rem = divmod(delta.seconds, 3600)
    minutes, seconds = divmod(rem, 60)
    text = fillzero(str(hours)) + ":" + fillzero(str(minutes)) + ":" + fillzero(str(seconds))
    label.config(text=text)
    label.after(1000, countdown)

def fillzero(x):
    return x.zfill(2)


label = Label(root, font=('arial', 100, 'bold'), background="black", foreground="white", text="Countdown Clock")
label.pack(anchor='center')


countdown()

root.mainloop()
