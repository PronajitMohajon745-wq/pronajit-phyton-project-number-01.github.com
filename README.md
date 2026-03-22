import qrcode
from PIL import Image  # ensure PIL installed: pip install pillow

# URL
url = "https://www.instagram.com/mit?igsh=MXR0anBraW1uOGtsMA=="

# QR code setup
qr = qrcode.QRCode(
    version=1,
    error_correction=qrcode.constants.ERROR_CORRECT_H,
    box_size=10,
    border=4,
)

qr.add_data(url)
qr.make(fit=True)

# Create image
img = qr.make_image(fill_color="black", back_color="white")

# Save
img.save("MIT_Instagram.png")
print("QR code generated successfully!")
