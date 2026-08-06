
# FCJ Template — Hướng dẫn (Flow: clone → push → sửa → push để GitHub Actions chạy)

Mục tiêu: bạn chỉ cần clone repo gốc, push sang repo của bạn, chỉnh nội dung `content/` và thêm ảnh vào `static/` rồi push — GitHub Actions sẽ chạy trên server, sinh LaTeX và (tùy workflow) biên dịch PDF.

## Yêu cầu trước
- Không cần cài gì trên local để chạy CI; GitHub Actions sẽ cài `pandoc`, LaTeX và `python` theo workflow mẫu.
- Nếu muốn chạy local: Python 3.8+, `pandoc`, LaTeX, `pip install pyyaml`.

## Các file quan trọng
- `scripts/convert_hugo_to_latex.py`: script chuyển Markdown → LaTeX.
- `scripts/hugo-notice.lua`: Lua filter cho `pandoc`.
- `report/`: template LaTeX (`main.tex`, `main_en.tex`) và nơi chứa output.
- `.github/workflows/build_report.yml`: workflow CI mẫu (chạy conversion + biên dịch PDF, upload artifact).

## Flow chi tiết (lệnh copy/paste)

- Clone repo gốc về local:

```
git clone https://github.com/ORIGINAL_USER/ORIGINAL_REPO.git
cd ORIGINAL_REPO
```

- Kết nối vào repo của bạn và push lần đầu (tạo repo trên GitHub trước):

```
git remote rename origin upstream
git remote add origin https://github.com/YOUR_USER/YOUR_REPO.git
git push -u origin main
```

- Chỉnh nội dung: sửa file trong `content/`, ví dụ `content/1-Worklog/_index.md`.

- Thêm ảnh vào thư mục `static/images/` (hoặc `static/` theo cấu trúc của bạn):

```
cp /path/to/myimage.png static/images/myimage.png
```

- Commit & push thay đổi lên repo của bạn:

```
git add content/ static/images/myimage.png
git commit -m "Update content and add image for report"
git push origin main
```

Sau khi push, workflow `Build Report` sẽ chạy tự động (nếu branch là `main`). Kết quả PDF được upload dưới mục `Artifacts` trong trang run của job.


## Gợi ý cấu hình ảnh trong Markdown
- Trong nội dung Markdown, dùng đường dẫn phù hợp với theme:
  - `![Alt text](/images/myimage.png)` hoặc `![Alt text](/static/images/myimage.png)` tuỳ template. Script có xử lý một số mẫu `(/static/images/...)` và `(/images/...)`.


## Luy Y
- Report se nam trong phan release o cot ben tay phai trang github