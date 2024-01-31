# localrpm

localrpm allows you to download packages and dependencies based on a software list to package then and have them available **"OffLine"**

## Dependencies

- dnf-plugin-core  
how to install: `dnf install dnf-plugin-core`
> Note.- Fedora hast it "pre-installed"

## List of Tools

To add a list of tools, it is necessary to modify the list inside the `localrpm` file, for example:

    LIST_PACKAGES=()  
   
it is modified as follows:     
    
    LIST_PACKAGES=(lazarus umbrello htop)
> The order of installation of the rpm packages will be the same increasing order of the list, e.g., lazarus umbrello htop

    1.- lazarus  
    2.- umbrello  
    3.- htop

## How to Run

Once the list of tools has been added, the `localrpm` script must be executed:

    sudo ./localrpm

## Offline Installation

To perform the installation, you hace to follow the instructions below:

> replace * with the version that the tar.gz has been generated  

    tar -xzvf Fedora-Packages-*.tar.gz
    sudo -s
    cd Fedora-Packages-*
    bash installer   

## Important!

This script should be run on a fresh Fedora installation to avoid dependecy conflicts with the tools planned to be downloaded and installed offline.  

Please note that the script does not delete the directory, this is so it can be repackaged if any modification and/or personal addition is required.  

    tar -czvf Fedora-Packages-*.gz Fedora-Packages-*/
