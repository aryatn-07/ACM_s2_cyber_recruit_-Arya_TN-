CHALLENGE DESCRIPTION:
An image was given and asked to find the hidden flag. Hidden information is embedded in the image's binary data. The task is to analyse the image at a hexadecimal level and recover the flag.

ANALYSIS/APPROACH:
I used the command 'file image.jpg' to confirm that the file is an image. The terminal confirmed it was an image and image details were shown. Since the data was in hexadecimal, I used the command xxd image.jpg to decode it. At the end of the given output was the flag.

COMMANDS USED : 
file image.jpg
xxd image.jpg

Flag: flag{jai_mahismathi)
