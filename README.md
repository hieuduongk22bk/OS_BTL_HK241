# Bài tập lớn Hệ điều hành: L06 Nhóm 1

**HK241: OS Simulation**

## Thành viên nhóm

| MSSV    | Họ và Tên        |
| ------- | ---------------- |
| 2012938 | Nguyễn Thành Đạt |
|         |                  |
|         |                  |
|         |                  |

**Hạn nộp bài**: Chủ Nhật, 12 tháng 1 2025, 12:00 AM [Nộp bài](https://lms.hcmut.edu.vn/mod/assign/view.php?id=452059) `assignment STUDENTID.zip`

**Hạn nộp slide thuyết trình**: Thứ Tư, 25 tháng 12 2024, 6:00 PM  [Nộp slide](https://lms.hcmut.edu.vn/mod/assign/view.php?id=452067)

[Form Hỏi câu hỏi về BTL](https://docs.google.com/forms/d/e/1FAIpQLSf7-MHl84ohImqb1Akzb8C0GO5VlQxFMCV_IBNxgPgZPa3j-w/viewform)

[Sheet trả lời câu hỏi về BTL](https://docs.google.com/spreadsheets/d/1e1GV4gecZEIcA3LYIfJBZ0k38sjQxUrTfZONe9T0NFU/edit?usp=sharing)

## Cách chạy mô phỏng

```
make all # biên dịch os
make os # giống make all

make mem # chỉ biên dịch module memory
make sched # chỉ biên dịch module scheduler

make clean # xóa tất cả các file đã biên dịch và obj file
```

```
./os [config file]  # đường link tới configure file (trong thư mục input)
```

# Bài nộp = Report + Code

Source code styling: https://www.gnu.org/prep/standards/html_node/Writing-C.html



**Overall**: giải thích kết quả chạy test/mô phỏng

- so sánh với output có sẵn (có thể có nhiều hơn 1 output đúng), nên phải giải thích nó bằng lý thuyết



**Trả lời các câu hỏi trong đề**

- Question: What will happen if the synchronization is not handled in your simple OS? Illustrate the problem
  of your simple OS (assignment outputs) by example if you have any



## Simple operating system

**Scheduling** (the scheduler that employs MLQ policy) & dispatcher - determines which process is allowed to run on which CPU

- vẽ sơ đồ gantt các process chạy ở CPU



**Memory Management** (mechanism of memory allocation)

Tham chiếu đến vùng nhớ bằng index
Có giới hạn cho số lượng biến của mỗi chương trình/process

physical mem vs virtual mem: cách ly không gian bộ nhớ của các process với nhau (vì chúng cùng dùng chung physical mem): ánh xạ và dịch địa chỉ virtual cung cấp bởi processes sang địa chỉ physical

- MMU Paging: paging subsystem
- heap segment
- Heap godown strategy
- Heap and data free management (statistics of free space, fragmentation, reference
  counting, how to keep track of free space, tracing etc.)
- Show the status of the memory allocation in heap and data segments.



**Synchronization**: the OS runs on multiple processors, it is possible that share resources could be concurrently accessed by more than one process at a time.

- find share resource and use lock mechanism to protect them 



(Đọc tiếp phần 2.1 và 2.2 trong đề)

## Software (Processes)

Đọc phần định nghĩa các instruction của chương trình

## Hardware (hardware ảo)

- Multicore CPU
- Physical memory