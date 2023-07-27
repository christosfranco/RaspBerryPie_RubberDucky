# RaspBerryPie_RubberDucky
Implementing a rubberducky on a raspberry pie pico. 

Notice: this project is purely for educational purposes. I did not develop rubberducky or the script language associated. This project is just a quickguide and includes all the relevant files needed for RaspBerryPie Pico to be transformed into a RubberDucky bad usb. The main page includes alot of unnessesary files. Do not use rubberducky for malious purposes. 

## Setup (2 min)
1. Copy *.uf2 file onto raspberry pie pico to transform it to a bad-usb (keyboard emulator). Should now have name CIRCUITPY

2. once the usb is transformed, copy all the contents in PICO_BASE folder

3. Develop you own rubberducky script and put it into the "payload (2).dd" file (example can be found on https://github.com/hak5/usbrubberducky-payloads)

4. OBS! once you rename the file, it will execute the script after 0.5 second on the computer its currently plugged into. rename "payload (2).dd" -> "payload.dd"

5. Plug into another computer and the script will execute. 

## To reset (common for files to be corrupted) (1 min)
1. Hold the BOOTSEL button while plugging usb into computer, this will prevent script from running and leave it partly in factory state

2. copy "flash_nuke.uf2" onto the device to reset it fully.

3. do "Setup" section again

## Change keyboard language
The files currently set it to danish keyboard.

To change to us keyboard. 
1. change lines in ```duckinpython.py```
```
# comment out these lines for non_US keyboards
# from adafruit_hid.keyboard_layout_us import KeyboardLayoutUS as KeyboardLayout
# from adafruit_hid.keycode import Keycode

# uncomment these lines for non_US keyboards
# replace LANG with appropriate language
from keyboard_layout_win_da import KeyboardLayout
from keycode_win_da import Keycode
```

For other keyboard look here: https://github.com/Neradoc/Circuitpython_Keyboard_Layouts/releases/tag/20221209