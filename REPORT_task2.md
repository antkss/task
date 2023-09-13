# REPORT

## Dữ liệu từ việc gán

- Khi khai báo 1 biến với không giá trị ban đầu, biến đó đang sở hữu 1 giá trị rác.
- khi biến khai báo được khởi tạo 1 giá trị, giá trị rác sẽ không còn và để hiển thị biến giá trị của biến a ra màn hình ta phải có các đặc tả của biến đó đi kèm.
- các đặc tả trong c như sau:

- int: %d
- long long: %lld
- float: %f
- double %lf
- char: %c
  ex: printf(“the value: %d”, a);
  - Đặc tả của các biến có thể được sử dụng kiết hợp với các chuỗi kí tự trong ngoặc kép để mô tả vị trí của giá trị của biến a khi xuất ra màn hình trong chuỗi kí tự .
    ex: printf(“%d,%d”, a);
  - khi dùng sai đặc tả sẽ dẫn tới giá trị của biến a bị sai khi xuất ra màn hình.
  - mặc định float và double chỉ có 6 số sau số thập phân, muốn sửa theo ý mình cần thực hiện chèn như sau: float: printf(“%.mf”, a) hoặc double: prinf(“%.mlf”,a) với m là độ chính xác.

## Dữ liệu từ người dùng

- Để nhập dữ liệu ta dùng scanf(“d”,&a) với:

* c là đặc tả kiểu dữ liệu của a
* & toán tử địa chỉ có nhiệm vụ nhận ra địa chỉ của a

- Với nhiều biến: scanf(“d e f”, &a, &b, &c ) với d,e,f lần lượt là đặc tả của biến a, b, c.
- Sau đặc tả cuối cùng ví dụ scanf(“d e f”, &a, &b, &c ) là f thì sẽ ko có dấu cách, vì nó dẫn tới vòng lặp liên tục khi nhập.

## Gets

- cách dùng gets(a) với a là biến có kiểu dữ liệu kí tự dùng để lấy 1 chuỗi kí tự từ bàn phím mà không chấp nhận chuỗi null.
## puts
- cách dùng puts(a) với a là biến có kiểu dữ liệu là kí tự dùng để xuất chuỗi kí tự ra màn hình trừ chuỗi null
```
