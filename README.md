# Tapastic-Comic-Downloader
This is a downloader to download and update whole comics from https://tapas.io/. (Not official!)

## Attention:
**This script could be illegal in certain cases, please first read the terms of service on https://tapas.io/ !**

## Usage:
1. Installing python3 and needed modules:
 * Can be installed on Debian and Ubuntu and other Linux distribution that use 'apt' like this:
 ```
 # git clone https://github.com/TilCreator/Tapas-Comic-Downloader && cd Tapas-Comic-Downloader
 # apt install python3 python3-dev python3-pip libxml2-dev libxslt1-dev zlib1g-dev
 # pip3 install -r requirenments.txt
 # pip3 install -r requirenments_novels.txt  # If novels are expected to be downloaded
 ```
 * On Arch/Antergos:
 ```
 # git clone https://github.com/TilCreator/Tapas-Comic-Downloader && cd Tapas-Comic-Downloader
 # pacman -S python python-pip
 # pip install -r requirenments.txt
 # pip install -r requirenments_novels.txt  # If novels are expected to be downloaded
 ```
 * On Windows:
   * Install python from python.org
   * Open cmd
   * Navigate to repo location (needs to be downloaded)
   * Install needed modules:
      ```
      pip install -r requirenments.txt
      pip install -r requirenments_novels.txt  # If novels are expected to be downloaded
      ```
   * Execute the script
      ```
      python tapas-dl.py [-h/--help] [-f/--force] [-v/--verbose] URL/name [URL/name ...] [-o \output\path\]
      ```
      More exact usage in the next section
   * (thx @ [ONSKJ](https://github.com/ONSKJ) for help with Windows)
 + If someone got it running on another OS, please let me know!
2. Get input link
 * Go to the comic you want to download (any page)
 * Click on the comic name or thumbnail in the upper right corner to get the download URL or just use the name behind series in the url.
 * Examples: `https://tapas.io/series/Erma`, `RavenWolf`, ...
3. Start the download
 * Usage of `tapas-dl.py`:
 ```
 $ ./tapas-dl.py -h
 usage: tapas-dl.py [-h] [-f] [-v] [-r] [-c [PATH]] [-o [PATH]]
                    URL/name [URL/name ...]
 
 Downloads Comics from 'https://tapas.io'.
 If folder of downloaded comic is found, it will only update (can be disabled with -f/--force).
 
 positional arguments:
   URL/name              URL or URL name to comic
                         Go to the comic you want to download (any page)
                         Rightclick on the comic name in the upper left corner and select "Copy linkaddress" (Or similar) or just use the name behind series in the url
                         Examples: https://tapas.io/series/Erma, RavenWolf, ...
 
 optional arguments:
   -h, --help            show this help message and exit
   -f, --force           Disables updater.
   -v, --verbose         Enables verbose mode.
   -r, --restrict-characters
                         Removes '? < > \ : * | " ^' from file names
   -c [PATH], --cookies [PATH]
                         Optional cookies.txt file to load, can be used to allow the script to "log in" and circumvent age verification.
   -o [PATH], --output-dir [PATH]
                         Output directory where comics should be placed.
                         If left blank, the script folder will be used. 
 ```
 * The script will create an folder with the name and urlName (`name [urlName]`) of the comic in the current shell location (like git) and download all images of the comic into it.
 * If the script finds an folder with the name of the comic, it will only update, this can be disabled with `-f/--force`.
 * To get the verbose output use `-v/--verbose`.
 * To specify an base output path use `-o/--output-dir \desired\path` (If not specified, files and folders will be created where the script was run.)
 * On some file systems (expecialy Windows ones) some characters are unsupportet, if you run into problems with that use the -c, --restrict-characters option
