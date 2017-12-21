What this? ~~Probably~~ unstable!
=================================

This is an alternative to an alternative of _xinput_calibrator_ called _xcal_.

xcal:
[github](https://github.com/reinderien/xcal)

xinput_calibrator:
[github](https://github.com/tias/xinput_calibrator),
[FreeDesktop](https://www.freedesktop.org/wiki/Software/xinput_calibrator/),
[Ubuntu](https://packages.ubuntu.com/zesty/xinput-calibrator), etc.).

Why was this forked from master?:

I forked it for a very very specific use, to remove text input requirements from the calibration process for the KeDei touchscreen i have for my raspberry pi.


Why would you want to remove text input requirements?:

Because now I can calibrate without having a keyboard attached, easier for non permanent setups and debugging.


Which speciffic touchscreen is this calibrated for?:

This was adapted for the KeDei Raspberry pi Display 3.5 inch HDMILCD 18bit version 1.1 2017/9/9 with a resolution of 480 by 320. It will probably work with other resolutions too but not sure. The touchscreen chipset i tested this on is the XPT2046


Whats different from the master?:

The original xcal is designed for versitility(i assume), this one is adapted for the slightly braindead like me trying to calibrate this specific touchscreen with ease. The biggest difference between master and this is that the master was written by someone who knew what they where doing, this fork was not.


Everything below this is untouched from master, it may or may not be correct so pull conclusions at own caution.
================================================================================================================


Similarities:
- For Unix-like OS
- Calibrates touchscreens

Differences:

|Thing           |xinput_calibrator                |xcal                           |
|----------------|---------------------------------|-------------------------------|
| Language       |C++                              |Python3                        |
| LOC            |2,289                            |284                            |
| Interface      |Command-line args with some GUI  |Walkthrough-based with some GUI|
| GUI toolkit    |X                                |tk                             |
| Cal points     |4                                |Selectable                     |
| Math           |Manual                           |Numpy least-squares            |
| Outputs        |Xorg.conf, hal, xinput           |xinput                         |
| Popularity     |High                             |Zero so far                    |
| Tested         |Pretty well                      |Not very well                  |
| OS distribution|Available in most major repos    |Zero so far                    |
| Dependencies   |libstdc++, libx11, libxi         |python3, tkinter, numpy        |

_xinput_calibrator_ features precalibration, timeouts, misclick detection, fake driver testing, and
a resizable window.
_xcal_ features none of those things, but offers some other features not present in
_xinput_calibrator_, including pre-save cal test, cal quality indicator, arbitrary cal point count,
and a slightly more informative GUI. Also, the source is quite simpler.

Why this?
=========

After I couldn't figure out why _xinput_calibrator_ wasn't doing anything on my system (an old CF-29),
I read and followed
[this excellent walkthrough](https://wiki.archlinux.org/index.php/Talk:Calibrating_Touchscreen#Libinput_breaks_xinput_calibrator)
on the Arch wiki. It was too hacky for my comfort, so I wrote this tool inspired by Zootboy's
procedure but with some key differences - this is a stand-alone tool that does not require running
_xinput_calibrator_; and it uses Numpy to do some real matrix math instead of hacking around with
element-by-element calculations and a fixed calibration dataset size.

How this?
=========

    ./xcal

To do
=====

- ?

Discuss
=======

[![Join the chat at https://gitter.im/reinderien_xcal/Lobby](https://badges.gitter.im/reinderien_xcal/Lobby.svg)](https://gitter.im/reinderien_xcal/Lobby?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
