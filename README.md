
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


## CI/CD

On every push to `main`:

| Job | What it does |
|-----|-------------|
| `build-deploy` | Builds Hugo site → deploys to `gh-pages` branch |
| `build-pdf` | Converts Hugo content → compiles VN + EN PDFs → creates/updates GitHub Release (`latest` tag) |

Each release contains `report_vn.pdf` and `report_en.pdf`.

## Adding New Content

1. Create `_index.md` / `_index.vi.md` files in `content/` following the directory naming convention (e.g. `8-NewSection/_index.md`)
2. Add section titles to `SECTION_TITLES_EN` / `SECTION_TITLES_VI` in `scripts/convert_hugo_to_latex.py`
3. The script discovers pages dynamically — no other changes needed


## Report-Specific Frontmatter Options

The PDF generator supports several optional frontmatter fields that control how Hugo pages are included in the generated LaTeX/PDF reports.

### Excluding a Page from the PDF Report

To prevent a page (and all of its descendants) from appearing in the generated report:

```yaml
---
title: "Internal Notes"
includeInReport: false
---
```

Supported aliases:

```yaml
includeInReport: false
include_in_report: false
isincludeinlatex: false
includeInLatex: false
```

When a section container is excluded, all child pages are excluded automatically.

---

### Selecting Specific Columns from Markdown Tables

Large markdown tables often do not render well in PDF format.

You can choose which columns should be included:

```yaml
---
title: "Week 1 Worklog"

reportTableColumns:
  - Day
  - Task
  - Completion Date
---
```

Vietnamese example:

```yaml
---
title: "Tuần 1"

reportTableColumns:
  - Thứ
  - Công việc
  - Ngày hoàn thành
---
```

Only the listed columns will be preserved in the generated PDF.

---

### Selecting Specific Headings

If a page contains many sections but only some should appear in the PDF report:

```yaml
---
title: "Week 1"

reportHeadings:
  - Week 1 Objectives
  - Tasks to be carried out this week
  - Week 1 Achievements
---
```

Only the selected headings and their content will be included.

Supported aliases:

```yaml
reportHeadings
report_headings
latexHeadings
latex_headings
```

---

### Worklog Tables

Worklog pages can be rendered using a custom LaTeX table generator instead of Pandoc's default table conversion.

```yaml
---
title: "Week 1 Worklog"

reportType: worklog

reportTableColumns:
  - Day
  - Task
  - Completion Date
---
```

Supported aliases:

```yaml
reportType
report_type
```

When `reportType: worklog` is enabled:

* The first markdown table on the page is converted into a custom LaTeX `longtable`.
* Task cells are rendered as multi-line lists.
* Selected columns are preserved using `reportTableColumns`.
* The output is optimized for PDF readability compared to Pandoc's default table rendering.

---

### Example

```yaml
---
title: "Week 1 Worklog"

includeInReport: true

reportType: worklog

reportTableColumns:
  - Day
  - Task
  - Completion Date

reportHeadings:
  - Week 1 Objectives
  - Tasks to be carried out this week
  - Week 1 Achievements
---
```

This configuration:

* Includes the page in the PDF report.
* Uses the custom worklog table renderer.
* Keeps only the selected table columns.
* Includes only the selected headings.