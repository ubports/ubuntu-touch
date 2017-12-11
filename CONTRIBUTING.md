This page contains information to help you help us reporting an actionable bug for Ubuntu Touch. It does NOT contain information on reporting bugs in apps, most of the time their entry in the OpenStore will specify where and how to do that.

## Make sure you're on the latest version of the OS

This might seem obvious, but it's easy to miss. Go to (Settings - Updates) and make sure that your device doesn't have any Ubuntu updates. If not, continue through this guide.  If so, update your device and try to reproduce the bug. If it still occurs, continue through this guide. If not, do a little dance! The bug has already been fixed and you can continue using Ubuntu Touch.

## Check if the bug report already exists

Open up the bug tracker for [ubuntu-touch](https://github.com/ubports/ubuntu-touch).

First, you'll need to make sure that the bug you're trying to report hasn't been reported before. Search through the bugs reported. When searching, use a few words that describe what you're seeing. For example, "Lock screen transparent" or "Lock screen shows activities".

If you find that a bug report already exists, select the "Add your Reaction" button (it looks like a smiley face) and select the +1 (thumbs up) reaction. This shows that you are also experiencing the bug.

If the report is missing any of the information specified later in this document, please add it yourself to help the developers fix the bug.

## Reproduce the issue you've found

Next, find out exactly how to recreate the bug that you've found. Document the exact steps that you took to find the problem in detail. Then, reboot your phone and perform those steps again. If the problem still occurs, continue on to the next step. [If not...](https://youtu.be/nn2FB1P_Mn8?t=10s)

## Getting Logs

We appreciate as many good logs as we can get when you report a bug. In general, `/var/log/dmesg` and the output of `/android/system/bin/logcat` are helpful when resolving an issue. I'll show you how to get these logs. 

To get set up, follow these steps:

1. Reboot your device
1. Place your device into developer mode (Settings - About - Developer Mode - check the box to turn it on)
 1. When you're done getting logs from your device, it's a good idea to turn Developer Mode off again.
1. Plug the device into a computer with `adb` installed
1. Open a terminal and run `adb devices`. 

If there's a device in the list here (The command doesn't print "List of devices attached" and a blank line), continue on. If there is not, try following these steps again then contact us at one of our support channels.

Now, you can get the two most important logs.

### dmesg

1. Using the steps you documented earlier, reproduce the issue you're reporting
1. `cd` to a folder where you're able to write the log
1. Delete the file `UTdmesg.log` if it exists
1. Run the command: `adb shell "dmesg" > "UTdmesg.txt"`

This log should now be located at `UTdmesg.txt` under your working directory, ready for uploading later.

### logcat

1. Using the steps you documented earlier, reproduce the issue you're reporting
1. `cd` to a folder where you're able to write the log
1. Delete the file `UTlogcat.log` if it exists
1. Run the command: `adb shell "/android/system/bin/logcat -d" > "UTlogcat.txt"`

This log will be located at `UTlogcat.txt` in your current working directory, so you'll be able to upload it later.

## Making the bug report

Now it's time for what you've been waiting for, the bug report itself!

First, pull up the bug tracker and click "New Issue". Log in to GitHub if you haven't yet.

Next, you'll need to name your bug. Pick a name that says what's happening, but don't be too wordy. Four to eight words should be enough.

Now, write your bug report. A good bug report includes the following:

* **What happened**: A synopsis of the erroneous behavior
* **What I expected to happen**: A synopsis of what should have happened, if there wasn't an error
* **Steps to reproduce**: You wrote these down earlier, right?
* **Logs**: Attach your logs by clicking and dragging them into your GitHub issue.
* **Software Version**: Go to (Settings - About) and list what appears on the "OS" line of this screen. Also include the release channel that you used when you installed Ubuntu on this phone.

Once you're finished with that, post the bug. You'll get the option to add tags, so add the tag for the device you're experiencing the issue on.

A developer or triager will confirm and triage your bug, then work can begin on it. If you are missing any information, you will be asked for it, so make sure to check in often!
