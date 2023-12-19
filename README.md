# Jarkom-Modul-5-IT25-2023


## Contents

- [Topology](#topology)


## Subnetting

![Subnetting](https://i.ibb.co/XScHSRh/subnetting.jpg)



### IP Table

| *Nama Subnet*   | *Rute*                                 | *Jumlah IP* | *Netmask* |
| ----------------- | ---------------------------------------- | --------- | ------- |
| A1                | Fern - Switch1 - Revolte                 | 2         | /30     |
| A2                | Fern - Richter                           | 2         | /30     |
| A3                | Himmel - Switch1 - Fern - SchwerMountain | 66        | /25     |
| A4                | Himmel - LaubHills                       | 256       | /23     |
| A5                | Frieren - Himmel                         | 2         | /30     |
| A6                | Frieren - Stark                          | 2         | /30     |
| A7                | Aura - Frieren                           | 2         | /30     |
| A8                | Aura - Heiter                            | 2         | /30     |
| A9                | Heiter - TurkRegion                      | 1023      | /21     |
| A10               | Heiter - Switch3 - Sein - GrobeForest    | 514       | /22     |
| *Total (10 Subnet)* |                                      | *1871*  | */20* |


### Assigning IP from Subnet

| Subnet | Node           | IP                           | Netmask         | Length | NID           | Broadcast      |
|--------|----------------|------------------------------|-----------------|--------|---------------|----------------|
|   A1   | Fern           | 10.76.0.1                  | 255.255.255.252 | /30    | 10.76.0.0   | 10.76.0.3    |
|        | Revolte        | 10.76.0.2                  | 255.255.255.252 | /30    | 10.76.0.0   | 10.76.0.3    |
|   A2   | Fern           | 10.76.0.5                  | 255.255.255.252 | /30    | 10.76.0.4   | 10.76.0.7    |
|        | Richter        | 10.76.0.6                  | 255.255.255.252 | /30    | 10.76.0.4   | 10.76.0.7    |
|   A4   | Himmel         | 10.76.2.1                  | 255.255.254.0   | /23    | 10.76.2.0   | 10.76.3.255  |
|        | LaubHills      | 10.76.2.2 - 10.76.3.255  | 255.255.254.0   | /23    | 10.76.2.0   | 10.76.3.255  |
|   A5   | Frieren        | 10.76.0.13                 | 255.255.255.252 | /30    | 10.76.0.12  | 10.76.0.15   |
|        | Himmel         | 10.76.0.14                 | 255.255.255.252 | /30    | 10.76.0.12  | 10.76.0.15   |
|   A6   | Frieren        | 10.76.0.17                 | 255.255.255.252 | /30    | 10.76.0.16  | 10.76.0.19   |
|        | Stark          | 10.76.0.18                 | 255.255.255.252 | /30    | 10.76.0.16  | 10.76.0.19   |
|   A7   | Aura           | 10.76.0.21                 | 255.255.255.252 | /30    | 10.76.0.20  | 10.76.0.23   |
|        | Frieren        | 10.76.0.22                 | 255.255.255.252 | /30    | 10.76.0.20  | 10.76.0.23   |
|   A8   | Aura           | 10.76.0.25                 | 255.255.255.252 | /30    | 10.76.0.24  | 10.76.0.27   |
|        | Heiter         | 10.76.0.26                 | 255.255.255.252 | /30    | 10.76.0.24  | 10.76.0.27   |
|   A9   | Heiter         | 10.76.8.1                  | 255.255.248.0   | /21    | 10.76.8.0   | 10.76.15.255 |
|        | Turk Region    | 10.76.8.2 - 10.76.15.255 | 255.255.248.0   | /21    | 10.76.8.0   | 10.76.15.255 |
|   A10  | Heiter         | 10.76.4.1                  | 255.255.252.0   | /22    | 10.76.4.0   | 10.76.7.255  |
|        | Sein           | 10.76.4.2                  | 255.255.252.0   | /22    | 10.76.4.0   | 10.76.7.255  |
|        | Grobe Forest   | 10.76.4.3 - 10.76.7.255  | 255.255.252.0   | /22    | 10.76.4.0   | 10.76.7.255  |
|   A3   | Himmel         | 10.76.0.129                | 255.255.255.128 | /25    | 10.76.0.128 | 10.76.0.255  |
|        | Fern           | 10.76.0.130                | 255.255.255.128 | /25    | 10.76.0.128 | 10.76.0.255  |
|        | SchwerMountain | 10.76.0.131                | 255.255.255.128 | /25    | 10.76.0.128 | 10.76.0.255  |


## Topology Setup

![Topoloy](https://i.ibb.co/chWGGgq/topologi.png)


## Node Configuration

### Client Configuration
------------------------------------------------

#### Revolte
bash
auto eth0
iface eth0 inet static
address 10.76.0.2
netmask 255.255.255.252
gateway 10.76.0.1


#### Richter
bash
auto eth0
iface eth0 inet static
address 10.76.0.6
netmask 255.255.255.252
gateway 10.76.0.5


#### SchwerMountain
bash
auto eth0
iface eth0 inet dhcp
address 10.76.0.131
netmask 255.255.255.128
gateway 10.76.0.129


#### LaubHills
bash
auto eth0
iface eth0 inet dhcp
address 10.76.2.2
netmask 255.255.254.0
gateway 10.76.2.1


#### Stark
bash
auto eth0
iface eth0 inet static
address 10.76.0.18
netmask 255.255.255.252
gateway 10.76.0.17


#### TurkRegion
bash
auto eth0
iface eth0 inet dhcp
address 10.76.8.2
netmask 255.255.248.0
gateway 10.76.8.1


#### Sein
bash
auto eth0
iface eth0 inet static
address 10.76.4.2
netmask 255.255.252.0
gateway 10.76.4.1


#### GrobeForest
bash
auto eth0
iface eth0 inet dhcp
address 10.76.4.3
netmask 255.255.252.0
gateway 10.76.4.1


### Router Configuration
----------------------------------------------------------------

#### Fern
bash
auto lo
iface lo inet loopback

auto eth2
iface eth2 inet static
address 10.76.0.1
netmask 255.255.255.252
gateway 10.76.0.129

auto eth1
iface eth1 inet static
address 10.76.0.5
netmask 255.255.255.252

auto eth0
iface eth0 inet static
address 10.76.0.130
netmask 255.255.255.128


#### Himmel
bash
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 10.76.0.14
netmask 255.255.255.252
gateway 10.76.0.13

auto eth1
iface eth1 inet static
address 10.76.2.1
netmask 255.255.254.0

auto eth2
iface eth2 inet static
address 10.76.0.129
netmask 255.255.255.128


#### Frieren
bash
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 10.76.0.22
netmask 255.255.255.252
gateway 10.76.0.21

auto eth1
iface eth1 inet static
address 10.76.0.17
netmask 255.255.255.252

auto eth2
iface eth2 inet static
address 10.76.0.13
netmask 255.255.255.252


#### Heiter
bash
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 10.76.0.26
netmask 255.255.255.252
gateway 10.76.0.25

auto eth1
iface eth1 inet static
address 10.76.8.1
netmask 255.255.248.0

auto eth2
iface eth2 inet static
address 10.76.4.1
netmask 255.255.252.0


#### Aura
bash
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet dhcp

auto eth1
iface eth1 inet static
address 10.76.0.25
netmask 255.255.255.252


auto eth2
iface eth2 inet static
address 10.76.0.21
netmask 255.255.255.252


## Node Routing

#### Fern
bash
echo nameserver 192.168.122.1 > /etc/resolv.conf
route add -net 10.76.0.0 netmask 255.255.255.252 gw 10.76.0.1
route add -net 10.76.0.4 netmask 255.255.255.252 gw 10.76.0.5


#### Himmel
bash
echo nameserver 192.168.122.1 > /etc/resolv.conf
route add -net 10.76.2.0 netmask 255.255.254.0 gw 10.76.2.1
route add -net 10.76.0.128 netmask 255.255.255.128 gw 10.76.0.129
route add -net 10.76.0.0 netmask 255.255.255.252 gw 10.76.0.130
route add -net 10.76.0.4 netmask 255.255.255.252 gw 10.76.0.130


#### Frieren
bash
echo nameserver 192.168.122.1 > /etc/resolv.conf
route add -net 10.76.0.16 netmask 255.255.255.252 gw 10.76.0.17
route add -net 10.76.0.12netmask 255.255.255.252 gw 10.76.0.14
route add -net 10.76.2.0 netmask 255.255.254.0 gw 10.76.0.14
route add -net 10.76.0.128 netmask 255.255.255.128 gw 10.76.0.14
route add -net 10.76.0.0 netmask 255.255.255.252 gw 10.76.0.14
route add -net 10.76.0.4 netmask 255.255.255.252 gw 10.76.0.14


#### Heiter
bash
echo nameserver 192.168.122.1 > /etc/resolv.conf
route add -net 10.76.4.0  netmask 255.255.252.0 gw 10.76.4.1
route add -net 10.76.8.0  netmask 255.255.248.0  gw 10.76.8.1


#### Aura
bash
# Heiter
route add -net 10.76.4.0  netmask 255.255.252.0 gw 10.76.0.26
route add -net 10.76.8.0  netmask 255.255.248.0  gw 10.76.0.26
route add -net 10.76.0.24  netmask 255.255.255.252 gw 10.76.0.26

# Frieren
route add -net 10.76.0.20 netmask 255.255.255.252 gw 10.76.0.22
route add -net 10.76.0.16 netmask 255.255.255.252 gw 10.76.0.22
route add -net 10.76.0.12netmask 255.255.255.252 gw 10.76.0.22
route add -net 10.76.2.0 netmask 255.255.254.0 gw 10.76.0.22
route add -net 10.76.0.128 netmask 255.255.255.128 gw 10.76.0.22
route add -net 10.76.0.0 netmask 255.255.255.252 gw 10.76.0.22
route add -net 10.76.0.4 netmask 255.255.255.252 gw 10.76.0.22


# Soal

1. Agar topologi yang kalian buat dapat mengakses keluar, kalian diminta untuk mengkonfigurasi Aura menggunakan iptables, tetapi tidak ingin menggunakan MASQUERADE.

  - Aura
bash
ETH0_IP=$(ip -4 addr show eth0 | grep -oP '(?<=inet\s)\d+(\.\d+){3}')

iptables -t nat -A POSTROUTING -o eth0 -j SNAT --to-source $ETH0_IP


Karena kita menggunakan IP DHCP sebagai sebagai jalur keluar ke internet, maka kita harus mengambil IP dari eth0 aura sebagai jalur keluar. ip -4 addr show eth0 | grep -oP '(?<=inet\s)\d+(\.\d+){3}' akan mereturn IP dari eth0 Aura

Selanjutnya, untuk menyambungkan ke nat, maka kita masukkan ke NAT Table dengan POSTROUTING chain : iptables -t nat -A POSTROUTING -o eth0 -j SNAT --to-source $ETH0_IP


2. Kalian diminta untuk melakukan drop semua TCP dan UDP kecuali port 8080 pada TCP.

  - GrobeForest, Stark, and Sein
bash
echo 'nameserver 192.168.122.1' > /etc/resolv.conf

apt-get update
apt-get install netcat -y

# Menolak semua koneksi TCP kecuali port 8080
iptables -A INPUT -p tcp --dport 8080 -j ACCEPT
iptables -A INPUT -p tcp -j DROP

# Menolak semua koneksi UDP
iptables -A INPUT -p udp -j DROP




3. Kepala Suku North Area meminta kalian untuk membatasi DHCP dan DNS Server hanya dapat dilakukan ping oleh maksimal 3 device secara bersamaan, selebihnya akan di drop.

  - Revolte & Richter (DHCP server & DNS Server)
bash
# Allow established and related connections
iptables -A INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT

# Limit ICMP connections to 3 per second
iptables -A INPUT -p icmp -m connlimit --connlimit-above 3 --connlimit-mask 0 -j DROP


- --connlimit-above 3 adalah parameter menentukan batas koneksi yang terhubung
- --connlimit-mask 0 adalah parameter menentukan mask


4. Lakukan pembatasan sehingga koneksi SSH pada Web Server hanya dapat dilakukan oleh masyarakat yang berada pada GrobeForest.

  - Sein & Stark (Web Server)
bash
iptables -A INPUT -p tcp --dport 22 -s 10.76.4.0/22 -j ACCEPT
iptables -A INPUT -p tcp --dport 22 -j DROP



5. Selain itu, akses menuju WebServer hanya diperbolehkan saat jam kerja yaitu Senin-Jumat pada pukul 08.00-16.00.
  - Sein & Stark (Web Server)
bash
# Izinkan akses ke Web Server pada senin-jumat pukul 08:00-16:00
iptables -A INPUT -p tcp --dport 80 -m time --timestart 08:00 --timestop 16:00 --weekdays Mon,Tue,Wed,Thu,Fri -j ACCEPT


6. Lalu, karena ternyata terdapat beberapa waktu di mana network administrator dari WebServer tidak bisa stand by, sehingga perlu ditambahkan rule bahwa akses pada hari Senin - Kamis pada jam 12.00 - 13.00 dilarang (istirahat maksi cuy) dan akses di hari Jumat pada jam 11.00 - 13.00 juga dilarang (maklum, Jumatan rek).

  - Konfigurasi Sein & Stark (Web Server)
bash
# Larangan Akses pada hari Senin-Kamis jam 12:00 - 13:00
iptables -A INPUT -p tcp --dport 80 -m time --timestart 12:00 --timestop 13:00 --weekdays Mon,Tue,Wed,Thu -j DROP

# Larangan akses pada hari jumat pada 11:00 - 13:00
iptables -A INPUT -p tcp --dport 80 -m time --timestart 11:00 --timestop 13:00 --weekdays Fri -j DROP



7. Karena terdapat 2 WebServer, kalian diminta agar setiap client yang mengakses Sein dengan Port 80 akan didistribusikan secara bergantian pada Sein dan Stark secara berurutan dan request dari client yang mengakses Stark dengan port 443 akan didistribusikan secara bergantian pada Sein dan Stark secara berurutan.
  - Sein
bash
# Soal 7
iptables -A PREROUTING -t nat -p tcp -d 10.76.4.2 --dport 80 -m statistics --mode nth --every 2 --packet 0 -j DNAT --to-destination 10.76.4.2:80

iptables -A PREROUTING -t nat -p tcp -d 10.76.4.2 --dport 80 -j DNAT --to-destination 10.76.0.14:80


  - Stark
bash
# Soal 7
iptables -A PREROUTING -t nat -p tcp -d 10.76.0.4 --dport 443 -m statistic --mode nth --every 2 --packet 0 -j DNAT --to-destination 10.76.4.2:443

iptables -A PREROUTING -t nat tcp -d 10.76.0.4 --dport 443 -j DNAT --to-destination 10.76.0.14:443


8. Karena berbeda koalisi politik, maka subnet dengan masyarakat yang berada pada Revolte dilarang keras mengakses WebServer hingga masa pencoblosan pemilu kepala suku 2024 berakhir. Masa pemilu (hingga pemungutan dan penghitungan suara selesai) kepala suku bersamaan dengan masa pemilu Presiden dan Wakil Presiden Indonesia 2024.

  - Sein
bash
### apabila ingin meng-drop TCP 
iptables -A INPUT -p tcp -s 10.76.0.2 --dport 80 -m time --datestart 2023-10-19T00:00 --datestop 2024-02-15T00:00 -j DROP

### namun ingin drop semua, bisa digunakan :
iptables -A INPUT -s 10.76.0.2 -m time --datestart 2023-10-19T00:00 --datestop 2024-02-15T00:00 -j DROP



9. Sadar akan adanya potensial saling serang antar kubu politik, maka WebServer harus dapat secara otomatis memblokir  alamat IP yang melakukan scanning port dalam jumlah banyak (maksimal 20 scan port) di dalam selang waktu 10 menit. (clue: test dengan nmap)

  - Sein
bash
# Soal No 9
iptables -A INPUT -p tcp --syn -m recent --name portscan --set
iptables -A INPUT -p tcp --syn -m recent --name portscan --rcheck --seconds 600 --hitcount  20  -j  DROP


  - Stark
bash
# Soal No 9
iptables -N PORTSCAN
iptables -A PORTSCAN -m recent --set --name portscan
iptables -A PORTSCAN -m recent --update --seconds 600 --hitcount 20 --name portscan -j LOG --log-prefix "Portscan Detected: " --log-level 4
iptables -A PORTSCAN -m recent --update --seconds 600 --hitcount 20 --name portscan -j DROP
iptables -A INPUT -p tcp --tcp-flags SYN,ACK,FIN,RST RST -m limit --limit 2/s -j ACCEPT
iptables -A INPUT -p tcp --tcp-flags SYN,ACK,FIN,RST RST -j PORTSCAN


10. Karena kepala suku ingin tau paket apa saja yang di-drop, maka di setiap node server dan router ditambahkan logging paket yang di-drop dengan standard syslog level.

logging dapat ditambahkan dengan syntax iptables berikut yang dijalankan di semua node server dan router

bash
iptables -A INPUT -j LOG --log-level debug --log-prefix "Dropped Packet: " -m limit --limit 1/second --limit-burst 10
