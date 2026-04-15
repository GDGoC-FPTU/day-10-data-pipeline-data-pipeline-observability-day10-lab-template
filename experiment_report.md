# Báo cáo thí nghiệm: Ảnh hưởng của chất lượng dữ liệu đến AI Agent

**Student ID:** AI20K-115  
**Name:** Lương Thanh Hậu  
**Date:** 2026-04-15

---

## 1. Kết quả thực nghiệm

Chạy `agent_simulation.py` với hai bộ dữ liệu và ghi nhận đầu ra:

| Kịch bản | Đầu ra của Agent | Đánh giá độ chính xác (1-10) | Nhận xét |
|----------|------------------|------------------------------|----------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200. | 9 | Dữ liệu đã được làm sạch nên giá trị hợp lệ, loại sản phẩm nhất quán, Agent chọn phương án hợp lý. |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 2 | Dữ liệu nhiễu chứa outlier giá cực lớn và giá trị bất thường, làm Agent ưu tiên phương án phi thực tế. |

Kết quả kiểm thử tự động:

- **Autograding: 9/9 passed (100%)**

---

## 2. Phân tích và nhận xét

### Vì sao Agent trả lời sai với Garbage Data?

Trong bộ dữ liệu nhiễu, xuất hiện bản ghi có giá trị bất thường (`Nuclear Reactor` giá `999999`) nên Agent bị kéo theo tín hiệu sai.  
Ngoài ra, dữ liệu bẩn thường đi kèm trùng lặp, sai kiểu dữ liệu hoặc thiếu trường thông tin, dẫn đến quá trình tổng hợp/so sánh không còn phản ánh đúng thực tế.  
Vì Agent dựa trên dữ liệu đầu vào để suy luận, chỉ cần một số bản ghi nhiễu mạnh cũng đủ làm sai lệch quyết định cuối cùng.

---

## 3. Kết luận

### Quan điểm: “Quality Data > Quality Prompt”

**Đồng ý.**  
Prompt tốt giúp mô hình diễn đạt rõ hơn, nhưng không thể bù đắp cho dữ liệu đầu vào kém chất lượng.  
Thực nghiệm cho thấy cùng một logic Agent, dữ liệu sạch tạo ra kết quả hợp lý (`Laptop`), còn dữ liệu nhiễu dẫn tới kết luận sai lệch (`Nuclear Reactor`).  
Do đó, đảm bảo chất lượng dữ liệu là bước nền tảng trước khi tối ưu prompt hoặc mô hình.
