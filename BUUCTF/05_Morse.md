**5.Morse**

![](https://i.imgur.com/Acplmx7.png)

-   Mô tả: Chall này sẽ giúp ta giải mã được mã Morse

-   Đây là bảng chữ cái mã hóa Morse:

![](https://i.imgur.com/gWpEOid.png)![](https://i.imgur.com/2yHn40a.png)![](https://i.imgur.com/00mxnc8.png)

-   Chall cho ta 1 đoạn dữ liệu data = .. .-.. --- ...- . -.-- --- ..-

-   Cái này thì ta dùng tools cho nó nhanh https://www.dcode.fr/morse-code

-   Nhập dữ liệu vào rồi chọn TRANSLATE AUTOMATICALLY ta được như sau:
![](https://i.imgur.com/ZmndqsV.png)

-   Chắc chắn là ILOVEYOU rồi <3
-   Ngoài ra, nếu bạn không thích dùng tools, thì ta có đoạn code như sau:
```
morse_dict = {'.-': 'A', '-...': 'B', '-.-.': 'C', '-..': 'D', '.': 'E',
              '..-.': 'F', '--.': 'G', '....': 'H', '..': 'I', '.---': 'J',
              '-.-': 'K', '.-..': 'L', '--': 'M', '-.': 'N', '---': 'O',
              '.--.': 'P', '--.-': 'Q', '.-.': 'R', '...': 'S', '-': 'T',
              '..-': 'U', '...-': 'V', '.--': 'W', '-..-': 'X', '-.--': 'Y',
              '--..': 'Z', '-----': '0', '.----': '1', '..---': '2',
              '...--': '3', '....-': '4', '.....': '5', '-....': '6',
              '--...': '7', '---..': '8', '----.': '9'}

def morse_decode(message):
    message += ' ' # để xử lý trường hợp chuỗi Morse kết thúc bằng tín hiệu dài ('-')
    result = ''
    word = ''
    for char in message:
        if char != ' ':
            word += char
        else:
            result += morse_dict.get(word, '?')
            word = ''
    return result

data='.. .-.. --- ...- . -.-- --- ..-'
print(morse_decode(data))

```
***Flag của bài này là: flag{ILOVEYOU}***