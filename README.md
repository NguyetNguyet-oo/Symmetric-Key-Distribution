**Compiling Crypto++ in Microsoft Visual Studio 2019/2017 (with Cryptopp-PEM)**
-	Download thư viện Crypto++: https://github.com/weidai11/cryptopp
-	Download Crypto++ PEM Pack: https://github.com/noloader/cryptopp-pem
-	Copy các file trong thư mục cryptopp-pem (trừ /git) chuyển sang thư mục cryptopp
-	Mở file cấu hình cryptlib.vcxproj để thêm các file pem vào solution:
-	Header files: thêm các file pem.h, pem_common.h trong thư mục cryptopp dã tải ở trên.
-	Source files: thêm các file pem_common.cpp, pem_write.cpp, pem_read.cpp 
-	Chỉnh sửa cấu hình cho phù hợp (release-x64) rồi tiến hành build Crypto++ solution.
  
**Configuring our project to use the complied Crypto++ library**
-	Chuột phải vào properties cần cấu hình, chọn Properties.
-	Chỉnh sửa configuration và platform:
 ![image](https://github.com/NguyetNguyet-oo/Symmetric-Key-Distribution/assets/134104269/f0026f8a-6dd5-4a40-aae4-b3068950b0b1)

-	Vào C/C++, chọn General, chỉnh sửa mục Additional Include Directories thành đường dẫn khi tải thư viện cryptopp
 ![image](https://github.com/NguyetNguyet-oo/Symmetric-Key-Distribution/assets/134104269/25c067a4-ae9f-4ac8-9e8b-e1f38df84829)

-	Ở C/C++, chọn tiếp Code generation, chỉnh sửa mục Runtime Library thành Multi-threaded(/MT)
 ![image](https://github.com/NguyetNguyet-oo/Symmetric-Key-Distribution/assets/134104269/2811df9e-ace0-41e2-a5f3-c8793f90bb01)

-	Chọn Linker -> General, chỉnh mục Additional Library Directores thành đường dẫn lưu file release output
 ![image](https://github.com/NguyetNguyet-oo/Symmetric-Key-Distribution/assets/134104269/b2820b3d-26a2-4462-9743-72f034e08ec8)

-	Chọn Linker -> Input, chỉnh mục Additional Dependencies thành cryptlib.lib 
![image](https://github.com/NguyetNguyet-oo/Symmetric-Key-Distribution/assets/134104269/a15856d8-b2c2-4892-b460-830bc3eb1aa9)
