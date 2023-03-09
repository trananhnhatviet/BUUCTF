**4.Caesar***

![](https://i.imgur.com/iVCZlKa.png)

-   Mô tả: Chall này giúp ta biết cách Caesar là gì và cách giải mã nó

-   Caesar là gì:
    +   Mật mã Caesar là một phương pháp mã hóa đơn giản bằng cách dịch chuyển các ký tự trong bảng chữ cái. 
    +   Cách thực hiện mã hóa Caesar như sau:

        +   Chọn một giá trị số nguyên k bất kỳ từ 1 đến 25 (k có thể là bí mật).

        +   Chuyển đổi mỗi ký tự trong thông điệp ban đầu theo quy tắc sau:

        +   Với mỗi chữ cái, dịch chuyển nó k vị trí trong bảng chữ cái. Ví dụ, với k = 3, chữ A sẽ được mã hóa thành D, chữ B sẽ được mã hóa thành E, và cứ như vậy.

        +   Nếu ký tự đó là khoảng trống, hoặc là dấu câu, không thực hiện bất kỳ thay đổi nào.

        +   Sau khi mã hóa, gửi tin nhắn được mã hóa đến người nhận. Người nhận sẽ sử dụng giá trị k đó để giải mã tin nhắn.

    +   Để giải mã một tin nhắn được mã hóa bằng phương pháp Caesar, người nhận chỉ cần dịch chuyển các ký tự ngược lại k vị trí trong bảng chữ cái. Ví dụ, nếu k = 3, chữ D sẽ được giải mã thành A, chữ E sẽ được giải mã thành B, và cứ như vậy.

-   Ở chall này, ta nhận được 1 đoạn dữ liệu là data='synt{5pq1004q-86n5-46q8-o720-oro5on0417r1}
'

-   Ta có thể vào tool này để decrypt https://www.dcode.fr/caesar-cipher

-   Nhập data vào và chọn decrypt
![](https://i.imgur.com/CE9gXw9.png)
-   Ta thấy được rất nhiều kết quả hiện ra vì đang dùng BruteForce
    ![](https://i.imgur.com/FAaD8bP.png)
-   Và chắc chắn flag là cái đầu tiên rồi :v:

-   Ngoài ra, nếu bạn không thích dùng tools, thì ta có đoạn code như sau:
```
def caesar_decrypt(ciphertext, k):
    plaintext = ""
    for i in range(len(ciphertext)):
        char = ciphertext[i]
        # kiểm tra nếu char là chữ cái
        if char.isalpha():
            # giải mã ký tự và thêm vào chuỗi plaintext
            plaintext += chr((ord(char) - k - 65) % 26 + 65) if char.isupper() else chr((ord(char) - k - 97) % 26 + 97)
        else:
            # nếu không phải là chữ cái thì giữ nguyên ký tự đó
            plaintext += char
    return plaintext

data='synt{5pq1004q-86n5-46q8-o720-oro5on0417r1}'
for i in range(30): 
    #vì mình không biết k là bao nhiêu nên cho nó vào vòng for
    print(caesar_decrypt(data,i))

```
***Flag của bài này là: flag{5cd1004d-86a5-46d8-b720-beb5ba0417e1}***