# C++ Boilerplate (Eclipse support)
[![Build Status](https://travis-ci.org/dpiet/cpp-boilerplate.svg?branch=master)](https://travis-ci.org/dpiet/cpp-boilerplate)
[![Coverage Status](https://coveralls.io/repos/github/dpiet/cpp-boilerplate/badge.svg?branch=master)](https://coveralls.io/github/dpiet/cpp-boilerplate?branch=master)
---

## Overview

Simple starter C++ project with:

- cmake
- googletest

## Installation
Open a terminal and navigate to a directory where you want to create an Eclipse workspace in. A common place is:
```
$ mkdir ~/eclipse_workspace
$ cd ~/eclipse_workspace
```
Clone this repository (and submodules) into this directory
```
$ git clone --recursive https://github.com/patnolan33/cpp-boilerplate-eclipse.git
```

## Importing into Eclipse
This repository has a ready-made directory included for importing into Eclipse (`cpp-boilerplate-eclipse/eclipse_import`). Open Eclipse and navigate to File-->Import. Choose General-->Existing Projects into Workspace and hit "Next". Select the root directory by browsing to `cpp-boilerplate-eclipse/eclipse_import` and hitting "OK" then "Finish". You should see the project files show up in the Project Explorer window. 

NOTE: If the eclipse_import directory has to be re-built (due to CMake changes or other build configuration changes), simply run the following commands (you may have to clear the eclipse_import directory first):
```
$ cd ~/eclipse_workspace/cpp-boilerplate-eclipse/eclipse_import
$ cmake -G "Eclipse CDT4 - Unix Makefiles" -DCMAKE_BUILD_TYPE=Debug ..
```

## Build and Run with Eclipse
To build the project, expand the scratch@eclipse_import project and then expand the "Build Targets" to show the various build options available. To build the application and tests, double click on the ": all" build target. If you have the Console open, you will see the build status and eventually a "Build Finished" notification. 

Now that we've built our projects, we can run it a few ways. The first option is to use the Project Explorer window. Right-click the top-level directory (i.e. scratch@eclipse_import) and select Run As-->Local C/C++ Application, then select the application you wish to run (either cpp-test or shell-app) and hit OK. If you have the console open, you will see the application output. 

The second option for running the project is to use the Toolbar at the top of the Eclipse IDE. There is a green "Play button" on top of the IDE window with a small arrow next to it. Click the small arrow and select "Run As" and follow the same steps as before. If you have already run the project, you can skip the Run As step and select one of the Run configurations directly from that dropdown menu.

## Debugging with Eclipse
Similar to running the project, debugging can be done in many ways from the Eclipse IDE. First, just as before, we can right click on the top level project and select "Debug as", and follow the exact same steps (i.e. Debug as-->Local C/C++ Application-->shell-app or cpp-test). If prompted, switch to the Debug perspective to provide a view of pertinent debugging options (i.e. the variables breakdown, a console, and other debugging windows). 

Also similar to running the project, debugging can be done using the Toolbar. Next to the Run button (the green play button), there is a "Bug" icon. Just like the run button, you can expand a dropdown menu to select which target to debug as well as start debugging any previously run targets. 

While debugging, you can add breakpoints in the source code by double clicking the left margin of the line on which you want the application to break. If the application has broken at a breakpoint, you can use F5 to "Step Into" a function or F6 to "Step Over" a function. Also, on the Toolbar, there is a grean play button with a yellow bar next to it that will "Continue" (i.e. run the program until the next breakpoint is hit).

## CPP Check
To use cppcheck in Eclipse, you first must install the cppcheclipse plugin. Navigate to Help-->Eclipse Marketplace and search for cppcheck. The first option should be the cppcheclipse plugin. Install this plugin and wait for it to finish. Now navigate to Window-->Preferences-->C/C++-->cppcheclipse and add `/usr/bin/cppcheck` to the binary path. 

To run cppcheck, right click the desired project and run cppcheck-->Run cppcheck. For example, in the project tree if we wanted to check the source files for shell-app, we would navigate to Targets-->[exe]shell-app-->Source Files and right click the directory, then choose cppcheck-->Run cppcheck. 

## Google Style Guide 
Included in this repository is an XML file for using the Google Style Guide within Eclipse. To use it in Eclipse, navigate to Window-->Preferences-->C/C++ Code Style-->Formatter. Click "Import" and navigate to `~/eclipse_workspace/cpp-boilerplate-eclipse/` and select `eclipse-cpp-google-style.xml` and select OK. You should see "Google C++" as the Active profile now. Apply the changes and then click OK to close the window.

To use the formatter, open any file and right click, navigate to Source-->Format, which should apply the Google formatting to the open file. In addition, you can press Ctrl+Shift+F when in an open file to compelte the same action. 
