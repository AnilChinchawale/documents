# Atheios Mining Guide

## Prerequisites:

* [Claymore's Dual Ethereum AMD+NVIDIA GPU Miner v11.9 (Windows/Linux)](https://bitcointalk.org/index.php?topic=1433925.0)

* AMD or Nvidia compatible video card with at least 2GB memory

* Atheios Wallet | [Web](https://wallet.atheios.com/) or [Desktop](https://atheios.com)


## Set Virtual Paging File:

In this guide I will assume we’re running Windows 10 (although the process is very similar in later versions of Windows). We first need to click on the start menu then right click on “This PC” and select “Properties”. Our next step is to click on “Advanced System Settings” in the new window.

In the system properties window that comes up we’ll click on the “Settings” button listed under the section labeled Performance. From here we’ll click on the “Advanced” Tab which will display a couple of options. We want to click on the “Change” button listed in the Virtual Memory section of this screen.

Claymore recommends a 16 gigabyte page file when using his miner so we want our Virtual Page File to be at least 16 Gigabytes. On the new screen we’ll select the “Custom size” radio button and input in the “Initial size (MB): area the following number: 16384. You can enter a number higher than our minimum in the “Maximum size (MB)” box or input 16384 again.

Once we’ve completed that we’ll click the “Set” button and we can click “OK” on the remaining open boxes.

## Atheios Wallet and/or Address Creation:

Before we move any further we need a place to store our Atheios. We can achieve this via the [Atheios web wallet](https://wallet.atheios.com/) or by downloading the [Atheios Desktop Wallet](https://atheios.com).

#### Creating a Wallet with the Web Wallet:

Visit the [Atheios Web Wallet here](https://wallet.atheios.com/). Always verify that you are on “wallet.atheios.com” to ensure you are not submitting your private key and keystore to someone attempting to steal your wallet.

On this page, we’ll be presented with the option to create a new wallet. Type in your desired password then click the “Create New Wallet” button.

IT IS IMPERATIVE that you click the “Download Keystore File”. This is your wallet which can be unlocked via the web wallet or the desktop wallet with the password you set on the previous screen.

Once you’ve downloaded your keystore file, you can click the “Continue” button. The new web page will display your private key. It is suggested that you print a “paper wallet” that contains your information. If you cannot print it on the computer you are using, attempt to print anyway and save the file as a PDF to print for later.

Proceeding to the next screen we can see that the web wallet gives us several ways to unlock our wallet to view and send funds. We can do this with the keystore we downloaded or the private key that was offered.

Unlock your wallet with your keystore and password then notate your wallet address as we’ll need it later when we setup our mining software.

#### Creating A Wallet With the Desktop Wallet:

We first need to download the desktop wallet client from the Atheios homepage. You will be presented with multiple options. For this guide we’re assuming your running a windows 10 environment. Most computers in this day and age are 64bit so we’ll select that download.

Once we have it downloaded, extract the contents of the zip file to a folder on your desktop. From here, we’ll navigate into the folder and double click the file “Atheios Wallet”. The wallet will automatically begin syncing itself to the Atheios network.

Note: If the 64 bit executable fails to run, please download the 32bit version of the wallet.

What this means is that the wallet is downloading each block from the chain which contains transactions, think of it as literally a public ledger. This process will generally take between 15-20 minutes.

Once syncing is complete we can then move on to adding a wallet address to the wallet. We’ll do this by clicking the large “Add Account” button shown on the left side of the screen.

A new window will appear asking you to enter your password. Once you have entered your desired password, click the “OK” button or hit Enter.

Note: You may have to resize the new window to make the “Cancel” and “OK” buttons appear.

The wallet will then ask you to repeat the password you entered. Do make sure you read the pop-up box that appears showing how you can make a backup of your keystore.

We can now click on our new wallet address which should show up as “Etherbase Main Account”, we’ll leave this up for now because we need to copy the address here shortly.

## Claymore Setup:

Download claymore from the [official source here](https://bitcointalk.org/index.php?topic=1433925.0). Unzip/Extract the contents to a folder on your desktop. Before we hop into mining some Atheios, we’ll want to configure the default claymore batch file with things like our preferred pool and our Atheios wallet address.

If you’d like to tweak claymore to get the best results I would advise that you read the official Claymore documentation to learn about the plethora of features the miner comes with.

Note: To many anti-virus programs, Claymore comes up as a virus. So long as you have downloaded the program from the official link listed above, the program is free of any virus or malware.

Now that we have claymore extracted to a folder on your desktop, let’s open the folder and scroll to the bottom where we should see a file called “Start” or “Start.bat”. This is a batch file which can contain command line instructions. In this batch file you’ll see a premade command line, we’ll want to edit this command line. We can do this by right clicking the file and selecting edit. If you’re asked what you’d like to edit with, use notepad.

What you’ll see initially is this:

EthDcrMiner64.exe -epool eu1.ethermine.org:4444 -ewal 0xD69af2A796A737A103F12d2f0BCC563a13900E6F -epsw x -dpool stratum+tcp://dcr.suprnova.cc:3252 -dwal Redhex.my -dpsw x

We’re not going to be doing any decred mining with this so I’ll include a premade command line that you can copy and paste.

setx GPU_FORCE_64BIT_PTR 0
setx GPU_MAX_HEAP_SIZE 100
setx GPU_USE_SYNC_OBJECTS 1
setx GPU_MAX_ALLOC_PERCENT 100
setx GPU_SINGLE_ALLOC_PERCENT 100
EthDcrMiner64.exe -epool stratum+tcp://POOLURLHERE -ewal ATHEIOS-WALLET -epsw x -ethi 12 -allpools 1 -esm 0 -allcoins 1 -eworker MyMiner

Copy the above lines and paste them into your start.bat and save the file (CRTL+S or File > Save).

We’ll need to replace “POOLURLHERE” with what mining pool we’d like to use. We can find a list of pools on the Atheios website and scrolling to the bottom. Most pools will give you instruction on what URL to use, in this case we’ll use the dev pool located at https://pool.atheios.com.

Visiting the above pool you are shown on the page what Stratum urls to use based off of how much hash power you have. For the simplicity of this guide we’ll assume you have one card so we’ll use the URL and port for 0-100MHs (pool.atheios.com:8008). 

Our command line should now look like this:

EthDcrMiner64.exe -epool stratum+tcp://pool.atheios.com:8008 -ewal ATHEIOS-WALLET -epsw x -ethi 12 -allpools 1 -esm 0 -allcoins 1 -eworker MyMiner

Our last step is to insert our Atheios wallet address into the command line so the pool knows where to send your mined coins. If you used the web wallet simply copy your wallet address into the section that reads “ATHEIOS-WALLET” in the command line.

If you use the Desktop wallet, switch to that window and click on the wallet we made. You should be presented with a screen that will let you highlight your wallet address to be copied (right click > Copy). We can now paste the wallet where it reads “ATHEIOS-WALLET” in our command line.

Your command line should be complete and look something like this:

setx GPU_FORCE_64BIT_PTR 0
setx GPU_MAX_HEAP_SIZE 100
setx GPU_USE_SYNC_OBJECTS 1
setx GPU_MAX_ALLOC_PERCENT 100
setx GPU_SINGLE_ALLOC_PERCENT 100
EthDcrMiner64.exe -epool stratum+tcp://pool.atheios.com:8008 -ewal 0xd05ad5F477C7c417710204915D126136c7ed9808 -epsw x -ethi 12 -allpools 1 -esm 0 -allcoins 1 -eworker MyMiner

Save the file one final time and we’re ready to mine! Simply double click the “start.bat” file and watch the magic happen.

If you run into any issues feel free to join [our discord server here](https://discord.gg/e3bGbJX) and ask questions. There are many Staff and Atheios community members who are willing to help.
