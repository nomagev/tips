# Windows 10 Tricks

The following are a set of practical tips to use on Windows 10.

**IMPORTANT:** I am doing this repository of things for myself. If you plan to use some of it, make sure you know what you are doing and, to be clear, you will be doing so under your own discretion.

The idea is to compile all useful things I do on Windows 10 not to forget about them.

## Tip 1 - Windows 10 "God Mode"
#### Note: it also works on Windows 7

There is a way to trigger Windows 10 "God Mode", a menu, "Control Panel"-like, where you will have all available options to use on Windows, Operating System wise.

To do so:

1. Create a new, empty folder in the Desktop.
2. Rename folder name to: `GodMode.{ED7BA470-8E54-465E-825C-99712043E01C}`
3. Enjoy it and be careful.

## Tip 2 - Equivalent of UNIX's `cd ~` in Windows Command Promt
#### Note: it also works on Windows 7

There is a way to quickly switch from anywhere in Windows Command Prompt Path into the User Home.

This is the equivalent of UNIX's `cd ~`

To do so:

1. Just type on your Windows Command prompt `cd %USERPROFILE%`

### Tip 3 - Set default path on Windows Command Prompt to %USERPROFILE%
#### Note: it also works on Windows 7

Every time you execute CMD.exe, default prompt (the first directory you fall / start in) is `c:\windows\win32`

There's a way to change this behavior, so your default starting path is c:Users/YourUsername

To do so:

1. Open Windows Registry Editor (Press `Windows Key`, type `regedit` and press `enter`).
2. Follow the following path in regedit:
  * HKEY_LOCAL_MACHINE
  * Software
  * Microsoft
  * Command Processor
3. Once in "Command Processor", create a new registry key (Select `Expandable String Value`)
4. Call it `AutoRun`
5. Enter `cd /d %USERPROFILE%` command as value into it.
6. Close regedit and test it by opening Windows Command Prompt (Press `Windows Key`, type `cmd` and press `enter`).

### Tip 4 - Use "Someonewhocares.org" host file as a manual firewall
#### Note: it also works on Windows 8 and previous (although with slightly different paths to find Windows's host file).

Every time you ran a website, it may contain calls to "SPAM-like" sites, or just advertising networks or similar. Not only they consume bandwith, but they also could bring malicious or just tracking code within.

Also, Windows 10 now includes some calls to Microsoft Servers to compile telemetry information about your computer and your usage.

Wouldn't it be great if you could stop that?

There is an old-fashion, and yet very effective way to avoid that, by using a manual firewall using Dan Pollock's [someonewhocares.org](http://someonewhocares.org) host file.

**Please note:** Using Dan's host file does substitute the use and/or need of antivirus software or similare protective technologies. Also, using this method, you will remove all customizations into your Windows host file.

To do so:

1. Go to [someonewhocares.org/hosts](http://someonewhocares.org/hosts).
2. Select "txt file" on the right-side menu (or simply download the file).
3. Open downloaded file (it may @ `%USERPROFILE%/Downloads` under hosts.txt name).
  - Select All content within the file (CONTROL + A)
  - Copy the content of if (CONTROL + C).
  - Close the file.
4. On Windows 10, go to  `C:\Windows\System32\drivers\etc\hosts`
5. Find `Notepad` Application on the Windows Menu and, to open it, right-click on it and and select `Run as Administrator`
  - Select All content within the file (CONTROL + A)
  - Past the content of the original downloaded file (CONTROL + V).
  - Close the file and Save Changes.
