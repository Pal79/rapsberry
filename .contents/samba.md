<h1 align="center">
	<img src="../.pictures/samba_logo.png" alt="Samba logo" width="128"/>
</h1>

<!--
Shell:      console, shell
Bash:       bash, sh, zsh
PowerShell: powershell, ps
DOS:        dos, bat, cmd
-->

---

> Rendszer frissítése

```console
sudo apt update
```

> Telepítés

```console
sudo apt install samba
```

> Ellenőrzés

```console
whereis samba
```

> Eredmény:

```console
samba: /usr/sbin/samba /usr/lib/samba /etc/samba /usr/share/samba /usr/share/man/man7/samba.7.gz /usr/share/man/man8/samba.8.gz
```

> Könyvtár létrehozás (ha még nincs)

```console
sudo mkdir /home/<username>/sambashare/
```

> konfigurációs fájl szerkesztése:

```console
sudo nano /etc/samba/smb.conf
```

> A fájl végére beírni:

```console
[sambashare]
    comment = Samba on Ubuntu
    path = /home/username/sambashare
    read only = no
    browsable = yes
```

> Samba szerver újraindítása

```console
sudo service smbd restart
```

> Tűzfal engedély:

```console
sudo ufw allow samba
```

> Felhasználónév létrehozás és jelszó megadása*2

```console
sudo smbpasswd -a username
```

> Samba server elérése:

```console
smb://ip-address
```

### Ha nem tudsz fájlokat megosztani:

> hozzáadás az smb.conf >> [Global] részéhez:

```console
server min protocol = NT1
client min protocol = NT1
```

---

[Raspberry menü](../README.md)
