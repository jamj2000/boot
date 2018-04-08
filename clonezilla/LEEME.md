Pasos a seguir para instalar Clonezilla en el disco duro
========================================================


1. Iniciar CDLive de Clonezilla.

2. Montar partición que va a contener Clonezilla. En el ejemplo es `/dev/sda4`.

```bash
sudo su
mount  /dev/sda4  /mnt
```

3. Copiar archivos de Clonezilla

```bash
cp  -r  /lib/live/mount/medium/*  /mnt
```

4. Cambiar nombre `/mnt/live` a `/mnt/live-hd`

```bash
mv  /mnt/live  /mnt/live-hd
```

5. Montar en `/media` el pendrive con los archivos de configuración. En el ejemplo `/dev/sdb1`.

```bash
mount  /dev/sdb1  /media
```

6. Copiar archivos [`/media/grub.cfg)`](grub.cfg) y [`/media/bg.png`](bg.png) a `/mnt/EFI/boot`.
 
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

