# J2TEAM CTF Writeups part 2:
###### *10/27/2020*

___
Sau phần 1 được khá nhiều bạn đón nhận thì tiếp tục hôm nay mình sẽ lên phần 2 writeup lần này nhé :v

## Nhiệm vụ 21:
Mô tả nhiệm vụ t sẽ thấy 1 đoạn source code php, nhìn có vẻ để verify flag đó.

![](image/63.png)

Nhìn ta sẽ phát hiện ra vòng lặp for được thực hiện để giảm đi tạo chuỗi mới đảo ngược với chuỗi ban đầu ở đây là flag. Vì vậy ta sẽ thu được flag mới là:

![](image/64.png)

done :3

## Nhiệm vụ 23:
Hmm flag ngay trước mặt submit ngay thoi :v

![](image/65.png)

Có vẻ như không được:

![](image/66.png)

Sau một hồi search googe mình đã tìm ra đó là request submit flag chỉ có thểđược gửi bằng AJAX, thêm header: “X-Requested-With: XMLHttpRequest” vào và submit lại.

Done :3

## Nhiệm vụ 23:
Nhiệm vụ 23 này xem ra không có gì view-source thử thì để ý thấy:

![](image/67.png)

Khi truy cập vào url đó thì:

![](image/68.png)

Oke :3 thế thì mình sẽ mở tab ẩn danh, oh yeah đã tìm thấy flag

## Nhiệm vụ 24:
Nhiệm vụ lần này mình hoàn toàn không thấy gì bất thường phải xem cả hmmm nó được giấu ở đâu nhỉ? Sau 1 hồi lần mò thì mình đã tìm thấy nó ở phần headers reponse của web challenge 24

![](image/69.png)

Nice :3 submit và done.

## Nhiệm vụ 25:
![](image/70.png)

Hmm là 1 repository của github, hãy cùng kiểu tra nhé :3

![](image/71.png)

Trông chẳng thấy có gì mình sẽ kiểu tra đến phần history commit thì lòi ra:

![](image/72.png)

Đây chính là flag yeah.

![](image/73.png)

## Nhiệm vụ 26:

![](image/74.png)

Really?? Repository github challenge trước vẫn còn flag ư🤔hmm, mình sẽ kiểm tra lại lần này sẽ kiểm tra đến phần branches của git.

Oh có tận 12 branches tìm cái patch cuối cùng này có thể chứa flag:

![](image/75.png)

Đã xong đã tìm thấy flag :3

![](image/76.png)

## Nhiệm vụ 27:

![](image/77.png)

Ái chà câu này mà muốn submit chắc cx phải đợi lâu lắm đây :3 mình sẽ lươn lẹo để set lại thời gian nhé.

![](image/78.png)

Không phải đây thực chất là 1 challenge đã được ẩn form submit đi, tìm flag trước đã thì khi mình kéo trang view-source thì flag nằm ở cuối trang.

![](image/79.png)

Mình sẽ submit câu này bằng code như sau:

```javascript
document.querySelector('[name="flag"]').value = document.querySelector('body').childNodes[9].data.trim().split('Flag: ')[1]
document.querySelector('form').submit()
```
Done :3

## Nhiệm vụ 29:
![](image/80.png)

Câu này nhìn có vẻ khá quen thuộc :3

![](image/81.png)

Oh, một câu gợi ý ư, mình sẽ thử cái đuôi khác cho cái ảnh xem sao

![](image/82.png)

Ồ thì ra nó ở trong file txt.c

## Nhiệm vụ 30:
![](image/83.png)

Lại một bài source code PHP nữa :3
Để ý ta sẽ thấy hàm `substr($input, 15)` sẽ lấy ra các kí tự đứng đằng sau kí tự thứ 15 của chuỗi `$input`, vì vậy muốn submit đúng t phải thêm 15 kí tự bất kì vào chuỗi flag.

Flag phần view-source đã có

Done :3

----
Cuộc thi dù vẫn còn dài, các challenge vẫn chưa được up hết nhưng vì điều khoản bên J2TEAM nên mình xin phép tạm dừng writeup ở đây. Hi vọng các bạn đều đã tìm được những kiến thức bổ ích cho mình <3 <3