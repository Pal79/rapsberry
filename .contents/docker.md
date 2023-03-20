<h1 align="center">
	<img src="../.pictures/docker_logo.png" alt="Docker logo" width="128"/>
</h1>

---

## Régi verzió törlése

```
sudo apt-get remove docker docker-engine docker.io containerd runc
```

## Repository beállítása

1. Update the apt package index and install packages to allow apt to use a repository over HTTPS:

> Rendszer frissítése

```
sudo apt update
```

> csomagok telepítése

```
sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
```

## Docker GPG kulcs hozzáadása

> könyvtár létrehozás

```
sudo mkdir -p /etc/apt/keyrings
```

> GPG kulcs másolása a könyvtárba

```
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```

## Repository beállítása:

```
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/debian \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```  

## Docker telepítése

> Rendszer frissítése:

```
sudo apt-get update
```

---

> GPG hiba üzenet a frissítés futtatásakor?
> Lehetséges, hogy az alapértelmezett umask rosszul van konfigurálva, ami miatt nem lehet a kulcsot olvasni. A frissítés előtt olvasási engedélyt kell adni a docker nyilvános kulcsának:

```
sudo chmod a+r /etc/apt/keyrings/docker.gpg
sudo apt-get update
```

---

## Docker-engine, konténer és docker-compose telepítés

```
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
```

## A hello-world image futtatásával ellenőrizzük a docker-engine sikeres telepítését:

```
sudo docker run hello-world
```

---

[Raspberry menü](../README.md)
