
# DU AN WEBSITE HOC TRUC TUYEN

## Danh cho nguoi dung :

- Hien thi danh sach khoa hoc
- Hien thi thong tin chi tiet khoa hoc
- Xem video bai giang
- Download tai lieu bai giang
- Hoc thu bai giang
- Dang ky / dang nhap
- Trang tai khoan : Thong tin ca nhan, khoa hoc cua toi
- Mua khoa hoc
- Gio hang
- Hien thi danh sach tin tuc
- Hien thi chi tiet tin tuc

## Danh cho quan tri

- Quan ly danh muc (*)
- Quan ly hoc vien (*)
- Quan ly khoa hoc (*)
- Quan ly giang vien (*)
- Quan ly bai giang (*)
- Quan ly file tai lieu (*)
- Quan ly video (*)
- Quan ly danh muc tin tuc (*)
- Quan ly tin tuc (*)
- Kich hoat khoa hoc cho hoc vien (*)
- Quan ly don hang (*)
- Quan ly nguoi dung (Quan ly he thong)
- Phan quyen quan tri he thong
- Bao cao, thong ke, ...


## API

- Xay dung API hoan chinh

## Phan tich database

### 1. Table categories - Quan ly danh muc
    - id (Int)
    - name (varchar 255)
    - slug (varchar 255)
    - parent_id (Int)
    - created_at (timestamp)
    - updated_at (timestamp)

### 2. Table courses - Quan ly khoa hoc
    - id (int)
    - name (varchar 255)
    - slug (varchar 255)
    - detail (text)
    - teacher_id (int)
    - thumnail (text)
    - price (float)
    - sale_price (float)
    - duration (float)
    - have_document (tinyInt)
    - supports (text)
    - status (tinyInt)
    - created_at (timestamp)
    - updated_at (timestamp)

### 3. Table lessions - Quan ly bai giang
    - id (int)
    - name (varchar 255)
    - slug (varchar 255)
    - description (text)
    - video_id (int)
    - document_id (int)
    - parent_id (int)
    - is_trial (tinyInt)
    - views (bigInt)
    - position (int)
    - created_at (timestamp)
    - updated_at (timestamp)

### 4. Table categories_courses - Trung gian lien ket giua khoa hoc va danh muc
    - id (int)
    - category_id (int)
    - course_id (int)
    - created_at (timestamp)
    - updated_at (timestamp)

### 5. Table teachers - Quan ly giang vien
    - id (int)
    - name (varchar 255)
    - slug (varchar 255)
    - description (text)
    - experience (float)
    - avatar (varchar 255)
    - created_at (timestamp)
    - updated_at (timestamp)

### 6. Table video - Quan ly video
    - id (int)
    - name (varchar 255)
    - url (varchar 255)
    - created_at (timestamp)
    - updated_at (timestamp)

    
### 7. Table document - Quan ly tai lieu bai giang
    - id (int)
    - name (varchar 255)
    - url (varchar 255)
    - size (float)
    - created_at (timestamp)
    - updated_at (timestamp)


### 8. Table categories_posts - Quan ly danh muc tin tuc
    - id (Int)
    - name (varchar 255)
    - slug (varchar 255)
    - parent_id (Int)
    - created_at (timestamp)
    - updated_at (timestamp)

### 9. Table posts - Quan ly tin tuc
    - id (Int)
    - title (varchar 255)
    - slug (varchar 255)
    - content (text)
    - category_post_id (int)
    - thumnail (varchar 255)
    - excerpt (text)
    - created_at (timestamp)
    - updated_at (timestamp)

### 10. Table students - Quan ly hoc vien
    - id (Int)
    - name (varchar 255)
    - email (varchar 255)
    - email_verified_at (timestamp)
    - password (varchar 500)
    - phone (varchar 30)
    - address (varchar 300)
    - status (tinyint 1)
    - created_at (timestamp)
    - updated_at (timestamp)

### 11. Table students_courses - Trung gian giua hoc vien va khoa hoc
    - id (int)
    - course_id (int)
    - student_id (int)
    - created_at (timestamp)
    - updated_at (timestamp)

### 12. Table orders - Quan ly don dang ly cua hoc vien
    - id (int)
    - student_id (int)
    - total (float)
    - status (tinyint 1)
    - created_at (timestamp)
    - updated_at (timestamp)

### 13. Table order_detail - Chi tiet don hang
    - id (int)
    - order_id (int)
    - course_id (int)
    - price (float)
    - created_at (timestamp)
    - updated_at (timestamp)

### 14. Table orders_status - Quan ly trang thai don hang
    - id (int)
    - name (varchar 100)
    - created_at (timestamp)
    - updated_at (timestamp)

### 15. Table users - Quan tri he thong (giong bang users mac dinh)
    - id (int)
    - name (varchar 255)
    - email (varchar 255)
    - password (varchar 500)
    - group_id (int)
    - rememberToken, email_verified_at, ...
    - created_at (timestamp)
    - updated_at (timestamp)    

### 16. Table groups - Quan tri nhom nguoi dung
    - id (int)
    - name (varchar 100)
    - permissions (text - Quan ly phan quyen)
    - created_at (timestamp)
    - updated_at (timestamp)    

### 17. Table modules - Danh sach cac module trong trang quan tri
    - id (int)
    - name (varchar 100)
    - title (varchar 200)
    - role (varchar 255)
    - created_at (timestamp)
    - updated_at (timestamp)

### 18. Table options - Quan ly cac thiet lap
    - id (int)
    - name (varchar 100)
    - value (text)