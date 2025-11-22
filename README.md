import qrcode
import os

url = input("Enter URL: ")

img = qrcode.make(url)

windows_user = os.popen('cmd.exe /c "echo %USERNAME%"').read().strip()


path = f"/mnt/c/Users/{windows_user}/Desktop/qrcode.png"

img.save(path)

print(f"QR Code saved on your Windows Desktop as qrcode.png")


===============================


import qrcode
import tkinter as tk
from tkinter import simpledialog, messagebox
import os


desktop_path = os.path.join(os.path.expanduser("~"), "Desktop")


root = tk.Tk()
root.withdraw()


messagebox.showinfo("Welcome", "Welcome!\nEnter a URL to generate a QR code.")


url = simpledialog.askstring("QR Code Generator", "Enter the URL:")

if url:
    img = qrcode.make(url)
    file_path = os.path.join(desktop_path, "qrcode.png")
    img.save(file_path)
    messagebox.showinfo("Success", f"QR Code saved to Desktop:\nqrcode.png")
else:
    messagebox.showwarning("Cancelled", "No URL entered.")
====================≠=========


import qrcode


import tkinter as tk


from tkinter import simpledialog, messagebox


import os



root = tk.Tk()



root.withdraw()


url = simpledialog.askstring("QR Code Generator", "Enter the URL:")



if url:
    
    img = qrcode.make(url)


    desktop = os.path.join(os.path.expanduser("~"), "Desktop")
   
    
    save_path = os.path.join(desktop, "qrcode.png")
   
    
    img.save(save_path)

  
    messagebox.showinfo("Done", "QR Code saved to Desktop as qrcode.png")


else:
   
    
    messagebox.showwarning("No Input", "You did not enter a URL.")
