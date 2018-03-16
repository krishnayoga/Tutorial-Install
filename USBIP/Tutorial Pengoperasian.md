# Tutorial Pengoperasian USBIP pada Linux Ubuntu
## Pada Host
1. Buka terminal ubuntu (terminal nomor 1)
- Load module usbip-host
```
sudo modprobe usbip-host
```
- Jalankan usbipd, **Jangan close terminal 1 agar usbipd tetap berjalan**
```
sudo usbipd -D
```

2. Buka terminal ubuntu (terminal baru atau terminal nomor 2)
- Untuk menampilkan seluruh device
```
sudo usbip list -l
```
- Catat busid device yang ingin di share, kemudian lakukan perintah berikut
```
sudo usbip bind --busid <busid device>
```
- Maka akan muncul pesan bind telah sukses dilakukan
```
bind device on busid <busid>: complete
```

## Pada Client
- Load module vhci-hcd
```
sudo modprobe vhci-hcd
```
- Menampilkan seluruh device yang di share oleh host
```
sudo usbip list --remote <host ip>
```
- Catat busid device yang ingin disambungkan, kemudian attach device
```
sudo usbip attach -r <host ip> -b <busid device>
```
- Cek device yang di attach. Jika sukses, maka anda dapat melihat nama device anda
```
lsusb
```

## Mengakhiri sambungan (pada client)
- Menampilkan port device yang terhubung
```
sudo usbip port
```
- Catat nomor port yang akan di disconnect, kemudian detach
```
sudo detach -p <nomor port device>
```

## Mengakhiri sambungan (pada host)
- Cukup hentikan process usbipd dengan CTRL+C pada terminal 1

## FAQ
- Muncul TCP error saat akan connect
> Pastikan host dan client berada dalam satu jaringan
- Muncul error query saat attach
> Pastikan vhci-hcd telah berjalan. Jika telah berjalan maka anda dapat melihatnya di terminal setelah menjalankan perintah berikut
```
lsmod | grep vhci-hcd
```
- Error query masih ada meskipun vhci-hcd telah berjalan
> Ulangi perintah attach device beberapa kali dan pastikan dijalankan sebagai root (dengan sudo)