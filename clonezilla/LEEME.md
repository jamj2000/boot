Pasos a seguir para instalar Clonezilla en el disco duro
========================================================

A continuación se ofrecen 2 formas de instalar Clonezilla en el disco duro, una para sistemas EFI y otra para MBR. 

En ambos casos se utiliza el GRUB del sistema Linux previo (Ubuntu, Debian, ...) Se hace así para que cuando éste se actualice no se pierda GRUB.

El proceso consiste en sustituir el archivo `/etc/grub.d/40_custom` por el que se ofrece aquí y configurarlo para indicar las particiones de nuestro disco (Partición de sistema de Windows, Partición de sistema de Linux, Partición para imágenes de Clonezilla, ...).

EFI
---
Esta forma es para equipos modernos con EFI. 


Pasos a seguir:

Es necesario haber creado previamente una partición ext4 para las imágenes de clonezilla. 

1. Iniciamos el sistema Linux previo (Ubuntu, ...)

2. Descargamos la **ISO de Clonezilla** de la página oficial y la copiamos al **directorio raíz** con el nombre **`clonezilla.iso`**.

3. Sustituimos el archivo **`/etc/grub.d/40_custom`** por el disponible en este repositorio.

4. Editamos el archivo anterior para establecer los números de partición adecuados.

5. Actualizamos GRUB  

```bash
sudo  update-grub
```


MBR
---
Esta forma es para equipos legacy con MBR. 

Es necesario haber creado previamente una partición ext4 para las imágenes de clonezilla. Además es necesario disponer de otra partición para el sistema Clonezilla.

Pasos a seguir:

1. Iniciamos el sistema Linux previo (Ubuntu, ...)

2. Descargamos el **ZIP de Clonezilla** de la página oficial y lo descomprimimos a la partición del sistema clonezilla.

```bash
sudo  mount  /dev/sdax  /mnt
sudo  unzip  clonezilla.zip  -d  /mnt
sudo  mv  /mnt/live  /mnt/live-hd
```
siendo sdax la partición del sistema clonezilla.

3. Sustituimos el archivo **`/etc/grub.d/40_custom`** por el disponible en este repositorio.

4. Editamos el archivo anterior para establecer los números de partición adecuados.

5. Actualizamos GRUB  

```bash
sudo  update-grub
```
