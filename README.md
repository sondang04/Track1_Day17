# Track 1 — Day 17: Problem Hypothesis & Customer Interview

---

## 1. Thông Tin Cá Nhân và Nhóm

**Cá nhân**

| | |
|---|---|
| **Họ và tên** | Đặng Thái Nam Sơn |
| **MHV/MSSV** | 2A202601431 |
| **Vai trò trong vòng này** | Người ghi chép + phân tích kết quả; người viết Problem Hypothesis và Conversation Guide |

**Nhóm**

**Tên nhóm**: [Điền tên nhóm]

| # | Họ và tên | MHV/MSSV |
|---|---|---|
| 1 | Đặng Thái Nam Sơn | 2A202601431 |
| 2 | Đào Ngọc Bích | 2A202601745 |
| 3 | Lương Thanh Trang | 2A202601363 |

**Case đã chọn**: **Case C — AI Support Radar**

> Sau mỗi phiên học, hệ thống phân tích các tín hiệu (di chuyển giữa slide, dừng lâu hoặc xem lại, highlight và ghi chú, đánh dấu "Chưa hiểu", thay đổi câu trả lời, nội dung trao đổi với AI Chat) rồi tạo một **Support Queue** cho giảng viên: những học viên có thể cần hỗ trợ, phần nội dung họ đang gặp khó, các tín hiệu dẫn tới nhận định đó, và một hành động hỗ trợ được đề xuất. Giảng viên xem lại và quyết định có liên hệ hay không.

| Thành phần | Solution đã mô tả |
|---|---|
| Trigger | Kết thúc một phiên học |
| Input | Slide navigation, notes, answers và AI Chat |
| AI action | Suy đoán nhu cầu hỗ trợ và xếp mức ưu tiên |
| Output | Support Queue cho giảng viên |
| Human control | Giảng viên quyết định có can thiệp hay không |

---

## 2. Problem Hypothesis Brief (Kết quả Chặng 1)

📄 Bản đầy đủ: [01-hypothesis/problem-hypothesis-SonDang.md](01-hypothesis/problem-hypothesis-SonDang.md)

**Capability trung tính**: Thu thập hành vi học tập của học viên trên VLearn trong phiên học, tổng hợp cho giảng viên, chỉ ra chỗ từng học viên có thể chưa hiểu và đề xuất hướng hỗ trợ.

**Actor được chọn để điều tra**: **Học viên** (không phải giảng viên).
Lý do: cả chuỗi thay đổi của Case C đứng trên giả định *"học viên dùng VLearn đủ nhiều để sinh ra tín hiệu"*. Nếu giả định đó sai thì vấn đề của giảng viên có thật đến đâu cũng không giải được bằng Support Queue.

**Ba giả thuyết trước phỏng vấn**

| | Giả thuyết |
|---|---|
| **H1** | Học viên trên VLearn, khi **đọc lại bài sau buổi học và chọn nội dung ôn cho kỳ giữa kỳ**, không xác định được phần nào mình chưa nắm để ưu tiên ôn, vì không có phản hồi khách quan nào ngoài điểm kiểm tra — thứ đến quá trễ — nên phải dựa vào cảm giác chủ quan; dẫn tới ôn dàn trải, vẫn hổng kiến thức, kèm lo lắng. |
| **H2** | Học viên không để lại đủ tín hiệu chủ động trên VLearn (highlight, ghi chú, đánh dấu "Chưa hiểu", AI Chat) vì các thao tác này **tốn công và không trả lại lợi ích tức thì**, khiến dữ liệu thu được thưa và thiên lệch. |
| **H3** | Giảng viên lớp đông, khi viết recap, không xác định được chủ đề nào lớp thực sự cần củng cố vì chỉ có tín hiệu từ số ít học viên chủ động hỏi. |

**Kết quả sau khi phỏng vấn User 1** (n=1, chưa chốt)

| Giả thuyết | Kết luận | Bằng chứng |
|---|---|---|
| **H1** | ⚠️ **Cần điều chỉnh** — lõi root cause ✅ đúng, Situation ❌ sai, Pain ⬜ chưa đo được | *"mình cũng không biết là mình có bỏ qua hay không. Cái đấy là quan trọng."* [05:31] — nhưng *"mình không dành thời gian ôn tập quá nhiều ở sau giờ học"* [00:44] |
| **H2** | ✅ **Ủng hộ mạnh** — nhưng root cause khác hẳn | Ghi chú ra app ngoài [03:02]; AI tutor *"quá chậm... 1 phút 2 phút"* nên dùng AI ngoài [04:13] |
| **H3** | ⬜ **Chưa phỏng vấn được giảng viên** | — |
| **H4** *(mới)* | ⚠️ Bằng chứng ban đầu ủng hộ | Không có known-unknown [03:52] + không biết mình bỏ sót gì [05:31] + đọc đều 3–5 phút mọi slide [01:18] |

**Giả thuyết đã cập nhật**

> **H1'** — Học viên chủ động trên VLearn (đọc trước toàn bộ slide, ôn lại từ đầu đến cuối trước kỳ kiểm tra) **không thể biết mình đã lướt qua mất phần nào**, vì những chỗ vô tình bỏ qua **không để lại dấu hiệu nào cho chính họ**; điều này buộc họ quét lại toàn bộ như một hình thức bảo hiểm, kèm cảm giác bất an mà chính họ gọi là *"điều đáng quan ngại"*.

> **H2'** — Học viên không để lại tín hiệu trên VLearn vì **công cụ trong VLearn phản hồi chậm hơn công cụ ngoài** (AI tutor mất 1–2 phút/câu), nên cả ghi chú lẫn câu hỏi đều chảy sang ứng dụng bên ngoài — nơi hệ thống không nhìn thấy.

> **H4 (mới)** — Các tín hiệu Case C dựa vào (dừng lâu, xem lại, đánh dấu "Chưa hiểu") **chỉ bắt được known-unknown**. Với unknown-unknown — chỗ học viên tự tin lướt qua — hệ thống **không thu được tín hiệu nào**. Vùng rủi ro cao nhất cũng là vùng vô hình nhất với Support Queue.

⚠️ **Phạm vi bằng chứng**: vòng này chỉ có **learner-side evidence** với **n = 1**, và User 1 thuộc nhóm học viên rất chủ động. Instructor-side job chưa được kiểm chứng. Không suy rộng kết luận nào ra cả tệp học viên cho tới khi có User 2.

---

## 3. Conversation Guide — Phiên Bản Cuối

📄 Bản đầy đủ: [02-guide/conversation-guide-SonDang.md](02-guide/conversation-guide-SonDang.md)
(Phần A = guide dùng để phỏng vấn; Phần B = bản đã sửa sau khi luyện)

**Cấu trúc**: 5 phase / 45 phút — Mở đầu (chốt "buổi học neo") → Quá khứ gần nhất → Hiện trạng + **mở VLearn ra đối chứng** → Cảm xúc & nỗi đau → Kết thúc. Kèm module 6 câu cho giảng viên (H3) và một khối câu hỏi về quyền riêng tư đặt **sau** khi đã đóng buổi.

**Những gì đã sửa sau buổi luyện với User 1**

*Bỏ:*
- Câu tóm tắt đóng kết thúc bằng *"đúng không?"* [01:00] → chỉ nhận được "Đúng rồi.", giết mạch đào ngay sau phát hiện lớn nhất buổi.
- Câu mô tả sẵn khái niệm "vùng giữa" dài ~30 giây [04:29] → đáp án nằm sẵn trong câu hỏi; bằng chứng thu được phải đánh dấu 🚩 và loại bỏ.
- Vế *"...hay là bạn đã biết trước?"* [02:27] → tự cấp sẵn lý do cho user.

*Sửa:*
- Câu hỏi hai nòng [01:46] → tách hẳn hai lượt. Bằng chứng: user rối, phải hỏi ngược *"bạn hỏi lại... hỏi lại cái..."*, vế hai rơi mất 2 phút rưỡi.
- *"Bạn biết bằng cách nào?"* → tách riêng và **đòi lại cho tới khi có câu trả lời**. Ở buổi User 1, vế này bị lảng và không bao giờ được trả lời.
- Câu săn điểm mù → thêm đường vòng bắt buộc khi user trả lời "không/rất ít": *"Có lần nào đi thi rồi gặp một phần mà lúc học bạn thấy ổn không? Kể lần gần nhất."*
- *"Cái gì khiến bạn chọn cách ghi chú hiện tại?"* → nêu đích danh từng tính năng (*"tại sao không dùng bôi đen / ghi chú / tutor?"*), vì bản đích danh cho ra root cause sắc nhất buổi.

*Thêm:*
- *"Trước buổi giảng bạn có đọc slide trước không?"* → vào warm-up, vì giả định "học sau buổi" đã sai.
- *"Buổi đó bạn dừng ở slide nào lâu nhất? Vì sao?"* → kiểm chứng H4.
- Câu sàng lọc trước khi mời user, để tránh mẫu lệch về nhóm học viên chăm.

*Quy tắc vận hành mới:*
- **Mốc 20 phút**: quá mốc là chuyển sang Phase 4 bất kể đang dở gì.
- **Không ai được nói "câu cuối"** khi chưa tick đủ 8 câu ⭐.
- **Warm-up là bắt buộc**, kể cả khi buổi bị rút ngắn.

---

## 4. Practice Reflection (Ba câu trả lời ở Chặng 4)

📄 Bản đầy đủ: [interview_sondang/practice-reflection.md](interview_sondang/practice-reflection.md)

### Câu 1 — Câu hỏi nào hiệu quả nhất?

**"Lần đầu tiên bạn mở lại nội dung bài đó là lúc nào? Bạn mở cái gì trước?"** [00:28]

Hiệu quả vì nó hỏi về **một buổi học có thật đã được neo**, và **không giả định** rằng user có ôn lại — dù cả nhóm tin chắc là có. Chính chỗ trống đó cho user cơ hội nói ngược lại, và trong **40 giây** nó phá vỡ phần Situation của giả thuyết mà tôi mất cả buổi để viết:

> *"thực ra thì mình không dành thời gian ôn tập quá nhiều ở sau giờ học. Mà bình thường mình sẽ dùng VLearn để theo dõi cái bài giảng của cô và hiểu bài ngay trong cái lúc đấy."*

Hai câu hiệu quả tiếp theo: *"tại sao bạn không dùng bôi đen / ghi chú / tutor của VLearn?"* (cho ra root cause thật: chậm 1–2 phút), và câu săn điểm mù — câu tưởng như thất bại nhưng lại tạo ra phát hiện sắc nhất buổi.

### Câu 2 — Khi nào tôi lỡ dẫn dắt?

Ba lần, và đau nhất là lần thứ ba:

1. **Câu tóm tắt đóng** [01:00] — *"...bạn dùng VLearn đa phần trong lúc đang học đúng không?"* → nhận đúng 2 từ: "Đúng rồi."
2. **Câu hai nòng** [01:46] → user rối, hỏi ngược *"bạn hỏi lại... hỏi lại cái..."*, một nửa câu hỏi rơi mất.
3. **Mô tả sẵn khái niệm rồi hỏi có/không** [04:29] → user đáp *"mình nghĩ là có, nghĩ là có... có thể là sẽ có"*. Ngữ điệu đó là của người đang suy đoán để chiều người hỏi, không phải người đang nhớ lại. Đây đúng là dữ liệu **H1 cần nhất**, và giờ nó không dùng được — tôi phải đánh dấu 🚩 và loại khỏi phần xác thực giả thuyết.

Tôi ngồi vai ghi chép nên không phát ra các câu này. Nhưng chính guide tôi viết có dòng *"người ghi chép được hỏi bù ở 5 phút cuối"* — tôi nghe thấy cả ba lần và **không dùng quyền đó lần nào**. Nên tôi tính đây là lỗi của mình ở mức "thấy mà không cứu".

### Câu 3 — Bài học chính rút ra là gì?

**Tôi đoán sai ở phần dễ nhất, không phải phần khó.** Tôi đổ rất nhiều công vào H2 — giả thuyết tinh vi về việc học viên không để lại tín hiệu — và H2 đúng. Nhưng tôi lại đoán sai một chuyện đơn giản hơn nhiều: **khi nào học viên thật sự học**. Tôi mặc định "ôn tập = việc làm sau giờ học", mà đó là thói quen của chính tôi chứ không phải dữ liệu. Phần nguy hiểm nhất của một giả thuyết không phải phần mình thấy khó, mà phần mình thấy **hiển nhiên nên không buồn kiểm tra**.

Hai bài học còn lại:
- **Phải đọc cả buổi như một chỉnh thể.** Câu [03:52] ("chưa gặp trường hợp đấy") nhìn riêng là bác bỏ H1; đặt cạnh [05:31] ("không biết mình có bỏ qua hay không") thì thành phát hiện quan trọng nhất buổi — user không có *known-unknown*, vấn đề của họ nằm hoàn toàn ở *unknown-unknown*.
- **Vai người ghi chép không phải vai bị động.** Buổi dừng ở 5 phút 54 giây / 45 phút thiết kế, Phase 4 mất trắng, nên đến giờ nhóm vẫn chưa biết vấn đề này có đáng giải hay không.

---

## 5. AI Support Log

**AI đã giúp gì**
- Hoàn thiện Problem Hypothesis từ bản nháp của tôi: điền Bước 1–4, viết tiêu chí kiểm chứng, và thêm **bảng dấu hiệu bác bỏ** — thứ tôi chưa nghĩ tới và hoá ra là phần hữu ích nhất khi đọc lại transcript.
- Soạn Conversation Guide: 5 phase kèm script, module 6 câu cho giảng viên, bảng đối chiếu câu hỏi dẫn dắt, và bản rút gọn 8 câu ⭐ cho tình huống thiếu giờ.
- Dựng interview notes từ transcript: tách Facts / Interpretation, gắn timestamp cho từng quote, đánh dấu 🚩 các bằng chứng đến sau câu hỏi dẫn dắt.
- Phát hiện mâu thuẫn biểu kiến giữa [03:52] và [05:31] và diễn giải nó thành phân biệt known-unknown / unknown-unknown — từ đó sinh ra H4.

**Chỗ AI sai hoặc hời hợt, và tôi đã sửa thế nào**

| # | AI đưa ra | Vấn đề | Tôi đã sửa |
|---|---|---|---|
| 1 | Root cause của H2: *"thao tác tốn công và không trả lại lợi ích tức thì"* | Đây là lối mòn "học viên ngại/lười". Phỏng vấn thật cho ra nguyên nhân hoàn toàn khác: **AI tutor mất 1–2 phút mới trả lời**, thua các AI ngoài | Viết lại thành **H2'** — vấn đề hiệu năng, không phải động lực. Kéo theo hệ quả khác hẳn: phải sửa độ trễ trước khi nói tới Support Queue |
| 2 | Situation: *"đọc lại bài sau buổi học"* viết như dữ kiện | AI chỉ đánh dấu "giả định cần kiểm chứng" ở phần *hành vi hiện tại*, không đánh dấu ở phần *Situation* — nên chỗ sai nhất lại là chỗ trông chắc chắn nhất | Viết lại Situation thành "trước và trong giờ giảng", và thêm câu sàng lọc *"bạn có hay đọc slide trước buổi học không?"* vào warm-up của guide |
| 3 | Lần đầu AI **ghi đè trực tiếp** lên `conversation-guide-v1.md` (file gốc của lab) | Làm mất bản template gốc, không còn đối chiếu được | Tôi yêu cầu làm trên **bản copy riêng** (`conversation-guide-SonDang.md`); file gốc được khôi phục nguyên trạng |
| 4 | AI điền **tên đầy đủ** vào phần Người phỏng vấn / Người ghi chép của interview notes | Tài liệu có mặt người thứ ba và một người được phỏng vấn | Tôi tự đổi sang dạng ẩn danh (**T\*\*\*h / S\*n**) và gọi người được phỏng vấn là **User 1** |
| 5 | AI viết rất dài, giọng chắc nịch | Dễ khiến người đọc tưởng kết luận đã vững, trong khi mẫu chỉ có **n = 1** và User 1 lại thuộc nhóm học viên rất chủ động | Giữ nguyên các cảnh báo n=1 ở mọi tài liệu, và tự đối chiếu lại từng quote với transcript trước khi nộp |

**Giới hạn cần ghi rõ**: AI không có mặt trong buổi phỏng vấn. Mọi FACT trong interview notes đều đến từ transcript, nên phần mô tả thái độ / phản ứng của người được phỏng vấn là **suy ra từ lời nói và ngữ điệu văn bản**, không phải quan sát trực tiếp tại chỗ.

---

## 📁 Cấu Trúc Bài Nộp

| File | Nội dung |
|---|---|
| [01-hypothesis/problem-hypothesis-SonDang.md](01-hypothesis/problem-hypothesis-SonDang.md) | Problem Hypothesis đầy đủ (Chặng 1) |
| [02-guide/conversation-guide-SonDang.md](02-guide/conversation-guide-SonDang.md) | Conversation Guide — Phần A (dùng để hỏi) + Phần B (đã sửa sau khi luyện) |
| [interview_sondang/interview-notes-user1.md](interview_sondang/interview-notes-user1.md) | Interview Notes User 1 — Facts vs Interpretation, 5 insight |
| [interview_sondang/transcript_phong_van_on_thi.md](interview_sondang/transcript_phong_van_on_thi.md) | Transcript đầy đủ |
| [interview_sondang/practice-reflection.md](interview_sondang/practice-reflection.md) | Practice Reflection cá nhân (Chặng 4) |
| `interview_sondang/Interview_SonDang.m4a` | File ghi âm |

---

## 🔜 Việc Còn Thiếu

- [ ] **Phỏng vấn User 2** — ưu tiên số 1: dành trọn Phase 4 (severity, tần suất, chi phí đã trả), phần mất trắng ở buổi User 1
- [ ] **Phỏng vấn giảng viên/coach** để kiểm chứng H3
- [ ] Cập nhật H1' / H2' / H4 vào file Problem Hypothesis sau khi có User 2
- [ ] Điền tên nhóm

---

**Trạng thái**: Hoàn thành vòng 1 (1/2 phỏng vấn học viên) — 17/08/2026
