- Quản lý danh mục
- Quản lý học viên
- Quản lý khóa học
- Quản lý giảng viên
- Quản lý bài Giảng
- Quản lý danh mục tin tức
- Quản lý tin tức
- Quản lý người dùng (Quản lý hệ thống)
- Kích hoạt khóa học cho học viên
- Phân quyền quản trị hệ thống
- Báo cáo, thống kê ..
- Quản lý file tài liệu
- Quản lý video
- Quản lý đơn hàng

## Phân tích Database
1. Table categories => Quản lý danh mục
 - id => int
 - name => varchar(200)
 - slug => varchar(200)
 - parent_id => int
 - created_at => timestamp
 - updated_at => timestamp

2. Table courses => Quản lý khóa học
 - id => int
 - name => varchar(255)
 - slug => varchar(255) 
 - detail => text
 - teacher_id => int 
 - thumbnail => varchar(255) 
 - price => float
 - sale_price => float
 - code => varchar(100)
 - durations => float
 - is_document => tinyint
 - supports => text
 - status => tinyint
 - created_at => timestamp
 - updated_at => timestamp

3. Table lessions => Quản lý bài giảng
 - id => int
 - name => varchar(255)
 - slug => varchar(255) 
 - video_id => int
 - document_id => int
 - parent_id => int
 - is_trial => tinyint
 - views => int
 - position => int
 - duration => float
 - description => text
 - created_at => timestamp
 - updated_at => timestamp

4. Table categories_courses => Trung gian liên kết giữa danh mục và khóa học
 - id => int
 - category_id => int
 - course_id => int
 - created_at => timestamp
 - updated_at => timestamp

 5. Table teacher = Giảng viên
  - id => int
  - name => varchar(100)
  - slug => varchar(100)
  - description => text
  - exp => float
  - image => varchar(255)
  - created_at => timestamp
  - updated_at => timestamp

 6. Table videos => Quản lý video bài Giảng 
  - id => int
  - name => varchar(255)
  - url => varchar(255)
  - created_at => timestamp
  - updated_at => timestamp

 7. Table documents => Quản lý tài liệu bài Giảng
  - id => int
  - name => varchar(255)
  - url => varchar(255)
  - size => float
  - created_at => timestamp
  - updated_at => timestamp

 8. Table categories_posts => Quản lý danh mục tin tức
  - id => int
  - name => varchar(255)
  - slug => varchar(255)
  - parent_id => int
  - created_at => timestamp
  - updated_at => timestamp

 9. Table posts => Quản lý tin tức
  - id => int
  - title => varchar(255)
  - slug => varchar(255)
  - content => text
  - exceprt => text
  - thumbnail => varchar(255)  
  - category_id => int
  - created_at => timestamp
  - updated_at => timestamp

 10. Table students => Quản lý học viên 
  - id => int
  - name => varchar(100)
  - email => varchar(100)
  - phone => varchar(20)
  - password => varchar(100)
  - address => varchar(200)
  - status => tinyint(1)
  - created_at => timestamp
  - updated_at => timestamp

 11. Table students_courses => Trung gian học viên và khóa học
  - id => int
  - course_id => int
  - student_id => int
  - status => tinyint(1)
  - created_at => timestamp
  - updated_at => timestamp

 12. Table orders => Quản lý đơn hàng đăng ký của học viên
  - id => int
  - student_id => int
  - total => float
  - status => tinyint(1)
  - created_at => timestamp
  - updated_at => timestamp 

 13. Table orders_detail => Chi tiết đơn hàng
  - id => int
  - order_id => int
  - course_id => int
  - price => float
  - created_at => timestamp
  - updated_at => timestamp 

 14. Table orders_status => Quan lý trạng thái đơn hàng
  - id => int
  - name => varchar(200)  
  - created_at => timestamp
  - updated_at => timestamp 

 15. Table users => Quản lý hệ thống
  - id => int
  - name => varchar(100)
  - email => varchar(100)
  - password => varchar(100)
  - group_id => int
  - created_at => timestamp
  - updated_at => timestamp

 16. Table groups => Quản trị nhóm người dùng
  - id => int
  - name => varchar(100)
  - permissions => text
  - created_at => timestamp
  - updated_at => timestamp

 17. Table modules => Danh sách các module trong trang quản trị
  - id => int
  - name => varchar(100)
  - title => varchar(200)
  - role => text

 18. Table options => Quản lý các thiết lập
  - id => int 
  - name => varchar(100)
  - value => text
