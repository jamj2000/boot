Pasos a seguir para instalar Clonezilla en el disco duro
========================================================


1. Iniciar USB de Clonezilla Live. Tiene 2 particiones:
    - sdb1 (MULTIBOOT)
    - sdb2 (DATA)

2. Montar partición que va a contener Clonezilla.

```bash
sudo su
mount  /dev/sda4  /mnt
```

3. Copiar archivos de Clonezilla

```bash
cp -r /lib/live/mount/medium/*  /mnt
```

4. Cambiar nombre /mnt/live a /mnt/live-hd

```bash
mv  /mnt/live  /mnt/live-hd
```

5. Montar sdb2, la cual tiene los archivos de configuración

```bash
mount /dev/sdb2 /media
```

6. Copiar archivos `/media/grub.cfg` y `/media/bg.png` a /mnt/EFI/boot
 
```bash
cd  /mnt/EFI/boot
cp  /media/grub.cfg  /media/bg.png  .
```

7. Instalar grub2  

```bash
grub-install  /dev/sda  --root-directory=/mnt 
```

## Información consultada

- http://joaalsai.com/index.php/2017/11/17/creacion-de-un-menu-de-restauracion/

