jsms
====

Simple command-line script to send SMS messages via *ssh* commands to a SailfishOS phone.

The script runs in a Linux terminal window (for example: Ubuntu Gnome-Terminal)
and sends *ssh* commands to Jolla phone on the same LAN.

How:
- ubuntuprompt$ *jsms lauriston Russia has no good generals. The only exception is Bagration.*

Why:
- I spend a lot of time working in a Linux terminal window

Requirements:
- a SailfishOS/SailfishX phone connected to your LAN or WiFi, having a known IP address
- the phone has to be in "developer mode" with *ssh* enabled and *authorized_keys*
- a Linux box with at least *Ruby 1.9* installed

Note: if you don't get UTF-8 characters correctly shown in the text messaging app,
then you need to specify language support in */home/nemo/.bashrc* for example adding
these three lines to it:

    export LC_ALL=en_US.UTF-8
    export LANG=en_US.UTF-8
    export LANGUAGE=en_US.UTF-8

Configuration:
- edit *jsms* script to verify/change the default options
- create *$HOME/.jsms-contacts* with your *name,phone* aliases

Usage:
- accepts either a phone number or an alias

What happens:
- sanitizes the single- and double-quotes
- executes the *ssh* call to ask the Sailfish OS *dbus* to send an SMS
- executes the *ssh* call to get the "group" of the phone stored SMS conversation
- executes the *ssh* call to update the relevant conversation

Still missing:
- does not check for text length (thus it cannot tell you if the message requires more than one SMS)

Similar projects:
- https://github.com/messaggiero/jollaSms
