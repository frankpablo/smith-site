---
layout: default
title: Install-VSCode
parent: CSC110
grand_parent: Teaching
nav_order: 7
#permalink: /docs/teaching/csc110/
---  

# Installing a Development Environment

In order to write Python programs and execute (or run) them, you need to have a editor (to write) and an interpreter (to run) the program. Depending on your individual setup, you will take a different approach.

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

### 3. Instal Python

1. Open Visual Studio Code (VS Code).
2. Click the `Explore` Icon (the top icon in left toolbar, overlapping pieces of paper).
3. Click `Open Folder`, then select the folder where you saved `first.py` in Step 0.
4. Click on first.py. Add a comment with your name at the top. A comment starts with the `#` symbol. For example:
```
# This is a python comment.
```
5. When you open `first.py`, you should receive a notification in the bottom right corner, asking if you want to install Python. You should click to install Python. _If this notification doesn't show up, you can either [install it via this link](https://marketplace.visualstudio.com/items?itemName=ms-python.python) OR click the `Extensions` (bottom "stacking blocks" icon in the left toolbar), then search Python and select the "Python IntelliSense (Pylance)..." item by Microsoft._
6. After the installation has complete, go back to the `first.py` file in VS Code and click the `Run Python File` button (triangle play button on the top toolbar). Your code should run and the `Terminal` window should appear at the bottom. You should see `Hello World` and should look something like this:
```
F-CSC:CSC110-S24 amgrubb$ first.py
Hello World
F-CSC:CSC110-S24 amgrubb$ 
```
7. Change "Hello World" to your own message and run it.
8. Proceed to [lab0 on Moodle](https://moodle.smith.edu/mod/assign/view.php?id=1146269).

_If you have trouble with any of these steps, see Backup for Option A (below)._

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

### Thonny - If you couldn't get VS Code to install.

[**Thonny**](https://thonny.org) is the name of an _Integrated Development Environment_ you can use to create Python programs on your computer. You should install Thonny on your own computer. (Mac Users: after downloading and opening the `.dmg` file. Open `readme.txt` for further instructions.)

Here's a quick overview of how to use Thonny to program in Python. There are two distinct ways of typing in Python statements:

1. You can use the _shell_, where each line you type is
interpreted by Python as soon as you hit `return`. 
2. You can also use the _editor_, which allows you to write a
collection of statements (a program), save the collection in a file, and then
have Python execute the contents of the program. 

## Backup for Option B - Python Tutor

There are some free services that allow you to run Python, but you will have to create an account.

* [Trinket](https://trinket.io/) 
* [Python Anywhere](https://www.pythonanywhere.com/)
