# REPORT
- đầu tiên muốn sử dụng buffer overflow với 1 file, ta phải có được offset, có nhiều cách để lấy offset, 2 trong số đó là:
- cách 1: sử dụng cyclic để tạo 1 dãy ngẫu nhiên, sau đó lấp đầy dữ liệu, cuối cùng là tìm offset nơi chứa dữ liệu của địa chỉ cụ thể của biến cần tìm (địa chỉ có thể được tìm bằng cách sử dụng lệnh x/xg $rbp-0xM với M là số nguyên của thanh ghi được lấy từ ida64 với dạng rbp-Mh ngay bên cạnh biến cần tìm địa chỉ), sau đó dữ liệu được đưa vào lệch cyclic -l <dữ liệu bên cạnh địa chỉ của biến>
- cách 2: sử dụng H với H nằm trong rsp+Hh được lấy từ phần mềm ida64 ngay bên cạnh biến cần tìm và offset phải được để theo dạng hexadecimal như sau 0xH
# cách dùng payload và ljust
- payload dùng để fill dữ liệu vào chương trình 1 cách nhanh gọn lẹ mà không cần quan tâm đến ảnh hưởng của các biến khác vào biến cần fill dữ liệu như cách thông thường, payload như công cụ teleport sang các biến để gán dữ liệu
- nguyên tắc khai báo:
- đầu tiên ta cần khai báo: "payload = b'' " để tạo chuỗi rỗng, sau đó là: "payload = payload.ljust(M, 'a') ' với M là offset của biến đầu tiên cần fill trong chuỗi các biến, sau đó ta cộng dữ liệu cần fill vào payload += <dữ liệu> VD: payload += p64(0xdeadbeef) hoặc payload += 'This is text\0'
- các biến tiếp theo payload = payload.ljust(N, 'a') với N là offset và sau đó payload += <dữ liệu> (các biến khác tương tự)
- khi đã đủ số biến, ta dùng sendline để gửi payload đi
# Lưu ý 
- các biến trong payload phải được sắp xếp từ bé đến lớn theo offset, nếu không sẽ xảy ra tình trạng ljust không ghi dữ liệu do offset các biến trước quá lớn
- sử dụng '\0' đối với c vì c chỉ ghi nhận kết thúc chuỗi kí tự khi có null, nếu không có thì sẽ lấy các dữ liệu về sau, gây ảnh hưởng đến độ chính xác của dữ liệu
- các bước trên thực hiện trên pwndbg là plugin của gdb, đối với các plugin khác thì có lệnh khác với chức năng tương tự
