# PROJECT MEMORY — AI-BOT

**Mục đích:** Quy định cách AI đọc, ghi, duy trì và kiểm toán bộ nhớ dự án AI-BOT.
**Phạm vi:** Repository `chienmkt2018-bit/AI-BOT`, nhánh mặc định `main`.

## Quy trình đầu phiên
1. Đọc `dang-lam.md` để nắm trạng thái và bước tiếp theo.
2. Đọc `ghi-chu/muc-luc.md`, sau đó chỉ đọc các ghi chú liên quan.
3. Kiểm tra GitHub khi thông tin có thể đã thay đổi; ghi chú không thay thế trạng thái thực tế.

## Khi cập nhật bộ nhớ
Đề xuất cập nhật khi người dùng đính chính thông tin, chốt quyết định, thay đổi phạm vi/kiến trúc/quy trình, hoàn thành hoặc bị chặn một việc, hoặc phát hiện ghi chú sai/trùng/lỗi thời.

## Quy tắc ghi chú
- Một tệp cho một chủ đề; kiểm tra mục lục trước khi tạo tệp mới.
- Ghi ngày cập nhật, nguồn/bằng chứng khi có.
- Phân biệt Đã xác minh, Người dùng xác nhận, Đề xuất, Giả định và Chưa rõ.
- Không lưu mật khẩu, token, khóa API, secrets hoặc dữ liệu nhạy cảm không cần thiết.
- Cập nhật ghi chú hiện hành khi sự thật thay đổi; không để các ghi chú mâu thuẫn.

## POS — đề xuất ghi nhớ
1. Xác định chủ đề, kiểm tra ghi chú liên quan.
2. Soạn ghi chú và cập nhật mục lục/trạng thái nếu cần.
3. Trình bày tệp và diff để người dùng xem.
4. Chỉ ghi GitHub khi người dùng phê duyệt rõ hoặc trực tiếp yêu cầu thực hiện ghi trong yêu cầu hiện tại.
Bot hiện đã được tích hợp khả năng nạp bộ nhớ dự án theo chế độ chỉ đọc vào ngữ cảnh AI. Tuy nhiên, quy trình POS/POSB (đề xuất, duyệt, kiểm toán và cập nhật bộ nhớ) vẫn do người dùng/AI thực hiện theo yêu cầu; không tự động ghi hoặc dọn bộ nhớ.

## POSB — kiểm toán bộ nhớ
1. Đọc toàn bộ `ghi-chu/` và `dang-lam.md`.
2. Phát hiện nội dung trùng, sai, mâu thuẫn, lỗi thời.
3. Đề xuất gộp và chỉ rõ nguồn/đích; đánh dấu nội dung lỗi thời thay vì âm thầm xóa bằng chứng.
4. Chuyển việc hoàn tất khỏi danh sách đang mở; cập nhật mục lục.
5. Trình thay đổi/diff để người dùng duyệt; không tự sửa/xóa nếu chưa được yêu cầu/phê duyệt.

## Quyền hạn và an toàn
- Mặc định đọc, phân tích và soạn bản nháp.
- Ghi/sửa/xóa cần yêu cầu hoặc phê duyệt rõ ràng.
- Không tự ý sửa `README.md`, `bot.py`, `.github/workflows/ai-bot.yml` trong nhiệm vụ chỉ quản lý bộ nhớ.
- Không tự chạy workflow, deploy hoặc thay đổi secrets.
- Trước khi ghi, kiểm tra tệp đích; sau khi ghi, xác minh cây tệp và commit SHA.
- Khi thông tin chưa đủ bằng chứng, ghi rõ Chưa xác minh.
