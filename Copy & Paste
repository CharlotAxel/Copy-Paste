import shutil
import os
from os import path
from tkinter import filedialog
from tkinter import messagebox
from tkinter import *

root = Tk()
root.title('Copy/Past')
root.geometry('475x275')
root.config(bg='#283747')

#Create a file dialog to chose src directory
def src_fcn():
	'''Function that allow the user to chose a source directory thanks to the .filedialog module'''
	global src_var
	root.filename = filedialog.askdirectory(initialdir=r"C:\Users\\", title="Select A Directory")
	src_var = str(root.filename)
	src_label = Label(root, text=src_var)
	src_label.grid(row = 1, column = 1)
	
#Create a file dialog to chose dst directory
def dst_fcn():
	'''Function that allow the user to chose a destination directory thanks to the .filedialog module'''
	global dst_var
	root.filename = filedialog.askdirectory(initialdir=r"C:\Users\Axel\Desktop\\", title="Chose Destination")
	dst_var = str(root.filename)
	dst_label = Label(root, text=dst_var)
	dst_label.grid(row = 2, column = 1)

#Create the copy function.
def copy():
	'''Function that allows the user to copy the content of a folder into another anywhere on the computer, with a few restriction (see comments)'''
	src = src_var
	dst = dst_var
	#Select the files
	files = os.listdir(src)
	files.sort()
	#copy the files
	for f in files:
		try:
			shutil.copy2(path.join(src,f), dst)
			#pop up that ensure everything went fine
			messagebox.showinfo('Files pasted', 'Done')
		except shutil.SameFileError:#error when the files are identics
		#popup that display the error message
			messagebox.showerror('Error', 'You cannot chose the same folder as source and destination.')

#Create Buttons
src_btn = Button(root, text='Copy from :', command = src_fcn, bd = 5)
src_btn.grid(row = 1, column = 0, pady = 20, padx = 20)

dst_btn = Button(root, text='Copy to :', command = dst_fcn, bd = 5, width = 9)
dst_btn.grid(row = 2, column = 0, pady = 20, padx = 40)

copy_btn = Button(root, text ='Copy!', command = copy, bd = 5, width = 15, height = 3)
copy_btn.grid(row = 4, column = 1, columnspan = 2, pady = 20, padx = 20)

root.mainloop()
