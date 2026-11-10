# 002 — Lệnh và xử lý bot

**Cập nhật:** 2026-11-10  
**Nguồn:** README.md và bot.py trên nhánh `main` đã được kiểm tra khi thiết lập bộ nhớ.

## Các lệnh được README mô tả

| Lệnh | Cách dùng | Mục đích |
|---|---|---|
| `/help` | `/help` | Hiển thị hướng dẫn |
| `/file` | `/file ten-file.py : mo ta` | Yêu cầu tạo tệp |
| `/sua` | `/sua ten-file : mo ta sua` | Yêu cầu sửa tệp |
| `/poster` | `/poster : chu de` | Tạo nội dung poster |
| `/issue` | `/issue : tieu de | noi dung` | Tạo issue |

Bot cũng xử lý tin nhắn thông thường theo luồng chat trong `bot.py`.

## Giới hạn đã ghi nhận
- Mã bot tích hợp GitHub API/GitHub Models.
- Có danh sách đường dẫn bị chặn đối với thao tác tệp, gồm khu vực workflow, `.env`, secrets và `.git/`.
- Thao tác tạo/sửa tệp có thể tạo commit lên nhánh đích theo logic bot; cần kiểm tra mã hiện hành trước khi sử dụng.
- Khi một lệnh cần gọi AI, bot nạp `PROJECT_MEMORY.md`, `dang-lam.md`, `ghi-chu/muc-luc.md` và ba ghi chú 001–003; nội dung tối đa 12.000 ký tự và cache trong một lượt chạy.
- Bộ nhớ được gắn vào phần ngữ cảnh của lời gọi AI để bot hiểu trạng thái và quy ước dự án.
- `commit_file()` từ chối đường dẫn `PROJECT_MEMORY.md`, `dang-lam.md`, `ghi-chu/` và đường dẫn traversal; việc cập nhật bộ nhớ phải thực hiện qua quy trình được người dùng yêu cầu/phê duyệt.
- Tích hợp này không đồng nghĩa bot tự động tạo ghi chú, cập nhật mục lục hoặc chạy kiểm toán POSB.

## Quy tắc vận hành
- Dùng `/help` để kiểm tra cú pháp hiện tại khi README hoặc mã thay đổi.
- Trước lệnh có thể ghi repository, xác định tên tệp, nội dung, nhánh và phạm vi.
- Sau thao tác ghi, xác minh commit và nội dung thực tế.

## Lưu ý
Bảng lệnh phản ánh README tại ngày ghi chú. Nếu README và mã khác nhau, kiểm tra mã và cập nhật ghi chú theo bằng chứng mới.
