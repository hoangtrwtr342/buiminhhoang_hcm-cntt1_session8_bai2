Bài 2 : Xử lý sự cố Website từ Access Log



Phần 1: Phân tích

An nhầm giữa tìm tên tệp và tìm nội dung trong tệp. Get-ChildItem -Filter "*404*" liệt kê các tệp hoặc thư mục có tên chứa 404; nó không đọc nội dung access.log.

Select-String tìm từ khóa bên trong tệp. Kết quả mặc định có số dòng và tìm không phân biệt chữ hoa, chữ thường.


Phần 2: Lệnh PowerShell
Tìm các dòng chứa error : Select-String -Path .\access.log -Pattern 'error'

Nếu cần tìm các dòng có chứa 404 hoặc ERROR, dùng : Select-String -Path .\access.log -Pattern '404|ERROR'
