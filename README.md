# GIT_Knowledge
Knowledge and experience on GIT <br>
https://git-scm.com/book/en/v2

## Kiến thức cơ bản về GIT
### Version Controll System
- là công cụ quản lý sự thay đổi của mã nguồn dự án theo thời gian
- VD: GIT, CVS, SVN, Mercurial, Monotone, Bazaar, TFS...
- Lợi ích
  - Quản lý sự thay đổi mã nguồn, theo dõi và hạn chế những rủi rõ liên quan đến sự thay đổi của mã nguồn
  - Hỗ trợ quản lý nhóm: Phân nhánh, sát nhập, hạn chế sự xung đột
  - Theo dõi tiến độ, cống hiến của các thành viên
  - Truy xuất nguồn gốc: ai? lúc nào? chỗ nào? vì sao? lại sửa như thế này? 

Tham khảo <br>
https://www.atlassian.com/git/tutorials/what-is-version-control

### GIT: một hệ thống quản lý mã nguồn phân tán ( Distributed Version Control System - DVCS )
Khi sử dụng GIT, "mỗi developer" đều lưu một bản sao của mã nguồn như là một kho lưu trữ toàn bộ lịch sử thay đổi của mã nguồn.

Tham khảo <br>  
https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control <br> 
https://sukhacnhau.com/may-tinh-va-internet/ngon-ngu-lap-trinh/su-khac-biet-giua-git-va-svn/

### Repository 
- Remote (Origin)
- Local
- Pull
- Push
- Fetch

### Branch
- Master branch
- Checkout new branch to start new task

### Commit

### Merge
- Conflic

## Các điều cần tuân thủ khi làm việc với Git
0. Config git trước khi sử dụng
Tham khảo: <br>
https://www.atlassian.com/git/tutorials/setting-up-a-repository/git-config

0. Trước khi tiến hành code, tạo nhánh mới từ nhánh được chỉ định ( nếu không được yêu cầu thì mặc định là master )
   ```
   git checkout -b ten_nhanh orgin/ten_nhanh
   ```
   * Lưu ý: xác nhận các sửa đổi hiện tại trước khi tạo một nhánh mới
1. Nội dung sửa đổi phải phù hợp với nội dung của task
 => không có nội dung thừa
2. Trước khi commit phải check lại nội dung sửa đổi xem đã sửa đúng, đủ chưa
3. Commit message cũng phải phù hợp với nội dung sửa đổi.
 Không nên commit quá nhiều nội dung nhỏ lẻ, nhưng cũng không nên lưu một commit với số lượng sửa đổi lớn
4. Trước khi push code lên thì check lại toàn bộ thay đổi so với thời điểm bắt đầu. 
 Nếu không có vấn đề gì mới được push code lên
5. Merge code theo cách sau
```
git merge ten_nhanh
```
  
## Các vấn đề có thể gặp phải và cách giải quyết
1. Tạo nhánh mới trong khi vẫn còn file đang sửa đổi
Cách sử lý:
PA1: Xoá sạch những gì đã sửa đổi > Dùng cho trường hợp không cần lưu giữ những sửa đổi 
```
git add .
```
```
git reset -hard HEAD~1
```
PA2: Tạo nhánh temp để lưu code đang sửa đổi > Dùng cho trường hợp muốn lưu giữ những sửa đổi
```
git checkout -b {temp_20200520}
```
```
git add .
```
```
git commit -m "test"
```

PA3: Sử dụng stash để lưu tạm sửa đổi lên một commit nào đó > Dùng cho những trường hợp muốn lưu giữ những sửa đổi
Lưu sửa đổi
```
git stash -u
```
Lấy những sửa đổi về
```
git stash pop 

2. Conflic


## Cách sử dụng sourcetree kết hợp với git để tăng tốc độ, và làm việc hiệu quả hơn với git
