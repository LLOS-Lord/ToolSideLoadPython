# iOS Sideload Tool (Upgraded)

Công cụ hỗ trợ sideload file IPA lên thiết bị iOS sử dụng Apple ID, được nâng cấp với các tính năng tự động hóa thông minh.

## Tính năng mới & Cải tiến

1.  **Sideload Thông Minh**:
    - Tự động nhận diện thiết bị (UDID) khi cắm USB.
    - Tự động kiểm tra và đăng ký thiết bị với Apple Developer.
    - **Lách giới hạn 10 App ID/7 ngày**: Khi Apple trả về lỗi giới hạn, tool sẽ tự động đối chiếu danh sách ứng dụng trên iPhone (`ideviceinstaller list`) với danh sách App ID trên tài khoản Apple để chọn một App ID có sẵn chưa dùng và đổi Bundle ID của IPA cho khớp.
2.  **Quản lý Cấu hình**:
    - Lưu Apple ID, Anisette URL và UDID để không phải nhập lại nhiều lần.
    - Tự động sử dụng cấu hình đã lưu.
3.  **Xử lý Certificate**:
    - Tự động dùng lại Certificate cũ nếu còn hạn để tránh đụng giới hạn 2 cert/tài khoản.
    - Hỗ trợ thu hồi (Revoke) Certificate ngay trong tool.

## Lệnh Setup Môi Trường
```bash
pkg install git
pkg install python
git clone https://github.com/LLOS-Lord/ToolSideLoadPython.git
cd ToolSideLoadPython
pip install srp requests 
pkg install python-cryptography
```


## Cách sử dụng

```bash
python main.py
```

### Menu chính:
1. **Sideload IPA**: Thực hiện quy trình ký và cài đặt.
2. **Thu hồi Certificate**: Quản lý các chứng chỉ hiện có.
3. **Cấu hình**: Lưu thông tin đăng nhập và thiết bị.

## Yêu cầu

- `libimobiledevice` & `ideviceinstaller`
- `zsign` (đã đi kèm)
- Kết nối iPhone qua USB và chọn "Tin cậy" (Trust).

---
*Lưu ý: Luôn sử dụng tài khoản Apple ID phụ để đảm bảo an toàn.*
