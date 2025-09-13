## Bài tập thực hành
Tạo một image docker bằng docker-composer, cài đặt vnc-server và một desktop environment (Xfce/GNOME/LXDE/LXQt/KDE/…) cho image đó. Thử remote thông qua trình vnc-viewer trên máy

Lưu ý không dùng các image có sẵn các gói nêu trên

Được phép cài các package sau khi đã truy cập được máy ảo

Gợi ý sử dụng ssh để truy cập vào máy ảo rồi mới cài DE
## Cài VNC và DE xfce4
Sử dụng câu lệnh sau để tạo một terminal instance trong container <br>
```docker exec -it w1_remote_vnc /bin/bash```
### Tải DE xfce4 và vncserver
```sudo apt-get install -y nano xfce4 xfce4-goodies tightvncserver dbus-x11```
### config file cấu hình `~/.vnc/xstartup` cho xfce4
```
#!/bin/bash
xrdb $HOME/.Xresources
startxfce4 &
```
### Khởi chạy vncserver lần đầu và setup mật khẩu 
```vncserver```
## Tại máy client 
install vncviewer -> vncviewer localhost:5901

