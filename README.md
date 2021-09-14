# WRITE UP CTF JUNIOR HACKING TALENTS
## PHẦN I: CRYPTO
### Bài 1: Mã ROT và Bases 
Bạn đang giải mã một cuốn sách cổ. Đây là trang đầu của cuốn sách:
> ROT13 and bases = ez cipher

> Code: Zrffntr fnh qn qhbp rapbqr onat onfr64: "JaWzMz50pvOzozttpJ4tpJuvpPOlLKOvpKVto25uqPOiozMlAGt6VPWOM3H4E1DkpRk1oxAynQSSJGLmqmMjAwqKBHA3Hmy6GRqyrSywp0gwG2kHZJgbLz1Kq1S6MxuioRImA0Zv"

> ![image](https://user-images.githubusercontent.com/90112096/132126503-e32978de-cebb-4db5-9c0a-6fe1abf51a57.png)

#### ***Cách giải:***

Bước 1: Vào trang rot13.com decode ra :
> Message sau da duoc encode bang base64: "WnJmZm50ciBmbmggcW4gcWhicCByYXBicXIgb25hdCBvbmZyNTg6ICJBZ3U4R1QxcEx1bkNlaDFFWTYzdzZwNjdXOUN3Uzl6TEdleFljc0tjT2xUMWtoYm1Xd1F6ZkhvbEVzN0Mi"

Bước 2: Vào trang https://www.base64decode.org/ decode ra:
> Zrffntr fnh qn qhbp rapbqr onat onfr58: "Agu8GT1pLunCeh1EY63w6p67W9CwS9zLGexYcsKcOlT1khbmWwQzfHolEs7C"

Bước 3: Quay lại trang rot13.com decode ra đoạn mã trên ra: 
> Message sau da duoc encode bang base58: "Nth8TG1cYhaPru1RL63j6c67J9PjF9mYTrkLpfXpByG1xuozJjDmsUbyRf7P"

Bước 4 Vào trang https://www.dcode.fr/base-58-cipher decrypt ta được Flag:
> **CTF{3NCODING_DOES_N0T_K33P_C0NFIDENTIAL1TY}**

### Bài 2: Mã Morse bất thường:
Lật tiếp sang trang thứ hai, em phát hiện một loại mật mã rất quen thuộc tuy nhiên…có chút gì đó khác thường.
> NEW MORSE CODE - CAN YOU READ IT?

> XYXY X YYXY { X YYYY Y _ XX XXX YXY YYY Y _ XYXX XXX YYX _ XYX XY XXX YXX _ X YYYY Y _ XX XXX YXY Y _ XYXX XXX YYX _ XYX XY XXX YXX }

> ![image](https://user-images.githubusercontent.com/90112096/132126739-032bb1cb-0bfa-4074-a0ae-d070bcff8d3b.png)

#### ***Cách giải:***

Bước 1: Do bộ mã Morse chỉ có 2 kí tự là ‘-‘ và ‘.’ . 
> Nên ta quy định X là ‘-‘ và Y là ‘.’.

Bước 2: Theo quy tắc của bộ mã Morse:
> ![image](https://user-images.githubusercontent.com/90112096/132126803-aed8d9d1-cb9c-463e-815a-99b9a2a9a1be.png)

> Ta tìm được flag là **CTF{THE_MORSE_YOU_KNOW_THE_MORE_YOU_KNOW}**

### Bài 3: Mật mã Vigenere
Trang thứ 3 bạn được đưa bản rõ và bản mã, có vẻ như mình cần hiểu thuật toán mã hóa và khôi phục được khóa?
> Plaintext:   HELLOWORLDCRYPTOGRAPHERS

> Ciphertext: HRNTSJHTTSJVPHTFKRWTZSDW

> Flag sẽ có dạng: CTF{<key>}

> ![image](https://user-images.githubusercontent.com/90112096/132126854-16ab7591-9a65-4b46-8deb-615050cfe412.png)

#### ***Cách giải:***
  
Bước 1: Xem file ảnh btc cung cấp:
> ![image](https://user-images.githubusercontent.com/90112096/132126897-f8be138d-e1e0-4298-99ea-3e0c3614ca1c.png)

Bước 2: Theo quy tắc của mật mã Vigenere . Qua Plaintext và Ciphertext cho ở trên ta tìm được:
> ![image](https://user-images.githubusercontent.com/90112096/132126914-dd9726a1-7ad4-45d2-9e28-1086c50b3ae9.png)

>Tương tự như bảng trên ta tìm được Flag là:
**CTF{ANCIENTCIPHERSAREAWESOME}**
  
### Bài 4: Mật mã thay thế
Được biết bản rõ và bản mã của mật mã thay thế ở trang thứ 4 này như sau:
> Message = HELLO WHAT ARE YOU DOING  
> Ciphertext = PYZZC SPFK FEY JCQ ACBHX

Hãy tìm ra nguyên tắc của mật mã thay thế này và giải mã thông điệp dưới đây:
> Ciphertext = DKW{KPBGSFGQGYABHSFE}  
> Message = ???

>![image](https://user-images.githubusercontent.com/90112096/132127171-b13f7ad8-f2da-4ec8-a20d-1a6d887f4540.png)

#### ***Cách giải:***
  
Bước 1: Dựa vào Message và Ciphertext ta tìm được quy luật của bài:
> ![image](https://user-images.githubusercontent.com/90112096/132127223-5daff66c-f18a-4a07-ad86-5ae2e1daf9cd.png)

Bước 2: Dựa vào quy luật tìm được ta giải ra Ciphertext đề cho là :
CTF{THI_WA_U_EDINWAR}
> Do chỉ còn 1 khoảng trống nên ta nhanh chóng đó là S và hoàn hiện Flag là:
> **CTF{THISWASUSEDINWAR}**
  
### Bài 5: XOR
Chỉ bằng một phép toán thao tác bit là XOR, ta đã có thể mã hóa bất kì thông điệp nào. Thật thú vị đúng không nào.
> ![image](https://user-images.githubusercontent.com/90112096/132129504-6a68bd42-8557-4986-94be-805dd5cc4279.png)

> [xor-a6bd2cd40ff271cbe0c790aa80c1e8a3 (4).zip](https://github.com/Peteraad/CTFJUNIORHACKING/files/7111722/xor-a6bd2cd40ff271cbe0c790aa80c1e8a3.4.zip)

#### ***Cách giải:***
Bước 1: Tải file .zip bài đã cho, giải nén ta được file encrypt.py và output.txt.
 
Bước 2: Mở file output.txt, ta được cipher
> Ciphertext: 0xf7c6c18fccc76c0fc0838fc3c64e1428da8fcd4e150ec18fcc6c1c8fdbc74e142c8fcbcaccddd6dfdb8f6b3e691f4e140ccc8fecfbe9d4fafbe99782e2eef682fcecfd9cf882f69ffad28fc4c76c1bc1c88fc1c74e142690a5

Bước 3: Copy ciphertext và encrypt bằng trang https://www.dcode.fr/xor-cipher. Xem các kết quả và ta tìm được flag như hình
> ![image](https://user-images.githubusercontent.com/90112096/132129685-8b7e0c47-bd08-45ce-a126-c19876123c9f.png)
> **CTF{UTF8-MAY-SCR3W-Y0U}**

## PHẦN II: BINARY
### Bài 1: Con trỏ
Dưới đây là đoạn mã nguồn bằng ngôn ngữ lập trình C. Em hãy cho biết giá trị của biến b là bao nhiêu?
> int buffer[3] = {0x1234,0x2456,0x4567};
 
> int *a = buffer;

> int b = a[2]*0x4141;

> Ví dụ: Giá trị của b là 0x1A thì flag sẽ là CTF{0x1A} (in hoa tất cả)
  
> ![Capture](https://user-images.githubusercontent.com/90112096/132130196-615466e7-1cf4-401a-a210-4fa714d7ae85.PNG)
 
#### ***Cách giải:***
Bước 1: Ta thấy con trỏ a mang giá trị của mảng buffer mà b lại là a[2]*0x4141 

Bước 2: Tức rằng b=0x4567*0x4141=0x11B0C627
> Vậy flag là **CTF{0x11B0C627}**

### Bài 2: LIFO
Ở độ khó tiếp theo, đoạn mã hợp ngữ trở nên dài hơn. Em hãy tính toán và tìm ra kết quả của thanh ghi EBX sau khi thực thi 4 lệnh hợp ngữ dưới đây:
> MOV  EAX,0x41414141

> PUSH EAX
  
> POP  EBX

> SUB  EBX,0x2A

> Ví dụ: Kết quả của thanh ghi EBX là 0x1A thì flag sẽ là CTF{0x1A} (in hoa tất cả)

> ![Capture1](https://user-images.githubusercontent.com/90112096/132130374-58663cd6-6c75-4ff6-978a-568ce40af539.PNG)

#### ***Cách giải:***
Bước 1: Ta thấy EBX= 0x41414141- 0x2A =0x41414117 do là SUB

Bước 2: Flag cần tìm là  **CTF{0x41414117}**

### Bài 3: Hợp ngữ
Em tìm thấy một máy tính cổ ra đời năm 19xx, thân máy vẫn còn bám bụi, ngay cả nhựa của vỏ máy cũng nhuốm màu vàng của sự cũ kỹ.

Trên màn hình máy tính CRT, hiện lên 2 dòng mã nguồn hợp ngữ. Em hãy tìm ra kết quả của thanh ghi EAX sau khi thực thi đoạn hợp ngữ này nhé:

> MOV EAX, 0x3A  

> ADD EAX, 0x21

>Ví du: EAX là 0x1A thì flag sẽ là CTF{0x1A}
  
> ![image](https://user-images.githubusercontent.com/90112096/132130407-ceb05cfb-7624-4b48-a6aa-3bb7a2350df0.png)

#### ***Cách giải:***
Bước 1: ta thấy EAX = 0x21+0x3A =0x5B do là ADD

Bước 2: Vậy flag cần tìm là **CTF{0x5B}**

## PHẦN III: NETWORK
### Bài 1: HTTP 101
Được biết rằng có một website có tên miền là: http.kid.cyberjutsu-lab.tech với cổng mạng 5555.
Em có thể truy cập vào nó không?

> ![image](https://user-images.githubusercontent.com/90112096/132130498-6fd73bba-a02e-4b5b-b3a2-8b32df20e7a9.png)

#### ***Cách giải:***
Bước 1: Do đề bài đã cho port của trang web là 5555 thì đơn giản ta chỉ cần truy cập: http.kid.cyberjutsu-lab.tech:5555

Bước 2: Tìm được flag là **CTF{Hypertext_Transfer_Protocol}**
 
### Bài 2: Domain name system 101
Tên miền onepiece.kid.cyberjutsu-lab.tech đang được phân giải đến một địa chỉ IP trên Internet. Em hãy tìm ra nó nhé!

> Định dạng flag là CTF{địa chỉ IP của tên miền}

>![image](https://user-images.githubusercontent.com/90112096/132130544-1a68f87d-edeb-4b92-8b0f-0ecc5a49095e.png)

#### ***Cách giải:***
Bước 1: Vào trang https://domaintoipconverter.com/index.php tìm kiếm với domain đã cho ta tìm được ip:  93.13.33.22

Bước 2: Flag cần tìm là **CTF{93.13.33.22}**

### Bài 3: Socket 101
Có một bí mật đang được cất giữ tại máy chủ có địa chỉ IP là 167.71.204.85 trên cổng mạng 7878 bằng giao thức TCP. Em hãy kết nối đến để xem bí mật cho manh mối kế tiếp là gì!

> ![image](https://user-images.githubusercontent.com/90112096/132130591-62c71786-37e5-4635-91ab-367538aa62ae.png)

#### ***Cách giải:***
Bước 1: Sử dụng netcat để truy cập đến  IP là 167.71.204.85 trên cổng mạng 7878 bằng giao thức TCP

Bước 2: Sau đó ta tìm được flag qua hình dưới đây:
> ![image](https://user-images.githubusercontent.com/90112096/132130655-a9b4eb73-d943-42ac-9a2d-1f754f36d7ab.png)
  
> **CTF{connect_to_somewhere}**
  
### Bài 4: File Sharing
Em đã bao giờ nghe về giao thức FTP chưa?
Hãy sử dụng tài khoản user với mật khẩu là network. Sau đó, thực hiện kết nối đến máy chủ 167.71.204.85 ở dịch vụ FTP để xem bí mật là gì nhé!

> ![image](https://user-images.githubusercontent.com/90112096/132130702-270e4098-921b-4f93-812c-1fa36b233d62.png)
  
#### ***Cách giải:***
Bước 1: Mở cmd nhập prompt -> ftp -> open -> 167.71.204.85 và nhập user password đề đã cho . Thế là ta đã kết nối đến máy chủ.
> ![image](https://user-images.githubusercontent.com/90112096/132130777-e6837d22-c97b-4802-89ea-8bc13d9b5421.png)

Bước 2: Dùng câu lệnh dir để xem list files và ta tìm được file flag.txt. Sau đó dùng get flag.txt để lấy file về thư mục user 
> ![image](https://user-images.githubusercontent.com/90112096/132130804-089273c6-a8ed-457f-a20b-8017c8633111.png)

Bước 3: Mở file flag.txt ta tìm được flag là **CTF{File_Transfer_Protocol}**

### Bài 5: Packet capture 101
Tập tin em đang có trong tay chính là một đoạn trích xuất nội dung gói tin mạng ra vào của máy tính nạn nhân trong khoảng thời gian anh ta bị lừa đảo. Em hãy tìm ra địa chỉ trang web lừa đảo ấy là gì và gửi ngay cho BTC nhé!

Ví dụ:
> Trang web lừa đảo là http://luadao.com thì

> Định dạng flag sẽ là CTF{http://luadao.com}

> ![image](https://user-images.githubusercontent.com/90112096/132130841-2240c34d-2c0d-4b23-b391-238d9b0b221b.png)

FILE: **https://file.io/ZNqzxmzJFoq2**
  
#### ***Cách giải:***
Bước 1: Sử dụng WireShark để đọc file bài đã cho, sau đó ta đọc từng tập tin.

Bước 2: Cuối cùng ta tìm được tập tin có địa chỉ trang web cũng như là flag của bài
> ![image](https://user-images.githubusercontent.com/90112096/132130912-e76690bb-f340-4cd1-89ae-cda2a0fb17c1.png)

Bước 3: Địa chỉ trang web cần tìm là https://xacminhgarenavn.xyz
> Flag bài này là **CTF{https://xacminhgarenavn.xyz}**
  
## PHẦN IV: FORENSICS
### Bài 1: Mật thư trong ảnh
Người chơi Z! Không gian mạng chứa rất nhiều loại tri thức và thông tin. Có hàng ngàn loại tập tin, hàng ngàn giao thức khác nhau. Là một người điều tra chứng cứ số, bạn không thể nào biết hết được nó. Nhưng hãy tập luyện cho mình một tư duy nhạy bén, một óc quan sát nhanh nhạy!

Hãy tìm ra thông điệp ẩn nằm trong bức ảnh này.

File ảnh : https://cdn.cjstatic.com/kidctf/forensics/easy_1_basic_hidden/image-5c8ba6fbe0337c1781072b9b47cf213d.png

> ![image](https://user-images.githubusercontent.com/90112096/132131053-30b77639-1c98-4895-974c-ab7218324860.png)

#### ***Cách giải:***
Bước 1: Tải file ảnh mà đề bài đã cung cấp về

Bước 2: Open file with Notepad, tìm keyword ‘CTF’ thì ta tìm được flag của bài là **CTF{I_was_here_all_the_time}**
> ![image](https://user-images.githubusercontent.com/90112096/132131075-4c056042-626c-4fb0-bccc-ce09dbb5a98a.png)

### Bài 2: Ổ đĩa hỏng
Trong quá trình sao lưu dữ liệu, một phần của ổ cứng đã bị hư hại. Chỉ còn sót lại duy nhất một tập tin đã bị mất phần đuôi (file extension). Người chơi Z! Bạn có thể giúp chúng tôi xác định đây là tập tin gì và khám phá ra bí mật bên trong không?

> ![image](https://user-images.githubusercontent.com/90112096/132131095-0d9197d8-9f5a-48a3-9b5e-e41edb178d96.png)

File:https://file.io/tByFz5jK3mP7

#### ***Cách giải:***
Bước 1: Vào trang https://www.toolsley.com/file.html để tìm đuôi của file và tìm được là .zip
> ![Capture](https://user-images.githubusercontent.com/90112096/132131332-3aa001ae-ea8b-4a61-9e31-0e7563d92f3f.PNG)
  
Bước 2: Thêm tên file đuôi .zip sau đó giải nén ra ta được file hình và cũng là flag của bài
> ![secret](https://user-images.githubusercontent.com/90112096/132131360-e3d59d4d-6457-4470-9b19-90aadddd574a.jpg)

> Flag của bài này là **CTF{You_cannot_see_me}**

### Bài 3: Trốn tìm
Lần theo manh mối của các thử thách trước, em phát hiện ra có một máy tính đang được khởi động. Bỗng nhiên bảng điều khiển của hệ điều hành Linux được bật lên.
Một dòng chữ hướng dẫn hiện ra...
________________________________________
https://ssh.kid.cyberjutsu-lab.tech/ssh/host
username: player
password: player

> ![image](https://user-images.githubusercontent.com/90112096/132131423-8fef8c01-df24-428b-9ad9-211a587976a4.png)

#### ***Cách giải:***
Bước 1: Truy cập đường link nhập user và password đã cho.

Bước 2. Dùng câu lệnh find / -type f để tìm xem các file thường xuyên được sử dụng ở trong máy tính này ko và ta tìm được file secret/secret2/getFlag mà để bài cần tìm
> ![image](https://user-images.githubusercontent.com/90112096/132188950-d1f4a174-9f4a-4748-84f8-10ed70a9470d.png)

Bước 3: Truy cập vào thư mục secret2 bằng câu lệnh cd secret/secret2 . Sau đó ta dùng câu lệnh ./getFlag | grep CTF để mở và tìm chữ "CTF", sau đó ta tìm được flag của bài là
**CTF{now_you_know_grep}**

> ![image](https://user-images.githubusercontent.com/90112096/132189303-84333ad5-1eb1-4464-a061-d63b72efda71.png)

### Bài 4: Dấu vết sót lại
Cũng trong máy tính hệ điều hành Linux từ thử thách trước, thông qua những dấu hiệu được để lại. Em phát hiện ra trước đó đã có một người đã sử dụng máy tính này, có vẻ đây chính là manh mối tiếp theo dẫn đến kho báu.

Quan sát thấy rằng, người bí ẩn ấy có username là "admin". Nhiệm vụ bây giờ của chúng ta là truy vết xem, người bí ẩn "admin" đã làm gì trên máy tính này!

https://ssh.kid.cyberjutsu-lab.tech/ssh/host

username: player
password: player

> ![image](https://user-images.githubusercontent.com/90112096/132131600-2aa0cf2a-ee1e-4b21-b429-c851feed199a.png)

#### ***Cách giải:***
Bước 1: Truy cập vào trang web và đăng nhập bằng tk và mk cho trước.

Bước 2: Sử dụng câu lệnh history để kiểm tra lịch sử câu lệnh đã sử dụng và ta tìm được
> ![image](https://user-images.githubusercontent.com/90112096/132131848-e5576d52-de2d-4081-af89-f2abfe7e6ae4.png)

> **CTF{s0mething_sn34ky_hidd3n}**

## PHẦN V: WEB
### Bài 1: Mật báo
"Người chơi Z! Bạn đã sẵn sàng chưa?" - Tai nghe của bạn phát ra thông báo.
Bỗng nhiên trong một thoáng, bạn đã dịch chuyển tới một nơi rất lạ. Từ từ lấy lại thăng bằng
"Người chơi Z! Đây là chặng thử thách đầu tiên của bạn, trước mắt bạn là một mảnh giấy chứa một bí mật đang được ẩn đi"
________________________________________
http://castle.kid.cyberjutsu-lab.tech/secret.php

> ![image](https://user-images.githubusercontent.com/90112096/132189582-8fc7339c-f14d-48da-a9ba-94dcea066125.png)

#### ***Cách giải:***
Bước 1: Vào trang web và ấn f12 ta tìm được flag của bài: **CTF{4lwayS_1nsP3ct}**

> ![image](https://user-images.githubusercontent.com/90112096/132189662-4e272ffd-6f54-4fb4-8fcd-2c76c7ce0a02.png)

### Bài 2: Chú vẹt thông minh
Có được manh mối từ mảnh giấy kia, bạn vội vàng gấp lại, bỏ vào túi áo khoác của mình và đi lên tầng kế tiếp của tòa lâu đài.
Vừa đi vừa quan sát hành lang của tòa lâu đài này, phần vòm được thiết kế bởi những họa tiết rất tinh xảo. Phỏng đoán vòm này phải cao tận 50m.
"Này này! Người lạ kia"
Đột nhiên, có một tiếng nói với tông giọng rất kì lạ đến từ góc phòng xa xa.
"Đưa cho tôi một thứ, tôi sẽ cho bạn manh mối tiếp theo"
Bạn càng đi gần lại từ nơi âm thanh vọng ra, dần dần nhân vật kia đã lộ diện. Đó chính là... một chú vẹt
"Vẹt?!"
Bạn đáp lại với giọng đầy sự kinh ngạc
"Vâng! tôi có thể nói tiếng người đấy. Này người chơi, đưa cho tôi một miếng "bánh quy" cookie. Tôi sẽ cho bạn chỉ dẫn tiếp theo" - Chú vẹt nhanh nhảu đáp theo.
________________________________________
http://castle.kid.cyberjutsu-lab.tech/cookie.php
 
> ![image](https://user-images.githubusercontent.com/90112096/132189782-f1b95ad1-6999-431b-99d5-6a78fd01904e.png)

#### ***Cách giải:***
Bước 1: Truy cập vào trang web và ấn f12. Sau đó vào network, ta sẽ thấy file cookie.php mở nó ta tìm được dãy **CTF%7BmY_f%40vor1tE_c0Oki3%7D**

> ![image](https://user-images.githubusercontent.com/90112096/132189869-9df7ea75-7ea4-4aa6-aeeb-1ad2a3305194.png)

Bước 2 Sau khi mã hóa các kí tự, ta được flag cần tìm là: **CTF{mY_f@vor1tE_c0Oki3}**	
  
### Bài 3: Hành lang tối
Khắp trong căn phòng bạn đang đứng là những tác phẩm nghệ thuật điêu khắc vừa tinh xảo lại vừa cầu kì. Đồ vật trang trí xung quanh được làm từ gỗ hương, kim loại và vàng, tạo ra một không gian vừa trang trọng lại vừa huyền bí.
Nhưng hãy luôn nhớ rằng, tất cả những thứ trong tòa lâu đài này đều là sản phẩm của những mã lập trình thực tế ảo.
Đi theo lời chỉ dẫn của chú vẹt, bạn bước tới một hành lang mang tên "HTTP Header". Theo lời chú vẹt, trong hàng lang này có một thông điệp đang bị giấu đi. Hãy tìm ra và đọc thật to nó lên, một cánh cổng mới sẽ được mở ra.
________________________________________
http://castle.kid.cyberjutsu-lab.tech/header.php

> ![image](https://user-images.githubusercontent.com/90112096/132190013-f86075ab-db5d-4de1-8e13-7debd1f0d0f1.png)
 
#### ***Cách giải:***
Bước 1: Vào trang https://reqbin.com/ tìm kiếm địa chỉ trang web đề cho.

Bước 2: Vào mục Header ta tìm được:
Server: nginx/1.18.0 (Ubuntu)
Date: Sat, 04 Sep 2021 16:42:39 GMT
Content-Type: text/html; charset=UTF-8
Content-Length: 408
Connection: keep-alive
X-Powered-By: PHP/7.3.29
Secret: CTF{s3crEt_hEaD3r}
Vary: Accept-Encoding
Content-Encoding: gzip
> Flag cần tìm là: **CTF{s3crEt_hEaD3r}**

> ![image](https://user-images.githubusercontent.com/90112096/132190153-bfea082e-02c1-4a04-b9f0-9d705d9fc398.png)

### Bài 4: Rương bí mật
Sau khi đọc to câu thần chú, bỗng nhiên bức tường làm từ đá hoa cương đã rục rịch di chuyển, để lộ ra một gian phòng hoàn toàn mới.
Đưa mắt đảo thật nhanh, bạn thấy một rương đồ được đặt tại một góc phòng. Nhưng thật không may, nó đang bị khóa!
________________________________________
http://castle.kid.cyberjutsu-lab.tech/treasure.php

> ![image](https://user-images.githubusercontent.com/90112096/132190235-6aac3afe-8b60-4677-8066-defbeca44c77.png)

#### ***Cách giải:***
Bước 1: Truy cập vào trang và ấn f12,ta tìm được script là 
> function checkPass(password) {
       
  > if (password[0] != "3")
            return false;
        
  > if (password[1] + 1 != String.fromCharCode(53, 49))
            return false;
        
  > if (password.charCodeAt(5) != 8 * 6)
            return false;
       
  > if (password[2] + password[3] != "62")
            return false;
    
  > if (password[4] - password[0] != 4)
            return false;
        
  > return true;
    }

> ![image](https://user-images.githubusercontent.com/90112096/132190324-8ba0d271-9d19-4cfa-8428-5a2b00080c96.png)

Bước 2: Dựa vào script ta tìm được các số mà đề bài cần
 
> Số đầu tiên là 3

> Số thứ 2 sẽ từ 0-5

> Số thứ 3 là 6

> Số thứ 4 là 2

> Số thứ 5 là 7

> Số thứ 6 là từ 1-9

> Còn hai khoảng trống thay từ từ và cuối cùng mất khẩu ta tìm được là 356270

>  Và Flag tìm được là **CTF{wHy_1+1=11_iN_JS?}**

> ![image](https://user-images.githubusercontent.com/90112096/132190767-bf0ff139-5971-4a61-bfb0-149383766580.png)

## PHẦN VI: PROGRAMMING
###Bài 1: Bất đồng
"Này người chơi Z! Hãy đi theo tôi, tôi sẽ dẫn anh tới gặp robot master" - Robot dẫn tôi đi về phía đường lớn.
Xung quanh là khung cảnh của một thành phố rất hiện đại, những chiếc tàu đang chạy lơ lửng trên bầu trời cùng với những ánh đèn sực sỡ.
"Bạn có thích văn chương không?" - ANA bỗng hỏi.
"Hm..." - Bạn ngập ngừng hồi lâu
"Này nhé! Tôi sẽ đưa bạn 2 tập tin chứa các bài văn, hãy tìm ra TẤT CẢ sự khác nhau của hai tập tin này. Nếu bạn trả lời đúng, tôi sẽ tiếp tục dẫn bạn tới gặp chủ nhân!"

> ![image](https://user-images.githubusercontent.com/90112096/132191166-5aa03d70-4ca6-4532-9a96-961f0867fde7.png)

#### ***Cách giải:***
Bước 1: Vào trang https://www.diffchecker.com/ để check điểm khác biệt của hai text.

Bước 2: Sâu chuỗi những từ khác biệt ta được flag
**CTF{difference_makes_you_difference}**
  
### Bài 2: Đếm chữ số
"Giỏi lắm người chơi Z!" - Robot động viên bạn với ánh mắt đầy hào hứng.

"Câu đố lần này là: 1*2*3*4*5*...*10000, kết quả của nó sẽ có bao nhiêu chữ số?" - ANA liền lập tức đưa ra câu hỏi một cách dứt khoát.

> Flag sẽ có format: CTF{<số chữ số bạn tính được>}

> Ví dụ, giả sử chỉ cần tính 1*2*3*4*5

> Flag sẽ là CTF{3} (vì 1*2*3*4*5 = "120" có 3 chữ số)
  
> ![image](https://user-images.githubusercontent.com/90112096/132195977-400ddebf-33d3-45ab-8e0e-b193443f400f.png)

#### ***Cách giải:***
Bước 1: Viết code tìm số chữ số của kết quả, ta tìm được kết quả có 35660 chữ số
> Flag của bài là **CTF{35660}**

> ![image](https://user-images.githubusercontent.com/90112096/132196249-b3268809-ed05-446f-96d8-200d2f725639.png)

### Bài 3: Trò chơi tính tổng
Trên chuyến tàu để đi đến một vùng đất mới, trạm ga cuối cùng nơi bạn được đưa đến là trước một thế giới rất hiện đại với những ánh đèn neon mang đậm phong cách CyberPunk.
Ngay khi bạn vừa bước chân ra khỏi ga tàu, có một chú robot đang vẫy tay như muốn tìm lấy sự chú ý từ bạn.

> "Chào mừng người chơi Z đến với vùng đất Robot, tôi là robot ANA. Ở mục thử thách này bạn phải tìm lời giải cho những câu đó hóc búa mà nếu không dùng lập trình, sẽ khó lòng vượt ải. Bạn sẵn sàng chưa? Đây là màn đầu tiên. Hãy tính tổng của dãy số trong tập tin này và đưa tôi kết quả!"
  
> Flag sẽ có format: CTF{<tổng bạn tính được>}

Ví dụ:

> Dãy số: 33 77 10 -200

> Flag sẽ là: CTF{-80}
  
> ![image](https://user-images.githubusercontent.com/90112096/132191549-4d64cbcc-9201-4058-8992-f731c48d3d36.png)

File: [dayso.txt](https://github.com/Peteraad/CTFJUNIORHACKING/files/7114742/dayso.txt)

#### ***Cách giải:***
Bước 1: Vào trang https://miniwebtool.com/sum-calculator/ để tính tổng tất cả chữ số

Bước 2 Kết quả là 6474238. Vậy flag là CTF{6474238}

> ![image](https://user-images.githubusercontent.com/90112096/132191630-00b6a812-5cc4-40aa-b839-eab96c44f75c.png)
  
### Bài 4: Socket cơ bản

ANA dừng lại trước cánh cổng của một căn biệt thự nhìn rất hiện đại. Một chú robot ăn mặc như một người quản gia với chiếc nơ màu đỏ sẫm đến trò chuyện với bạn:

"Chào người chơi Z! Cảm ơn robot ANA" - Robot quản gia xoay sang ANA và nói. ANA không quên chào tạm biệt và chúc bạn may mắn.

"Tôi sẽ dẫn bạn tới gặp chủ nhân, nhưng trước hết, chủ nhân tôi muốn bạn giải đố thử thách này. Lần này bạn sẽ không giao tiếp với tôi, mà sẽ phải giao tiếp thông qua socket từ xa với một máy chủ trên Internet"

"Bạn có thể dùng chương trình netcat để tạo kết nối tới máy chủ thông qua câu lệnh: nc 167.71.204.85 20001. Tuy nhiên tôi đã chuẩn bị sẵn một tập tin lập trình Python cho bạn rồi đây."

Robot quản gia liền đưa bạn một tập tin nhằm giúp việc kết nối trở nên dễ dàng hơn.

Tải tệp đính kèm tại đây ↓ : [baby-socket-client-3412512e8af09208b7201fc648aa119f (1).zip](https://github.com/Peteraad/CTFJUNIORHACKING/files/7114756/baby-socket-client-3412512e8af09208b7201fc648aa119f.1.zip)

> Thông tin truy cập: nc 167.71.204.85 20001
  
> ![image](https://user-images.githubusercontent.com/90112096/132192001-6b228417-f887-47fe-8dbe-7e32fcfbba41.png)

#### ***Cách giải:***
Bước 1: Mở file .py mà để bài cho, đọc hiểu code sau đó thực hiện theo yêu cầu đề bài và tìm được flag **CTF{can_you_write_your_own_script?}**
 
> Code : https://pastebin.com/cVPW7PFE
  
> ![image](https://user-images.githubusercontent.com/90112096/132193252-ee463d37-c15f-4128-9a16-347cd2879ab0.png)
  













  






