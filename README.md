Tiêu đề: AKA Lab - Git Safety Foundation.
Học viên: Lê Phước Nhật Minh.
Mục tiêu: Xây dựng "Phanh an toàn" và "Cỗ máy thời gian" cho việc lập trình cùng AI.

## Tôi sẽ dùng Git như thế nào khi Vibe Code với AI?
Tôi dùng Git làm 'Phanh an toàn' để kiểm soát các đoạn code AI sinh ra trước khi gộp vào nhánh chính và làm 'Cỗ máy thời gian' để quay lại bản cũ nếu AI làm hỏng hệ thống
## Danh sách lệnh Git đã sử dụng.
git init: Khởi tạo repository.
git status: Kiểm tra trạng thái tệp.
git add: Đưa tệp vào vùng chờ.
git commit: Lưu phiên bản.
git push: Đẩy code lên GitHub.
git log: Xem lịch sử commit.

### Chi tiết về triết lý Git trong Vibe Coding
- **Phanh an toàn (Safe Brake):** Trước khi để AI thực hiện các thay đổi lớn hoặc cài đặt thư viện mới, tôi sẽ tạo một commit hoặc nhánh (branch) mới. Điều này giúp tôi kiểm soát được những gì AI đã can thiệp vào hệ thống [2].
- **Cỗ máy thời gian (Time Machine):** Nếu AI sinh code lỗi làm hỏng các chức năng đang chạy tốt, tôi có thể dùng lệnh `git checkout` hoặc `git revert` để quay về phiên bản ổn định gần nhất ngay lập tức [2, 3].

### Bổ sung chi tiết các lệnh Git đã thực hành:
- `git status`: Giúp tôi biết mình có quên lưu file hay chưa (như lỗi tôi vừa gặp) [3].
- `git log`: Cho phép tôi xem lại lịch sử các "điểm dừng" an toàn mà mình đã tạo [3].
- `git push`: Đưa toàn bộ thành quả lên GitHub để mentor có thể theo dõi và xác nhận kết quả [4].

### Thực hành với Nhánh (Branching) - "Phanh an toàn" nâng cao
- **Tại sao cần dùng Branch?**: Theo quy trình của AKA Lab, khi tôi muốn nhờ AI viết một tính năng mới hoặc sửa lỗi phức tạp, tôi sẽ không làm trực tiếp trên nhánh `main`. Tôi sẽ tạo một nhánh riêng để thử nghiệm [1, 3].
- **Lợi ích**: Nếu AI sinh code lỗi, nhánh `main` (phiên bản ổn định) vẫn hoàn toàn an toàn. Tôi chỉ việc xóa nhánh lỗi đó đi là xong [3].

### Thực hành "Cỗ máy thời gian" (Rollback & Revert)
- **Tình huống áp dụng**: Khi AI hỗ trợ viết code nhưng vô tình làm hỏng các tính năng cũ hoặc gây lỗi hệ thống không mong muốn [1, 5].
- **Cách tôi xử lý**:
    - Sử dụng `git log --oneline` để tìm ID của commit ổn định gần nhất [3].
    - Sử dụng lệnh `git revert <commit-id>` để đảo ngược các thay đổi lỗi mà vẫn giữ nguyên lịch sử làm việc [2].
    - Đây chính là "phao cứu sinh" giúp tôi tự tin hơn khi thực hiện Vibe Coding với tốc độ nhanh.

    ### Thực hành xử lý Xung đột (Conflict)
- **Xung đột là gì?**: Xảy ra khi có hai sự thay đổi khác nhau trên cùng một dòng của cùng một file. Trong Vibe Coding, điều này thường xảy ra khi tôi yêu cầu AI sửa một đoạn code mà trước đó tôi đã tự tay chỉnh sửa nhưng chưa đồng bộ.
- **Cách tôi xử lý**:
    - Git sẽ đánh dấu vùng bị xung đột.
    - Tôi sẽ xem xét và chọn giữ lại phiên bản của mình, phiên bản của AI, hoặc kết hợp cả hai.
    - Sau khi sửa, tôi dùng `git add` để đánh dấu đã xử lý xong và thực hiện commit kết thúc quá trình.

    ### Thực hành GitHub Flow và Bảo mật Repository
- **GitHub Flow**: Tôi hiểu quy trình làm việc chuẩn gồm: Tạo nhánh (Branch) -> Thực hiện thay đổi (Commits) -> Mở Pull Request (PR) -> Thảo luận/Review -> Trộn vào nhánh chính (Merge). Quy trình này giúp kiểm soát chất lượng code trước khi chính thức xuất hiện ở nhánh `main`.
- **Nguyên tắc bảo mật**: 
    - Tuyệt đối không đưa các thông tin nhạy cảm như mật khẩu, API keys hoặc thông tin cá nhân lên GitHub repository công khai.
    - Sử dụng file `.gitignore` để loại bỏ các file không cần thiết hoặc file chứa dữ liệu mật khỏi quá trình theo dõi của Git.

    ### Thực hành Quản lý dự án với GitHub Issues và Projects
- **GitHub Issues**: Tôi sử dụng Issues để theo dõi các đầu việc (tasks), các lỗi (bugs) hoặc các tính năng mới cần phát triển. Đây là nơi tôi mô tả chi tiết yêu cầu trước khi bắt đầu viết code hoặc nhờ AI hỗ trợ.
- **GitHub Projects (Project Board)**: Giúp tôi có cái nhìn tổng quan về tiến độ dự án thông qua các cột trạng thái như "Todo", "In Progress", và "Done". Việc này giúp tôi không bị lạc lối khi thực hiện nhiều thay đổi cùng lúc với AI.
- **Mối liên hệ**: Mỗi commit hoặc Pull Request nên được gắn với một Issue cụ thể để dễ dàng truy xuất nguồn gốc và lý do của sự thay đổi.

### Checklist Tự đánh giá Hoàn thành Project (Gatekeeping)
- [x] **Repository cá nhân**: Đã khởi tạo và đẩy lên GitHub.
- [x] **Số lượng Commit**: Đang thực hiện (Mục tiêu: ít nhất 10 commit có ý nghĩa).
- [x] **Số lượng Branch**: Đã thực hành ít nhất 3 nhánh khác nhau.
- [x] **Pull Requests**: Đã thực hiện ít nhất 2 PR trên GitHub.
- [x] **Xử lý Conflict**: Đã mô tả/thực hành cách giải quyết xung đột.
- [x] **Rollback/Revert**: Đã thực hành "Cỗ máy thời gian" để quay lại phiên bản ổn định.
- [x] **Mô tả Vibe Code**: Đã có đoạn viết về cách dùng Git làm "Phanh an toàn" khi làm việc với AI.