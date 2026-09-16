# AN Sức khỏe

> Chatbot hỗ trợ đánh giá triệu chứng ban đầu, xác định mức độ nguy hiểm và đưa ra lời khuyên an toàn dựa trên flow triage rõ ràng.

## 1. Tổng quan dự án

AN Sức khỏe là sản phẩm chăm sóc sức khỏe hướng tới người dùng cần:
- kiểm tra triệu chứng một cách nhanh chóng,
- hiểu mức độ nguy hiểm của tình trạng hiện tại,
- nhận khuyến nghị rõ ràng như theo dõi tại nhà, khám bác sĩ, hoặc gọi cấp cứu.

Dự án lấy cảm hứng từ các ứng dụng symptom assessment thực tế nhưng được tối giản cho demo hackathon: chỉ tập trung vào flow quan trọng nhất, nhanh, dễ hiểu, và có độ an toàn cao.

## 2. Điểm mạnh so với sản phẩm thực tế

Các ứng dụng y tế thực tế như Ada Health thường ưu tiên 3 yếu tố:
- flow hỏi từng bước,
- triage rõ ràng theo mức độ nguy hiểm,
- giao diện không gây overload cho người dùng.

AN Sức khỏe kế thừa đúng nguyên tắc đó nhưng bổ sung thêm:
- xác nhận lại thông tin AI đã hiểu,
- hiển thị mức độ rủi ro rõ ràng,
- có fallback logic nếu AI không chắc chắn,
- luôn có cảnh báo an toàn và disclaimer.

Điểm khác biệt lớn là: sản phẩm không chỉ "chat AI" mà có cấu trúc triage và hành động rõ ràng, rất phù hợp cho demo và có tính khả thi khi mở rộng.

## 3. Luồng demo

1. Người dùng nhập triệu chứng bằng ngôn ngữ tự nhiên.
2. Hệ thống xác nhận triệu chứng đã hiểu.
3. Hỏi tối thiểu 1–3 câu để làm rõ tình trạng.
4. Đánh giá low / medium / high risk.
5. Gợi ý hành động phù hợp:
   - theo dõi tại nhà,
   - gặp bác sĩ trong 24h,
   - gọi cấp cứu ngay.

## 4. Công nghệ sử dụng

- Frontend: React + Vite
- UI animation: Framer Motion
- Backend: Python
- AI provider: Gemini / provider abstraction
- Design: single-flow symptom assessment, mobile-friendly

## 5. Kiến trúc hệ thống

- Frontend render giao diện triage và hiển thị kết quả
- Backend xử lý hội thoại, tool-calling và model orchestration
- Provider layer cho phép thay đổi model mà không phá app
- Fallback rule-based engine để đảm bảo app không chết khi AI lỗi
- Transcript logging để review và debug các lượt demo

## 6. Tại sao đây là sản phẩm đáng xem

- Flow demo rõ ràng, không dài dòng
- Dễ hiểu với người xem vì ai cũng biết mục tiêu của app
- Thể hiện được khả năng AI trong thực tế, không chỉ mock UI
- Có tính an toàn và minh bạch, rất quan trọng trong y tế
- Có khả năng mở rộng sang đặt lịch khám, đọc bệnh nền, gợi ý cơ sở y tế

## 7. Cách chạy local

Frontend:

```bash
cd codebase
npm install
npm run dev
```

Backend:

```bash
cd codebase/backend
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
python server.py
```

## 8. Kết luận

AN Sức khỏe là một AI health assistant tập trung vào triage triệu chứng, UX đơn giản và an toàn. Nó không cố làm “AI y khoa hoàn chỉnh”, mà tập trung vào việc chứng minh một trải nghiệm khả thi, rõ ràng và có giá trị trong thực tế.

---

AN Sức khỏe — lightweight, explainable, and demo-ready.
