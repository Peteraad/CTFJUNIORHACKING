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














  






