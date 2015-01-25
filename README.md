jsms
====

Simple command-line script to send SMS messages via a Jolla phone.

Yes, *j* stands for Jolla phone.

The script runs in a Linux terminal window (for example: Ubuntu Gnome-Terminal)
and sends *ssh* commands to Jolla phone on the same LAN.

How:
- ubuntuprompt$ *jsms lauriston Russia has no good generals. The only exception is Bagration.*

Why:
- I spend a lot of time working in a Linux terminal window

Requirements:
- a Jolla phone connected to your LAN using a fixed IP address
- the phone has to be in "developer mode" with *ssh* enabled and *authorized_keys*
- a Linux box with at least *Ruby 1.9* installed

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
