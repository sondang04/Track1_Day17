# Problem Hypothesis Development

**Bài Lab**: Track 1 - Day 17  
**Ngày hoàn thành**: [Điền ngày]  
**Tác giả/Thành viên**: [Điền tên]

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

**User Segment** (Ai là người dùng): Giảng viên
- Đặc điểm: [Tuổi, công việc, kỹ năng, ...]
- Nhu cầu cốt lõi: [...]
- Hành vi hiện tại: [...]

**Situation** (Hoàn cảnh, bối cảnh):
- Khi nào người dùng gặp tình huống này: [...]
- Điều kiện có sẵn: [...]
- Ràng buộc: [...]


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
- [Mục tiêu chính]: [...]
- [Tại sao nó quan trọng]: [...]

**Motivation** (Tại sao lại muốn làm công việc này):
- Lợi ích kỳ vọng: [...]
- Nỗi sợ/Rào cản hiện tại: [...]

**Expected Outcome** (Kết quả mong muốn):
- Thành công trông như thế nào: [...]
- Tiêu chí đánh giá: [...]

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
1. **Pain 1**: [Mô tả] → **Severity** (1-5): [?] → **Frequency**: [Hiếm/Thỉnh thoảng/Thường xuyên]
2. **Pain 2**: [Mô tả] → **Severity**: [?] → **Frequency**: [...]
3. **Pain 3**: [Mô tả] → **Severity**: [?] → **Frequency**: [...]

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

> [Điền giả thuyết chính ở đây]

---

### Secondary Problem Hypotheses (Tùy chọn)

Nếu có nhiều vấn đề, liệt kê thêm:

**Hypothesis 2**:
> [Giả thuyết thứ hai]

**Hypothesis 3**:
> [Giả thuyết thứ ba]

---

## 🔍 Tiêu Chuẩn Kiểm Chứng

Để xác thực giả thuyết này, chúng ta sẽ tìm kiếm những dấu hiệu sau trong phỏng vấn:

| Tiêu Chí | Dấu Hiệu Xác Thực | Cách Kiểm Chứng |
|---------|------------------|-------------------|
| **Root Cause** | Người dùng thừa nhận thiếu [nguyên nhân] | "Bạn thiếu gì?" / "Lúc đó, bạn biết không?" |
| **Pain Severity** | Người dùng mô tả tần suất, cảm xúc | "Điều này xảy ra bao lâu? Bạn cảm thấy như thế nào?" |
| **Current Behavior** | Người dùng có workaround nào không | "Bạn đang làm gì để giải quyết?" |
| **Motivation** | Người dùng muốn thay đổi | "Bạn có muốn thay đổi điều này không?" |

---

## 📝 Ghi Chú Phát Triển

**Ngày phát triển**: [Điền ngày]

### Điều chỉnh/Sửa đổi

- **v1** (Ngày ...): Giả thuyết ban đầu
- **v1.1** (Ngày ...): Sửa đổi sau [lý do]
- **Final** (Ngày ...): Giả thuyết cuối cùng sau thảo luận nhóm

---

## ✅ Checklist Hoàn Thành

- [ ] Đã xác định rõ User & Situation
- [ ] Đã định nghĩa Job to be Done
- [ ] Đã liệt kê tất cả Perceived Pains
- [ ] Đã viết Primary Problem Hypothesis (cụ thể, có thể kiểm chứng)
- [ ] Đã có Secondary Hypotheses (nếu cần)
- [ ] Giả thuyết đã được nhóm đồng ý
- [ ] Đã xác định tiêu chí kiểm chứng trong phỏng vấn

---

## 🔗 Liên Kết

- **Bước tiếp theo**: [02-guide/conversation-guide-v1.md](../02-guide/conversation-guide-v1.md)
- **Tham khảo**: Job Stories Framework, Jobs to be Done

---

**Trạng thái**: [Đang phát triển / Đã hoàn thành]  
**Người duyệt cuối**: [Tên]  
**Ngày duyệt**: [Ngày]
