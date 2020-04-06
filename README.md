# QuestTweak

Available for PC, MAC and LINUX (slight configuration needed),
QuestTweak is a console app designed to modify graphics settings for Oculus Quest and Oculus Go.
It uses adb commands to run inputed tasks.

## Download and usage

Download the directory 'QuestTweak', and put it on your desktop for easy access.

Download the android platform tools, available for Windows, Mac, Linux:

https://developer.android.com/studio/releases/platform-tools

### Attention MAC Users:

For this application to work on mac, please download the Windows Mono framework:

https://www.mono-project.com/download/stable/

### Launching QuestTweak

Once the platform tools finished downloading, place the 'adb' file (present inside platform tools) inside the QuestTweak directory.

Open a terminal, and enter the following command to navigate inside QuestTweak


```sh
cd Desktop/QuestTweak/
```

Once inside, verify that all files are present by typing

```sh
ls
```

You should see 'adb' and 'QuestTweak'.

To execute the file, type the following command for Windows:

```sh
./QuestTweak
```

Or for Mac:

```sh
mono QuestTweak
```

Once running, make sure your headset is connected to your computer, and you should be ready to go!

For the modifications to take effect, you must start an application on the headset.

To restore the Quest's or Go's default settings, just reboot the headset.

## If the application does not work DO NOT WORRY!

You are still able to modify without too much difficulty your headset's settings via command lines!

First off, navigate to wherever the 'adb' file is present on your computer; if you followed the steps above correctly you should already be there.

Secondly, open a shell inside the Oculus Quest by typing:

```sh
./adb shell
```

Warning: be careful while manipulating commands, you may cause problems for your device if you do not know what you are doing.

Here is the list of functions that allow you to modify graphics settings:

```sh
setprop debug.oculus.textureWidth 1920
```
(resolution width, standard is 1280)

```sh
setprop debug.oculus.textureHeight 1920
```
(resolution height, standard is 1280)

```sh
setprop debug.oculus.foveation.level 4
```
(0 - 4, blurs the edges of the screen, enhancing rendering capacity, all the while having barely any visible effect)

```sh
setprop debug.oculus.gpuLevel 4
```
(0 - 4, 0: barely any power consumption, barely any gpu power. 4: high battery consumption, and significant increase in gpu power)

```sh
setprop debug.oculus.cpuLevel 4
```
(0 - 4, does not really affect rendering capability)

## Recommended settings

Certain games use more gpu power than others, and so it will be difficult to effectively change the resolution without it lagging.

It's a generally good idea to always set foveation level to 4, as it barely affects the VR experience, and increases performance.

Just set the gpu level to 4 all the time, as well as the cpu level.

### Beat saber - runs 4/4 GPU Level by default

It's actually a really demanding game, you can't really augment the resolution too much without it lagging, and for any expert+ users out there, please trust me on that one, don't bump it up too much

Res: ~ 1536 max

Fov level: 4

GPU/CPU level: 4

### Pistol Whip - runs 2/4 GPU Level by default

If you set the GPU level to 4, you can bump your graphics up to rift s resolution! There's slight lag, so if you want smoother gameplay set it to about 1920, but if you don't care go for 2440! (I personally do not care)

Res: 1920 - 2440 Makes a HUGE difference to have these resolutions

Fov level 4

GPU/CPU level: 4

### Mission ISS - runs 2/4 GPU Level by default

Same goes here! Turn the resolution really high for a great space immersion!

Res: 1920 - 2440 Makes a HUGE difference to have these resolutions

Fov level 4

GPU/CPU level: 4

### Debugging for other games

If you are interested in seeing wether or not certain games can support high resolutions, type this command in (from the same folder that contains the 'adb' file):

```sh
./adb logcat -s VrApi
```

A very big chunk of text will appear, and will update every few moments; you are basically looking at the Rendering logs of the oculus quest!

To see if your game requires a lot of GPU/CPU power, just launch it after having typed that command in, and observe the change in GPU usage, it should look something like this: "GPU=2/4", with the '2' replaced by whatever number is actually being used