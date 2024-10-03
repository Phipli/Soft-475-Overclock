# Soft-475-Overclock
If you wish to compile this project on the classic Mac OS, you can use either the .hqx or MacBinary versions. Github modifies files by changing newlines to a different format, and also these files have resource forks, so they had to be protected by wrapping as hqx or .bin will. I'm not sure what the best way of managing this is, so I've done multiple things to ensure that while messy, the data is preserved.

I may be wrong, but I believe that the overclock is done in one of two ways - either by setting the DJMEMCjr pins as outputs and driving the clock speed pins on the clock generator, overriding the pull-up / pull-down resistors (as fitted), or, the advanced mode (offering greater granularity), serially shifts parameters into the clock generator. The first method only allows 20, 25, 33 or 40MHz.

This Extension / Control Panel pair allows you to overclock the LC 475 and similar machines in software. It builds on the work of Mustermann, zigzagjoe and cheesestraws from the 68kmla forums. With input from Arbee, Mr.Fahrenheit and Bolle.

I have made a version of zigzagjoe's extension that...
- Loads an icon at boot, using cheesestraws Force32 as a code example.
- Is able to switch between a number of pre-selected speeds based on the contents of the "SPD!" resource.
- Ensures that the computer is in 32bit addressing mode (and doesn't run if it isn't).

I have also written a little program (it isn't a true Control Panel, but imagine it is) that gives a user interface to easily select from a few speeds, namely 0 (off - the extension disables itself), 20, 25, 33 and 40MHz. It additionally allows you to enter a target speed and automagically calculates the parameters needed, or lets you manually enter your own set of parameters.

Note that all of this is very much at your own risk, as even correct operation of the software can cause your computer to crash.

If your computer can't handle the speed you set, or otherwies crashes due to this software, power cycle the computer and hold the shift key prior to the happy mac during boot. This will prevent the extension from loading and effectively return your machine to "stock" assuming you don't already have a hardware overclock implemented. You'll then be able to either replace it with a clean copy, or use the application to set a lower speed.

The following machines should be compatible...
- LC 475 / Performa 475 / Performa 476.
- Quadra 605.
- LC / Performa 575 / 577  / 578.
- Apple STB.
- Hardware overclocked versions of the LC 475, Quadra 605, LC 575 and variants.
- PowerPC upgraded versions of the LC 475, Quadra 605, LC 575 and variants.

Note - at higher speeds you may find you get disk access related crashes. This may be possible to fix by moving the resistor R96 to position R95 (near the fan header). This divides the clock to the SCSI chip by two, and puts the SCSI chip back in spec for 33MHz and higher speeds. This configuration matches what was shipped on similar 33MHz machines such as the LC 630.

This software has not been extensively tested, and comes with no warranty, implied or otherwise. USE AT YOUR OWN RISK.

Finding some help - Note that I have created some Balloon Help bubbles for the main screen in the program. Enable Balloon Help in the help menu to see some additional guidance on these functions.

Summary of extension startup icon meanings.

- Plain jigsaw with red cross - This computer is not supported.
- Jigsaw with blue number - The current speed setting for common overclocks.
- Jigsaw with "475 Pro" - The extension has been set to a speed using one of the advanced modes.
- Jigsaw with red "Off" - The extension is installed, but has been disabled. Use the Control Panel to enable it.
- Jigsaw with red "Err" - The extension has tried to load malformed or missing settings.
- Jigsaw with red "24b" - The computer is currently in 24b bit mode and so the extension has disabled itself. Use the Memory Control Panel to switch to 32 bit mode.

Note the error checking is unlikely to be fully comprehensive, and the software does allow you to effectively shoot yourself in the foot, so to speak. For example, you could enter parameters for 0.5MHz, which would likely result in your computer crashing. Almost all situations are recoverable by booting with the shift key depressed to disable Extensions temporarily.

Current version 0.5.1
Phipli - 2024
http://stuffandnonsense.elephantandchicken.co.uk

