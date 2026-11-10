# 003 — Quy trình GitHub Actions

**Cập nhật:** 2026-11-10  
**Nguồn:** `.github/workflows/ai-bot.yml` trên nhánh `main` đã được kiểm tra khi thiết lập bộ nhớ.

## Workflow
- Tệp: `.github/workflows/ai-bot.yml`
- Trigger gồm comment được tạo trên issue và issue mới được mở, theo cấu hình tại thời điểm kiểm tra.
- Job checkout repository, thiết lập Python 3.11, cài `requests`, sau đó chạy `bot.py`.

## Permissions đã khai báo
- `contents: write`
- `issues: write`
- `models: read`

Đây là quyền khai báo trong workflow; khả năng thực tế còn phụ thuộc cấu hình repository, token và chính sách GitHub.

## Luồng tổng quát
1. GitHub phát sự kiện phù hợp.
2. Actions khởi chạy workflow.
3. Runner checkout mã nguồn.
4. Runner thiết lập Python và cài dependency.
5. Workflow thực thi `bot.py`.
6. Bot xử lý sự kiện và tương tác với GitHub theo logic/quyền được cấp.

## Kiểm soát thay đổi
- Không chạy workflow chỉ để kiểm tra tài liệu bộ nhớ.
- Không thay đổi trigger, permissions, secrets hoặc runner trong nhiệm vụ chỉ quản lý bộ nhớ.
- Khi sửa workflow, xem diff và đánh giá quyền tối thiểu.
- Sau thay đổi được phê duyệt, kiểm tra run/log; không coi commit là bằng chứng workflow thành công.

## Cần xác minh lại
Đọc workflow hiện hành trước khi thao tác vì trigger, quyền, dependency và môi trường có thể thay đổi.
