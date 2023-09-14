# REPORT

- Buffer Overflow: là tình trạng các biến khai báo sau được gán giá trị do giá trị nhập vào biến trước đó nhiều quá kích thước đã quy định. 
- Khi 1 biến a được khai báo với sức chứa dữ liệu là m byte, nhưng khi ta nhập lượng dữ liệu với kích thước m+1, biến a sẽ chứa đủ lượng dữ liệu kích thước là m, lượng còn dư sẽ chuyển qua cho biến b được khai báo kế tiếp 
- Để khảo sát buffer overflow, ta dùng gdb: gõ gdb + tên file sau đó gõ start để bắt đầu debug
- để xem địa chỉ của biến ta sử dụng x/xg + $m (với m dạng rsp-0x20, rbp-0x18, ... được lấy ra từ ida )
- để kiể
