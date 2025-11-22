import qrcode
import os

url = input("Enter URL: ")

img = qrcode.make(url)

windows_user = os.popen('cmd.exe /c "echo %USERNAME%"').read().strip()


path = f"/mnt/c/Users/{windows_user}/Desktop/qrcode.png"

img.save(path)

print(f"QR Code saved on your Windows Desktop as qrcode.png")
