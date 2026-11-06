# All In One Pro Max Ultimate — Loon

Bản plugin chuyển đổi từ cấu hình Shadowrocket do người dùng cung cấp sang định dạng Loon.

**Tệp cài đặt:** [All_In_One_Pro_Max_Ultimate_Loon.plugin](./All_In_One_Pro_Max_Ultimate_Loon.plugin)

**URL Raw:**
```text
https://raw.githubusercontent.com/nguyendp911/nguyendp-loon/main/All_In_One_Pro_Max_Ultimate_Loon.plugin
```

## Yêu cầu

- Loon 3.5.1 (Build 983) trở lên trên iOS/iPadOS.
- Đây là **plugin**, không phải cấu hình proxy hoàn chỉnh.
- Các chức năng cần đọc HTTPS có thể yêu cầu cài và tin cậy chứng chỉ MITM của chính Loon.

## Thành phần

| Tính năng | Trạng thái mặc định | Ghi chú |
| --- | --- | --- |
| YouTube: chặn endpoint quảng cáo | Bật | Không đảm bảo chặn mọi quảng cáo |
| YouTube: lọc feed | Bật | Sử dụng script app2smile |
| YouTube: xử lý nâng cao | Tắt | Thử nghiệm, có thể gây lỗi phát video |
| YouTube: sửa `ctier=L` | Tắt | Thử nghiệm |
| Spotify | Bật | Dùng script app2smile; không đồng nghĩa sở hữu Premium |
| Sub-Store | Bật | Có lịch đồng bộ; tắt nếu đã cài plugin Sub-Store riêng |
| SoundCloud, Locket, Alight Motion, PicsArt, Wink, Truecaller, KineMaster, CamScanner, BeautyPlus | Không bật | Script gốc không truy cập được hoặc chưa xác minh |

## Cài đặt

1. Mở Loon và tìm mục **Configuration → Plugin** (tên menu có thể khác nhau theo phiên bản).
2. Thêm plugin bằng đường dẫn Raw ở trên.
3. Bật plugin; cấu hình chứng chỉ MITM của Loon nếu sử dụng các quy tắc HTTPS.
4. Mở **Plugin Arguments** để chọn tính năng.
5. Kiểm tra log khi phát sinh lỗi. Nếu YouTube không phát video hoặc Spotify gặp vấn đề, thử tắt nhóm xử lý tương ứng.

## Các thay đổi khi chuyển đổi

- Chuyển `[Url Rewrite]`, `[Header Rewrite]`, `[Map Local]` sang `[Rewrite]` kiểu Loon.
- Giữ các quy tắc chặn UDP/QUIC cho YouTube.
- Sửa phạm vi hostname/URL cho Spotify.
- Không sử dụng các đường dẫn JavaScript trả HTTP 404.
- Giảm miền MITM, loại bỏ can thiệp RevenueCat khi thiếu script xác minh.
- Cung cấp các công tắc bật/tắt để khoanh vùng lỗi.

## Lưu ý bảo mật

Plugin tải một số JavaScript từ bên thứ ba. Chỉ bật MITM cho những hostname cần thiết, theo dõi thay đổi nguồn script, và tránh sử dụng trên các tài khoản nhạy cảm nếu chưa tự kiểm tra mã. Quyền thuê bao trả phí được xác thực bởi nhà cung cấp; plugin không cấp quyền thuê bao hợp lệ.

**Mức độ kiểm thử:** đã kiểm tra tĩnh và đối chiếu file trên GitHub; **chưa kiểm thử trên thiết bị chạy Loon**.

## Nguồn tham khảo

- [Tài liệu Loon](https://nsloon.app/en/docs/Plugin/)
- [app2smile — rules](https://github.com/app2smile/rules)
- [Sub-Store](https://github.com/sub-store-org/Sub-Store)
- [Maasea — sgmodule](https://github.com/Maasea/sgmodule)
