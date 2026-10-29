# Lab1_FAP201_IC2001 - Wiring Switches to LEDs

## Thông tin chung
* **Môn học:** FAP201 - FPGA Programming[cite: 1]
* **Bài thực hành:** Lab01 - Wiring Switches to LEDs[cite: 1]
* **Mục tiêu:** Thiết kế, kiểm chứng và hiện thực mạch tổ hợp 3 switch độc lập điều khiển 3 LED tương ứng trên bo mạch FPGA[cite: 1].

## Môi trường và Phần cứng
* **Công cụ phát triển:** Gowin EDA[cite: 1]
* **Bo mạch (Board):** Xiaomeige ACG525[cite: 1]
* **Target Device:** GW5A-LV25UG324C2/I1[cite: 1]
* **Ngôn ngữ mô tả phần cứng:** VHDL[cite: 2]

## Nguyên lý hoạt động
* **Mạch tổ hợp (Combinational Circuit):** Thiết kế sử dụng các phép gán tín hiệu đồng thời trong VHDL để ánh xạ trực tiếp mức logic từ switch sang LED[cite: 2, 3].
* Đầu ra của mạch phụ thuộc hoàn toàn vào trạng thái đầu vào hiện thời, do đó thiết kế không sử dụng xung nhịp (clock), thanh ghi (register) hay máy trạng thái (FSM)[cite: 2, 7].
* File Constraints (`.cst`) được sử dụng để ánh xạ các cổng logic (logical ports) vào các chân vật lý (physical pins) tương ứng trên bo mạch, đồng thời cấu hình điện áp I/O chuẩn là 3.3V[cite: 3, 11].

## Cấu trúc thư mục (Project Structure)
Dự án được đóng gói theo tiêu chuẩn đánh giá của môn học[cite: 2]:

* `analysis/`: Chứa bài phân tích quy luật hoạt động (`operating_rule.pdf`)[cite: 2].
* `src/`: Chứa file mã nguồn mô tả phần cứng (`Lab1.vhd`)[cite: 2].
* `constraints/`: Chứa file cấu hình gán chân vật lý (`Lab1.cst`)[cite: 2].
* `sim/`: Chứa file testbench dùng để mô phỏng (`lab01_tb.vhd`)[cite: 2].
* `waveform/`: Chứa hình ảnh/trace mô phỏng có chú thích[cite: 2].
* `reports/`: Chứa các báo cáo Synthesis và Place & Route (P&R)[cite: 2].
* `evidence/`: Chứa minh chứng thực tế trên phần cứng (bảng 8 trường hợp test, ảnh/video chạy trên board và log Programmer)[cite: 2].

## Cách chạy dự án (How to Run)
1. Mở dự án bằng Gowin EDA và kiểm tra lại thông số target device `GW5A-LV25UG324C2/I1`[cite: 1, 4].
2. Chạy mô phỏng (Functional Simulation) với 8 vector test để kiểm tra bảng chân lý logic[cite: 2, 4].
3. Chạy quá trình **Synthesis** và **Place & Route (P&R)** để tổng hợp mạch[cite: 4].
4. Cắm bo mạch Xiaomeige ACG525, sử dụng công cụ Programmer để nạp file bitstream (`.fs`) xuống FPGA[cite: 1, 4].
5. Thao tác bật/tắt 3 switch trên bo mạch và quan sát 3 LED tương ứng để nghiệm thu (đảm bảo thử đủ 8 trường hợp tổ hợp ngõ vào)[cite: 2, 4].
