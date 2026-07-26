# Social Map + PostGIS Backend Checklist

## Phase 1 – Preparation

- [ ] Đọc schema Prisma liên quan (Activity, ActivityParticipant, User, City)
- [ ] Đọc module Activities hiện tại
- [ ] Xác định business requirements
- [ ] Xác định các API cần triển khai
- [ ] Chuẩn bị tài liệu API
- [ ] Chuẩn bị test plan (TDD)

---

## Phase 2 – Database & PostGIS

### Database

- [ ] Kiểm tra bảng Activity
- [ ] Kiểm tra bảng ActivityParticipant
- [ ] Kiểm tra quan hệ với User
- [ ] Kiểm tra quan hệ với City

### PostGIS

- [ ] Enable PostGIS Extension (nếu chưa có)
- [ ] Kiểm tra cột location (Point)
- [ ] Tạo GiST Index cho location
- [ ] Chuẩn bị truy vấn ST_DWithin
- [ ] Chuẩn bị truy vấn ST_Distance

---

## Phase 3 – Activities CRUD

### Create Activity

- [ ] DTO
- [ ] Validation
- [ ] Service
- [ ] Controller
- [ ] Database Insert
- [ ] Response

### Get Activities

- [ ] Pagination
- [ ] Filter
- [ ] Sort

### Get Activity Detail

- [ ] Find by ID
- [ ] Include participants

### Update Activity

- [ ] Permission check
- [ ] Update fields
- [ ] Validation

### Delete Activity

- [ ] Permission check
- [ ] Soft delete hoặc hard delete
- [ ] Cleanup participant records (nếu cần)

---

## Phase 4 – Nearby Feed (PostGIS)

### Feed API

- [ ] Thiết kế endpoint
- [ ] Validate latitude
- [ ] Validate longitude
- [ ] Validate radius

### Spatial Query

- [ ] ST_DWithin
- [ ] ST_Distance
- [ ] Sort theo khoảng cách
- [ ] Sort theo thời gian
- [ ] Sort theo số người tham gia

### Performance

- [ ] Verify GiST Index được sử dụng
- [ ] Kiểm tra execution plan
- [ ] Pagination

---

## Phase 5 – Join Activity

### Join API

- [ ] Kiểm tra Activity tồn tại
- [ ] Kiểm tra Activity còn mở
- [ ] Kiểm tra chưa join
- [ ] Kiểm tra capacity
- [ ] Tạo ActivityParticipant
- [ ] Cập nhật participant count (nếu có)

---

## Phase 6 – Validation

### DTO Validation

- [ ] Title
- [ ] Description
- [ ] Latitude
- [ ] Longitude
- [ ] Radius
- [ ] Max Participants
- [ ] Start Time
- [ ] End Time

### Business Validation

- [ ] Start < End
- [ ] Capacity > 0
- [ ] City tồn tại
- [ ] Owner hợp lệ

---

## Phase 7 – Authorization

- [ ] AuthGuard
- [ ] Current User
- [ ] Owner check
- [ ] Edit permission
- [ ] Delete permission
- [ ] Join permission

---

## Phase 8 – Error Handling

- [ ] 400 Validation Error
- [ ] 401 Unauthorized
- [ ] 403 Forbidden
- [ ] 404 Activity Not Found
- [ ] 409 Already Joined
- [ ] 409 Activity Full

---

## Phase 9 – Testing (TDD)

### Create Activity

- [ ] Success
- [ ] Invalid DTO
- [ ] Invalid City
- [ ] Invalid Time

### Get Activities

- [ ] Success
- [ ] Empty List

### Nearby Feed

- [ ] Radius 1 km
- [ ] Radius 5 km
- [ ] Radius 10 km
- [ ] Invalid coordinates
- [ ] Invalid radius
- [ ] Sort by distance
- [ ] Sort by time
- [ ] Sort by participants

### Join Activity

- [ ] Success
- [ ] Duplicate Join
- [ ] Full Activity
- [ ] Activity Not Found

---

## Phase 10 – API Verification

- [ ] Test bằng Swagger
- [ ] Test bằng Postman
- [ ] Verify JSON Response
- [ ] Verify Status Code

---

## Phase 11 – Documentation

- [ ] Update API documentation
- [ ] Update implementation notes
- [ ] Ghi lại các quyết định kỹ thuật (PostGIS, ST_DWithin, GiST)

---

## Phase 12 – Final Review

- [ ] Code Review
- [ ] Refactor
- [ ] Remove unused code
- [ ] Verify lint
- [ ] Verify tests
- [ ] Ready for merge
