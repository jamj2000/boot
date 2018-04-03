# boot
Experimentos personales con gestores de inicio (grub, ...)


## Inicio de imagenes ISO

```
qemu-system-x86_64 -enable-kvm -machine q35,accel=kvm  -cdrom lubuntu-14.04-desktop-i386.iso -m 2048 -usb -device usb-tablet
```

### Opciones:

- `-enable-kvm -machine q35,accel=kvm`  para mejorar el rendimiento
- `-m 2048`  para reservar memoria RAM (si no indicamos nada puede que la máquina no inicie)
- `-usb -device usb-tablet` para evitar la captura del puntero del ratón por parte de la máquina virtual. Si no establecemos esta opción, deberemos pulsar `Ctrl+Alt` para devolver el puntero del ratón al anfitrión.


## Inicio de USB arrancable

```
qemu-system-x86_64 -enable-kvm -machine q35,accel=kvm  -drive format=raw,file=/dev/sdb  -m 2048 -usb -device usb-tablet
```

### Opciones

- `-drive format=raw,file=/dev/sdb` formato raw para /dev/sdb (nuestro pendrive arrancable)



## Referencias 

- https://wiki.archlinux.org/index.php/QEMU 
- https://wiki.gentoo.org/wiki/QEMU/Options
