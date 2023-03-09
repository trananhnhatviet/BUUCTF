*8.Quoted-printable**

![](https://i.imgur.com/FkVZLis.png)

-   Mô tả: Chall này sẽ giúp ta hiểu về mã Quoted printable

-   Quoted-printable là một phương thức mã hóa dữ liệu để truyền tải thông tin qua mạng bằng cách sử dụng các ký tự ASCII có sẵn. Phương thức này được sử dụng để mã hóa các dữ liệu không phải ký tự ASCII hoặc các ký tự đặc biệt trong dữ liệu để tránh các lỗi truyền tải hoặc các xung đột bảng mã.

-   Quá trình mã hóa Quoted-printable đơn giản là chuyển đổi các ký tự không phải ASCII hoặc các ký tự đặc biệt thành các ký tự ASCII an toàn. Điều này được thực hiện bằng cách thay thế các ký tự này bằng một chuỗi ba ký tự được bao gồm dấu bằng "=" và hai ký tự thập phân là mã Unicode của ký tự đó. Ví dụ ký tự "a" khi mã hóa bằng Quoted-printable sẽ trở thành "=61". 

-   Thực chất, sau các ký tự '=' thì chính là mã hexadecimal biểu diễn cho ký tự đó, nên nếu chúng ta muốn giải tay thì ta tìm các phần tử có '=' đằng trước và lấy phần tử đứng liền sau nó và decode. Ví dụ ký tự "a" khi mã hóa bằng Quoted-printable sẽ trở thành "=61" và 61 chính là mã hexadecimal biểu diễn cho ký tự 'a'.

-   Chall cho ta 1 đoạn dữ liệu data='=E9=82=A3=E4=BD=A0=E4=B9=9F=E5=BE=88=E6=A3=92=E5=93=A6'

-   Ta bỏ hết dấu bằng đi, decode mã hexa, thu được 1 đoạn bytes và decode theo 'utf-8'.
-   Đoạn code sẽ như sau: 

```
from binascii import*

data='=E9=82=A3=E4=BD=A0=E4=B9=9F=E5=BE=88=E6=A3=92=E5=93=A6'
string = data.replace('=','')
print(unhexlify(string).decode('utf-8'))

```
***Flag của bài này là: 那你也很棒哦***
//là chứ Trung Quốc lmao :))))