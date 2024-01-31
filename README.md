# localrpm

localrpm permite descargar los paquetes y dependencias tomando una lista de software para empaquetarlos y tenerlo de manera **"OffLine"**

## Dependencias

- dnf-plugin-core  
como instalar: `dnf install dnf-plugin-core`
> Nota.- Fedora lo tiene "pre-instalado"

## Lista de herramientas

Para agregar una lista de herramientas es necesario modificar la lista que existe dentro del archivo `localrpm`   , ejemplo:

    LIST_PACKAGES=()  
   
se modifica de la siguiente manera:     
    
    LIST_PACKAGES=(lazarus umbrello htop)
> El orden de instalación de los paquetes rpm va ser el mismo orden creciente de la lista ej: lazarus umbrello htop  

    1.- lazarus  
    2.- umbrello  
    3.- htop

## Como ejecutar

Una vez que se haya agregado la lista de herramientas, se debe ejecutar el script `localrpm` :

    sudo ./localrpm

## Instalación Offline

Para realizar la instalación, se tiene que seguir las siguientes instrucciones: 

> cambiar el * por la versión que se haya generado el tar.gz  

    tar -xzvf Fedora-Packages-*.tar.gz
    sudo -s
    cd Fedora-Packages-*
    bash installer   

## Importante!

Este script se debe ejecutar en una nueva instalación de Fedora para evitar conflictos de dependencias con las herramientas que se planea descargar e instalar de manera Offline.  

Tomar en cuenta que el script no elimina el directorio, esto es para que se pueda volver a empaquetar si en caso requiere alguna modificación y/o adición personal

    tar -czvf Fedora-Packages-*.gz Fedora-Packages-*/
