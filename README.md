# Pico 4WD Car

This car is based around a Raspberry Pi Pico (Pico) board.
See <https://www.amazon.co.uk/SunFounder-Raspberry-MicroPython-Control-Electronic/dp/B09FXM5QW6>

This car was used as an example of a simple vehicle that can be used as a test vehicle for various experiments in pipes.

This readme contains info about programming the Pico board.

## Thonny

Thonny is used as the editor and for transferring files to and from the
RPi Pico.  The Thonny editor needs to be the latest version to work with the Pico board.

### Windows

The SunFound instructions are here <https://docs.sunfounder.com/projects/pico-4wd/en/latest/get_started/install_thonny.html> and explain the Windows installation very well.  It boils down to:

1. Go to: <https://thonny.org/>.
2. Click on the Windows download link and install.  This installs the latest
    version of Thonny so should work right out of the box.

### Ubuntu

A great place to start is: <https://thonny.org/>  We need to make sure it
works on any distro, so use this one liner to get and install the latest
version:

```bash
bash <(curl -s https://thonny.org/installer-for-linux)
```

To start Thonny, use this command:

```bash
~/apps/thonny/bin/thonny
```

NOTE: The normal `sudo apt install thonny` installs the version that is
shipped with your distro and not the latest version.  I tried the
following:

* Ubuntu 16.04 doesn't have Thonny at all and is missing Python 3.
* Ubuntu 20.04 has a version that predates the Pico board, so is useless.

Hence the instructions to install the latest from a script.

## Setting up the Pico

The starting place was the SunFounder instructions:
<https://docs.sunfounder.com/projects/pico-4wd/en/latest/get_started/install_micropython_to_pico.html>
This is way too complicated and we could not get it to work.  So we followed
the official RPi instructions that boil down to download MicroPython and copy
it on to the Pico.

### Windows

1. Download MicroPython software from MicroPython.org.
<https://micropython.org/download/rp2-pico/rp2-pico-latest.uf2>
2. Press and hold down the `BOOTSEL` switch on the Pico and plug the USB lead
    from the Pico into your laptop (two people make this easy!)  The Pico should appear as a new drive.
3. Copy the `.uf2` file from the Downloads directory on your PC to the Pico using Windows Explorer (file manager).

### Ubuntu

1. Download MicroPython software from MicroPython.org.
<https://micropython.org/download/rp2-pico/rp2-pico-latest.uf2>
2. Press and hold down the `BOOTSEL` switch on the Pico and plug the USB lead
    from the Pico into your laptop (two people make this easy!)  The Pico should appear as a new drive.
3. Mount the drive by clicking on the notification popup.
4. Copy the `.uf2` file from the Downloads directory on to the Pico using the file manager or command line.
5. Reboot the Pico by pressing and releasing the `BOOTSEL` switch.
6. Verify that the device `/dev/ttyACM0` appears.
7. Verify that you can communicate with the Pico connecting a serial terminal
    program, e.g. `cutecom`, to `/dev/ttyACM0` and typing some Python
    instructions.

### Verify connection to Thonny

Verify that you can connect to the Pico using Thonny as follows

1. Select the option "Run -> Select Interpreter...".
2. In the dialog box, select the "Interpreter" tab.
3. Then select the interpreter "MicroPython (Raspberry Pi Pico)".  The
     "Port" option should automatically be filled out if a Pico is attached.
4. Press the "OK" button.

## Upload libraries

The SunFounder instructions
<https://docs.sunfounder.com/projects/pico-4wd/en/latest/get_started/upload_libraries.html>
for this bit are pretty good but are out of date with Thonny.

1. Download the SunFounder files from here
<https://github.com/sunfounder/pico_4wd_car/archive/refs/heads/main.zip>
2. Copy the zip file to a new directory (I used `C:\pico4wdcar` on Windows and
    `~/pico4wdcar` on Ubuntu) and unzip the files.  A new directory should be
    created called `pico_4wd_car-main`.  This directory contains libraries
    needed to control the car and many tests and example programs.
3. In Thonny, open the files view, View -> Files.  Select the directory
    `pico_4wd_car-main/libs` in the `This computer` window.
4. Upload the files

    * `pico_4wd.py`
    * `pico_rdp.py`
    * `ws.py`

   by selecting each file in turn, right button clicking, selecting
   `Upload to /` and wait until the file has been uploaded.

## Run some tests

This section of the documentation works pretty well.
<https://docs.sunfounder.com/projects/pico-4wd/en/latest/get_started/test_the_modules.html>

Essentially, it says:

1. Open one of the examples or test files in Thonny.
2. Press the "Run" icon (green icon with white arrow).
3. The script should run.
4. Press the "Stop" icon when you want to do something else.

## Acknowledgements

This work is supported by the UK's Engineering and Physical Sciences Research Council (EPSRC) Programme Grant EP/S016813/1

© 2022, University of Leeds.

The author, A. Blight, has asserted their moral rights.
