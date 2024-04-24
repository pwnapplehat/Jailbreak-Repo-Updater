# Jailbreak-Repo-Updater
A script made to update jailbreak repository without having to manually fill out each details in Packages file.

# Overview

This Python script automates the process of updating a Debian Packages file (Packages) by extracting information from Debian package files (.deb) in a specified folder. It enhances the management of Debian package repositories by ensuring that the Packages file accurately reflects the metadata and file paths of the available packages.

# Features

Extracts package metadata (name, version, architecture, dependencies, etc.) from .deb files.
Calculates file size and checksums (MD5, SHA1, SHA256) for each .deb package.
Updates existing entries in the Packages file if architecture matches.
Adds new entries for packages not already listed in the Packages file.
Supports different architectures and sets the Filename path accordingly.

# How It Works

1. 'get_deb_info(deb_file)': Extracts metadata and checksum information from a Debian package file ('deb_file') using the 'ar' command and hashlib library.
2. 'update_packages_file()': Updates the 'Packages' file by iterating through '.deb'files in the script's folder. For each '.deb' file:

   - Extracts package information using 'get_deb_info'.
   - Constructs a package entry string.
   - Updates or adds entries in the 'Packages' file based on architecture and package ID.

# Usage

1. Clone the repository: "git clone https://github.com/your_username/your_repository.git"
and "cd your_repository"
2. Place your 'Packages' and '.deb' files in the script's folder. (Only keep the script, Packages file and .deb files you want to update in Packages file)
3. Run the script: Right click> Open With> Python Launcher. The script will soon then update your Packages file with updated information of already existing package entries in the 'Packages' file with the new one placed in same folder and also will add or construct new package entries for '.deb' files whose package entries is not there in 'Packages' file.

# Important

If you have '.deb' files for both 'iphoneos-arm' and 'iphoneos-arm64' architectures, then you have to place only '.deb' files first of one architecture for example: 'iphoneos-arm', and then run the script and it will update your 'iphoneos-arm' package entries with the new one. And then place only 'iphoneos-arm64' .deb files you want to update in the folder and run the script. Btw, the script can also add new '.deb' files entries too in the Packages file if the entry for that '.deb' is not there in 'Packages' file.

# Requirements

 - Python 3.x
 - 'ar' command (typically available in Unix-like systems)
 - Ensure that the script has appropriate permissions to read/write files in the script's folder.

# Modifications

You can do some changes in the script like the 'Filename' path according to your repository '.deb' files location.
You can also check out my jailbreak repository if it helps: https://github.com/pwnapplehat/pwnapplehat.github.io

# License

This project is licensed under the MIT License.
