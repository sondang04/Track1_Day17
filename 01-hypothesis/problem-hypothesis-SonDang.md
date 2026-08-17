# Problem Hypothesis Development

**Bài Lab**: Track 1 - Day 17  
**Ngày hoàn thành**: 17/08/2026  
**Tác giả/Thành viên**: Đặng Thái Nam Sơn (MSSV 2A202601431)

---

## 📌 Solution Directive (Xuất phát điểm)

**Đề bài đã chọn**

>Case C — AI Support Radar
Sau mỗi phiên học, hệ thống phân tích các tín hiệu như di chuyển giữa slide, dừng lâu hoặc xem lại, highlight và ghi chú, đánh dấu “Chưa hiểu”, thay đổi câu trả lời, và nội dung trao đổi với AI Chat.

AI tạo một Support Queue cho giảng viên, gồm:

Những học viên có thể cần hỗ trợ.
Phần nội dung mà họ có thể đang gặp khó khăn.
Các tín hiệu dẫn đến nhận định đó.
Một hành động hỗ trợ được đề xuất.
Giảng viên xem lại và quyết định có liên hệ với học viên hay không.

| Thành phần | Solution đã mô tả |
|---|---|
| Trigger | Kết thúc một phiên học |
| Input | Slide navigation, notes, answers và AI Chat |
| AI action | Suy đoán nhu cầu hỗ trợ và xếp mức ưu tiên |
| Output Support | Queue cho giảng viên |
| Human control | Giảng viên quyết định có can thiệp hay không |

**Người phù hợp để phỏng vấn:** ưu tiên hai learners và một coach/instructor. Nếu không có coach/instructor trong giờ lab, nhóm có thể phỏng vấn ba learners nhưng phải ghi rõ: “Vòng này chỉ có learner-side evidence; instructor-side job chưa được kiểm chứng.”


1. Diễn đạt lại directive dưới dạng capability trung tính:

- Thu thập thông tin và hành vi của học viên trên VLearn trong phiên học, như di chuyển giữa slide, highlight/ghi chú/hỏi tutor, etc. sau đó tổng hợp thông tin cho giảng viên, highlight các chi tiết mà từng học viên chưa hiểu và đề xuất hướng hỗ trợ học viên

=> Nâng cấp chất lượng giảng dạy của giảng viên


2. Chuỗi thay đổi được kỳ vọng:

Từ Solution (giải pháp) -> 
0: Học viên được kỳ vọng sẽ sử dụng Vlearn nhiều hơn. 
A. Mở rộng database: thông tin được bôi đen, chatlogs, thời gian đọc slide -> chia theo mỗi bài giảng. 
B. Có thêm data về thời gian đọc slide, sẽ giúp chỉ ra các slide mà học viên dành nhiều thời gian đọc. 
C. Có dữ liệu đọc, sẽ giúp giảng viên xác định được học viên đang tập trung vào phần nào của bài giảng nhiều, và đang thiếu tập trung vào phần nào của bài giảng.
...
-> Outcome: Giảng viên hỗ trợ được học viên hiểu bài giảng một cách hiệu quả và chuyên sâu hơn thông qua Support Queue.  




---

## 🔄 Quá Trình Phát Triển Giả Thuyết

### Bước 1: Xác Định User & Situation

**User Segment** (Ai là người dùng):

Solution Case C có **hai** user: giảng viên là người *nhận* Support Queue, học viên là người *tạo ra* tín hiệu đầu vào. Vòng này chọn điều tra **học viên** trước (lý do ở bảng actor bên dưới).

**(A) Segment điều tra chính — Học viên trên VLearn**
- Đặc điểm: học viên/sinh viên năm 1–3, học 4–6 môn song song, quen dùng laptop + điện thoại, dùng VLearn chủ yếu để xem slide trước buổi học và đọc lại slide khi ôn bài; kỹ năng tự học chưa hệ thống, thường ôn dồn sát kỳ kiểm tra.
- Nhu cầu cốt lõi: biết **chính xác phần nào trong bài giảng mình chưa nắm**, để phân bổ đúng thời gian tự học vốn rất hạn chế.
- Hành vi hiện tại (giả định cần kiểm chứng): lướt slide nhanh, ít dùng tính năng highlight/ghi chú của VLearn mà ghi chú tay hoặc chụp màn hình; hỏi bạn/nhóm chat lớp thay vì hỏi giảng viên; khi ôn thì đọc lại toàn bộ slide theo thứ tự bài giảng chứ không theo mức độ chưa hiểu.

**(B) Segment hưởng lợi trực tiếp — Giảng viên / coach (vòng này CHƯA kiểm chứng)**
- Đặc điểm: dạy lớp đông (30–100 học viên), quỹ thời gian sau buổi học rất ít, phải viết recap và định hướng ôn tập cho cả lớp.
- Nhu cầu cốt lõi: biết lớp và từng cá nhân đang mắc ở đâu mà không phải hỏi thủ công từng người.
- Hành vi hiện tại: dựa vào số ít câu hỏi phát sinh trên lớp, trí nhớ cá nhân về buổi giảng, và điểm quiz/bài tập (đến trễ và thưa).

> ⚠️ **Ghi chú phạm vi bằng chứng**: Vòng phỏng vấn này chỉ có **learner-side evidence**; instructor-side job **chưa được kiểm chứng** (xem Hypothesis 3).

**Situation** (Hoàn cảnh, bối cảnh):
- **Khi nào người dùng gặp tình huống này**:
  - Ngay sau buổi học (tối cùng ngày hoặc 1–2 ngày sau), học viên mở lại slide trên VLearn để "xem lại xem hôm nay học gì".
  - Giai đoạn 1–2 tuần trước kỳ kiểm tra giữa kỳ, học viên phải chọn ôn bài nào trước, phần nào bỏ qua → **Situation 1 ở Bước 2**.
  - Giảng viên ngồi viết recap/thông báo sau buổi học, phải chọn 3–5 điểm để nhấn mạnh cho cả lớp → **Situation 2 ở Bước 2**.
- **Điều kiện có sẵn**: slide bài giảng trên VLearn; tính năng highlight/ghi chú/đánh dấu "Chưa hiểu"; AI Chat/tutor trong VLearn; nhóm chat lớp và bạn cùng lớp; đề cương môn học (nếu có); điểm quiz các buổi trước.
- **Ràng buộc**:
  - Thời gian tự học ít và phải chia cho nhiều môn → không thể ôn lại toàn bộ.
  - Không có tín hiệu phản hồi nào cho biết "mình hiểu đến đâu" ngoài điểm kiểm tra, mà điểm thì đến sau khi đã quá muộn để sửa.
  - Ngại hỏi công khai trên lớp hoặc trong nhóm vì sợ bị đánh giá; lớp đông nên câu hỏi cá nhân dễ bị lướt qua.
  - **Ràng buộc quan trọng nhất với Case C**: mọi tín hiệu chỉ tồn tại nếu học viên thật sự thao tác trên VLearn. Nếu học viên chỉ mở slide rồi ghi chú ra ngoài, database sẽ trống hoặc gây hiểu nhầm.


| Actor | Họ đang làm gì? | Pain hoặc hậu quả có thể có | Họ hưởng lợi như thế nào? |
| --- | --- | --- | --- |
| Giảng viên | Giảng bài giảng trên lớp, thuyết trình dựa trên slides. | Không nắm bắt được tình hình học tập của học viên do số lượng học viên quá đông | Hưởng lợi trực tiếp: Có support queue để điều tra quá trình học của học viên, có thể dễ dàng điều phối coach/lab coach thông báo cho học viên cần tập trung vào bộ phận nào |
| Học viên | Đọc slide trên VLearn, nghe giảng viên giảng bài trên lớp, có thể sau đó đọc lại slide để ôn bài | Có thể nhiều chi tiết trong slide mỗi buổi giảng chưa rõ ràng, chưa chú ý đến các mục khác trong bài giảng, dẫn đến nguy cơ hổng kiến thức, ôn lệch đề | Hưởng lợi trực tiếp: Support queue giúp học viên dễ dàng được biết mình và các bạn khác cần tập trung vào cái gì trong bài giảng hôm đó, còn chưa chú ý đến cái gì trong bài giảng. | 

Actor đề xuất điều tra: ***Học viên***. Tại sao? Cần xác định nếu học viên có thực sự sử dụng Vlearn đủ để thu thập dữ liệu có thiết thực cho giảng viên. 


**Example**:
```
User: Sinh viên năm 3, học chuyên ngành khó, có nhiều bài tập
Situation: Buổi tối sau 19h, người dùng không biết nên học môn nào trước, 
           bao nhiêu thời gian, hoặc có nên nghỉ
```

---

### Bước 2: Xác Định Job to be Done

**Job** (Công việc mà người dùng muốn hoàn thành):
- **Mục tiêu chính (học viên)**: Xác định đúng những phần kiến thức mình **chưa nắm** trong mỗi bài giảng, rồi dồn thời gian tự học vào đúng những phần đó.
- **Mục tiêu chính (giảng viên — chưa kiểm chứng)**: Chọn ra đúng những chủ đề mà lớp thực sự cần củng cố để đưa vào recap / buổi ôn / phân công coach hỗ trợ.
- **Tại sao nó quan trọng**: Thời gian tự học và thời gian đứng lớp đều là nguồn lực khan hiếm. Chọn sai chỗ để ôn (hoặc sai chỗ để nhấn mạnh) không chỉ lãng phí thời gian mà còn để lại lỗ hổng kiến thức chỉ lộ ra khi đã đi thi — lúc đó không còn sửa được.

**Motivation** (Tại sao lại muốn làm công việc này):
- **Lợi ích kỳ vọng**: không phải đọc lại toàn bộ slide; tiết kiệm thời gian ôn; điểm kiểm tra tốt hơn; cảm giác tự tin "mình biết mình đang đứng ở đâu" trước kỳ thi; với giảng viên là recap trúng nhu cầu thật của lớp thay vì phỏng đoán.
- **Nỗi sợ / Rào cản hiện tại**:
  - Sợ ôn lệch, hổng đúng phần bài thi hỏi.
  - **Không biết là mình không biết** — đọc slide thấy quen nên tưởng đã hiểu, đến lúc làm bài mới phát hiện chưa hiểu.
  - Ngại hỏi lại giảng viên vì sợ bị đánh giá là "không theo kịp", nhất là ở lớp đông.
  - Thao tác ghi chú/đánh dấu trên hệ thống tốn công mà không thấy được lợi ích gì ngay → bỏ qua, làm theo thói quen cũ (ghi tay, chụp màn hình).

**Expected Outcome** (Kết quả mong muốn):
- **Thành công trông như thế nào**: Trước khi bắt đầu ôn, học viên có thể chỉ ra cụ thể 3–5 điểm cần ôn trong mỗi bài (theo slide/khái niệm), thay vì nói chung chung "ôn lại cả bài"; thời gian ôn thực tế rơi vào đúng những điểm đó; khi đi thi không gặp tình huống "phần này mình tưởng đã hiểu rồi".
- **Tiêu chí đánh giá**:
  - Tỷ lệ thời gian ôn dành cho phần thật sự chưa nắm (so với ôn dàn trải).
  - Số lần "bị bất ngờ" khi gặp câu hỏi thuộc phần chưa ôn.
  - Độ trễ giữa lúc phát sinh chỗ chưa hiểu và lúc học viên biết mình chưa hiểu (hiện tại: đến khi có điểm; mong muốn: trong vòng 1 buổi).
  - Mức tự tin trước kỳ kiểm tra (thang 1–5).

**Example**:
```
Job: Lên kế hoạch học tập hàng ngày sao cho hiệu quả
Motivation: 
  - Lợi ích: Không phí thời gian, cải thiện điểm số
  - Nỗi sợ: Học sai môn, quá tải
Expected Outcome:
  - Biết chính xác nên học gì, bao lâu, theo thứ tự nào
  - Cảm thấy tự tin vào kế hoạch
```

**Situation 1**
> Khi **ôn tập cho kỳ kiểm tra giữa kỳ**, **học viên** đang cố **hiểu và ghi nhớ càng nhiều thông tin càng tốt** bằng cách **ôn tập dàn trải, sau đó tập trung vào những bài giảng tự thấy cần ôn kỹ hơn hay các bài giảng đã quên / chưa nhớ.** 

> **JTBD**: Khi **gặp kiến thức mà chưa chắc cần ôn tập hoặc chưa chắc bài thi sẽ cover**, tôi muốn **biết được cần tập trung vào kiến thức nào**, để có thể **tiết kiệm được thời gian tự học**

**Situation 2**
> Khi **viết một bản recap cho học viên về bài học**, **giảng viên** đang cố **chọn lọc những chi tiết muốn nhấn mạnh cho học viên về bài học** bằng cách **tự nhớ lại mình nói những gì trong bài học, soát lại slide để chọn chi tiết, và nhớ lại học viên có hỏi nhiều về vấn đề gì nhất**

> **JTBD**: Khi **chọn giữa các chủ đề muốn đưa vào recap**, tôi muốn **biết được chủ đề nào học viên thực sự cần củng cố hoặc tập trung học**, để có thể **đưa vào bài recap để học viên đọc và làm theo ý mình, củng cố việc ôn lại sau buổi học**




---

### Bước 3: Xác Định Perceived Pain (Nỗi đau cảm nhận)

**Pain Categories**:
- 🔴 **Functional Pain**: Vấn đề công năng (làm không được, quá khó)
- 🟠 **Emotional Pain**: Nỗi sợ, lo lắng, xấu hổ
- 🟡 **Social Pain**: Áp lực xã hội, so sánh với người khác
- 🟢 **Financial/Time Pain**: Tốn tiền, lãng phí thời gian

**Perceived Pains** (Hiện trạng nỗi đau):

**Phía học viên (actor điều tra vòng này)**

1. **Pain 1 — Không xác định được mình chưa hiểu chỗ nào**: đọc lại slide thấy "quen quen" nên tưởng đã nắm, tự đánh giá hoàn toàn bằng cảm giác. → **Severity**: 4/5 → **Frequency**: Thường xuyên (mỗi lần ôn bài) → **Type**: 🔴 Functional + 🟠 Emotional
2. **Pain 2 — Ôn dàn trải, tốn thời gian**: vì không có thứ tự ưu tiên nên đọc lại toàn bộ slide từ đầu, hết thời gian trước khi tới phần khó. → **Severity**: 4/5 → **Frequency**: Thường xuyên (mỗi đợt kiểm tra, hàng tuần với môn nặng) → **Type**: 🟢 Time + 🔴 Functional
3. **Pain 3 — Phản hồi đến quá trễ**: chỉ biết mình hổng chỗ nào khi đã có điểm kiểm tra, lúc đó không còn cơ hội sửa cho bài thi đó. → **Severity**: 4/5 → **Frequency**: Mỗi kỳ kiểm tra → **Type**: 🔴 Functional + 🟠 Emotional (bất lực)
4. **Pain 4 — Ngại hỏi lại**: lớp đông, sợ bị xem là không theo kịp, nên giữ thắc mắc cho riêng mình hoặc chỉ hỏi bạn thân. → **Severity**: 3/5 → **Frequency**: Thỉnh thoảng (mỗi buổi có chỗ khó) → **Type**: 🟡 Social + 🟠 Emotional
5. **Pain 5 — Ghi chú/đánh dấu trên VLearn không "đáng công"**: highlight, ghi chú, đánh dấu "Chưa hiểu" tốn thao tác mà không trả lại lợi ích tức thì → học viên quay về ghi tay/chụp màn hình. → **Severity**: 2/5 *với học viên* → **Frequency**: Thường xuyên → **Type**: 🟢 Time
   > ⚠️ Pain này nhẹ với học viên nhưng **chí mạng với Case C**: nếu đúng, Support Queue sẽ được xây trên dữ liệu thưa và thiên lệch. Đây là lý do vòng này chọn phỏng vấn học viên trước.

**Phía giảng viên (giả định — chưa kiểm chứng vòng này)**

6. **Pain 6 — Chỉ nghe được thiểu số**: tín hiệu về mức hiểu của lớp chỉ đến từ vài học viên chủ động hỏi; nhóm im lặng hoàn toàn vô hình. → **Severity**: 4/5 → **Frequency**: Mỗi buổi học → **Type**: 🔴 Functional
7. **Pain 7 — Recap dựa vào trí nhớ**: phải tự nhớ lại đã giảng gì, học viên hỏi gì, rồi đoán nội dung cần nhấn mạnh. → **Severity**: 3/5 → **Frequency**: Mỗi buổi học → **Type**: 🔴 Functional + 🟢 Time

**Example**:
```
Pain 1: Không biết ưu tiên môn nào
  - Severity: 4/5 (rất khó chịu)
  - Frequency: Hàng ngày
  - Type: Functional + Emotional (lo lắng)
  
Pain 2: Cảm thấy áp lực từ bạn bè học giỏi hơn
  - Severity: 3/5
  - Frequency: Thỉnh thoảng
  - Type: Social + Emotional


```

---

### Bước 4: Problem Hypothesis (Giả thuyết vấn đề)

**Definition**: Một mệnh đề khẳng định rõ ràng, có thể bị bác bỏ về vấn đề thực mà người dùng gặp phải.

**Tiêu chuẩn giả thuyết tốt**:
- ✅ Cụ thể và có thể quan sát được (observable)
- ✅ Có thể bị bác bỏ/kiểm chứng (falsifiable)
- ✅ Dựa trên phân tích User + Situation + Job + Pain
- ❌ KHÔNG nêu ra solution
- ❌ KHÔNG chung chung hoặc mơ hồ

**Problem Hypothesis Format**:
```
[User Type] trong tình huống [Situation] không thể [Job được thực hiện tốt]
vì họ [Cụ thể: thiếu thông tin/công cụ/kỹ năng/confidence]
và điều này gây ra [Perceived Pain].
```

**Examples**:

**Ví dụ 1 - TỐTC**:
> Sinh viên năm 3 chuyên ngành khó không thể lên kế hoạch học tập hàng ngày
> vì họ thiếu thông tin rõ ràng về thứ tự ưu tiên các môn học và thời gian
> cân xứng cho mỗi môn, dẫn đến lo lắng và lãng phí thời gian.

**Ví dụ 2 - TỐTC**:
> Sinh viên trong giai đoạn thi cử không thể giữ được động lực học tập
> vì họ thiếu sự tích tụ tiến độ trực quan và phản hồi thường xuyên
> về hiệu quả học tập của mình, dẫn đến cảm thấy bất lực.

**Ví dụ 3 - KHÔNG TỐT** (mơ hồ, không thể kiểm chứng):
> Sinh viên muốn quản lý thời gian tốt hơn. ❌ (Chung chung, không nêu vấn đề cụ thể)

**Ví dụ 4 - KHÔNG TỐT** (nêu solution):
> Sinh viên cần một ứng dụng để quản lý thời gian. ❌ (Nêu solution, không phải problem)

---

## 📊 Problem Hypothesis Của Nhóm

### Primary Problem Hypothesis

```
[USER TYPE] trong tình huống [SITUATION] không thể [JOB]
vì họ [ROOT CAUSE/CONSTRAINT]
và điều này gây ra [PRIMARY PAIN].
```

**Giả thuyết của nhóm**:

> **H1 (Primary — learner-side)**
> **Học viên đang học trên VLearn**, trong tình huống **đọc lại bài sau buổi học và chọn nội dung ôn cho kỳ kiểm tra giữa kỳ**, **không xác định được phần kiến thức nào mình thực sự chưa nắm để ưu tiên ôn trước**, vì **họ không có phản hồi khách quan nào về mức độ hiểu của bản thân ngoài điểm kiểm tra — thứ đến quá trễ — nên phải dựa hoàn toàn vào cảm giác chủ quan khi đọc lại slide**, và điều này khiến họ **ôn dàn trải và tốn thời gian, vẫn để lại lỗ hổng kiến thức, kèm cảm giác lo lắng vì không chắc mình đã ôn đúng chỗ (Pain 1, 2, 3)**.

---

### Secondary Problem Hypotheses (Tùy chọn)

**Hypothesis 2 — Giả định dữ liệu đầu vào (rủi ro lớn nhất của Case C)**:
> **Học viên**, trong tình huống **đang học/đọc lại slide trên VLearn**, **không để lại đủ tín hiệu chủ động trên hệ thống (highlight, ghi chú, đánh dấu "Chưa hiểu", hỏi AI Chat)**, vì **các thao tác này tốn công và không trả lại lợi ích tức thì cho việc học, trong khi ghi tay / chụp màn hình / hỏi bạn nhanh hơn**, và điều này khiến **dữ liệu hành vi thu được thưa và thiên lệch — chỗ học viên im lặng nhất lại thường là chỗ họ mắc nhất (Pain 5)**.
>
> *Tại sao phải kiểm chứng H2 trước:* toàn bộ chuỗi thay đổi ở phần Solution Directive (bước 0 → A → B → C) đứng trên giả định "học viên dùng VLearn đủ nhiều để sinh dữ liệu". Nếu H2 đúng, Support Queue vẫn chạy được nhưng sẽ chỉ đúng với nhóm học viên vốn đã chăm chỉ — tức là bỏ sót đúng nhóm cần hỗ trợ nhất.

**Hypothesis 3 — Instructor-side (CHƯA kiểm chứng ở vòng này)**:
> **Giảng viên dạy lớp đông**, trong tình huống **viết recap / chọn nội dung nhấn mạnh sau buổi học**, **không xác định được chủ đề nào cả lớp thực sự cần củng cố**, vì **họ chỉ có tín hiệu từ số ít học viên chủ động hỏi cộng với trí nhớ cá nhân về buổi giảng**, và điều này khiến **recap được viết theo phỏng đoán, còn những học viên im lặng thì bị bỏ sót cho đến khi có điểm kiểm tra (Pain 6, 7)**.

---

### 🚫 Dấu hiệu sẽ BÁC BỎ giả thuyết (falsification)

Ghi trước để tránh việc phỏng vấn xong chỉ đi tìm bằng chứng ủng hộ:

| Giả thuyết | Bị bác bỏ nếu... |
|---|---|
| **H1** | Học viên kể lại được cụ thể, không do dự, phần nào mình chưa hiểu ngay sau buổi học; hoặc họ đã có cách xác định đủ tốt (làm thử bài tập, hỏi bạn, quiz tự kiểm tra) và không thấy đây là vấn đề đáng kể. |
| **H2** | Học viên mô tả được các lần cụ thể họ đã highlight / ghi chú / hỏi AI Chat ngay trên VLearn trong 1–2 tuần gần nhất, và đó là công cụ ghi chú chính của họ. |
| **H3** | Giảng viên cho biết họ đã nắm khá rõ lớp đang mắc ở đâu qua kênh sẵn có (quiz cuối buổi, hỏi trực tiếp, coach báo lại) và không thấy thiếu thông tin khi viết recap. |

---

## 🔍 Tiêu Chuẩn Kiểm Chứng

Để xác thực giả thuyết này, chúng ta sẽ tìm kiếm những dấu hiệu sau trong phỏng vấn:

Nguyên tắc: hỏi về **lần gần nhất đã thực sự xảy ra**, không hỏi "bạn có thường..." hay "bạn có muốn tính năng...".

| Tiêu Chí | Dấu Hiệu Xác Thực | Cách Kiểm Chứng (câu hỏi mẫu) |
|---------|------------------|-------------------|
| **Situation có thật** (H1) | Học viên kể lại được một buổi ôn cụ thể, có ngày/môn, không phải mô tả chung chung | "Lần gần nhất bạn ngồi ôn lại một bài giảng là khi nào? Kể lại giúp mình bạn đã mở cái gì trước, làm gì tiếp theo." |
| **Root Cause** (H1) — không có phản hồi khách quan | Học viên thừa nhận chỉ dựa vào cảm giác; không nêu được cách nào để kiểm tra xem mình đã hiểu chưa | "Lúc đó bạn dựa vào cái gì để biết phần nào cần ôn kỹ?" / "Làm sao bạn biết là mình đã hiểu phần đó rồi?" |
| **Pain Severity + Frequency** | Kể được hậu quả cụ thể đã xảy ra (đi thi gặp phần chưa ôn, mất buổi tối đọc lại cả bài) và cảm xúc kèm theo | "Chuyện đó dẫn tới gì?" / "Lần gần nhất bị như vậy là bao giờ? Trong kỳ này bao nhiêu lần rồi?" / "Lúc đó bạn thấy thế nào?" |
| **Current Behavior / Workaround** | Có workaround thật, tốn công (ghi tay, chụp màn hình, hỏi bạn, xem lại video, tự làm quiz) | "Bạn đã làm gì để xử lý?" / "Có cách nào bạn đã thử rồi mà bỏ không?" |
| **Chi phí đang trả** (mức độ nghiêm trọng thật) | Học viên đã bỏ thời gian/tiền/công sức cho vấn đề này (học thêm, hỏi gia sư, thức khuya ôn lại) | "Việc đó tốn của bạn bao nhiêu thời gian?" / "Bạn có từng nhờ ai hoặc trả tiền cho việc này chưa?" |
| **Dữ liệu đầu vào** (H2) — quan trọng nhất | Học viên chỉ ra được thao tác thật trên VLearn trong 1–2 tuần gần nhất, hoặc thừa nhận không dùng và nêu lý do | "Mở VLearn ra giúp mình — lần gần nhất bạn highlight hay ghi chú trên đó là bài nào?" / "Nếu không dùng thì bạn ghi chú ở đâu? Vì sao chọn cách đó?" |
| **Điểm mù của hệ thống** (H2) | Có chỗ học viên mắc nhưng không để lại dấu vết nào trên VLearn | "Có phần nào bạn không hiểu mà cuối cùng không hỏi ai, cũng không ghi lại gì không? Vì sao?" |
| **Motivation** | Học viên chủ động muốn giải quyết, không phải chỉ đồng ý cho lịch sự | "Nếu chuyện này không bao giờ được giải quyết thì sao?" / "So với các khó khăn khác khi học, cái này đứng thứ mấy?" |
| **Riêng giảng viên** (H3, nếu phỏng vấn được) | Kể lại được lần viết recap gần nhất và cách chọn nội dung | "Bản recap gần nhất bạn viết — bạn chọn nhấn mạnh những gì và dựa vào đâu để chọn?" / "Có học viên nào bạn phát hiện đuối muộn hơn mong muốn không?" |

---

## 📝 Ghi Chú Phát Triển

**Ngày phát triển**: 17/08/2026

### Điều chỉnh/Sửa đổi

- **v1** (17/08/2026): Giả thuyết ban đầu bám theo directive Case C — lấy **giảng viên** làm user chính, vấn đề đặt ở chỗ "giảng viên không nắm được tình hình học tập của lớp đông".
- **v1.1** (17/08/2026): Chuyển actor điều tra chính sang **học viên**. Lý do: cả chuỗi thay đổi của Case C phụ thuộc vào giả định "học viên dùng VLearn đủ nhiều để sinh ra tín hiệu". Nếu giả định đó sai thì vấn đề của giảng viên có thật đến đâu cũng không giải được bằng Support Queue. Vấn đề của giảng viên được giữ lại thành **H3** để kiểm chứng ở vòng sau.
- **v1.2** (17/08/2026): Tách riêng **H2** (giả định dữ liệu đầu vào) khỏi H1, vì đây là mệnh đề dễ bị bác bỏ nhất và cũng rủi ro nhất; bổ sung bảng dấu hiệu bác bỏ để tránh phỏng vấn thiên lệch.
- **Final** (chờ): Giả thuyết cuối cùng sau thảo luận nhóm và sau vòng phỏng vấn.

---

## ✅ Checklist Hoàn Thành

- [x] Đã xác định rõ User & Situation
- [x] Đã định nghĩa Job to be Done
- [x] Đã liệt kê tất cả Perceived Pains
- [x] Đã viết Primary Problem Hypothesis (cụ thể, có thể kiểm chứng)
- [x] Đã có Secondary Hypotheses (H2 dữ liệu đầu vào, H3 instructor-side)
- [ ] Giả thuyết đã được nhóm đồng ý *(chờ — chưa điền thành viên nhóm ở README)*
- [x] Đã xác định tiêu chí kiểm chứng trong phỏng vấn
- [x] Đã ghi rõ phạm vi bằng chứng: vòng này chỉ có learner-side evidence

---

## 🔗 Liên Kết

- **Bước tiếp theo**: [02-guide/conversation-guide-v1.md](../02-guide/conversation-guide-v1.md)
- **Tham khảo**: Job Stories Framework, Jobs to be Done

---

**Trạng thái**: Đã hoàn thành v1.2 — sẵn sàng cho vòng phỏng vấn, chờ nhóm duyệt  
**Người duyệt cuối**: [Chờ nhóm duyệt]  
**Ngày duyệt**: [Ngày]
