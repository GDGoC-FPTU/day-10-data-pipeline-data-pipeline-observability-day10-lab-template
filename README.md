# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** 26a1.hault@vinuni.edu.vn  
**Name:** Lương Thanh Hậu

---

## Mô tả

Bài lab này tập trung vào việc xây dựng pipeline ETL đơn giản và quan sát tác động của chất lượng dữ liệu đến quyết định của AI Agent.  
Quy trình gồm: làm sạch dữ liệu đầu vào, xuất dữ liệu đã xử lý (`processed_data.csv`), và so sánh phản hồi của Agent giữa dữ liệu sạch và dữ liệu nhiễu.

---

## Cách chạy

### 1) Cài đặt thư viện cần thiết
```bash
pip install pandas
```

### 2) Chạy ETL Pipeline
```bash
python solution.py
```

### 3) Chạy Agent Simulation (Clean vs Garbage Data)
```bash
python agent_simulation.py
```

---

## Cấu trúc thư mục

```text
├── solution.py              # Script ETL Pipeline
├── agent_simulation.py      # Mô phỏng Agent trên 2 bộ dữ liệu
├── processed_data.csv       # Dữ liệu đã làm sạch
├── garbage_data.csv         # Dữ liệu nhiễu để stress test
├── experiment_report.md     # Báo cáo thí nghiệm
└── README.md                # Tài liệu bài lab
```

---

## Kết quả chính

Kết quả chạy `agent_simulation.py`:

- **Testing with CLEAN data:**  
  `Agent: Based on my data, the best choice is Laptop at $1200.`
- **Testing with GARBAGE data:**  
  `Agent: Based on my data, the best choice is Nuclear Reactor at $999999.`

Kết quả cho thấy dữ liệu sạch giúp Agent đưa ra lựa chọn hợp lý, trong khi dữ liệu nhiễu khiến Agent đưa ra quyết định sai lệch do outlier bất thường.

Ngoài ra, phần kiểm thử tự động đạt: **Autograding 9/9 passed (100%)**.
