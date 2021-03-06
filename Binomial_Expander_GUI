#GUI_Bnomial 
import tkinter as tk
from matplotlib.backends.backend_tkagg import (
    FigureCanvasTkAgg, NavigationToolbar2Tk)
from matplotlib.backend_bases import key_press_handler
from matplotlib.figure import Figure
import numpy as np
from numpy import *


root = tk.Tk()
root.wm_title("Binomial Expander")


def factorial(n):
    if n == 1:
        return n 
    elif n==0: 
        return 1
    else: 
        return n*factorial(n-1)
    

#'(x+1)^10' 

def is_integer(n):     #Integer Determinator Function 
    try:
        float(n)
    except ValueError:
        return False
    else:
        return float(n).is_integer()
    
def is_float(n):       #Float Determiner 
    try:
        float(n)
    except ValueError:
        return False
    else:
        return True

def submit():   
    Formula = name_entry_func.get()
    for i in range(len(Formula)):
        if Formula[i] == '^':
            Formula = Formula[0:i+1]+'{'+Formula[i+1:len(Formula)]+'}'
    Formula = r"$"+Formula+"$"
    ax.clear()
    ax.text(0.2, 0.4, Formula, fontsize = 15)  
    canvas.draw()
    fac = name_entry_func.get()
    
    
    n = 0 
    for i in range(len(fac)):            #Finding use in input string
        if fac[i] == '^':
            n = fac[i+1:len(fac)]
        if fac[i] == '(':
            for j in range(len(fac)):
                if fac[j] == '+':
                    a = fac[i+1:j]
        if fac[i] == '+':
            for j in range(len(fac)):
                if fac[j] == ')':
                    b = fac[i+1:j]  
    
    if is_integer(n) == True:
        n = int(n)
        coeff = []
        powB = []
        powA = [] 
        for i in range((n+1)): #How Make for non - integers 
             powB.append(n-i) 
             powA.append(n-i)
             coff = ((factorial(n))/(factorial(n-i)))/factorial(i)
             coeff.append(int(coff))
        powB.reverse()
        #print(powA,powB,coeff)
        both1 = []
        for i in range(n+1): 
            Apow = str(a+'^'+str(powA[i]))
            Bpow = str(b+'^'+str(powB[i]))
            if len(str(powA[i])) > 1: 
                Apow = str(a+'^'+'{'+str(powA[i])+'}')
            if len(str(powB[i])) > 1: 
                Bpow = str(b+'^'+'{'+str(powB[i])+'}') 
            if str(coeff[i]) == '1':
                coeff[i] = '' 
            if str(powA[i]) == '0':
                Apow = ''
            if str(powB[i]) == '0':
                Bpow = ''
            if str(powA[i]) == '1':
                Apow = a
            if str(powB[i]) == '1':
                Bpow = b       
            both = str(coeff[i])+str('{'+Apow+Bpow+'}')
            if is_float(b) == True :
                    if str(coeff[i]) == '':             ##Tad in-efficiant 
                        coeff[i] = '1'
                    if is_integer(coeff[i]) == True and is_integer(b) == True:
                        both = str(int(coeff[i])*int(b)**powB[i])+Apow 
                        if int(coeff[i])*int(b)**powB[i] == 1 and Apow != '':
                            both = Apow
                    else:
                        both = str(int(coeff[i])*float(b)**powB[i])+Apow  
            if is_float(a) == True :
                    if str(coeff[i]) == '':             ##Tad in-efficiant 
                        coeff[i] = '1'
                    if is_integer(coeff[i]) == True and is_integer(a) == True:
                        both = str(int(coeff[i])*int(a)**powA[i])+Bpow 
                        if int(coeff[i])*int(a)**powA[i] == 1 and Bpow != '':
                            both = Bpow
                    else:
                        both = str(int(coeff[i])*float(a)**powA[i])+Bpow 
            both1.append(both)    #Account for negative 
        s = ' + '
        bot = s.join(both1)
        #Graph it?
        ax2.clear()
        ax2.text(0.01, 0.4, "$"+bot+"$", fontsize = 10)  
        canvas2.draw()
 
        
    if is_integer(n) == False and is_float(n) == True:
        ne = int(ne_var.get())
#        ne = int(input('To what order do you want to expand to?:'))
        coeff = []
        powB = []
        powA = [] 
        j = 0  
        me = 1 
        mul = [] 
        for i in range(ne):
            powB.append(ne-i) 
            powA.append(ne-i)
            mi = float(n)-i
            mul.append(mi)        
        for i in range(ne):
            me = mul[i]*me
            ma = me/factorial(i)
            coeff.append(ma)
    ### Append each coefficient 
    ### Divide Through 
        powB.reverse()
        both1 = []
        for i in range(ne): 
            Apow = str(a+'^'+str(powA[i]))
            Bpow = str(b+'^'+str(powB[i]))
            if len(str(powA[i])) > 1: 
                Apow = str(a+'^'+'{'+str(powA[i])+'}')
            if len(str(powB[i])) > 1: 
                Bpow = str(b+'^'+'{'+str(powB[i])+'}') 
            if str(coeff[i]) == '1':
                coeff[i] = '' 
            if str(powA[i]) == '0':
                Apow = ''
            if str(powB[i]) == '0':
                Bpow = ''
            if str(powA[i]) == '1':
                Apow = a
            if str(powB[i]) == '1':
                Bpow = b       
            both = str(coeff[i])+str('{'+Apow+Bpow+'}')
            if is_float(b) == True :
                    if str(coeff[i]) == '':          
                        coeff[i] = '1'
                    if is_integer(coeff[i]) == True and is_integer(b) == True:
                        both = str(int(coeff[i])*int(b)**powB[i])+Apow 
                        if int(coeff[i])*int(b)**powB[i] == 1 and Apow != '':
                            both = Apow
                    else:
                        both = str(int(coeff[i])*float(b)**powB[i])+Apow 
            if is_float(a) == True :
                    if str(coeff[i]) == '':            
                        coeff[i] = '1'
                    if is_integer(coeff[i]) == True and is_integer(a) == True:
                        both = str(int(coeff[i])*int(a)**powA[i])+Bpow 
                    else:
                        both = str(int(coeff[i])*float(a)**powA[i])+Bpow #Edit for non-zero solution 
            both1.append(both)
        s = ' + '
        bot = s.join(both1)
        ax2.clear()
        ax2.text(0.2, 0.4, "$"+bot+"$", fontsize = 10)  
        canvas2.draw()



Title = tk.Label(root, text = 'Binomial Expander', font = ('calibre',15,'bold'))
Title.pack()

fig = Figure(figsize=(5, 1), dpi=100)
ax2 = fig.add_subplot(111)
ax2.get_xaxis().set_visible(False)
ax2.get_yaxis().set_visible(False)

field =  ''   
row = tk.Frame(root)
lab2 = tk.Label(row, width=15, text=field, anchor='w')
canvas2 = FigureCanvasTkAgg(fig, master=root)  # A tk.DrawingArea.
canvas2.get_tk_widget().pack(side=tk.RIGHT, fill=tk.X)
row.pack(side=tk.TOP, fill=tk.X, padx=0, pady=0)

canvas2.draw()


fig = Figure(figsize=(2, 1), dpi=100)
ax = fig.add_subplot(111)
ax.get_xaxis().set_visible(False)
ax.get_yaxis().set_visible(False)



field =  ''        
row = tk.Frame(root)
lab = tk.Label(row, width=15, text=field, anchor='w')
canvas = FigureCanvasTkAgg(fig, master=root)  # A tk.DrawingArea.
canvas.get_tk_widget().pack(side=tk.RIGHT, fill=tk.X)
row.pack(side=tk.TOP, fill=tk.X, padx=0, pady=0)

canvas.draw()

Function_var=tk.StringVar()

row = tk.Frame(root)
lab = tk.Label(row, width=15, text='Input Binomial', anchor='w' , font=('calibre',10, 'bold'))
name_entry_func = tk.Entry(row,textvariable = Function_var)
row.pack(side=tk.TOP, fill=tk.X, padx=5, pady=5)
lab.pack(side=tk.LEFT)
name_entry_func.pack(side=tk.RIGHT, expand=tk.YES, fill=tk.X)

ne_var = tk.StringVar()
row = tk.Frame(root)
name_entry_Voltage = tk.Entry(row, textvariable = ne_var, font=('calibre',10,'normal'))
name_label = tk.Label(row, width=15, text = 'What order', font=('calibre',10, 'bold'))
name_entry = tk.Entry(row, textvariable = ne_var, font=('calibre',10,'normal'))
row.pack(side=tk.TOP, fill=tk.X, padx=5, pady=5)
name_label.pack(side=tk.LEFT)
name_entry.pack(side=tk.RIGHT, expand=tk.YES, fill=tk.X)

sub_btn=tk.Button(root,text = 'Submit', command = submit) 
sub_btn.pack()

root.mainloop()
