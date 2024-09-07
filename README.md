# Armbian BootSplash Creator

This simple script with bootsplash repacker are to assist users trying to replace their stock boot splash logos.

## Dependencies

You will need an x86-64 computer running Linux.
Dependencies are: ImageMagick

Be sure to install the dependencies with the package manager of your linux distribution.

## Instructions

First of all please take a moment and be sure to take a backup of your original bootsplash logo. This file is located at /usr/lib/firmware/bootsplash.armbian

Now you can place your image into this folder as logo.png (If your image is not png format please convert it)
and you will now be able to launch the script called create-bootsplash.sh (You may need to give it executable permissions by typing chmod +x create-bootsplash.sh ).

The script will run and will also give you nearly the same instructions as you have here. If all went correctly you will find a new file called bootsplash.armbian in this folder.

Now onto the slightly harder part. Getting this file onto your device to the correct folder.
Please copy this file over to your device by your method of choice. SSH works rather well for this but just simple USB drive containing the file will work as well :)

Now that the file is on the device you need to move it to its final destination. You will need superuser permissions to do this (sudo).

sudo cp <your-path-to-the-copied-file> /usr/lib/firmware/bootsplash.armbian

This will move your new logo to the correct destination.

That is the "hard" part over :)

Now please just update your initramfs so the file is used on bootup. You can do this by entering this command: update-initramfs -v -u

Now just reboot your device and you will see your new logo on boot :)
