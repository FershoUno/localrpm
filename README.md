# localrpm

localrpm allows you to download packages and dependencies based on a software list to package then and have them available **"OffLine"**

## Dependencies

This dependency comes pre-installed on Fedora Workstation

- dnf-plugin-core  

how to install:  

    dnf install dnf-plugin-core  
> Note.- Note: If you want to use a Fedora LXC container, then you need to install it.

## List of tools

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

    tar -xzvf fedora-packages-*.tar.gz
    sudo -s
    cd fedora-packages-*/
    bash installer   

## Important!

This tool is designed to work correctly on new Fedora installations. Some activities where this tool may be useful:
- Post FLISOL
- InstallFest at the university 