***3.URL***

![](https://i.imgur.com/Mi5hde1.png)

-   Mô tả: Chall này chả giúp ta biết cách decode 1 url 

-   Ta nhận được 1 đoạn url:'%66%6c%61%67%7b%61%6e%64%20%31%3d%31%7d'

-   Để decode được, ta vào trang web https://www.urldecoder.org/

-   Nhập mã url vào và chọn decode, ta sẽ thu được flag như hình:

![](https://i.imgur.com/dgx8g8z.png)

-   Ngoài ra, nếu bạn không thích dùng tools, thì ta có đoạn code như sau:
```
import urllib.parse

encoded_url = "%66%6c%61%67%7b%61%6e%64%20%31%3d%31%7d"
decoded_url = urllib.parse.unquote(encoded_url)

print(decoded_url)
```
***Flag của bài này là: flag{and 1=1}***