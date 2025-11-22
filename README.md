
import tkinter as tk

from tkinter import messagebox

import qrcode

import os

def generate_qr():
  
    url = url_entry.get()

    if not url.strip():
     
        messagebox.showwarning("Input Error", "Please enter a URL.")
     
        return

    try:
        img = qrcode.make(url)
       
        desktop = os.path.join(os.path.expanduser("~"), "Desktop")
        
        save_path = os.path.join(desktop, "qrcode.png")
      
        img.save(save_path)
      
        messagebox.showinfo("Success", "QR Code saved on Desktop as qrcode.png")
   
    except Exception as e:
       
        messagebox.showerror("Error", f"Something went wrong:\n{e}")



root = tk.Tk()

root.title("QR Code Generator")

root.geometry("350x200")



title_label = tk.Label(root, text="Enter URL:", font=("Arial", 14))

title_label.pack(pady=10)



url_entry = tk.Entry(root, width=40, font=("Arial", 12))

url_entry.pack(pady=5)



generate_button = tk.Button(root, text="Generate QR Code", font=("Arial", 12), command=generate_qr)

generate_button.pack(pady=20)


root.mainloop()





==========



python - <<EOF
import tkinter as tk
root = tk.Tk()
root.title("Test Window")
root.mainloop()
EOF
