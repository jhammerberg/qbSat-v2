This is the repository for **qbSat v2!** if you are looking for version one, switch to that repository!
qbSat v2 is a simplified version of the project in an effort to make it more simple and less expensive.
# qbSat
(This is just an open source repository of this project. If you're missing something try looking through that google drive folder!)
https://drive.google.com/drive/folders/1t1jHuP0nEzHlEdOj4gA296oam3h7xkxt?usp=share_link

Mirror:
https://mega.nz/folder/UqZE3BLB#-bwIp7tPUVvnyKYQCGDYIw
## What is qbSat?
qbSat is a mock CubeSat made to teach students the basics of electronics, programming and aerospace in a fun and engaging way! It is a data recording device in the standard CubeSat 1U form factor (10x10x10cm) with an infrared or visible light camera along with gas, light, and humidity sensors. With custom software, the qbSat can record hours of video from a high altitude balloon or drone. It also has a a built in web interface to see results in real-time (while in Wi-Fi range) and download your recordings.

## Parts List
The qbSat uses entirely COTS (Commerical off the shelf parts). However, due to recent supply chain shortages you may need to find alternate parts.

You must have access to: *An internet connection (only to download software), a  3D printer & filament, a phillips head screwdriver, a Windows, Chromebook or Mac computer with Wi-fi and an SD card slot.*

### (Name, Price, Quantity, Where to buy)
- Raspberry Pi 3B+ | $35.00 | 1 | [Link](https://www.adafruit.com/product/3775)
- Pimoroni EnviroPlus | $65 | 1 | [Link](https://shop.pimoroni.com/products/enviro/enviro-air-quality?variant=31155658457171)
- Raspberry Pi Camera Module | $29.95 | 1 | [Link](https://www.adafruit.com/product/3099)
- WaveShare UPS Hat (B) | $22.99 | 1 | [Link](https://www.waveshare.com/ups-hat-b.htm)
- 18650 Battery Cells | $6.50 | 2 | [Link](https://www.sparkfun.com/products/12895)
- Micro SD card | $9.99 | 1 | [Link](https://www.amazon.com/dp/B08GY9NYRM/ref=twister_B08KB38516?_encoding=UTF8&psc=1)
- 6 - 32 Machine Screws | $1.86 | 1 | [Link](https://www.amazon.com/Prime-Line-9003018-Machine-Phillips-Combination/dp/B074ZWNSFY/ref=sr_1_8?crid=23R9O7Q5KTG2&keywords=Screws&pd_rd_r=c1381165-4449-467e-86ec-1d006f4903be&pd_rd_w=FWSCb&pd_rd_wg=597NE&pf_rd_p=b4950e17-f2f6-494c-bba5-69a9d0aa3887&pf_rd_r=AKS50KGXAZCM7RRYCZG9&pid=kD6IyXH&qid=1644586593&refinements=p_n_feature_twenty-eight_browse-bin%3A19043647011&s=industrial&sprefix=6+-+32+machine+screws%2Caps%2C104&sr=1-8)
- M2.5 Screws | $11.49 | 1 | [Link](https://www.amazon.com/uxcell-Phillips-Fasteners-Laptop-Switch/dp/B08J3BDGKH/ref=sr_1_16?crid=2WNZ0XA8BDVZE&keywords=M2.5%2Bscrews&qid=1643724575&s=electronics&sprefix=m2.5%2Bscrews%2Celectronics%2C93&sr=1-16&th=1)

Notes: Only MSRP is given, some components may be out of stock. Any standard 18650 cells will work, as well as Raspberry Pi Camera Modules 2 and 3 however not the original first generation. A 32gb+ SD card is recommended but only 16GB+ is needed.

## Instructions
qbSat v2 has a set of written instructions and may have a video tutorial in future.

### Frame Assembly:

Use the provided laser cut pieces or, if you have access to a laser cutter, import the SVGs from the ‘Assembly Files’ folder and cut them, making sure to cut the inside geometry before the outside is cut. Also use the provided 3D printed pillars or, if you have access to a 3D printer, start printing the STL file labeled ‘Inner Pillar Set.stl’ from inside the ‘Assembly Files’ folder.

### Electronics Assembly:

Take the UPS hat and place it so that the battery housing goes through the slot. Then place spacers on the screw holes and screw in four M2.5 screws from the other side of the piece. Place the Raspberry Pi on top of the spacers and screw it in with M2.5 screws as well. Make sure that the spring loaded pins from the UPS are firmly touching the bottom of the pins on the Raspberry Pi. Now, plug in the EnviroPlus board onto the Raspberry Pi’s pins. 
Lift up the black plastic piece of the Raspberry Pi’s camera port (the port closest to the USB ports) and insert the ribbon cable that came with the camera module, make sure that the blue part is facing towards the USB ports. Make sure to route the ribbon cable through the small space next to the UPS board. Plug the other end into the camera (if it’s not already attached) and screw in the camera to its piece as well, making sure to screw in the M2.5 screws from the opposite side. Finally, place the 18650 cells into the UPS board. 

***MAKE SURE THAT THE END OF THE BATTERY THAT HAS A NEGATIVE SYMBOL LINES UP WITH THE NEGATIVE SYMBOL ON THE BOARD OR IT WILL DAMAGE IT.***

### Final Assembly:

Place down the back piece first (the wider symmetric piece) and then slot in the top piece (without the camera), middle piece (with your electronics), and bottom piece (with the camera). Then take the right piece (the one with the cutout for the USB ports) and attach it to the right side of the panels. Same with the left piece (the side with the cutout for the SD card), and the front piece (with cutouts for the UPS switch and charger). Finally take the pillars and slide them in, make sure that the screw holes align because they are not symmetric and must line up with the ones furthest apart facing the outside, then screw them in with 6-36 screws.

### Software:

Download the Raspberry Pi Imager and software image and then insert your micro SD card into your computer. Open the Raspberry Pi Imager, select the SD card and software image and then click flash. When it’s done take out the SD Card and insert it into the Raspberry Pi. 

### Utilizing:

Turn on the CubeSat by activating the switch on the UPS board, it should make a Wi-Fi signal a few seconds later called ‘qbSat-V2’. Connect to it and go to http://192.168.4.1 in your browser (Make sure to connect to http and not https). A live preview of the camera should start as well as the sensor readings. If it does not start, it may be helpful to restart the CubeSat. To make a recording, just hit the Stop/Start recording button on the website. When you’re done it will make and compress the file which may take several minutes. After it is done, go to the ‘Downloads’ tab and click on the file name with the newest time and date. Because it cannot connect to the internet, the time and date on the zip file are only relative to when it’s started. Opening the zip file you should find an MP4 and CSV file containing the video and sensor data respectively. If you want to clear the recordings taken on the CubeSat then click the ‘Delete all recordings’ button.
