<h1 align="center">
	<img src="../.pictures/samba_logo.png" alt="Samba logo" width="128"/>
</h1>

---

> Rendszer frissítése

```shell
sudo apt update
```

> Telepítés

```
sudo apt install samba
```

> Ellenőrzés

```
whereis samba
```

> Eredmény:

```
samba: /usr/sbin/samba /usr/lib/samba /etc/samba /usr/share/samba /usr/share/man/man7/samba.7.gz /usr/share/man/man8/samba.8.gz
```

> Könyvtár létrehozás (ha még nincs)

```
sudo mkdir /home/<username>/sambashare/
```

> konfigurációs fájl szerkesztése:

```
sudo nano /etc/samba/smb.conf
```

> A fájl végére beírni:

```
[sambashare]
    comment = Samba on Ubuntu
    path = /home/username/sambashare
    read only = no
    browsable = yes
```

> Samba szerver újraindítása

```
sudo service smbd restart
```

> Tűzfal engedély:

```
sudo ufw allow samba
```

> Felhasználónév létrehozás és jelszó megadása*2

```
sudo smbpasswd -a username
```

> Samba server elérése:

```
smb://ip-address
```

### Ha nem tudsz fájlokat megosztani:

> hozzáadás az smb.conf >> [Global] részéhez:

```
server min protocol = NT1
client min protocol = NT1
```

---

[Raspberry menü](../README.md)
