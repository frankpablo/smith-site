---
layout: default
#title: Anaconda-and-Spyder
parent: CSC110
grand_parent: Teaching
#nav_order: 7
published: false
#permalink: /docs/teaching/csc110/
---  

# Install Anaconda


Anaconda is a popular distribution of Python and R programming languages for data science, machine learning, and scientific computing. Here are step-by-step instructions for downloading, installing, and doing basic setup for Anaconda:

**<span style="text-decoration:underline;">Download and Install Anaconda</span>**



1. Visit the Anaconda Website at:  [https://www.anaconda.com/products/individual](https://www.anaconda.com/products/individual)
2. Select the download option for your operating system (Windows, macOS, or Linux). 
3. Click the "Download" button to start the download of the Anaconda installer.
4. Follow these instructions on-screen instructions:
    1. Windows: [https://docs.anaconda.com/free/anaconda/install/windows/](https://docs.anaconda.com/free/anaconda/install/windows/) 
    2. macOS: [https://docs.anaconda.com/free/anaconda/install/mac-os/](https://docs.anaconda.com/free/anaconda/install/mac-os/) 

**<span style="text-decoration:underline;">Initial Setup Instructions</span>**

Once Anaconda (or “conda” for short) has installed follow these steps to finish setup and use anaconda:

  <span style="text-decoration:underline;">OPTION A: Anaconda Navigator (GUI) - **Recommended**</span>

* Find and launch the Anaconda Navigator application. 
* An update for Anaconda Navigator may be available. _<span style="text-decoration:underline;">Say Yes!</span>_ 
* Follow the on-screen instructions.
* Relaunch Anaconda Navigator and get busy… 
* Review the [Navigator User Guide](https://docs.anaconda.com/free/navigator/) to familiarize yourself with the software.


# Our fist program with Spyder

* [Hello World with Spyder](https://docs.anaconda.com/free/anaconda/getting-started/hello-world/)


# Additional Resouces


  Next, consult the [Getting Started with Conda User Guide](https://conda.io/projects/conda/en/latest/user-guide/getting-started.html) for more information on creating and using environments, and installing packages, etc… 


 \
**<span style="text-decoration:underline;">Anaconda Documentation</span>** \
Conda is a powerful package manager, and you can explore more advanced options and features based on your specific needs. See these Helpful Resources:



* [Getting started with Anaconda](https://docs.anaconda.com/free/anaconda/getting-started/)
* [Anaconda Cheat Sheet](https://docs.conda.io/projects/conda/en/4.6.0/_downloads/52a95608c49671267e40c689e0bc00ca/conda-cheatsheet.pdf)
* [Conda Commands Documentation](https://docs.conda.io/projects/conda/en/latest/commands/index.html)



  <span style="text-decoration:underline;">Installation OPTION B: Command Line Interface (CLI)</span>

  If you prefer to work on the command line, open a command prompt (Windows) or the Terminal.app (macOS) and run the following:  (diffs between Mac/Win?)

* Activate conda: **source /Applications/anaconda3/bin/activate**
* Initialize conda: **conda init zsh** (mac only)
* Check conda is in PATH (optional):** echo $PATH**
* Update conda: **conda update conda**
