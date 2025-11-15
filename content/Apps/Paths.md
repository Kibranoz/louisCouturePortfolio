+++
title = "Paths"
description = "The path Application"
date = "2025-11-14"
aliases = ["paths"]
author = "Louis Couture"
+++

This application allows you to add paths to your PATH variable in a graphical user interface. You can also set alias and where those scripts are. 

![Path setup app screenshot](/images/paths/path.png)
![Path setup app alias screenshot](/images/paths/alias.png)

## FAQ 

### How does the app works?
This app use fedora's .bashrc.d folder, so it doesn't mess with your .bashrc file. If you are on another linux distro, it will create a .bashrc.d folder and add the following code to your .bashrc file
```
if [ -d ~/.bashrc.d ]; then
    for rc in ~/.bashrc.d/*; do
        if [ -f "$rc" ]; then
            . "$rc"
        fi
    done
fi
unset rc
```
This script loops through all the files in the .bashrc.d folder and sources them, making sure that the paths and aliases are available in your bash session.
### Why this app ?
While it is possible to manage your path from the file, some users are less familiar with code like syntax for path and alias management. Some also may find it quicker to open a gui to add their paths rather than add them through .bashrc

This was made as an attempt to make the family of operating system using tools such as the Linux kernel and the GNU library (Commonly refered to as Linux or LiGNUx) to be more user-friendly

### I opened the app and my paths were not added 
This is not something that is supported. It only manages the paths and alias that were set up in the app.
