**Michael Peters**

**ESE-5190**

**Lab 2 Install Log**

**Machine Details:**

Microsoft Surface Laptop 2017, Windows 10

**Installed Software:**

I ended up probably installing more software than needed, links to each are in their own sections below.
This video I found on YouTube was helpful in making sure I was installing things correctly, the video takes some additional steps which I ignored but was useful for some software installations.

https://www.youtube.com/watch?v=K0LNCunQZUw

**Software List**

	-Windows Terminal					- Build Tools for Visual Studio 2022
	-gVim							- Python 3.10
	-Arm GNU Toolchain					- GIT
	-CMake							- MS Visual Studio Code

**Prelab Log:**

**Windows Terminal**

Downloaded official windows terminal from https://apps.microsoft.com/store/detail/windows-terminal/9N0DX20HK701?hl=en-us&gl=us
Trying out the official one for now before using any others.
Using command prompt within the program, used the “type” function to read the contents
C:\Users\mike>type C:\Users\mike\Desktop\testRead.txt
Also using Powershell in the terminal type: “cat” then “desktop/testRead.txt”

After installing everything else however it seems this terminal might not have a good use and isn’t necessary yet. It seems other programs I downloaded after have more useful terminals.

**gVim**

I installed gVim from the top first link on their website that says gvim_9.0.0000.exe
 ![image](https://user-images.githubusercontent.com/114199773/194925225-05374f64-c5b3-4240-981e-1ea3e393a63b.png)

I set it up as default/recommended as described in the prelab.

**Putty**

I installed 64bitx86 putty link from the link provided in the prelab. I set it up as recommended and it loaded like it said it would. I configured as suggested in the guide in the PreLab. The guide for windows that I followed is:
https://learn.adafruit.com/welcome-to-circuitpython/advanced-serial-console-on-windows 
 
 
**Lab2A Log:**

I’m following the instructions in section 9.2 of the “Getting Started” guide for this setup of SDK.
https://datasheets.raspberrypi.com/pico/getting-started-with-pico.pdf 
I am not including significant detail for the steps that are already described in the pico guide linked above. This is more so a supplimental guide to the official one and to document what steps I followed and in what order to get the hello_usb.c code working on the RP2040.


**Arm GNU Toolchain Download**

First I downloaded from https://developer.arm.com/downloads/-/arm-gnu-toolchain-downloads
I downloaded the file ending in -arm-none-eabi.exe like the guide says (4th one down under the windows category). Opened the installer and ran it keeping everything default. I added path to environment variable like suggested.

**CMake**

![image](https://user-images.githubusercontent.com/114199773/194926560-4d8e615e-bf3b-4130-8c42-45568982243e.png)


Downloaded CMake “Windows x64 Installer:” from (https://cmake.org/download/) like the guide suggested
Added it as a path for all users like the guide suggested.

**Build Tools For Visual Studio 2022**

Downloaded from the link https://visualstudio.microsoft.com/downloads/#build-tools-for-visual-studio-2022
Selected only C++ as the Pico guide recommended. Kept everything else default.

**Python 3.10.7**

Downloaded the latest version of python 3.10 from https://www.python.org/downloads/release/python-3107/ (Windows installer 64 bit)
Installed for all users, added to PATH, and max_path disabled. Everything else default.

**GIT**

Downloaded the latest version 2.38.0 from https://git-scm.com/download/win
Kept standard install. Set Notepad as GITs default editor & followed the guide for rest of the GIT setup.

**Getting SDK and Examples**

Ran the 5 commands in order in the default command prompt from section 9.2.2. Everything worked as suggested without error. I then skipped section 9.2.3 and moved to 9.2.4.

**MS Visual Studio Code**

Installed MS Visual studio code from the download in the guide from section 9.2.4. I configured it as the guide suggested and added the CMake extension in order and built all the uf2 files. They took a few hours and I’m not sure if it is necessary to build them all initially but I did anyway just to be safe. Important note is to launch from the “Developer Command Prompt for VS 2022” that was downloaded earlier by typing “code”. This will open MS Visual Studio code configured how you need it to be to build and edit files properly. The youtube video I linked previously at the start of this guide was helpful for this step once all the initial software was installed and it was time to configure the software so the UF2 files could be built. It shows a step by step process for this that I couldn't include in just a written guide.

**Running Hello World**

To actually just run the code and see “Hello World” printed in the serial console I first plugged the RP2040 into the USB then pushed both buttons to reset the board  from the circuit python configuration it had been in from lab 1. Now a new .UF2 file can be dragged and dropped into the board. I dropped the Hello_USB.UF2 file from the pico-examples/build folder on my PC onto the board. I then opened PuTTY and connected using the serial console COM4. One note is that previously when I set it up during the prelab it was COM3 but when loaded with the new UF2 file it switched to COM4. Having the wrong COM port meant my laptop couldn’t read the serial print out. This gave me trouble for a few minutes so it might be good to double check you have the correct COM port after loading the new UF2 file by using the windows “Device Manager” like the adafruit guide says which I linked above when I first installed Putty.
 
 ![image](https://user-images.githubusercontent.com/114199773/194925251-1bc8a4dd-8b8a-4d39-8395-82eddb149f23.png)


Also able to edit the hello_usb.c file and then build it to change what it prints to Putty.
 ![image](https://user-images.githubusercontent.com/114199773/194925313-4b4ef5fa-e20f-48ac-80d9-eb3bc85ea859.png)

Edited the C code and changed the builder from [All] to just [hello_usb] so it only builds the edited code and then hit the build button next to it.

 ![image](https://user-images.githubusercontent.com/114199773/194925363-2973242b-43f7-49b5-a3ec-3b4f0cd857a0.png)



