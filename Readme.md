
##    Huion 950P tablet configure   Kubuntu Linux 20.04   October 2021
#  Source/Thanks to:
    https://askubuntu.com/questions/1000869/how-to-run-the-new-huion-tablets-on-linux


# Step 1:
 as superuser, copy this into a new file /usr/share/X11/xorg.conf.d/90-huion950P.conf

 
    Section "InputClass"
        Identifier "Huion tablets with Wacom driver"
        MatchUSBID "256c:006d*"
        MatchIsTablet "true"
        MatchDevicePath "/dev/input/event*"
        Driver "wacom"
    EndSection

# Step 2:  Restart X server by logging out or rebooting 

# Step 3:  Get names of your Huion tablet devices

    > xsetwacom --list

# example output:
  
    Wacom HID 488E Pen stylus               id: 20  type: STYLUS    
    Wacom HID 488E Finger touch             id: 21  type: TOUCH     
    Wacom HID 488E Pen eraser               id: 30  type: ERASER    
    HUION Huion Tablet_H950P Pen stylus     id: 32  type: STYLUS    
    HUION Huion Tablet_H950P Pad pad        id: 33  type: PAD       

# Step 4:  customize the device names for STYLUS and PAD below, and of course set  the commands according to your own preference. 

#  You are all set!!   make this file run-able, and run it whenever you plug in your tablet!
    > ./tabInit


