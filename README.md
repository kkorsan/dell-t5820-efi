# Dell 5820 Tower Workstation Opencore EFI

The usage is pretty simple, put the folders inside of an USB
and download the MacOS Ventura Recovery image with macrecovery

(Warning: the above EFI files are meant to be used with Ventura,
Sonoma (23.0.0+) and above gets stuck at the Apple logo, the ideal
solution to use Sonoma or Sequoia is to update after installing Ventura
unless a fix is released.)

# Usage and Sidenotes

The one thing that you may have realized while
using the workstation, is that the bios is OEM locked
the solution while may seem easy, it is much harder in
practice, you have to take a small jumper located under
the GPU units called PSWD, take that out, boot your device
(Optionally let it reboot a several times) and put the jumper back
in, you might have to use tweezers or take out the GPUs as the
space below is very tight.

Another thing you should do is that, if you are using the
Dual Quadro P400 model, you should not try to use the online installer
(as it gets stuck), I did include the horndis.kext in there, but
trying to use the online installer fails from what I understand,
instead create an offline installer using UnPlugged (https://github.com/corpnewt/UnPlugged)

Also create a few backup folders (efi_backup, recovery_backup, macos_backup)
because in my case, I was using a cheap 64 gigabyte usb drive and the drive 
suddenly corrupted and became unreadable/unwriteable, also the offline installer takes a bunch
of space so my recommendation is to use atleast a 32 gb usb.

(Warning: Allocation Unit Size Value should be less than 1024kb for the offline installer partition as 
MacOS struggles to recognize anything greater than that)

The last thing I wanna say that, while dual booting on the same drive is fine (which is what I did)
I suggest to use a secondary drive as I consider it a better practice.

# BIOS Settings

-
 \ System Configuration /
 
-- Decoding Above 4G for I/O [Enabled]

-- SATA Operations [AHCI]

 \ Virtualization Support /
 
-- Intel Virtualization Technology [Disabled]
