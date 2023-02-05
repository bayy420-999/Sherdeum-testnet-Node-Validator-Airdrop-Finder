# Tutorial Sherdeum Node Airdrop Finder

ef="https://t.me/airdropfind" target="_blank">Join Telegram Airdrop Finder<img src="https://user-images.githubusercontent.com/50621007/183283867-56b4d69f-bc6e-4939-b00a-72aa019d1aea.png" width="30"/></a>
</p>

<p align="center">
  <img height="auto" width="auto" src="https://raw.githubusercontent.com/bayy420-999/airdropfind/main/NavIcon.png">
</p>

## Referensi

* [Website](https://www.shardeum.org/)
* [Dokumen resmi](https://docs.shardeum.org/node/run/validator)
* [RPC](https://docs.shardeum.org/Network/Endpoints#connect-wallet)
* [Faucet](https://docs.shardeum.org/Faucet/Claim#shardeum-faucet-website)
* [Discord](https://discord.com/invite/shardeum)

## Spesifikasi Software & Hardware

### Persyaratan Hardware

| Komponen | Spesifikasi minimal |
|----------|---------------------|
|CPU|4 Cores|
|RAM|16 GB DDR4 RAM|
|Penyimpanan|250 GB SSD|
|Koneksi|10Mbit/s port|

| Komponen | Spesifikasi rekomendasi |
|----------|---------------------|
|CPU|32 Cores|
|RAM|32 GB DDR4 RAM|
|Penyimpanan|2 x 1 TB NVMe SSD|
|Koneksi|1 Gbit/s port|

### Persyaratan Software/OS

| Komponen | Spesifikasi minimal |
|----------|---------------------|
|Sistem Operasi|Ubuntu 16.04|

| Komponen | Spesifikasi rekomendasi |
|----------|---------------------|
|Sistem Operasi|Ubuntu 22.04|

## Setup

### Install docker

Jika kalian kalian pernah ikut Q-Blockchain dan testnet node lainnya kemungkinan kalian sudah pernah install docker, jadi bisa skip langkah ini.

1. Update `apt-get` dan install paket yang diperlukan
   ```console
   sudo apt-get update
   sudo apt-get install \
     ca-certificates \
     curl \
     gnupg \
     lsb-release
   ```
2. Tambahkan kunci GPG docker
   ```console
   sudo mkdir -p /etc/apt/keyrings
   curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
   ```
3. Setup repositori
   ```console
   echo \
   "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
   ```
4. Install docker
   ```console
   sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
   ```
5. Cek apakah docker sudah terinstall dengan benar
   ```console
   sudo docker run hello-world
   ```

### Instal dan jalankan Node

1. Download dan install node
   ```console
   curl -O https://gitlab.com/shardeum/validator/dashboard/-/raw/main/installer.sh && chmod +x installer.sh && ./installer.sh
   ```
   Nanti akan ada prompt keluar di terminal
   ```console
   Do you want to run the web based Dashboard? (y/n):
   ```
   Ketik `y`
   ```console
   Set the password to access the Dashboard: 
   ```
   Buat password untuk login `validator dashboard`
   ```console
   Enter the port (1025-65536) to access the web based Dashboard (default 8080): 
   ```
   Langsung pencet enter aja
   ```console
   What base directory should the node use (defaults to ~/.shardeum): 
   ```
   Pencet enter lagi
2. Masuk ke folder node
   ```console
   cd $HOME/.shardeum
   ```
3. Buka shell
   ```console
   ./shell.sh
   ```
4. Nyalakan Validator GUI
   ```console
   operator-cli gui start
   ```
5. Stake SHM di validator dashboard
   1. Pergi ke browser (chrome/kiwi) lalu masukan `http://<IP_VPS>:8080/`
   2. Kalian akan dimintai password, masukan password yang tadi dibuat 
   3. Pilih tab `Maintenance` lalu pencet `Start Node`
   4. Claim faucet [disini](https://faucet-sphinx.shardeum.org/) (Masukan address ERC-20)
   5. Pergi ke validator dashboard lagi, lalu pilih `Settings`
   6. Connect wallet yang sudah diisi faucet tadi menggunakan Metamask 
   7. Pilih `Add stake`, lalu masukan jumlah SHM yang ingin distake 
   8. Konfirmasi tx di Metamask 
   9. Done
