# Redeemer

Máy Redeemer là một máy Linux rất đơn giản, chỉ mở duy nhất dịch vụ Redis. Mục tiêu là làm quen với Redis và cách truy cập dữ liệu khi dịch vụ này không được cấu hình xác thực.

## Recon

- Đầu tiên kiểm tra kết nối tới máy bằng lệnh `ping`:

```bash
ping -c 4 <ip>
```

- Sau đó quét toàn bộ cổng TCP để tìm dịch vụ đang mở:

```bash
nmap -p- --min-rate 5000 <ip>
```

Kết quả cho thấy chỉ có cổng `6379/tcp` đang mở.

<!-- Thêm ảnh chụp màn hình nmap: ![alt text](image/1.png) -->

- Tiếp tục quét chi tiết cổng này để xem phiên bản dịch vụ:

```bash
nmap -p 6379 -sV -sC <ip>
```

Kết quả xác nhận dịch vụ là `redis`.

---

**Question 1: Which TCP port is open on the machine?**

Answer : 6379

**Question 2 : What service is running on that port?**

Answer : redis

**Question 3 : Which command-line tool comes with Redis?**

Answer : redis-cli

**Question 4 : Which flag is used with the Redis CLI to specify the host?**

- Mặc định `redis-cli` sẽ kết nối tới `127.0.0.1`, nên ta phải dùng flag `-h` để chỉ định host cần kết nối:

```bash
redis-cli -h <ip>
```

Answer : -h

**Question 5 : What is the command we use within the Redis CLI to get information and statistics about the server?**

- Sau khi đã kết nối vào Redis, ta dùng lệnh `info` để xem thông tin máy chủ như phiên bản, hệ điều hành, các database đang có dữ liệu...

```bash
redis-cli -h <ip>
info
```

Answer : info

**Question 6 : What is the number of the database being used?**

- Redis mặc định có 16 database được đánh số từ `0` đến `15`, và khi kết nối ta đang làm việc với database `0`. Trong output của lệnh `info`, mục `Keyspace` cũng cho biết database nào đang chứa key.

Answer : 0

**Question 7 : What is the command used to list all keys in the database?**

- Dùng lệnh `keys *` để liệt kê toàn bộ key trong database hiện tại:

```bash
keys *
```

Kết quả trả về một key có tên là `flag`.

Answer : keys *

**Question 8 : Which database is the flag located in?**

- Key `flag` nằm trong database mặc định mà ta đang dùng, tức database `0`.

Answer : 0

---

**Submit the flag**

- Dịch vụ Redis ở đây không bật xác thực nên ta truy cập được mà không cần mật khẩu. Thực hiện lần lượt các bước sau:

```bash
redis-cli -h <ip>
select 0
keys *
get flag
```

Trong đó:

- `select 0` chọn database số 0.
- `keys *` liệt kê tất cả key.
- `get flag` lấy giá trị của key `flag`.

<!-- Thêm ảnh chụp màn hình lấy flag: ![alt text](image/2.png) -->

```text
Flag: 03e1d2b376c37ab3f5319922053953eb
```
