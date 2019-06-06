### Lab-on-an-SSD ###

The Lab-on-an-SSD is a bootable, USB3 or USB-C drive, which contains:
- A Linux installation (Ubuntu 18.04)
- The nanopore software used to run MinION and Flongle (MinKNOW, Guppy)
- Bioinformatics analysis software used on this course (e.g. minimap2, Tablet, IQTree, etc.)

The Lab-on-an-SSD should work with most modern laptops (including MacBooks), but the following specifications are recommended:
- Intel i5 processor or Intel i7 processor (two or more cores)
- 8 gigabytes of RAM or more
- USB3 port (or USB-C)

To perform nanopore basecalling in real-time (not required for this course) laptops require a NVIDIA CUDA-compatible GPU. Modern GPUs will be labeled 1050, 1060, 1070 etc., or 1050 Ti, 1060 Ti, 1070Ti etc. Note that modern MacBooks do not have NVidia GPUs.

Your laptop may not be compatible in certain circumstances, most commonly:
If your laptop has certain BIOS settings, e.g. Secure Boot Mode, which cannot be disabled via the BIOS boot menu (ask your IT department for help, if this is the case)

### Booting the Lab-on-an-SSD ###

1. Shut down your computer (perform complete shutdown, not just suspend)
2. Insert the SSD into a free USB3 port (USB-C may work on some laptops)
3. Start up your computer
4. Access your BIOS boot menu by holding down the boot menu key: the boot menu key is different on different makes of laptop. Common keys are:
   - F12 - Dell
   - Option/Alt - Mac
   - F1 and F7 are also commonly used.
   Refer to your laptop manual or look for hints during the BIOS bootup screen.
5. When the boot-up menu appears, select the USB drive. It may be labelled “USB storage device” or “USB legacy boot”.
6. If booting was successful you will see the ARTIC network desktop. If booting was not successful, power off your laptop and try again.

### Getting started ###


You may want to configure a few things to your liking, via the system settings:
- Date/time and timezone
- Keyboard layout
- Mouse/trackpad sensitivity
- Power settings

### Managing your lab-on-an-SSD ###

**IMPORTANT: Do not disconnect your USB drive during operation, as this may lead to lost work, or even disk corruption.** You might want to use a sticky mat to help secure the disk to the table or even the back of your laptop screen.

### Shutting down ###

It is best to shut down your system each time after using it, using the “Power Off” option. Some laptops don’t support suspend when the SSD is plugged in.

The password, if you are logged-out, is "artic".

### Making your own lab-on-an-SSD at home ###

You will need an external SSD drive, ideally with 256GB or higher (120GB minimum). USB sticks can be used but they are often much slower and less reliable so not recommended for long-term use.

Download the latest lab-on-an-SSD image from here:
[SSD images](https://artic.climb.ac.uk/)
Write the image to your SSD using software such as:
- [Etcher](https://etcher.io/)
- [Rufus](https://rufus.akeo.ie/)
- dd (Linux)
