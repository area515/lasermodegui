from Tkinter import *
import tkFileDialog
import os
import subprocess

def sel():
	selection = "You selected the option " + str(var.get())
	label.config(text = selection)
	if var.get() == 1:
		labelframevector.grid()
		labelframeraster.grid_forget()
		root.rowconfigure(3, weight=0)
		root.rowconfigure(4, weight=1)
		labelframevector.grid(row=3, sticky = W+E+N+S )
		labelframevector.columnconfigure(1, weight=1)
		labelframevector.rowconfigure(0, weight=1)
		labelframevector.rowconfigure(1, weight=1)
		labelframevector.rowconfigure(2, weight=1)
		labelframevector.rowconfigure(3, weight=1)
	else:
		setrasterpower()
		labelframevector.grid_forget()
		labelframeraster.grid()
		root.rowconfigure(3, weight=0)
		root.rowconfigure(4, weight=1)
		labelframeraster.grid(row=3,sticky = W+E+N+S )
		labelframeraster.columnconfigure(0, weight=1)
		labelframeraster.rowconfigure(0, weight=1)
		labelframeraster.rowconfigure(1, weight=1)
		labelframeraster.rowconfigure(2, weight=1)
		labelframeraster.rowconfigure(3, weight=1)
		

def openlinuxcncvector():
	label.config(text = "Openning linuxCNC in vector mode")

def openlinuxcncraster():
	label.config(text = "Openning linuxCNC in raster mode")

def openfile():
	label.config(text = "Opening file")
	filename = tkFileDialog.askopenfilename()
	label.config(text = filename)
	if filename:
		entryfullfilelocation.delete(0, END)
		entryfullfilelocation.insert(0, filename)

def setrasterpower():
	print("Setting raster power")

def convertfile():
	print("Setting raster power")
	#cmdping = "ping -c4 www.cyberciti.biz"
	#p = subprocess.Popen(cmdping, shell=True, stderr=subprocess.PIPE)
	#while True:
    	#	out = p.stderr.read(1)
    	#	if out == '' and p.poll() != None:
        #		break
    	#	if out != '':
        #		sys.stdout.write(out)
        #		sys.stdout.flush()
	#
	#p = subprocess.Popen(["ls", "-l", "/etc/resolv.conf"], stdout=subprocess.PIPE)
	#output, err = p.communicate()
	#print "*** Running ls -l command ***\n", output

root = Tk()
root.wm_title("Laser Controller")
root.columnconfigure(0, weight=1)


var = IntVar()
radiobuttonvector = Radiobutton(root, text="Vector Mode", variable=var, value=1,command=sel)
radiobuttonvector.grid(row=0, sticky = W )

radiobuttonraster = Radiobutton(root, text="Raster Mode", variable=var, value=2,command=sel)
radiobuttonraster.grid(row=1, sticky = W )

label = Label(root)
label.grid(row=2, sticky = W)

# Vector group
labelframevector = LabelFrame(root, text="Vector Settings")
labelframevector.grid(row=3, sticky = W+E+N+S )
labelframevector.columnconfigure(1, weight=1)
labelframevector.rowconfigure(0, weight=1)
labelframevector.rowconfigure(1, weight=1)
labelframevector.rowconfigure(2, weight=1)
labelframevector.rowconfigure(3, weight=1)
# Stuff inside vector group
leftvector = Label(labelframevector, text="Max power is 50%")
leftvector.grid(row=0, column=1, sticky = W+S)
#	Set Power label/entry
labelsetpower = Label(labelframevector, text="Set Power (%)")
labelsetpower.grid(row=1, column=0,stick = W)
entrysetpower = Entry(labelframevector, bd =5)
entrysetpower.grid(row=1, column=1, stick = W+E)
#	Current Power lable/entry
labelcurrentpower = Label(labelframevector, text="Current Power (%)")
labelcurrentpower.grid(row=2, column=0, sticky = W)
labelcurrentpoweroutput = Label(labelframevector, text="Waiting...")
labelcurrentpoweroutput.grid(row=2, column=1,sticky = W+E+N+S)
#	Open LinuxCNC Vector
buttonopenlinuxcncvector = Button(labelframevector, text="Open LinuxCNC (Vector Mode)", command=openlinuxcncvector)
buttonopenlinuxcncvector.grid(row=3, columnspan=2,sticky = W+E+N+S)

# Raster group
labelframeraster = LabelFrame(root, text="Raster  Settings")
labelframeraster.grid(row=4,sticky = W+E+N+S )
labelframeraster.columnconfigure(0, weight=1)
labelframeraster.rowconfigure(0, weight=1)
labelframeraster.rowconfigure(1, weight=1)
labelframeraster.rowconfigure(2, weight=1)
labelframeraster.rowconfigure(3, weight=1)
# Stuff inside raster group
leftraster = Label(labelframeraster, text="Convert picture file to ngc")
leftraster.grid(row=0,sticky = W+S)
#	Set Power label/entry
entryfullfilelocation = Entry(labelframeraster, bd =5)
entryfullfilelocation.grid(row=1, column=0, stick = W+E)
buttonbrowse = Button(labelframeraster, text="Browse", command=openfile)
buttonbrowse.grid(row=1, column=1,sticky = W+E)
#	Current Power lable/entry
buttonconvertfile = Button(labelframeraster, text="Convert File", command=convertfile)
buttonconvertfile.grid(row=2, column=1 ,sticky = W+E)
#	Open LinuxCNC Raster
buttonopenlinuxcncraster = Button(labelframeraster, text="Open LinuxCNC (Raster Mode)", command=openlinuxcncraster)
buttonopenlinuxcncraster.grid(row=3, column=0,columnspan=2 ,sticky = W+E+N+S)

#	Select Vector Group to start
radiobuttonvector.invoke()


root.mainloop()
