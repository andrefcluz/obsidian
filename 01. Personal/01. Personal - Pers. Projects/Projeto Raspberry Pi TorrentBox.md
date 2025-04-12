---
title: Projeto Raspberry Pi TorrentBox
updated: 2024-10-06 10:51
created: 2018-06-23 12:24:28Z
author: André Luz
tags:
  - rpi_torrent_box
---

Things to research:

TRAKT

    - [ ] Get last watched episodes from each TV Show on the RPI list
    - [ ] Get next 4 episodes to watch from each TV Show on the RPI list
    - [ ] Mark episodes has watched

PLEX

    - [ ] Know when a episode is fully watched

RPi

    - [ ] Delete a specific file

1. Montar disco externo
https://www.instructables.com/id/Make-Your-Own-TorrentBox-From-a-Pi/

https://www.howtogeek.com/139433/how-to-turn-a-raspberry-pi-into-a-low-power-network-storage-device/

https://www.raspberrypi-spy.co.uk/2014/05/how-to-mount-a-usb-flash-disk-on-the-raspberry-pi/

/media/pidrive
73A1-3259

2. Instalar e configurar cliente Torrent
https://pimylifeup.com/raspberry-pi-torrentbox/

https://www.howtogeek.com/142044/how-to-turn-a-raspberry-pi-into-an-always-on-bittorrent-box/

[https://medium.com/@jakobud/automatic-anonymous-bittorrent-downloading-using-a-raspberry-pi-b367a67de238](https://medium.com/%40jakobud/automatic-anonymous-bittorrent-downloading-using-a-raspberry-pi-b367a67de238)

3. Instalar e configurar servidor Plex
https://pimylifeup.com/raspberry-pi-plex-server/

# Criar pasta onde o disco vai ser montado
sudo mkdir /media/pidrive

# Tornar pi o owner da pasta
sudo chown -R pi:pi /media/pidrive

# Ligar disco rígido
# Ver lista de dispositivos. O que interessa é o SDA
sudo fdisk -l

# Criar partição no disco
sudo fdisk /dev/sda

# Executar no comandos na ordem seguinte
1.     p - Verificar partições existentes
2. d - Eliminar as partições
3. n - Criar uma partição nova
    1. p - Primary
    2. ENTER (default 1)
    3. ENTER (default 1)
    4. ENTER (default 1)
4. p - Verificar se a nova partição foi criada
5. w - Sair

# Converter partição para FAT32
sudo mkfs.vfat /dev/sda1

# Ir buscar o ID do disco (ID_DISCO). Há-de ser semelhante a 73A1-3259
ls -l /dev/disk/by-uuid/

# Montar o disco
sudo mount /dev/sda1 /media/pidrive -o uid=pi,gid=pi

# Desmontar o disco
sudo umount /media/pidrive

# Montar automaticamente o disco
sudo nano /etc/fstab
# Substituir a última linha por:
UUID=ID_DISCO /media/usb vfat auto,nofail,noatime,users,rw,uid=pi,gid=pi 0 0

# Reiniciar RPi
sudo reboot

https://pastebin.com/1a3ZzSD6