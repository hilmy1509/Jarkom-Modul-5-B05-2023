# Jarkom-Modul-5-B05-2023

### Praktikum Jarkom Modul 5

| NRP | Name |
| ------ | ------ |
|5025211028|Keysa Anadea Aqiva Ajie|
|5025221202|Hilmy Septian Nursyekha|

## Topologi GNS3
<img width="606" alt="Cuplikan layar 2023-12-20 183434" src="https://github.com/hilmy1509/Jarkom-Modul-5-B05-2023/assets/115638253/fc73025a-8509-496c-9d5d-7356f81451e2">

## Prefix IP
`10.11`

## Rute
<img width="615" alt="Cuplikan layar 2023-12-20 183628" src="https://github.com/hilmy1509/Jarkom-Modul-5-B05-2023/assets/115638253/c0fe18fd-6b1c-4d76-8ebf-1b876a016f99">

## Tree
<img width="388" alt="Cuplikan layar 2023-12-20 183737" src="https://github.com/hilmy1509/Jarkom-Modul-5-B05-2023/assets/115638253/ba6d793a-c21a-4c31-aa0e-bdbe9626f8ea">

## Pembagian IP
<img width="697" alt="Cuplikan layar 2023-12-20 183858" src="https://github.com/hilmy1509/Jarkom-Modul-5-B05-2023/assets/115638253/c2f9f721-1393-4fa3-a9a3-18dc2177c49a">

## Subnetting
Mengacu pada `IP` yang telah diperoleh, berikut subnettingnya

#### Aura
```
auto eth0
#iface eth0 inet dhcp
iface eth0 inet static
	address 192.168.122.2
	netmask 255.255.255.252
	gateway 192.168.122.1

#A1
# Static config for eth1
auto eth1
iface eth1 inet static
        address 10.11.14.129
        netmask 255.255.255.252

#A8
# Static config for eth2
auto eth2
iface eth2 inet static
        address 10.11.14.149
        netmask 255.255.255.252
```
#### Heiter
```
#A8
# Static config for eth0
auto eth0
iface eth0 inet static
	address 10.11.14.150
	netmask 255.255.255.252
	gateway 10.11.14.149

#A9
# Static config for eth1
auto eth1
iface eth1 inet static
	address 10.11.0.1
	netmask 255.255.248.0 

#A10
# Static config for eth2
auto eth2
iface eth2 inet static
	address 10.11.8.1
	netmask 255.255.252.0 
```
#### Frieren
```
#A1
# Static config for eth0
auto eth0
iface eth0 inet static
	address 10.11.14.130
	netmask 255.255.255.252
	gateway 10.11.14.129

#A2
# Static config for eth1
auto eth1
iface eth1 inet static
	address 10.11.14.133
	netmask 255.255.255.252

#A7
# Static config for eth2
auto eth2
iface eth2 inet static
	address 10.11.14.145
	netmask 255.255.255.252
```
#### Himmel
```
#A2
# Static config for eth0
auto eth0
iface eth0 inet static
	address 10.11.14.134
	netmask 255.255.255.252
	gateway 10.11.14.133

#A3
# Static config for eth1
auto eth1
iface eth1 inet static
	address 10.11.12.1
	netmask 255.255.254.0

#A4
# Static config for eth2
auto eth2
iface eth2 inet static
	address 10.11.14.1
	netmask 255.255.255.128
```
#### Fern
```
#A4
auto eth0
iface eth0 inet static
	address 10.11.14.2
	netmask 255.255.255.128
	gateway 10.11.14.1

#A6
auto eth1
iface eth1 inet static
	address 10.11.14.141
	netmask 255.255.255.252

#A5
auto eth2
iface eth2 inet static
	address 10.11.14.137
	netmask 255.255.255.252
```
#### Revolte
```
#A6
# Static config for eth0
auto eth0
iface eth0 inet static
	address 10.11.14.142
	netmask 255.255.255.252
	gateway 10.11.14.141
```
#### Richter
```
#A5
# Static config for eth0
auto eth0
iface eth0 inet static
	address 10.11.14.138
	netmask 255.255.255.252
	gateway 10.11.14.137
```
#### Stark
```
#A7
# Static config for eth0
auto eth0
iface eth0 inet static
	address 10.11.14.146
	netmask 255.255.255.252
	gateway 10.11.14.145
```
#### Sein
```
#A10
# Static config for eth0
auto eth0
iface eth0 inet static
	address 10.11.8.2
	netmask 255.255.252.0
	gateway 10.11.8.1
```
#### Client (TurkRegion, GrobeForest, LaubHills, SchwerMountain)
```
auto eth0
iface eth0 inet dhcp
```

## Routing
Setelah subnetting, maka selanjutnya adalah routing yang scriptnya disimpan menggunakan `shell`

#### Aura
<img width="521" alt="Cuplikan layar 2023-12-20 202628" src="https://github.com/hilmy1509/Jarkom-Modul-5-B05-2023/assets/115638253/d058d9de-8dba-49a1-9109-0c75698ded17">

#### Frieren
<img width="457" alt="Cuplikan layar 2023-12-20 203014" src="https://github.com/hilmy1509/Jarkom-Modul-5-B05-2023/assets/115638253/bd9e55d0-40ed-4dd1-b4a3-bbb5d46abeb8">

#### Himmel
<img width="471" alt="Cuplikan layar 2023-12-20 204752" src="https://github.com/hilmy1509/Jarkom-Modul-5-B05-2023/assets/115638253/9c1ccdeb-ea70-455e-83f7-6e46f5ba3d1b">

### Konfigurasi
Jalankan perintah berikut pada `Aura`
```
iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE -s 10.11.0.0/16
```
### DNS Server (Richter)

### DHCP Server (Revolte)
<img width="319" alt="Cuplikan layar 2023-12-20 205425" src="https://github.com/hilmy1509/Jarkom-Modul-5-B05-2023/assets/115638253/b5d5527d-9d10-4a58-a72f-c6554534b097">
  <img width="346" alt="Cuplikan layar 2023-12-20 205523" src="https://github.com/hilmy1509/Jarkom-Modul-5-B05-2023/assets/115638253/9da46a7f-b641-476a-9946-dd2d98a18813">
    <img width="340" alt="Cuplikan layar 2023-12-20 205559" src="https://github.com/hilmy1509/Jarkom-Modul-5-B05-2023/assets/115638253/3a4b26d9-77fd-4025-a973-cb388b6e5c3d">
    <img width="357" alt="Cuplikan layar 2023-12-20 205703" src="https://github.com/hilmy1509/Jarkom-Modul-5-B05-2023/assets/115638253/2c55af86-17bf-4857-9ea8-2a777eef7c4f">


### DHCP Relay
himmel
<img width="331" alt="Cuplikan layar 2023-12-20 205923" src="https://github.com/hilmy1509/Jarkom-Modul-5-B05-2023/assets/115638253/cca50dd4-fbe1-42cf-af7b-f31d23d103d4">
fern
  <img width="330" alt="Cuplikan layar 2023-12-20 210032" src="https://github.com/hilmy1509/Jarkom-Modul-5-B05-2023/assets/115638253/0424cd84-8a15-48b7-ba5c-42733d163b3e">

### Web Server
```
echo 'nameserver 192.168.122.1' > /etc/resolv.conf

apt update
apt install netcat -y
apt install apache2 -y
service apache2 start

echo '# If you just change the port or add more ports here, you will likely also
# have to change the VirtualHost statement in
# /etc/apache2/sites-enabled/000-default.conf

Listen 80
Listen 443

<IfModule ssl_module>
        Listen 443
</IfModule>

<IfModule mod_gnutls.c>
        Listen 443
</IfModule>

# vim: syntax=apache ts=4 sw=4 sts=4 sr noet' > /etc/apache2/ports.conf
```









### Soal 1
Agar topologi yang kalian buat dapat mengakses keluar, kalian diminta untuk mengkonfigurasi Aura menggunakan iptables, tetapi tidak ingin menggunakan MASQUERADE.

```
nano .bashrc
iptables -t nat -A POSTROUTING -o eth0 -j SNAT -s 10.11.0.0/20 --to-source 192.168.122.2
echo nameserver 192.168.122.1 > /etc/resolv.conf
```
#### Testing
<img width="380" alt="Cuplikan layar 2023-12-20 214720" src="https://github.com/hilmy1509/Jarkom-Modul-5-B05-2023/assets/115638253/99015f39-95fd-4fc5-b876-2488981489e1">


### Soal 2
Kalian diminta untuk melakukan drop semua TCP dan UDP kecuali port 8080 pada TCP.

```
iptables -A INPUT -p tcp -m multiport ! --dport 8080 -j DROP
iptables -A INPUT -p udp -j DROP
```

#### Testing
<img width="457" alt="Cuplikan layar 2023-12-20 211200" src="https://github.com/hilmy1509/Jarkom-Modul-5-B05-2023/assets/115638253/ff5af55e-172f-4122-b9e7-e4da0875a60d">

### Soal 3
Kepala Suku North Area meminta kalian untuk membatasi DHCP dan DNS Server hanya dapat dilakukan ping oleh maksimal 3 device secara bersamaan, selebihnya akan di drop.

```
iptables -A INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT
iptables -A INPUT -p icmp -m connlimit --connlimit-above 3 --connlimit-mask 0 -j DROP
```
#### Testing


### Soal 4
Lakukan pembatasan sehingga koneksi SSH pada Web Server hanya dapat dilakukan oleh masyarakat yang berada pada GrobeForest.
```
iptables -A INPUT -p tcp --dport 22 -m iprange ! --src-range 10.11.8.3-10.11.11.254 -j DROP
```
#### Testing

### Soal 5
Selain itu, akses menuju WebServer hanya diperbolehkan saat jam kerja yaitu Senin-Jumat pada pukul 08.00-16.00.
```
iptables -A INPUT -m time --weekdays Sat,Sun -j DROP
iptables -A INPUT -m time --weekdays Mon,Tue,Wed,Thu,Fri --timestart 00:00 --timestop 07:59 -j DROP
iptables -A INPUT -m time --weekdays Mon,Tue,Wed,Thu,Fri --timestart 16:01 --timestop 23:59 -j DROP
```
#### Testing


### Soal 6
Lalu, karena ternyata terdapat beberapa waktu di mana network administrator dari WebServer tidak bisa stand by, sehingga perlu ditambahkan rule bahwa akses pada hari Senin - Kamis pada jam 12.00 - 13.00 dilarang (istirahat maksi cuy) dan akses di hari Jumat pada jam 11.00 - 13.00 juga dilarang (maklum, Jumatan rek).

```
iptables -A INPUT -m time --timestart 12:00 --timestop 13:00 --weekdays Mon,Tue,Wed,Thu -j DROP
iptables -A INPUT -m time --timestart 11:00 --timestop 13:00 --weekdays Fri -j DROP
```

#### Testing


### Soal 7
Karena terdapat 2 WebServer, kalian diminta agar setiap client yang mengakses Sein dengan Port 80 akan didistribusikan secara bergantian pada Sein dan Stark secara berurutan dan request dari client yang mengakses Stark dengan port 443 akan didistribusikan secara bergantian pada Sein dan Stark secara berurutan.

```
iptables -A PREROUTING -t nat -p tcp --dport 80 -d 10.11.8.2 -m statistic --mode nth --every 2 --packet 0 -j DNAT --to-destination 10.11.8.2

iptables -A PREROUTING -t nat -p tcp --dport 80 -d 10.11.8.2 -j DNAT --to-destination 10.11.14.146

iptables -A PREROUTING -t nat -p tcp --dport 443 -d 10.11.14.146 -m statistic --mode nth --every 2 --packet 0 -j DNAT --to-destination 10.11.14.146

iptables -A PREROUTING -t nat -p tcp --dport 443 -d 10.11.14.146 -j DNAT --to-destination 10.11.8.2
```

#### Testing


### Soal 8
Karena berbeda koalisi politik, maka subnet dengan masyarakat yang berada pada Revolte dilarang keras mengakses WebServer hingga masa pencoblosan pemilu kepala suku 2024 berakhir. Masa pemilu (hingga pemungutan dan penghitungan suara selesai) kepala suku bersamaan dengan masa pemilu Presiden dan Wakil Presiden Indonesia 2024.

```
iptables -A FORWARD -s 10.11.14.140/30 -d 10.11.8.2 -m time --datestop 2024-06-26 -j DROP
iptables -A FORWARD -s 10.11.14.140/30 -d 10.11.14.146 -m time --datestop 2024-06-26 -j DROP
```

#### Testing

### Soal 9
Sadar akan adanya potensial saling serang antar kubu politik, maka WebServer harus dapat secara otomatis memblokir alamat IP yang melakukan scanning port dalam jumlah banyak (maksimal 20 scan port) di dalam selang waktu 10 menit. (clue: test dengan nmap)

```
iptables -N port_scanning

iptables -A INPUT -m recent --name port_scanning --update --seconds 600 --hitcount 20 -j DROP
iptables -A FORWARD -m recent --name port_scanning --update --seconds 600 --hitcount 20 -j DROP

iptables -A INPUT -m recent --name port_scanning --set -j ACCEPT
iptables -A FORWARD -m recent --name port_scanning --set -j ACCEPT
```

#### Testing


### Soal 10
Karena kepala suku ingin tau paket apa saja yang di-drop, maka di setiap node server dan router ditambahkan logging paket yang di-drop dengan standard syslog level.

```
iptables -A INPUT  -j LOG --log-level debug --log-prefix 'Packet Log' -m limit --limit 1/second --limit-burst 10
```

#### Testing






