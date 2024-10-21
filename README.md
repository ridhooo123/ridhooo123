import tkinter as tk
import tkinter.messagebox
from tkinter.constants import SUNKEN

window=tk.Tk()
window.title('RIDHO')
window.geometry("515x515")

frame=tk.Frame(master=window,relief=SUNKEN,borderwidth=10,bg="gray",padx=10,pady=10)
frame.pack(fill=tk.BOTH,expand=True)

entry=tk.Entry(master=frame,borderwidth=10,width=25,bg="white",font=("arial",20,"bold"))
entry.grid(row=0,column=0,columnspan=4,pady=10,sticky="nsew")

def myclick(number):
    entry.insert(tk.END,number)

def clear():
    entry.delete(0,tk.END)

def equal():
    try:
        y=(str(entry.get()))
        entry.delete(0,tk.END)
        entry.insert(0,y)
    except:
        tkinter.messagebox.showinfo("Erorr","Syntax Error")

for i in range(8):
    frame.grid_rowconfigure(i,weight=1)
for j in range(4):
    frame.grid_columnconfigure(j,weight=1)

def toggle_fullscreen(event=None):
    fullscreen=window.attributes('-fullscreen')
    window.attributes('-fullscreen',not fullscreen)

def end_fullscreen(event=None):
    window.attributes('-fullscreen',False)

window.bind('<F11>',toggle_fullscreen)
window.bind('<Escape>',end_fullscreen)

def persen():
    current_value = entry.get()
    try:
        result = float(current_value) / 100
        entry.delete(0, tk.END)
        entry.insert(tk.END, str(result))
    except ValueError:
        entry.delete(0, tk.END)
        entry.insert(tk.END,"Error")

tujuh=tk.Button(master=frame,text='7',borderwidth=10,width=5,padx=5,pady=5,font=("arial",20,"bold"),bg="lightgray",command=lambda:myclick(7))
tujuh.grid(row=2,column=0,sticky="nsew")
delapan=tk.Button(master=frame,text='8',borderwidth=10,width=5,padx=5,pady=5,font=("arial",20,"bold"),bg="lightgray",command=lambda:myclick(8))
delapan.grid(row=2,column=1,sticky="nsew")
sembilan=tk.Button(master=frame,text='9',borderwidth=10,width=5,padx=5,pady=5,font=("arial",20,"bold"),bg="lightgray",command=lambda:myclick(9))
sembilan.grid(row=2,column=2,sticky="nsew")
empat=tk.Button(master=frame,text='4',borderwidth=10,width=5,padx=5,pady=5,font=("arial",20,"bold"),bg="lightgray",command=lambda:myclick(4))
empat.grid(row=3,column=0,sticky="nsew")
lima=tk.Button(master=frame,text='5',borderwidth=10,width=5,padx=5,pady=5,font=("arial",20,"bold"),bg="lightgray",command=lambda:myclick(5))
lima.grid(row=3,column=1,sticky="nsew")
enam=tk.Button(master=frame,text='6',borderwidth=10,width=5,padx=5,pady=5,font=("arial",20,"bold"),bg="lightgray",command=lambda:myclick(6))
enam.grid(row=3,column=2,sticky="nsew")
satu=tk.Button(master=frame,text='1',borderwidth=10,width=5,padx=5,pady=5,font=("arial",20,"bold"),bg="lightgray",command=lambda:myclick(1))
satu.grid(row=4,column=0,sticky="nsew")
dua=tk.Button(master=frame,text='2',borderwidth=10,width=5,padx=5,pady=5,font=("arial",20,"bold"),bg="lightgray",command=lambda:myclick(2))
dua.grid(row=4,column=1,sticky="nsew")
tiga=tk.Button(master=frame,text='3',borderwidth=10,width=5,padx=5,pady=5,font=("arial",20,"bold"),bg="lightgray",command=lambda:myclick(3))
tiga.grid(row=4,column=2,sticky="nsew")
nol=tk.Button(master=frame,text='0',borderwidth=10,width=5,padx=5,pady=5,font=("arial",20,"bold"),bg="lightgray",command=lambda:myclick(0))
nol.grid(row=5,column=0,columnspan=2,sticky="nsew")
clear=tk.Button(master=frame,text='C',borderwidth=10,width=5,padx=5,pady=5,font=("arial",20,"bold"),bg="lightgray",command=clear)
clear.grid(row=1,column=0,columnspan=2,sticky="nsew")
tambah=tk.Button(master=frame,text='+',borderwidth=10,width=5,padx=5,pady=5,font=("arial",20,"bold"),bg="lightgray",command=lambda:myclick('+'))
tambah.grid(row=1,column=3,sticky="nsew")
kurang=tk.Button(master=frame,text='-',borderwidth=10,width=5,padx=5,pady=5,font=("arial",20,"bold"),bg="lightgray",command=lambda:myclick('-'))
kurang.grid(row=2,column=3,sticky="nsew")
kali=tk.Button(master=frame,text='x',borderwidth=10,width=5,padx=5,pady=5,font=("arial",20,"bold"),bg="lightgray",command=lambda:myclick('*'))
kali.grid(row=3,column=3,sticky="nsew")
bagi=tk.Button(master=frame,text='/',borderwidth=10,width=5,padx=5,pady=5,font=("arial",20,"bold"),bg="lightgray",command=lambda:myclick('/'))
bagi.grid(row=4,column=3,sticky="nsew")
equal=tk.Button(master=frame,text='=',borderwidth=10,width=5,padx=5,pady=5,font=("arial",20,"bold"),bg="lightgray",command=equal)
equal.grid(row=5,column=2,columnspan=2,sticky="nsew")
persen=tk.Button(master=frame,text='%',borderwidth=10,width=5,padx=5,pady=5,font=("arial",20,"bold"),bg="lightgray",command=persen)
persen.grid(row=1,column=2,sticky="nsew")

window. mainloop()
