# xray-443-80

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

b. Jika salah satu path adalah */path, maka path lain bisa */path1, *path/2, dst.

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
location ~ /path2 {
```
