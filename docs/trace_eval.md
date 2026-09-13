# 📊 BÁO CÁO THU HOẠCH NGHIỆM THU BÀI LAB 3 (BƯỚC 3 — SUBMISSION ARTIFACT)

> **Họ và Tên Học viên:** [Lê Nguyễn Thái Dương]  
> **Mã Sinh Viên / Mã Học viên:** [02383]  
> **Chủ đề Lựa chọn:** [Trợ lý Học vụ Sinh viên VinUni]  

---

## 1. BẢNG CHẤM ĐIỂM AGENTIC FIT SCORING MATRIX (ĐÁNH GIÁ CHỦ ĐỀ)

| Tiêu chí Đánh giá | Mức độ (1 - 5) | Giải trình chi tiết lý do chọn điểm |
| :--- | :---: | :--- |
| **1. Multi-step Reasoning** | 5 / 5 | Tình huống yêu cầu Agent phải nhận diện intent, suy luận bước tiếp theo, rồi gọi Tool phù hợp để lấy dữ liệu và tổng hợp câu trả lời cuối cùng. |
| **2. Tool Interaction** | 5 / 5 | Hệ thống cần kết nối với MCP Server để tra cứu hồ sơ học vụ và đặt lịch hẹn, đây là dạng tác vụ chốt của ReAct Agent. |
| **3. Dynamic Decision** | 4 / 5 | Kết quả quan sát từ Tool thay đổi hành vi tiếp theo của Agent: nếu tìm thấy sinh viên thì trả lời, nếu không thấy sẽ phản hồi NOT_FOUND và không bịa dữ liệu. |
| **4. Long Horizon Goal** | 4 / 5 | Mục tiêu gồm nhiều lượt xử lý liên tiếp: nhận câu hỏi, quyết định Tool, thu thập dữ liệu, cuối cùng biên dịch thành phản hồi thân thiện cho học sinh. |
| **TỔNG ĐIỂM AGENTIC FIT** | **18 / 20** | *Nếu tổng điểm > 12/20: Bài toán rất phù hợp triển khai Agentic System.* |

---

## 2. TRÍCH XUẤT KẾT QUẢ WATERFALL TRACE LOG (SAU KHI CHẠY TEST SUITE TRÊN API THẬT)

> ⚠️ **Lưu ý hiện tại:** File `.env` vẫn đang chứa giá trị placeholder (`your_gemini_api_key_here` / `your_openai_api_key_here`), nên ứng dụng đang fallback về Mock Offline Provider. Kết quả hiện có xác minh đúng luồng ReAct và MCP, nhưng chưa đạt yêu cầu live API thực tế. Cần thay bằng API key thật trước khi nộp bài theo tiêu chí nghiệm thực tế.

Dán 1 đoạn trích xuất log tiêuểu từ file `docs/trace_waterfall.json` sau khi chạy test suite ở chế độ hiện tại:

```json
[
  {
    "step": 1,
    "query": "Hãy đặt lịch tư vấn học vụ cho sinh viên SV2026001 vào lúc 14:00 ngày 15/09/2026 với cố vấn PGS.TS Nguyễn Văn A.",
    "action_type": "TOOL_EXECUTION",
    "tool_name": "schedule_appointment",
    "arguments": {
      "student_id": "SV2026001",
      "datetime_str": "14:00 15/09/2026",
      "advisor_name": "PGS.TS Nguyễn Văn A"
    },
    "observation": {
      "status": "SUCCESS",
      "booking_id": "BK-SV2026001-99",
      "student_id": "SV2026001",
      "datetime": "14:00 15/09/2026",
      "advisor": "PGS.TS Nguyễn Văn A",
      "message": "Đặt lịch thành công cho sinh viên SV2026001 với PGS.TS Nguyễn Văn A vào lúc 14:00 15/09/2026."
    },
    "latency_ms": 7.76
  }
]
```

---

## 3. TỔNG KẾT KẾT QUẢ NGHIỆM THU & NỘP BÀI

- [ ] Đã điền API Key thật trong `.env` và xác nhận Agent chạy mượt mà trên LLM API thật (Gemini/OpenAI).  
  > Trạng thái hiện tại: `.env` vẫn là placeholder, nên ứng dụng đang chạy ở chế độ Mock Offline. Hãy thay `your_gemini_api_key_here` hoặc `your_openai_api_key_here` bằng key thật rồi chạy lại `python src/app.py --all`.
- **Tổng số Test Cases đã chạy thành công:** 5 / 5 test cases (ở chế độ mock hiện tại).
- **Số lượt gọi Tool qua MCP Server chính xác:** 5 lượt.
- **Kết quả đẩy Repo nộp bài:** [ ] Đã Commit và Push mã nguồn thành công lên GitHub cá nhân.

---

> ✅ **HOÀN TẤT NỘP BÀI:** Sao chép đường link GitHub Repository cá nhân của bạn và dán vào ô nộp bài trên hệ thống LMS VLearn để hoàn tất Bài Lab 3!
