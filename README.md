# Step Install

1. Update

```
apt update && apt upgrade -y && reboot
```

2. Download SC

```
wget https://raw.githubusercontent.com/fferry98/xray-443-80/main/sc
```

3. Install SC

```
bash sc
```

4. NOTE

   a. Jika salah satu path protokol adalah *, maka path protocol lain harus /path, /path1, dst.

   b. Jika salah satu path adalah */path, maka path lain bisa */path1, */path2, dst.

   c. Jika menggunakan Core yang official maka samakan path sebelum break; dengan path di config.json

Untuk a gunakan

```
location ~ / {
...
atau
location / {
...
```

untuk b gunakan

```
location ~ /path {
...
location ~ /path1 {
...
```

untuk ubuntu, edit /etc/nginx/nginx.conf bagian user www-data; , menjadi user root; jika ingin akses port 89.

5. WARP

# Add cloudflare gpg key
curl -fsSL https://pkg.cloudflareclient.com/pubkey.gpg | sudo gpg --yes --dearmor --output /usr/share/keyrings/cloudflare-warp-archive-keyring.gpg


# Add this repo to your apt repositories
echo "deb [signed-by=/usr/share/keyrings/cloudflare-warp-archive-keyring.gpg] https://pkg.cloudflareclient.com/ $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/cloudflare-client.list


# Install
sudo apt-get update && sudo apt-get install cloudflare-warp
