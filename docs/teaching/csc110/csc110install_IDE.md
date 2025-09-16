---
layout: default
title: Install_Python_and_IDE
parent: CSC110
grand_parent: Teaching
nav_order: 4
#permalink: /docs/teaching/csc110/
---  

<!-- 
Setting up Pytest in VSCode
https://code.visualstudio.com/docs/python/testing
 -->

# Installing a Development Environment

In order to write Python programs and execute (or run) them, you need to have a editor (to write) and an interpreter (to run) the program. Depending on your individual setup, you will take a different approach.


<!-- 
## Option A: I'm using a Laptop (or Desktop)

### 0. Download Starter Files

Download `first.py` from [Moodle](add link later) and save it locally on your computer. Consider putting it in a folder called `CSC110`...maybe even in a sub-folder called `class-demos`.

### 1. What is your processor?
Take note of whether your processor is ARM or x64.

_On an Apple Machine:_
Click on the `Apple` icon in the upper left corner of your screen, this menu should drop down, click on `About This Mac`. If next to Processor, it says M1/M2/M3, M1/M2/M3 Pro, M1/M2/M3 Max, or M1/M2 Ultra, you have an ARM-based Mac. If it says Intel, you have an x64.

_On a Windows Machine:_
On Windows 11, open Settings by pressing the key combination – Win + I. Click System on the left side and tap on About. Under the Device specifications section and locate System type to find what bit your computer is. If the screen says 64-bit operating system, x64-based processor, Windows 11 is 64-bit. If you see 64-bit operating system, ARM-based processor, it means the system type is ARM64.

### 2. Instal Visual Studio Code

Instal Visual Studio Code (VS Code): Go to [https://code.visualstudio.com](https://code.visualstudio.com) and click the blue download button.
Follow the installation instructions.

_If it doesn't work then go to [https://code.visualstudio.com/download](https://code.visualstudio.com/download), select the appropriate download. 
Make sure you click the correct version, based on your operating system (Windows/Mac) and chip (x64/ARM). Ask if you don't understand._



 -->
## 1. Instal Python

First, go to the section for your laptop (MAC or Windows) and then follow the instructions.

### Installing Python on a Mac

  1. Open this webpage: [Python Distributions for Mac](https://www.python.org/downloads/macos/)

     1. Instructions are also [here](https://docs.python.org/3/using/mac.html)
  2. Download the Latest Python 3 Release - Python 3.13.X (for some value of X)
  3. For a default installation, double-click on the downloaded installer package file. This should launch the standard macOS Installer app and display the first of several installer windows steps.
  4. Click Continue
  5. Read (scroll all the way down) and Continue
  6. Agree to the terms and conditions
  7. After the license terms are accepted, the next step is the Installation Type display. Select Customize and add all options show in the next slide

  ![custom Python install](../../../assets/images/csc110/mac_installer_05_custom_install.png){:width="500px"}

  8. Then click Install
  9. Double-click on the `Install Certificates.command` icon or file in the `/Applications/Python 3.13/` window to complete the installation.

  ![custom Python applications](../../../assets/images/csc110/mac_installer_07_applications.png){:width="500px"}


  10. This will open a temporary Terminal shell window that will use the new Python to download and install SSL root certificates for its use. **Note: this just means it let's you finish the configuration.**
  11. If Successfully installed certify and update complete appears in the terminal window, the installation is complete. Close this terminal window and the installer window.

_If you have trouble with any of these steps, ask for help._



### Installing Python on Windows

  1. Open this webpage: [Python Distributions for Win](https://www.python.org/downloads/windows/)

     1. Instructions are also [here](https://docs.python.org/3/using/windows.html)
  2. Download the Latest Python 3 Release - Python 3.13.X (for some value of X)
  3. Open the downloaded `.exe` file to launch the Python installer
     1. **Crucially**, on the first screen, check the box that says **"Add Python.exe to PATH"**.  OR Add Python to Environment Variables. This ensures you can easily run Python from the command prompt.
     2. **Crucially**, Also select Install Python 3.13 for all users

  ![custom Python applications](../../../assets/images/csc110/win_installer_05_custom_install.png){:width="500px"}

  4. Before picking the install method, make sure you pick "Customize installation" to select specific features.
     1. **Pick Customize** and select the features that match the ones for MAC shown in the previous section.
     2. ensure that "pip" (Python's package installer) is selected
  5. Open the Command Prompt (search for "cmd" in the Start Menu).
  6. Type `Python --version` and press Enter (or Return). This should display the installed Python 3.13 version, confirming a successful installation.

_If you have trouble with any of these steps, ask for help._


<!-- 
### 4. Remove automatic suggestions (they are annoying)

1. Open the settings by pressing the following combination: On Mac: press the command button and then the comma (CMD + ",")  or (⌘,). On Windows: press Control and comma (Ctrl + ",")
2. On the search bar, write: *Editor:Suggest*
3. On the resulting list of matches, one has the name *Editor: Quick Suggestions*. Under it, there is a link to *Editor: Suggest On Trigger Characters*. Select that link.
4. On the resulting page, you will see a series of selected options that start with *Editor:Suggest:*. There are many of them... please unselect them all. 




<br>

---

<br>

## Option B: I'm using a Chromebook or IPad Pro.

We recommend that you use Visual Studio Code for Education: [https://vscodeedu.com/](https://vscodeedu.com/).

1. Open a browser to [https://vscodeedu.com/](https://vscodeedu.com/).
2. Sign in with a Microsoft account. If you do not have one, create an account with your personal email (gmail/hotmail). If you want to used your Smith email and credentials, you will need to sign up for [Office 365 Education](https://www.microsoft.com/en-us/education/products/office).
3. Click `My Work` -> `My Projects` -> `New project`. Give your project a name (e.g., CSC110) then click `Create Project`.
4. A new project will be created, and you will be given a main.py file. From here you can drag files into the browser and they will be added to your project. 

<br>

---

<br>


##  Backup for Option A - Conda or Thonny

### Anaconda - If your couldn't get Python to install.

Download and Install Anaconda.

1. Visit the Anaconda Website at:  [https://www.anaconda.com/products/individual](https://www.anaconda.com/products/individual)
2. Select the download option for your operating system (Windows, macOS, or Linux). 
3. Click the `Download` button to start the download of the Anaconda installer.
4. Follow these instructions on-screen instructions: [Windows](https://docs.anaconda.com/free/anaconda/install/windows/) or [Apple](https://docs.anaconda.com/free/anaconda/install/mac-os/)

Once Anaconda (or “conda” for short) has installed follow these steps to finish setup and use anaconda: Find and launch the Anaconda Navigator application. 

Install Visual Studio Code (see above) and then ask for help.

 -->




## Install Thonny

[**Thonny**](https://thonny.org) is the name of an _Integrated Development Environment_ you can use to create Python programs on your computer. You should install Thonny on your own computer. (Mac Users: after downloading and opening the `.dmg` file. Open `readme.txt` for further instructions.)


Now we need to pick which version of Python to connect to Thonny. First, go to the section for your laptop (MAC or Windows) and then follow the instructions.


### Setting python version for Thonny in a Mac

  1. First, Open a terminal and run these commands:

  ![Setup Python in Thonny](../../../assets/images/csc110/find_python.png){:width="500px"}

  2. make a note of where python is saved on your system
  3. Now go back to Thonny
     1. Select Tools > Options > 
     2. In the window that opens, select the `Interpreter` tab, and then the three dots menu to select the python executable you found before.
     3. You should be able to see where we installed the new python3.13
        1. in my case, it's the line that reads `/usr/local/bin/python3`

     ![Setup Python in Thonny](../../../assets/images/csc110/select_python_thonny.png){:width="500px"}
  4. Select it, click OK, and restart Thonny.


### Setting python version for Thonny in Windows

  1. We need to tell Thonny to use our newest version of Python 
  2. Run, in a Command Prompt or PowerShell, the command:
  `where python`
  or inspect the Windows Registry
  3. write down the path it reports… it will be something like:
  `C:\Program Files\python313` or
  `C:\Users\<username>\AppData\Local\Programs\python\python313\`
  4. Verify that, inside that folder, you see `python.exe`
  5. Now go back to Thonny
     1. Navigate to `Run > Select interpreter`.
     2. Choose `Alternative Python 3`.
     3. Browse to the location where you installed Python 3.13 python.exe executable.


<!-- 
Here's a quick overview of how to use Thonny to program in Python. There are two distinct ways of typing in Python statements:

1. You can use the _shell_, where each line you type is
interpreted by Python as soon as you hit `return`. 
2. You can also use the _editor_, which allows you to write a
collection of statements (a program), save the collection in a file, and then
have Python execute the contents of the program. 
 -->


## Two other (online) tools: Python Tutor and Trinket

There are some free services that allow you to run Python, but you will have to create an account.

* [Trinket](https://trinket.io/) 
* [Python Anywhere](https://www.pythonanywhere.com/)
