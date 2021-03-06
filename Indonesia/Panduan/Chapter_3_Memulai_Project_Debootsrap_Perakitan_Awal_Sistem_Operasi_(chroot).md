**[ 1 ]---------------------------------------------------------------------------------**  
Panduan : Memulai Merakit Sistem Operasi (chroot)
Penjelasan :  
Catatan :  
Buka Terminal dan Ketik Perintah Berikut :  
```bash
32-Bit
cd /home/$(whoami)/Project/
sudo mount --bind /dev/ root32/dev
sudo cp /etc/resolv.conf root32/etc/

64-Bit
cd /home/$(whoami)/Project/
sudo mount --bind /dev/ root32/dev
sudo cp /etc/resolv.conf root32/etc/
```

**[ 2 ]---------------------------------------------------------------------------------**  
Panduan : Masuk chroot ke sistem operasi debootsrap yang sudah dibuat waktu pembuatan kerangka debootsrap.
Penjelasan :  
Catatan :  
Buka Terminal dan Ketik Perintah Berikut :  
```bash
32-Bit
sudo chroot root32
mount -t proc none /proc && mount -t sysfs none /sys && mount -t devpts none /dev/pts
export HOME=/root && export LC_ALL=C

64-Bit
sudo chroot root32
mount -t proc none /proc && mount -t sysfs none /sys && mount -t devpts none /dev/pts
export HOME=/root && export LC_ALL=C
```

**[ 3 ]---------------------------------------------------------------------------------**  
Panduan : Perintah untuk membuat hostname atau nama komputer cukup sekali saja.  
Penjelasan :  
Catatan :
Buka Terminal dan Ketik Perintah Berikut :  

```bash
echo "xenta" > /etc/hostname
```

**[ 4 ]---------------------------------------------------------------------------------**  
Panduan : Memulai Pemasangan Core & Kernel.  
Penjelasan : Mencari Versi Kernel tersedia.  
Catatan:  
Buka Terminal dan Ketik Perintah Berikut :  

```bash
apt-cache search linux-image
```

**[ 5 ]---------------------------------------------------------------------------------**  
Panduan : Memulai Update & Pemasangan Kernel serta paket core.  
Penjelasan : Memasang paket paket utama.  
Catatan :  
Buka Terminal dan Ketik Perintah Berikut :  

```bash
apt-get update
apt-get install --no-install-recommends linux-image-4.4.0-21-generic casper lupin-casper network-manager nano -y
```
