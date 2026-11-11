## x) Summary
### Heinonen 2026: [How to Install Linux to Virtualbox?](https://github.com/johannaheinonen/johanna-test-repo/blob/main/module_1.md)

The author has Windows 11, Virtualbox 7.x and Debian 13.x (Trixie). The steps are roughly: install Virtualbox -> download Debian ISO image (debian-live-13.6.0-amd64-xfce.iso was used in the article) -> create a new Virtual Machine (VM) on Virtualbox -> install Debian on the new VM

### Karvinen 2020: [Command Line Basics Revisited](https://terokarvinen.com/2020/command-line-basics-revisited/)
- Navigation
  ```ls
  $ pwd   # prints the working directory
  $ ls    # list files in working directory
  $ cd tnadir/    # change directory to tnadir
  $ cd ..    # change directory up
  $ less tna.txt    # view text file tna.txt
  $ ls /etc|less    # any command output can be read one screenfull at a time by piping the output to less
  ```
- File Manipulation
  ```ls
  $ nano FOO.TXT    # Easiest text editors are pico and nano
  $ mkdir NEWFOLDER    # Make a new directory
  $ mv OLDNAME NEWNAME    # Move or rename directory or file OLDNAME to target NEWNAME. If NEWNAME does not exist, OLDNAME is renamed to NEWNAME. If both parameters are files, NEWNAME is overwritten
  $ mv SOMEFILE NEWDIR/    # If target is a directory, OLDNAME is moved there.
  $ cp -r ORIGINAL COPY    # Copy ORIGINAL to COPY. “-r” means recursive, ORIGINAL is copied with contents if it is a directory.
  $ rmdir EMPTYDIR    # Remove an empty directory
  $ rm -r FOLDEROFJUNK    # Remove FOLDEROFJUNK/ and its contents
  $ rmdir Junk    # Remove a file called Junk
  ```
- SSH Remote Control
  ```ls
  $ ssh tna@example.com    # Open a remote command shell in a very secure way. Here, username is tna and server is example.com. A command line just like yours opens. Anything you type is sent to remote machine and the answer is sent back to you. You can use ‘w’ to see who else is on the same machine.
  remotecomputer$ exit    # Exit back to your own machine with ‘exit’
  $ scp -r FOLDER tna@example.com:public_html/    # Securely copy FOLDER to a folder in remote machine. Scp is run on your own machine. If you are connected to remote computer with ssh, ‘exit’ first.
                                                  # Syntax of remote path is login@server:path_from_your_home_dir. Note that there are no spaces between login name and path_from_your_home_dir. Server and path are separated with a colon “:”.


  ```
- Help
  ```ls
  $ man ls    # Show manual page of a command. Manual page is shown in ‘less’. Use space ” ” for next page, “q” to quit. “b” Moves backwards, slash “/” searches.
  $ ls --help    # short builtin help
  $ wget -h      # another short builtin help
  ```
- History and Guessing
  ```ls
  # Tab (above caps lock) twice shows what you can type next.
  $ ls /etc/re[tab][tab]
  reportbug.conf  resolvconf/     resolv.conf
  
  # Tab also fills commands if it is unambiguous. Always use tab when entering filenames and paths to avoid typos.
  # Arrow keys move in current command line and command history. Up arrow shows previous command. Left and right arrows allow you to modify current command line.
  $ ls /etc/resolv.[tab]
  $ ls /etc/resolv.conf

  # History commands you have ran. This history can be searched with ctrl-R (^R).
  $ history
  ```
- Important directories
  - `/`	Root directory, the top of the filesystem. There are no drive letters in Linux, everything is under /.
  - `/home/`	Contains home directories for all users.
  - `/home/tna/`	Home directory of user "tna". The only place where user "tna" can permanently store data.
  - `/etc/`	All system wide settings. They are in human readable, plain text files.
  - `/media/`	Removable media, such as /media/cdrom/ or /media/usbdisk/
  - `/var/log/`	System wide logs, such as /var/log/syslog, /var/log/auth.log and /var/log/apache2/error.log

- Administrative Commands
  ```ls
  $ sudo apt-get update    # Update list of available packages. Run apt-get update before giving other apt commands.
  $ apt-cache search dungeon adventure    # Search for software with keywords, no sudo needed.
  $ sudo apt-get -y install nethack-console    # Install software nethack-console

  # Many programs are shown in the applications menu. For most command line applications, you have to find out the right command.
  $ dpkg --listfiles nethack-console

  # Usually, the command is the file in one of the bin/ or game/ directories /usr/lib/games/nethack
  # run it with
  $ nethack
  $ sudo apt-get purge nethack    # use purge to remove the nethack game so that also it's system wide settings are destroyed.
  $ sudo apt-get -y install krita blender vlc tree httpie curl tmux python3-py    # Same apt-get command can install a lot of software.
  ```
  
### Karvinen 2022: [Cracking Passwords with Hashcat](https://terokarvinen.com/2022/cracking-passwords-with-hashcat/)
An example to crack "6b1628b016dff46e6fa35684be6acc96" password with Hashcat on Debian 11 Bullseye.
In this exercise, the correct word is in RockYou dictionary, and you will crack it.
In some other exercise, you might get "Status: Exhausted" instead of "Cracked". That would mean that all words in the dictionary were tried, but none of them worked.
  ```ls
  # Install Hashcat
  $ sudo apt-get update
  $ sudo apt-get -y install hashid hashcat wget

  # Create a new directory for our work
  $ mkdir hashed
  $ cd hashed

  # Get a big dictionary. Rockyou is probably the most popular
  $ wget https://github.com/danielmiessler/SecLists/raw/master/Passwords/Leaked-Databases/rockyou.txt.tar.gz
  $ tar xf rockyou.txt.tar.gz
  $ rm rockyou.txt.tar.gz

  # one word after another
  $ head rockyou.txt
  123456
  12345
  123456789
  password
  iloveyou
  princess
  1234567
  rockyou
  12345678
  abc123

  # With over 14 million words
  $ wc -l rockyou.txt 
  14344391 rockyou.txt

  # Identify Hash Type
  $ hashid -m 6b1628b016dff46e6fa35684be6acc96
  Analyzing '6b1628b016dff46e6fa35684be6acc96'
  [+] MD2 
  [+] MD5 [Hashcat Mode: 0]
  [+] MD4 [Hashcat Mode: 900]
  ...

  # Crack the Hash
  $ hashcat -m 0 '6b1628b016dff46e6fa35684be6acc96' rockyou.txt -o solved
  ...
  Status...........: Cracked
  Hash.Type........: MD5    # This is what we chose with 'hashcat -m 0 ...'
  Hash.Target......: 6b1628b016dff46e6fa35684be6acc96
  [..]
  Speed.Dev.#1.....: 37401.1 kH/s (4.60ms)    # This is 37 million words tried per second

  # After a moment, hashcat is done
  $ cat solved 
  6b1628b016dff46e6fa35684be6acc96:summer

  # If you already cracked it, but did not specify a file, you can see it with "--show"
  $ hashcat -m 0 6b1628b016dff46e6fa35684be6acc96 rockyou.txt 
  ... INFO: All hashes found in potfile! Use --show to display them. ...
  $ hashcat -m 0 6b1628b016dff46e6fa35684be6acc96 rockyou.txt --show
  6b1628b016dff46e6fa35684be6acc96:summer
  ```
  - `hashcat`	the hash cracking program.
  - `-m 0`	type of the hash, the number we obtained from `hashid` or `hashcat --example-hashes`.
  - `'6b1628b016dff46e6fa35684be6acc96'`	the hash we want to crack. Put single quotes around it, as many hashes contain special characters.
  - `-o` solved	save the solution as plain text to a new file "solved" in working directory.

## a) Presentation title
Security maturity model.
## b) Install Linux on a Virtual Machine
Install Debian Trixie-13 on VirtualBox 7.2.22 on my Windows 10.
### Install VirtualBox
1. Download latest version of VirtualBox for Windows host from https://www.virtualbox.org/wiki/Downloads
2. Launch the VirtualBox Setup wizard -> Keep clicking Next with all the default options unless you want to change some options until you see the Warning: Network Interfaces screen -> Click Yes to continue to the Ready to Install screen -> Click Install -> Installation takes a few minutes then click Finish.
3. Create your new Virtual Machine (VM) on VirtualBox by clicking the New button in the top-right corner of the VirtualBox window to open the Create Virtual Machine wizard -> on the Name and operating system page fill in VM Name (based on its intended purposes i.e nginx-web-server or windows10-development), ISO image (path to location where the image is downloaded from https://www.debian.org/download), VM Folder (a Windows VM will need at least 20GB so ensure there’s enough space on your drive for your VM), Type: Linux, Distribution: Debian, Version: Debian (64-bit) -> Click Specify virtual hardware accordion to set how much memory (RAM) your VM will have (minimun 2048MB RAM, recommended 4096MB, 2 CPUs for instance) -> Click Specify virtual hard disk accordion to create a new hard disk for your guest VM or use an existing one. If create new one minimun 20GB, recommended 20-40GB. -> Click Finish to complete.
   
### Install Debian
1. Start the VM you just created by double clicking or right‑clicking on its name and click Start.
2. Live Install: Select the first option from the list and press enter -> open Terminal Emulator and type some commands to check that keyboard is working e.g. pwd on your VM -> Click Install Debian that is visible in the GUI -> Go through the step in the Debian Installer until Partitions: Erase disk (safe to use when installing Linux on a fresh VM) -> Click Next to Users (set hostname for the new VM, non‑root username and a strong password for that user) -> Click Next to Summary page to check the final overview -> Click Install -> After a few mins it's completed click Done -> The system will boot into Debian GNU/Linux, log in using the credentials you created.
3. Update the package list by running in the terminal `sudo apt-get update` or `sudo apt-get upgrade`
## c) Crack
Done. Crack the hash 6b1628b016dff46e6fa35684be6acc96 following the instruction from [Karvinen 2022: Cracking Passwords with Hashcat](#karvinen-2022-cracking-passwords-with-hashcat).
## d) Voluntary bonus
John the Ripper. Install and test John the Ripper Jumbo, see [Karvinen 2023: Crack File Password With John](https://terokarvinen.com/2023/crack-file-password-with-john/).
## e) Voluntary bonus
The other John. Create an encrypted file (other than zip) and crack the hash with John.
