# Daily Knowledge Books

Sổ sách đã review dùng cho lịch ChatGPT **Sách đáng đọc mỗi ngày** (phi hư cấu). GitHub là nguồn lưu bền vững để chống trùng; **không cần GitHub Actions hoặc mã Python** để chọn sách.

## Tệp dữ liệu

- [data/reviewed.json](data/reviewed.json): các tác phẩm đã review/recap, kể cả văn học trong quá khứ, nhằm chống trùng trên phạm vi tác phẩm.
- `books[].original_title`: tên gốc hoặc tên định danh ổn định nhất có thể.
- `books[].aliases`: tên dịch/biến thể đã biết.
- `books[].author`: tác giả.
- `books[].reviewed_on`: ngày review (YYYY-MM-DD); `null` nếu lịch sử không cung cấp.
- `books[].source`: `initial_exclusion` (danh sách loại trừ người dùng cung cấp) hoặc `prior_review` (review đã ghi nhận).

## Quy trình mỗi ngày

1. Lịch ChatGPT đọc **bản mới nhất trên nhánh `main`** từ GitHub, sau đó đối chiếu thêm lịch sử review/hội thoại khi có.
2. Tự chọn một sách **phi hư cấu** chưa review; ưu tiên cân bằng chủ đề, vùng địa lý, độ đáng tin của tài liệu và khả năng phân tích sâu.
3. Nghiên cứu mục lục, luận điểm, nguồn dữ liệu và giới hạn; viết bằng tiếng Việt với biểu đồ/sơ đồ/bảng khi thực sự hữu ích.
4. Sau khi review được đăng thành công, **đọc lại file mới nhất và ghi thêm một tác phẩm** qua GitHub connector (dùng SHA hiện tại để tránh ghi đè); không đưa các sách chỉ mới gợi ý vào danh sách.
5. Kết bài: `Sổ sách đã review — mới thêm: [tên gốc | tác giả | ngày]`.

**Lưu ý:** Không tự nhận một lần đọc/ghi đã thành công khi GitHub không xác nhận. Nếu kho không truy cập được, vẫn dùng lịch sử có sẵn để tránh trùng và báo ngắn về giới hạn; không được xóa hoặc tạo lại sổ đã có.

## Phạm vi

Lịch hiện tại chỉ chọn sách khoa học, kinh tế, triết học, khoa học xã hội, lịch sử phân tích, công nghệ, y học, tâm lý học, quản trị, chính sách công, v.v. Tác phẩm văn học hư cấu dành cho lịch riêng nhưng các sách đã từng review vẫn được giữ trong sổ chung để chống trùng.

## Bảo trì

Có thể chỉnh [reviewed.json](data/reviewed.json) trực tiếp trên GitHub. Sách có nhiều tên dịch nhưng chỉ là **một tác phẩm**, không tạo thành nhiều bản ghi. Dữ liệu khởi tạo được tổng hợp từ danh sách loại trừ ban đầu và các review có trong hội thoại; cần bổ sung khi tìm thấy review cũ chưa được ghi nhận.
