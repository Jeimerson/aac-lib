# aac-lib
AAC Library of Tools

- <a href=https://github.com/Texiwill/aac-lib/tree/master/>List of Tools</a>

## vsm
Linux Version of VMware Software Manager (MacOS Install)
- <a href=https://github.com/Texiwill/aac-lib/tree/master/>List of Tools</a>

### NOTICE
__As of LinuxVSM v6.4.2, MacOSX support is available. However, the
dependencies must be met, including the xcode-select below. There is
often an issue where the Xcode CLI install needs to be repaired first.__

### Description
A MacOS and slightly more intelligent version of VSM. See README.md for more information:
- <a href=https://github.com/Texiwill/aac-lib/tree/master/vsm>LinuxVSM README</a>

### Installation
Follow the normal instructions, there is now nothing specific to MacOS
that you must do!

#### Deprecated
__Deprecated! Use above instructions__

Tested against MacOS X High Sierra - 10.13.4

To install vsm.sh on MacOS you need to first install the prerequisites. 
Those are Xcode, XML::Twig, Homebrew, jq, and wget. Here is how you do those:

* First install Xcode from Apple
* Next install Homebrew using:
```
$ ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
* Next install gnu-sed, jq, and wget
```
brew install gnu-sed
brew install wget
brew install jq
brew install node
```
* Next install XML::Twig (note the 'sudo'), if you rather not use sudo,
and I can understand why, you will have to update your PATH variables
to also point to where the xml_grep command is located. This is 
accomplished by editting/creating your .bash_profile or creating a file within /etc/paths.d with your path. It is usually installed somewhere 
within your home directory so 'find $HOME -name xml_grep -print' can 
find it for you.
```
sudo perl -MCPAN -e shell
cpan> install XML::Twig
... lots of questions and such. Answer YES or Y or y to
any yes/no question presented ...
cpan> exit
echo "export PATH=\$PATH:$HOME/perl5/bin" >> $HOME/.bash_profile
```
* Next install vsm.sh (note the use of 'sudo')
```
sudo wget -O /usr/local/bin/vsm.sh https://raw.githubusercontent.com/Texiwill/aac-lib/master/vsm/vsm.sh
sudo chmod +x /usr/local/bin/vsm.sh
```
* Start a new shell or kill the one you are using and start over. Now the PATH should be set properly for everything installed.

### Update
To keep vsm and your repository updated to the latest release/downloads
you can add the following lines to your local cron. This tells the
system to update the installer, then update vsm, then run vsm with your
currently marked favorite. Note 'user' is your username. 

Be sure to Mark a release as your favorite! If you do not, this does
not work. The 'Mark' menu item does this.

I added these lines using 'sudo crontab -e' to run at 3AM every day:
```
0 3 * * * wget -O /usr/local/bin/vsm.sh https://raw.githubusercontent.com/Texiwill/aac-lib/master/vsm/vsm.sh
0 3 * * * chmod +x /usr/local/bin/vsm.sh
```

The following line starts VSM download at 6AM. You would add using the
command `crontab -e`:
```
0 6 * * * /usr/local/bin/vsm.sh -y -c -mr --favorite
```

Note if you do not want to use sudo, you can install vsm.sh into
any directory you desire. You will have to adjust the paths above
appropriately.

### Support
Email elh at astroarch dot com for assistance or if you want to add
for more items.

