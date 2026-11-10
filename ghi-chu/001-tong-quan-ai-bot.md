# 001 — Tổng quan dự án AI-BOT

**Cập nhật:** 2026-11-10  
**Nguồn:** Cấu trúc repository và các tệp trên nhánh `main` đã được kiểm tra khi thiết lập bộ nhớ.

## Định danh
- Repository: `chienmkt2018-bit/AI-BOT`
- Nhánh mặc định được kiểm tra: `main`
- README mô tả bot hỗ trợ tương tác qua GitHub.

## Công nghệ và thành phần đã xác minh
- Python: mã bot nằm trong `bot.py`.
- GitHub Actions: workflow tại `.github/workflows/ai-bot.yml`.
- Bot sử dụng HTTP requests để gọi API.
- Model GitHub Models được cấu hình trong mã là `openai/gpt-4o-mini`.
- README mô tả các lệnh `/help`, `/file`, `/sua`, `/poster`, `/issue`.

## Cấu trúc repository khi kiểm tra
```text
AI-BOT/
├── .github/workflows/ai-bot.yml
├── README.md
└── bot.py
```

Bộ nhớ được bổ sung:
```text
AI-BOT/
├── PROJECT_MEMORY.md
├── dang-lam.md
└── ghi-chu/
    ├── muc-luc.md
    ├── 001-tong-quan-ai-bot.md
    ├── 002-lenh-va-xu-ly-bot.md
    └── 003-quy-trinh-github-actions.md
```

## Ranh giới phạm vi
- `bot.py` đã được cập nhật để đọc 6 tệp bộ nhớ qua GitHub Contents API khi cần gọi AI; nội dung được cache trong một lượt chạy.
- Bộ nhớ được đưa vào prompt dưới dạng dữ liệu tham khảo, không phải chỉ thị hệ thống có quyền vượt yêu cầu hiện tại.
- Bot chặn lệnh tạo/sửa tệp đối với `PROJECT_MEMORY.md`, `dang-lam.md` và toàn bộ `ghi-chu/`.
- Đây là tích hợp đọc ngữ cảnh; bot chưa tự thực hiện quy trình POS/POSB để đề xuất, duyệt hoặc dọn bộ nhớ.
- Khi chỉ quản lý bộ nhớ, không tự sửa README, bot.py hoặc workflow.

## Cần xác minh lại
Cấu trúc, nhánh, dependencies, model ID, trigger và quyền workflow có thể thay đổi. Kiểm tra phiên bản mới nhất trên GitHub trước quyết định kỹ thuật.
