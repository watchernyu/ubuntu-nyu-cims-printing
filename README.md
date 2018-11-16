# ubuntu-nyu-cims-printing
A short guide on how to setup NYU CIMS printing on Ubuntu. Should work for Ubuntu 18 and 16.

## Install packages (Problems with Ubuntu 18)
You are likely run into wierd problems if you use Ubuntu 18, it seems that some packages are not installed by default, or repository not available by default on Ubuntu 18. So first you need to install some packages. (You might not need to do this if you use Ubuntu 16)

Install smb related packages. I think these are packages related to the printers. 

sudo apt-get install python3-smbc
sudo apt-get install smbclient

## Set up printer
Now open the printers window on your Ubuntu.
Scroll down until you see "Additional Printer Settings", click it, and then click "Add" button to add a new printer. 

Click on "Network Printer" to unfold it, and then click "Windows Printer via SAMBA". (You might be asking, why windows printer? Shouldn't it be linux? I think this is because the printers are using sth related to Windows, I have figured this out from reading a bunch of NYU official printer help page. And of course they don't currently have good linux support page on printing.)

Now you need to give the correct smb:// link so that it knows which printer are you using. Check out Courant's printer guide to figure out which printer you want to use. For instance, smb://printserver.cims.nyu.edu/bwpr66

reference: https://cims.nyu.edu/webapps/content/systems/resources/printing/publicprinting, https://cims.nyu.edu/webapps/content/systems/resources/printing/locations

Now choose "Set authentication details below" option and enter your cims account and password (not your nyu home ones).
If it doesn't verify don't worry, might still work, just click forward. If you haven't installed packages, you might get ubuntu prompt saying some package not found (with name of packages), then you should go and first install those packages. If you are missing other packages then the 2 mentioned here, try google them and install them.  

Choose Driver part: Choose "select printer from database", for Makes, select "Generic", click forward.

Then if asks you to choose model for driver, choose "PostScript" on the left panel, and "Generic PostScript Printer Foomatic/PostScript [en] (recommended)". Click forward.

Pick names and optional description, you should be all set. You can now print from anywhere on NYU campus to that printer.

Note that if you want to print from outside NYU on that printer, you need to first connect to NYU VPN. I also have a short guide on that.

Note I'm not a printer expert, if you figured out a better way to do this please open an issue thank you!
