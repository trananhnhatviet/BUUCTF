**7.Super Caesar**

![](https://i.imgur.com/XesfbVW.png)

-   Mô tả: Chall này sẽ giúp ta hiểu thêm về mã Caesar

-   Chall cho ta 1 đoạn dữ liệu data='afZ_r9VYfScOeO_UL^RWUc'

-   Nếu ta giải như chall trước thì chắc chắn không ra rùi :v

-   data khi decrypt chắc chắn sẽ là dạng flag{gì đó ở trong} nên ta thấy:
    +   a + 5 --> f
    +   f + 6 --> l
    +   Z + 7 --> a
    +   _ + 8 --> g theo như bảng ascii
    ![](https://i.imgur.com/HT2Slzl.png)

-   Qua đó ta thấy key ban đầu sẽ bằng 5 và sau đó tịnh tiến lên 1 cho đến khi chạy hết ký tự trong data

-   Đoạn code sẽ như sau:
```
data='afZ_r9VYfScOeO_UL^RWUc'
key=5
flag=""
for i in data:
    flag = flag + chr(ord(i)+key)
    key=key+1
print(flag)
```
***Flag của bài này là: flag{Caesar_variation}***