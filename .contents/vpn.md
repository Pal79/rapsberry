<h1 align="center">
	<img src="../.pictures/vpn.png" alt="VPN logo" width="128"/>
</h1>

---

```
sudo apt update && sudo apt upgrade -y
```

```
sudo passwd // if must
```

> vpn install

```
sudo apt install openvpn -y // install
```

```
cd /etc/openvpn // change directory
```

```
sudo wget https://www.privateinternetaccess.com/openvpn/openvpn.zip // download
```

```
sudo unzip openvpn.zip // unzipping
```

```
sudo openvpn --config ./Netherlands.ovpn
```

```
sudo nano login.conf // create new document
```

```
sudo chmod 400 login.conf
```

```
sudo cp Singapore.ovpn Singapore.conf
```

```
sudo nano Singapore.conf
```

```
-> auth-user-pass /etc/openvpn/login.conf
-> crl-verify /etc/openvpn/crl.rsa.2048.pem
-> ca /etc/openvpn/ca.rsa.2048.crt

-> Ctrl+x -> y -> [enter]
```

```
sudo openvpn Singapore.conf
```

```
sudo nano /etc/default/openvpn
```

```
-> AUTOSTART="Singapore"
-> Ctrl+x -> y -> [enter]
```

```
sudo shutdown -r 0
```

```
curl http://ipinfo.io/ip
```

---

[Raspberry menü](../README.md)
