# Ý tưởng: Web app cho người tập gym & PT — tóm tắt trao đổi

> Ngày: 15/10/2026 · Trạng thái: **đang khám phá ý tưởng, chưa code**

## 1. Ý tưởng ban đầu (Phát)

- Web app lĩnh vực fitness / gym, người dùng đầu tiên là **người tập gym**.
- Tính năng chính:
  - Quản lý tiến trình bằng ảnh và cân nặng.
  - Ghi mức tạ tập luyện, so sánh và đánh giá theo thời gian.
  - Quản lý lịch ăn và lịch tập.
- Sau này mở rộng cho **PT kết nối với học viên**.
- Lộ trình: làm web app → quảng bá trên diễn đàn / nhóm gym → nếu nhiều người dùng thì thương mại hoá.

## 2. Đánh giá ban đầu

- **Thị trường rất đông** nếu làm app gym tổng quát:
  - Ghi mức tạ: Hevy, Strong, JEFIT, Fitbod.
  - Ăn uống / calo: MyFitnessPal, Cronometer, MacroFactor.
  - PT ↔ học viên: Trainerize, TrueCoach, Everfit (Everfit do người Việt làm).
- **Lợi thế thật nếu nhắm thị trường VN:**
  1. Dữ liệu món ăn Việt (cơm tấm, phở, "1 chén cơm"…) kèm calo / macro.
  2. Tiếng Việt và văn hoá tập ở VN.
  3. **Phía PT là chỗ ra tiền**: PT chịu trả phí, người tập ít trả. Một PT kéo theo 10–30 học viên.
- Kết luận: có tiềm năng nếu bám thị trường Việt; ít tiềm năng nếu làm "một Hevy thứ hai".

### Lưu ý thiết kế cho người tập
- Web app nhưng **ưu tiên điện thoại (PWA)**: ghi một hiệp chỉ 1–2 lần chạm, mở nhanh, ghi được khi mất mạng.
- **Ảnh cơ thể là dữ liệu nhạy cảm**: lưu riêng tư, mã hoá ngay từ đầu.
- Thước đo của bản thử: người dùng **còn dùng sau 4 tuần không**, không phải số người đăng ký.

## 3. Tính năng nếu hướng cho PT

Nỗi khổ của PT VN hiện tại: gửi giáo án bằng ảnh / Excel qua Zalo, nhắc từng học viên báo cáo bằng tin nhắn, đếm buổi còn lại bằng sổ tay hoặc trí nhớ (hay quên nhắc gia hạn), không có gì để cho học viên thấy tiến bộ.

**Bản đầu tiên (đủ để bỏ Zalo + Excel):**
1. Danh sách học viên: hồ sơ, mục tiêu, chấn thương; mời bằng link / mã.
2. Soạn giáo án: thư viện bài tập tiếng Việt, buổi tập hiệp × lần × tạ × nghỉ, lưu mẫu.
3. Giao giáo án theo tuần và xem kết quả học viên ghi.
4. Check-in định kỳ: cân nặng, số đo, ảnh 3 góc, câu hỏi ngắn; xem ảnh đặt cạnh nhau theo thời gian.
5. Quản lý gói buổi: số buổi, đã dùng, hết hạn, tự nhắc khi còn 2–3 buổi (**chỉ theo dõi, không làm thanh toán**).
6. Bảng tổng quan của PT: lịch hôm nay, ai bỏ tập, ai chưa báo cáo, ai sắp hết gói.

**Bản tiếp theo:** nhắn tin trong app, thực đơn món Việt, lịch hẹn buổi tập, báo cáo trước/sau để chia sẻ, gắn thương hiệu PT.

**Để sau nữa:** phòng gym nhiều PT, chợ tìm PT, thanh toán online, AI gợi ý giáo án.

**Hai điểm thiết kế phải đúng từ đầu (cửa một chiều):**
- Một tài khoản dùng được cả hai vai. Học viên dùng độc lập, kết nối PT sau. **Dữ liệu thuộc về học viên**, đổi PT thì dữ liệu đi theo.
- Phân quyền xem: PT chỉ thấy học viên đang kết nối; học viên ngắt kết nối thì PT mất quyền xem (nhất là ảnh).

**Gợi ý thu phí:** miễn phí tối đa 3 học viên, sau đó thu theo tháng; học viên luôn miễn phí.

## 4. Quan sát của Phát về nỗi khổ lớn nhất của PT

1. **Học viên mới:** PT chưa hiểu thể trạng, thói quen, nên phải mất thời gian làm việc cùng nhau để chỉnh giáo án.
2. **PT lớn, nhiều học viên:** tốn thời gian lên giáo án cho từng người theo từng giai đoạn, cực nhất là **peak week cho học viên thi đấu**.

### Hướng giải

**a. Rút ngắn thời gian hiểu học viên mới**
- Phiếu đánh giá đầu vào có cấu trúc (PT tự chỉnh): thể trạng, chấn thương, thói quen ngủ / ăn / làm việc, kinh nghiệm tập. Học viên điền trước buổi đầu.
- Tuần kiểm tra đầu tiên chuẩn hoá: kết quả thành **mốc gốc**, giáo án tính theo % mốc đó.
- **Lịch sử mang theo**: học viên tự dùng app từ trước → PT mới thấy ngay vài tháng dữ liệu. Đây là lợi thế lớn nhất, Zalo + Excel không làm được.

**b. Lên giáo án theo giai đoạn cho nhiều học viên**
- Mẫu nhiều tầng: chu kỳ lớn (vd 16 tuần) → khối 3–6 tuần → tuần → buổi. Giao cho ai thì tự quy đổi mức tạ theo mốc gốc người đó.
- Luật điều chỉnh (vd đạt đủ số lần → tuần sau +2,5 kg; mệt ≥ 8/10 → giảm khối lượng). App **đề xuất**, PT duyệt.
- Một bảng cho thấy học viên nào cần chỉnh giáo án tuần này.

**c. Peak week: mũi nhọn để vào thị trường**
- Người thi đấu chịu chi nhất, prep coach thu phí cao nhất, ở VN gần như chưa có công cụ riêng.
- Kế hoạch từng ngày 7–10 ngày cuối (carb, nước, muối, tập, cardio, giờ ăn); báo cáo mỗi sáng (cân, ảnh, cảm giác); **so với lần thi trước của chính người đó**; đếm ngược tới ngày thi.
- ⚠️ Peak week có thao tác nước / muối, làm sai có thể nguy hiểm. App **chỉ là công cụ ghi và theo dõi cho PT**, không tự đề xuất lượng nước / muối, có điều khoản trách nhiệm chuyên môn thuộc PT.

**Định vị đề xuất:**
> "Công cụ cho HLV chuẩn bị thi và PT lớn: hiểu học viên mới trong 1 tuần, lên giáo án theo giai đoạn trong vài phút."

## 5. Kết quả tìm trên internet (15/10/2026)

> Đa số nguồn là blog của bên bán phần mềm, chỉ dùng tham khảo. **Không tìm được ý kiến thật của PT Việt Nam.**

### Phát hiện quan trọng: đối thủ ở VN đã có
**[CoachHelm](https://coachhelm.vn/)**, "Coach OS cho Huấn luyện viên Cá nhân Việt Nam":
- Giáo án, ghi buổi tập, thực đơn / macro, check-in và phản hồi.
- Cảnh báo sắp hết buổi / hết gói, tự nhắc gia hạn, theo dõi thanh toán.
- Chạy trên web, không cần cài app; dùng thử 30 ngày; giá "dưới giá một buổi tập" (không công bố cụ thể).
- Đối tượng: PT tự do khoảng 10–30 học viên, PT phòng gym, HLV online. Hơn 20 HLV cố vấn; không công bố số người dùng.
- **Không nhắc tới prep coach / peak week.**

→ Hướng "phần mềm quản lý PT chung" ở VN đã có người đi trước. **Góc prep coach còn trống.**

### Bằng chứng khớp với quan sát của Phát
- Than phiền phổ biến của PT: mất nhiều thời gian tạo và sửa giáo án cho từng học viên; công cụ chậm, sửa nhỏ nhiều thao tác ([1fit](https://1fit.com/2026/07/reddit-personal-trainer-coaching-software-problems/)).
- TrueCoach không tự động hoá, phải sửa từng học viên; khoảng 10 học viên thì ổn, gần 30 thì rất mất thời gian ([Everfit blog](https://blog.everfit.io/everfit-vs-trainerize-vs-truecoach)).
- Người dùng PT Distinction khen việc dùng lại mẫu rồi chỉnh nhanh cho từng người ([Capterra](https://www.capterra.com/p/141155/PT-Distinction/reviews/?page=6)).
- PT không có quy trình đón học viên mất cả buổi đầu để hỏi thông tin, dễ sót chấn thương; học viên hăng 3–4 tuần rồi bỏ, thường do khâu đón chứ không do giáo án ([NFPT](https://nfpt.com/structuring-a-successful-fitness-client-onboarding-process/)).
- Khoảng 25 học viên là giới hạn khi dùng Excel + tin nhắn; 40–60 nếu check-in có khuôn cố định (blog bên bán, số không có nguồn) ([lvlup](https://lvlup-app.com/blog/how-many-clients-can-an-online-coach-handle)).
- PT online ở VN giao bài, thực đơn, nhận báo cáo qua Facebook / Zalo / Viber ([PTGo](https://ptgo.vn/tap-gym-voi-pt-online-loi-ich-va-rui-ro/)).

### Mảng prep coach ở nước ngoài
- [QuickCoach](https://www.quickcoach.fit/physique-prep-coaching-software.html): HLV chạy giáo án 16 tuần cho 10–30 học viên, khoảng 39 USD/tháng.
- [PeakIQ](https://peakiq.app/): có hỗ trợ peak week, từ khoảng 15 EUR/tháng.
- → Nhu cầu có thật và có người trả tiền; chưa ai làm cho VN.
- Điểm yếu chung nên tránh: phí theo số học viên, vượt mốc là nhảy bậc giá cao ([MicroGaps](https://www.microgaps.com/gaps/online-personal-trainer-flat-rate-platform)).

## 6. Dữ kiện: đã đủ gì, còn thiếu gì

**Đã đủ:** kỹ thuật dựng web app đầy đủ (Next.js + Django + Postgres); kiến thức chung về giáo án theo giai đoạn, quy đổi %, khuôn check-in; bức tranh đối thủ. Đủ để làm **một bản giống các app đang có**.

**Còn thiếu (phần quyết định thắng thua):**

| Thiếu | Vì sao quan trọng | Lấy ở đâu |
|---|---|---|
| Cách prep coach VN thật sự làm việc | Đây là điểm khác biệt; đoán sai thì dựng cho quy trình không ai dùng | Ngồi với 2–3 prep coach, xin xem file Excel |
| Peak week thực tế (mỗi HLV một kiểu) | Biết cần ghi trường nào; không tự đặt quy trình vì rủi ro sức khoẻ | Chính các HLV đó |
| Thứ tự đau thật (giáo án / check-in / gói buổi) | Quyết định làm gì trước 2–3 tháng đầu | Phỏng vấn 5–10 PT |
| Mức sẵn sàng trả tiền | Quyết định có đáng thương mại hoá | Hỏi thẳng hoặc thử bán trước |
| Dữ liệu món ăn Việt kèm calo / macro | Cần cho phần thực đơn, không tự bịa số | Bảng thành phần thực phẩm VN của Viện Dinh dưỡng + nhập dần |
| CoachHelm hở chỗ nào | Đọc trang giới thiệu không biết được | Dùng thử 30 ngày |

## 7. Việc tiếp theo (chưa code)

1. **Dùng thử CoachHelm 30 ngày**, ghi lại chỗ vướng / thiếu.
2. **Nhắn 3–5 prep coach** (group thể hình VN), hỏi:
   - Mùa thi vừa rồi quản lý bao nhiêu học viên?
   - Lên plan bằng gì?
   - Khâu nào mất thời gian nhất?
3. **Xin xem file Excel** họ dùng cho một học viên mùa thi: cột gì, nhịp nào, chỉnh ở đâu.
4. Có đủ ba thứ trên → thiết kế phần lõi (dữ liệu học viên, giáo án theo giai đoạn, peak week) → dựng bản đầu cho chính các HLV đó dùng thử.
