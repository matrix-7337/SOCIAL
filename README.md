import qrcode
import os

url = input("Enter URL: ")

img = qrcode.make(url)

# Get your Windows username automatically
windows_user = os.popen('cmd.exe /c "echo %USERNAME%"').read().strip()

# Save directly on Windows Desktop
path = f"/mnt/c/Users/{windows_user}/Desktop/qrcode.png"

img.save(path)

print(f"QR Code saved on your Windows Desktop as qrcode.png")
