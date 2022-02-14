title: Script to toggle Wacom Mode between Absolute/Relative
slug: script-to-toggle-wacom-mode-between-absolute-relative
lang: en
date: Mon Feb 14 05:44:42 PM -03 2022
modified: Mon Feb 14 05:44:42 PM -03 2022
tags: wacom
summary: 
status: published

Please change you device name accordingly; use the command `xsetwacom --list` to find it out.

##  `bash-zsh-wacom-toggle-mode.sh`

```
!#/usr/bin/env bash

if [[ -z `xsetwacom --get 'Wacom Intuos S Pen stylus' Mode | grep 'Absolute'` ]]; then
    xsetwacom --set 'Wacom Intuos S Pen stylus' Mode Absolute;
    echo absolute;
else
    xsetwacom --set 'Wacom Intuos S Pen stylus' Mode relative;
    echo relative;
fi
```

## one line without echoing


```
if [[ -z `xsetwacom --get 'Wacom Intuos S Pen stylus' Mode | grep 'Absolute'` ]]; then xsetwacom --set 'Wacom Intuos S Pen stylus' Mode Absolute; else xsetwacom --set 'Wacom Intuos S Pen stylus' Mode relative; fi
```
