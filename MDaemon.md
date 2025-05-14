# 2.Cài đặt và sử dụng
## 2.1.Cài đặt
- Download Mdaemon
  - ```bash
    https://mdaemon.com/pages/downloads-mdaemon-mail-server-free-trial
    ```
  - ![image](https://github.com/user-attachments/assets/e1e1038e-6459-40ec-8e38-fd20f20dadd3)
  - ![image](https://github.com/user-attachments/assets/5912fc2e-8a6c-4d26-ab29-9cdaeb981267)
- Chạy file cài đặt mới tải
  - ![image](https://github.com/user-attachments/assets/3e0e8340-e7ac-4f9d-be48-73b2f0016414)
  - Đồng ý điều khoản -> Nhấn I Agree
  - ![image](https://github.com/user-attachments/assets/80b9a10c-c290-4660-ba57-d97f3f1174cc)
  - Cấu hình thư mục cài đặt
  - ![image](https://github.com/user-attachments/assets/72e65ce1-027e-4ab8-8fc8-f7598228163f)
  - ![image](https://github.com/user-attachments/assets/256b7562-6951-42c2-89e2-77f565d58b9a)
  - ![image](https://github.com/user-attachments/assets/f981baa7-f87f-4fc0-9798-9cc13a182c21)
  - ![image](https://github.com/user-attachments/assets/9abfe326-3a5d-4dc1-bffc-ca547412dc6c)
  - ![image](https://github.com/user-attachments/assets/a3e5da9d-0574-4ea5-9340-e48fb6c94ee1)
  - Kiểm tra mail nhận key và điền
  - ![image](https://github.com/user-attachments/assets/d9740330-f5ea-49e0-bb21-9cc17ffd3139)
  - ![image](https://github.com/user-attachments/assets/395d8ded-0d26-42ad-9382-49e9f351728e)
  - ![image](https://github.com/user-attachments/assets/a3f2a919-a09e-4aef-a85b-cb779d54319b)
  - ![image](https://github.com/user-attachments/assets/3f7eafae-c6be-4739-94c8-f2be764433a9)
  - Cấu hình Domain
  - ![image](https://github.com/user-attachments/assets/3605cf30-611a-4279-87ab-522a7b7fc615)
  - Cấu hình User
  - ![image](https://github.com/user-attachments/assets/779b2335-d3d8-411e-b5a4-bf767a0a1a30)
  - ![image](https://github.com/user-attachments/assets/8b79b809-df06-479a-af0b-c52e0199274b)
  - ![image](https://github.com/user-attachments/assets/eb4b7b87-bc1a-4078-86e1-00be8f27a154)
  - ![image](https://github.com/user-attachments/assets/1a2abbc2-90db-4292-b77a-80426b637eaf)
  - License Trial được kích hoạt
  - ![image](https://github.com/user-attachments/assets/58650fe0-8602-4941-b145-16caf3be3c4b)
  - Chỉnh sửa file hosts C:\Windows\System32\drivers\etc\hosts thêm dòng
  - ![image](https://github.com/user-attachments/assets/1e8c5dd0-f260-478c-9233-d8eb69fb0c84)
  - Kiểm tra đăng nhập vào webmail
  - ![image](https://github.com/user-attachments/assets/eaac6e0b-2219-4f34-bf43-4e3e9354b887)
  - ![image](https://github.com/user-attachments/assets/dcf175b8-96d5-497a-8fd8-7905d678896b)
  - ![image](https://github.com/user-attachments/assets/e925b5d2-6248-4d8a-88bd-8169b2ee4d97)
## 2.2.Sử dụng
### 2.2.1 Truy cập admin và enduser
- Admin
- Truy cập web admin tại http://localhost:1000/
  - ![image](https://github.com/user-attachments/assets/1fb0492a-e132-4e52-813b-74b694fe31ee)
  - ![image](https://github.com/user-attachments/assets/32e79e25-d3fb-4dde-b266-1586c6e3e41c)
- Enduser
  - Truy cập web mail tại http://mail.qtrung.com/
  - ![image](https://github.com/user-attachments/assets/1c491ac8-1427-4d91-aff1-a0006735b571)
### 2.2.2 Các port cần thiết được sử dụng trên email server Mdaemon
- ```bash
  - SMTP inbound / outbound port - 25
  - MSA inbound port - 587
  - ODMR inbound port - 366
  - SMTP SSL port - 465
  - ActiveSync port - 80
  - ActiveSync SSL port - 443
  - POP3 inbound / outbound port - 110
  - IMAP inbound port - 143
  - POP3 SSL port - 995
  - IMAP SSL port - 993
  - DNS outbound port - 53
  - Remote Administration port - 1000
  - Remote Administration SSL port - 444
  - WorldClient port - 3000
  - WorldClient SSL port - 443
  - Minger port - 4069
  - XMPP port - 5222
  - XMPP SSL port - 5223
  - BOSH port (Webmail IM) - 7070
  - BOSH SSL port (for Webmail IM) - 7443
  ```
### 2.2.3 Khởi tạo domain, user, group, Alias, Mailing lists email
- Khởi tạo Domain
  - Trên WindowsServer mở Open MDaemon Configuration Session
  - ![image](https://github.com/user-attachments/assets/47d636d9-d287-49c5-a8e0-7c753e34f2c4)
  - Chọn icon Domain Manager
  - ![image](https://github.com/user-attachments/assets/6fe92dca-291f-4c22-b3fa-9c087283b888)
  - Click chọn New Domain để khởi tạo Domain mới.
  - ![image](https://github.com/user-attachments/assets/6481b567-7e26-4e74-91c1-a6e0738126d7)
  - ![image](https://github.com/user-attachments/assets/1c6fa11e-46f9-4e50-bc05-aae48c02b865)
  - Cấu hình hostname
  - ![image](https://github.com/user-attachments/assets/d35d0b5b-2318-4a6d-8195-378bddcc4ebe)
  - Thêm user để test tại phần accounts
  - ![image](https://github.com/user-attachments/assets/d9eac888-143e-4f93-a354-2d985166ab71)
  - ![image](https://github.com/user-attachments/assets/6bbcc741-0a93-47cc-bd6f-a7f85da778df)
  - ![image](https://github.com/user-attachments/assets/55296ad5-c256-4f2b-a186-56604bf8dd89)
  - Chỉnh sửa file hosts C:\Windows\System32\drivers\etc\hosts thêm dòng
  - ```bash
    192.168.88.153	mail.qtrung.vn
    ```
  - ![image](https://github.com/user-attachments/assets/8a653804-7bab-488f-952a-acfb9e295755)
  - Test login webmail với account, domain mới tạo. Truy cập web mail tại https://mail.qtrung.vn/
  - ![image](https://github.com/user-attachments/assets/59053359-c7c2-4866-9008-1f1ddd7106fe)
  - ![image](https://github.com/user-attachments/assets/73a097d3-6141-4ad7-9f28-91da8a9ff7f9)





















