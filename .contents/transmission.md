<h1 align="center">
	<img src="../.pictures/transmission_logo.jpeg" alt="Transmission logo" width="128"/>
</h1>

---

> rendszer frissítése

```
sudo apt-get update && sudo apt-get upgrade
```

> telepítés

```
sudo apt-get install transmission-daemon
```

> program leállítás

```
sudo systemctl stop transmission-daemon
```

> beállítások

```
sudo nano /etc/transmission-daemon/settings.json
```

> ezeket a sorokat módosítsd:

```
"download-dir": "/var/lib/transmission-daemon/downloads",
"rpc-username": "felhasznalo",
"rpc-password": "jelszo",
"rpc-whitelist": "192.168.*.*",
```

> Ctrl+x -> y -> [enter]

> minden jog megadása a torrent könyvtárának:

```
sudo chmod 777 -R /könyvtár
```

> program indítása

```
sudo systemctl start transmission-daemon
```


> webes belépés

```
http://RPi IP címe:9091/transmission/
```

> vagy

```
http://RPi IP címe:9091
```

---

[Raspberry menü](../README.md)
