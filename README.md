# Intro
Mở Port trên Ubuntu nhằm nhiều mục đích khác nhau nhưng đa số là nhằm các mục đích dưới đây:

Cung cấp dịch vụ: Mở port cho phép máy chủ của bạn cung cấp các dịch vụ và ứng dụng cho các máy khách khác trên mạng. <br>
Ví dụ:<br>
- **Mở port 80** để cung cấp dịch vụ web
- **Mở port 22** cho phép truy cập qua giao thức SSH.<br>
Chia sẻ tệp tin: Mở port cho phép chia sẻ tệp và thư mục trên mạng nội bộ hoặc qua Internet, ví dụ như 
- **Samba** (port 137-139 và 445) cho chia sẻ tệp trong mạng LAN.
Kết nối từ xa: Mở port cho phép truy cập từ xa vào máy chủ Ubuntu, 
- **SSH** (port 22) để quản lý máy chủ từ xa hoặc VNC (port 5900) để thực hiện kiểm soát từ xa qua giao diện đồ họa.
- **Database Server:** Mở các cổng cho cơ sở dữ liệu như MySQL (port 3306) 
- **PostgreSQL** (port 5432) để cho phép các ứng dụng và máy khách truy cập dữ liệu trong cơ sở dữ liệu.<br>
**Game Server:** Mở cổng cho máy chủ trò chơi để cho phép người chơi kết nối và tham gia trò chơi trực tuyến.

# connect

**Config ssh** <br>

*Install ssh* <br>
<code>apt-get install openssh-server</code> <br>

*Test ssh sever*<br>
<code>service ssh restart</code> <br>

*Test status*<br>
<code>systemctl status ssh</code> <br>

*Run the ss command and it will display output if port 22 opened:*<br>
<code>sudo ss -tulpn | grep :22</code> <br>

<code>sudo lsof -i:22 >/dev/null <br>

if [ $? -eq 0 ]
then
    echo "TCP port 22 opened and sshd is running on Linux"
else
   echo "Sorry: TCP port 22 not found in listing state. Install and enable SSHD service"
fi
</code><br>

*Trước khi mở các cổng, hãy kiểm tra xem cổng nào đang mở hoặc đóng bằng lệnh được đề cập bên dưới.*<br>
<code>sudo ufw status verbose</code><br>


**Cách mở cổng 22 trên Ubuntu**<br>
Cổng 22 cung cấp quyền truy cập quản lý từ xa vào VM và được sử dụng để liên lạc Secure Shell (SSH). Chạy lệnh được đề cập bên dưới để chấp nhận các gói TCP đến cổng 22.

<br> <code>sudo ufw allow 22/tcp <p>
sudo ufw status verbose <p>
sudo ufw allow 80/tcp <p>
sudo ufw allow 443/tcp <p>
sudo ufw allow 53 <p>
 sudo ufw status verbose </code>




