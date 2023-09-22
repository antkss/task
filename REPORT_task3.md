# REPORT
- đầu tiên muốn sử dụng buffer overflow với 1 file, ta phải có được offset, có nhiều cách để lấy offset, 2 trong số đó là:
- cách 1: sử dụng cyclic để tạo 1 dãy ngẫu nhiên, sau đó lấp đầy dữ liệu, cuối cùng là tìm offset nơi chứa dữ liệu của địa chỉ cụ thể của biến cần tìm (địa chỉ có thể được tìm bằng cách sử dụng lệnh x/xg $rbp-0xM với M là số nguyên của thanh ghi được lấy từ ida64 với dạng rbp-Mh ngay bên cạnh biến cần tìm địa chỉ), sau đó dữ liệu được đưa vào lệch cyclic -l <dữ liệu bên cạnh địa chỉ của biến>
- cách 2: sử dụng H với H nằm trong rsp+Hh được lấy từ phần mềm ida64 ngay bên cạnh biến cần tìm và offset phải được để theo dạng hexadecimal như sau 0xH
# cách dùng payload 
