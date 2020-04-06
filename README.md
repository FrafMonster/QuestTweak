# QuestTweak

Available for PC, MAC and LINUX (slight configuration needed),
QuestTweak is a console app designed to modify graphics settings for Oculus Quest and Oculus Go.
It uses adb commands to run inputed tasks.

## Download and usage

Download the directory 'QuestTweak', and put it on your desktop for easy access
Download the android platform tools, available for Mac, Linux:

https://developer.android.com/studio/releases/platform-tools

### Attention MAC Users:

For this application to work on mac, please download the Windows Mono framework:

https://www.mono-project.com/download/stable/

### Launching QuestTweak

Once the platform tools finished downloading, place the 'adb' file (present inside platform tools) inside the QuestTweak directory.

Open a terminal, and enter the following command to navigate inside QuestTweak

'''sh
cd Desktop/QuestTweak/
'''

Once inside, verify that all files are present by typing

'''sh
ls
'''

You should see 'adb' and 'QuestTweak'.

To execute the file, type the following command for Windows:

'''sh
./QuestTweak
'''

Or for Mac:

'''sh
mono QuestTweak
'''

Once running, make sure your headset is connected to your computer, and you should be ready to go!
For the modifications to take effect, you must start an application on the headset.
To restore the Quest's or Go's default settings, just reboot the headset.

## If the application does not work DO NOT WORRY!

You are still able to modify without too much difficulty your headset's settings via command lines!

First off, navigate to wherever the 'adb' file is present on your computer; if you followed the steps above correctly you should already be there.
Secondly, open a shell inside the Oculus Quest by typing:

'''sh
./adb shell
'''

Warning: be careful while manipulating commands, you may cause problems for your device if you do not know what you are doing.

Here is the list of functions that allow you to modify graphics settings:

'''sh
setprop debug.oculus.textureWidth 1920
'''  
(resolution width)

'''sh
setprop debug.oculus.textureHeight 1920
'''
(resolution height)

'''sh
setprop debug.oculus.foveation.level 4
'''  
(0 - 4, blurs the edges of the screen, enhancing rendering capacity, all the while having barely any visible effect)

'''sh
setprop debug.oculus.gpuLevel 4
'''
(0 - 4, 0: barely any power consumption, barely any gpu power. 4: high battery consumption, and significant increase in gpu power)

'''sh
setprop debug.oculus.cpuLevel 4
'''
(0 - 4, does not really affect rendering capability)