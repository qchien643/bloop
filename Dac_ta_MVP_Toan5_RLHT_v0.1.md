# ĐẶC TẢ MVP

## Hệ thống hỗ trợ điều chỉnh KHBD Toán 5 cho học sinh rối loạn học tập trong lớp hòa nhập

**Phiên bản:** 0.1  
**Ngày lập:** 03/11/2026  
**Trạng thái:** Bản đặc tả để xây prototype và thực hiện pilot  
**Tài liệu nền:** `dactasanpham.md`, `Khung_noi_bo_Toan5_RLHT_v0.1.docx`

---

# 1. Mục đích của MVP

MVP không nhằm chứng minh rằng sản phẩm đã hỗ trợ được mọi môn học, khối lớp và dạng khuyết tật.

MVP nhằm chứng minh một workflow dọc có thể vận hành trong thực tế:

> Từ hồ sơ và năng lực hiện tại của một học sinh, cùng với KHBD/giáo án giáo viên đã soạn, hệ thống có thể đề xuất các điều chỉnh có căn cứ cho từng hoạt động của tiết học, tạo học liệu phù hợp và thu lại minh chứng sau tiết học để theo dõi tiến bộ.

Các giả thuyết cần kiểm chứng:

1. Giáo viên có thể cung cấp đầu vào bằng những tài liệu họ đang sử dụng.
2. Hệ thống xác định được điểm giao giữa học sinh, mục tiêu cá nhân và KHBD chung.
3. Đề xuất đủ cụ thể để giáo viên sử dụng trong một tiết dạy thật.
4. Giáo viên hiểu được lý do, sửa được và giữ quyền phê duyệt cuối cùng.
5. KHBD điều chỉnh và phiếu học tập tạo ra có thể sử dụng ngay.
6. Kết quả sau tiết học quay lại cập nhật tiến bộ và mức hỗ trợ của học sinh.

MVP chỉ thành công khi chứng minh được toàn bộ vòng lặp trên, không phải khi AI chỉ sinh được một giáo án đẹp.

---

# 2. Quan hệ với sản phẩm toàn diện

Theo định hướng sản phẩm, phiên bản toàn diện có thể mở rộng sang:

- nhiều môn học và khối lớp;
- nhiều nhóm khuyết tật, khó khăn và nhu cầu hỗ trợ.

MVP chỉ kiểm chứng lõi dùng chung:

```text
Hồ sơ học sinh
        +
Yêu cầu chương trình
        +
Mục tiêu cá nhân
        +
KHBD giáo viên đã soạn
        ↓
Đối chiếu và giải thích khoảng cách
        ↓
Quyết định điều chỉnh
        ↓
KHBD hòa nhập + học liệu
        ↓
Minh chứng tiến bộ
```

Nếu lõi này hoạt động, sản phẩm mới có cơ sở mở rộng thêm bộ môn và mô hình hỗ trợ cho các nhóm học sinh khác.

---

# 3. Quy ước

- **Bắt buộc:** cần có để chứng minh workflow.
- **Nên có:** hữu ích nhưng không chặn việc pilot.
- **Ngoài MVP:** chưa thực hiện trong phiên bản này.
- **Quyết định MVP:** giới hạn nội bộ để xây prototype, không phải quy định pháp lý.
- **Ngưỡng đề xuất:** chỉ số cần product owner chốt trước pilot, không phải dữ kiện lấy từ nguồn.

---

# 4. Phạm vi MVP

## 4.1. Phạm vi bắt buộc

| Thành phần | Phạm vi MVP |
|---|---|
| Người dùng chính | Giáo viên lớp 5/GVCN dạy Toán |
| Môi trường | Lớp phổ thông có học sinh học hòa nhập |
| Môn và lớp | Toán lớp 5 theo CTGDPT 2018 |
| Mạch kiến thức | Số thập phân và các phép tính với số thập phân |
| Học sinh | Có hồ sơ/đánh giá cho thấy khó khăn học tập ảnh hưởng đến học Toán; hệ thống không chẩn đoán |
| Đơn vị xử lý | Một học sinh trong một bài/tiết ở mỗi lần tạo gói điều chỉnh |
| Đầu vào bài dạy | KHBD/giáo án giáo viên đã soạn |
| Đầu ra trung tâm | KHBD hòa nhập đã điều chỉnh, phiếu học tập và biểu mẫu thu minh chứng |
| Vòng phản hồi | Ghi kết quả sau tiết học và đề xuất mức hỗ trợ cho lần tiếp theo |

## 4.2. Giới hạn bộ sách

MVP chỉ hỗ trợ **một bộ SGK** trong đợt prototype/pilot.

Quyết định mặc định để xây demo:

> Toán 5 – Chân trời sáng tạo.

Bộ sách có thể đổi theo trường pilot trước khi nhập dữ liệu. Mô hình dữ liệu vẫn phải tách yêu cầu chương trình khỏi bài SGK để có thể mở rộng sau này.

## 4.3. Ngoài phạm vi

MVP chưa làm:

- môn học khác hoặc khối lớp khác;
- toàn bộ nội dung Toán 5;
- nhiều bộ SGK cùng lúc;
- chẩn đoán hoặc sàng lọc khuyết tật/RLHT;
- tự suy ra quyền miễn, giảm hoặc trạng thái pháp lý của học sinh;
- mô hình hỗ trợ chuyên sâu cho khuyết tật nhìn, nghe, vận động, trí tuệ, tự kỷ hoặc nhóm khác;
- tự động phê duyệt thay giáo viên;
- tự động sửa KHGDCN chính thức;
- sinh toàn bộ KHBD từ con số 0 trong luồng chính;
- đọc chữ viết tay hoặc OCR tài liệu scan chất lượng thấp;
- quản trị cấp trường, thời khóa biểu hoặc e-learning cho học sinh.

---

# 5. Tác nhân và trách nhiệm

## 5.1. Giáo viên

Giáo viên:

- tạo và xác nhận hồ sơ học sinh;
- cung cấp KHGDCN/kế hoạch hỗ trợ cá nhân nếu có;
- tải KHBD đã soạn;
- xem, sửa, chấp nhận hoặc từ chối đề xuất;
- phê duyệt trước khi xuất gói bài dạy;
- triển khai trong lớp và nhập minh chứng sau tiết học.

Giáo viên là người chịu trách nhiệm chuyên môn cuối cùng.

## 5.2. Người thẩm định chuyên môn

Có thể là giáo viên giáo dục đặc biệt, tổ trưởng chuyên môn hoặc cán bộ phụ trách giáo dục hòa nhập.

Trong pilot, người này cần xem các trường hợp có đề xuất `REDUCE_SCOPE` hoặc `REPLACE`.

## 5.3. Hệ thống

Hệ thống:

- trích xuất và chuẩn hóa dữ liệu;
- đối chiếu hồ sơ với mục tiêu và bài học;
- đề xuất, giải thích và tạo học liệu;
- lưu phiên bản, quyết định và minh chứng;
- không tự thay giáo viên ra quyết định cuối cùng.

---

# 6. Đầu vào của MVP

## 6.1. Hồ sơ học sinh

Thông tin bắt buộc:

| Trường | Nội dung |
|---|---|
| Mã học sinh | Mã nội bộ; không dùng tên trong phiếu phát cho lớp nếu không cần |
| Ngày lập profile | Ngày dữ liệu được xác nhận |
| Năng lực hiện tại | Học sinh hiện làm được gì trong mạch số thập phân |
| Khó khăn/loại lỗi | Lỗi lặp lại có thể quan sát |
| Minh chứng | Bài kiểm tra, sản phẩm, quan sát hoặc đánh giá làm căn cứ |
| Hỗ trợ hiệu quả | Hỗ trợ đã dùng và tác dụng quan sát được |

Thông tin tùy chọn:

- báo cáo chuyên môn;
- nhận xét của giáo viên;
- kết quả kiểm tra gần nhất;
- ảnh bài làm;
- thông tin về chú ý, ghi nhớ hướng dẫn, làm theo trình tự và tự kiểm tra;
- trạng thái pháp lý do nhà trường xác nhận.

Định dạng:

- form nhập trực tiếp;
- DOCX hoặc PDF có lớp văn bản;
- ảnh bài làm đính kèm làm minh chứng.

Hệ thống có thể trích xuất thông tin từ tệp, nhưng giáo viên phải xác nhận dữ liệu có cấu trúc trước khi sử dụng.

## 6.2. Mục tiêu cá nhân

Nếu đã có KHGDCN/kế hoạch hỗ trợ cá nhân, cần nhập tối thiểu:

- baseline;
- hành vi Toán cần đạt;
- điều kiện hoặc hỗ trợ được phép;
- tiêu chí đạt;
- thời hạn xem xét;
- cách thu minh chứng.

Nếu mục tiêu chưa đủ cấu trúc, hệ thống có thể đề xuất **bản nháp mục tiêu Toán** để giáo viên sửa và xác nhận.

Hệ thống chỉ dùng nhãn `KHGDCN` khi nhà trường xác nhận có căn cứ pháp lý phù hợp. Trường hợp khác dùng `Kế hoạch hỗ trợ học tập cá nhân`.

## 6.3. KHBD/giáo án của tiết học

Đây là đầu vào trung tâm và **bắt buộc**.

Giáo viên tải KHBD đã soạn hoặc dán nội dung vào biểu mẫu. Hệ thống không yêu cầu giáo viên viết lại giáo án từ đầu.

KHBD tối thiểu phải có:

| Nhóm | Dữ liệu cần có |
|---|---|
| Định danh | Môn, lớp, bộ SGK, bài, tiết, thời lượng |
| Yêu cầu cần đạt | Mục tiêu/YCCĐ chung của bài hoặc tiết |
| Học liệu | Đồ dùng, phương tiện và tài liệu dự kiến |
| Tiến trình | Các hoạt động theo thứ tự trong tiết |
| Mỗi hoạt động | Mục tiêu, việc của giáo viên, việc của học sinh, nhiệm vụ/sản phẩm và cách đánh giá nếu có |
| Đánh giá | Cách kiểm tra mức độ đạt trong hoặc cuối tiết |

Định dạng:

- DOCX là định dạng ưu tiên;
- form có cấu trúc là phương án dự phòng;
- PDF có lớp văn bản là tính năng nên có;
- file scan/ảnh giáo án nằm ngoài MVP.

Sau khi trích xuất, hệ thống phải cho giáo viên xem và sửa cấu trúc KHBD trước khi phân tích.

## 6.4. Tri thức hệ thống đã chuẩn bị sẵn

Giáo viên không phải nhập lại mỗi lần. MVP phải có:

1. YCCĐ liên quan đến số thập phân;
2. các kỹ năng và quan hệ tiên quyết;
3. mapping bài/tiết của bộ SGK pilot với YCCĐ;
4. taxonomy lỗi thường gặp;
5. thư viện chiến lược hỗ trợ;
6. rule `KEEP/SUPPORT/REDUCE_SCOPE/REPLACE`;
7. template phiếu, đáp án, rubric và evidence;
8. nguồn và phiên bản của các rule quan trọng.

## 6.5. Minh chứng sau tiết học

Giáo viên nhập tối thiểu:

| Trường | Nội dung |
|---|---|
| Bài/tiết | Tiết đã triển khai |
| Mục tiêu | Goal đang được đo |
| Nhiệm vụ | Câu/bài tạo minh chứng |
| Kết quả | Accuracy, rubric hoặc mô tả chất lượng |
| Mức hỗ trợ | Độc lập, trực quan, lời nói, làm mẫu hoặc hướng dẫn trực tiếp |
| Loại lỗi | Concept, quy trình, trình bày, ngôn ngữ hoặc loại khác |
| Ghi chú | Nhận xét ngắn của giáo viên |

Ảnh hoặc tệp bài làm là tùy chọn.

---

# 7. Đầu ra của MVP

## 7.1. Student Math Profile

Mỗi bản ghi kỹ năng phải có:

```text
Kỹ năng Toán
Năng lực hiện tại
Loại lỗi
Trạng thái prerequisite
Hỗ trợ hiệu quả
Nguồn và ngày của minh chứng
```

Profile phải mô tả hành vi quan sát được, không chỉ lưu nhãn chẩn đoán.

## 7.2. Bản nháp mục tiêu Toán cá nhân

Nếu đầu vào chưa đủ, hệ thống đề xuất:

- baseline;
- hành vi đích;
- điều kiện/hỗ trợ;
- tiêu chí đạt;
- thời hạn;
- cách thu minh chứng;
- liên kết với YCCĐ.

Đây là đề xuất để giáo viên phê duyệt, không tự trở thành KHGDCN chính thức.

## 7.3. Báo cáo đối chiếu bài học

Báo cáo phải cho biết:

- YCCĐ nào xuất hiện trong KHBD;
- bài học gồm những kỹ năng thành phần nào;
- prerequisite liên quan;
- học sinh đang ở mức nào theo evidence;
- mục tiêu cá nhân nào liên quan;
- barrier nào cần xử lý;
- dữ liệu nào còn thiếu.

## 7.4. Quyết định điều chỉnh

Mỗi đề xuất có cấu trúc:

```text
Decision: KEEP | SUPPORT | REDUCE_SCOPE | REPLACE | NEED_MORE_EVIDENCE
Lesson requirement:
Student barrier:
Evidence used:
Related individual goal:
Rationale:
Suggested strategy:
Required teacher approval:
```

## 7.5. KHBD hòa nhập đã điều chỉnh

Hệ thống không tạo hai giáo án tách biệt. Đầu ra là bản sao KHBD gốc có thêm lớp điều chỉnh cho học sinh.

| Thành phần | Cả lớp | Điều chỉnh cho học sinh |
|---|---|---|
| Mục tiêu | Mục tiêu chung | Mục tiêu của HS trong hoạt động |
| Nhiệm vụ | Nhiệm vụ chung | Giữ nguyên, hỗ trợ, thu hẹp hoặc thay thế |
| Cách tiếp cận | Cách dạy chung | Representation, prompt, scaffold |
| Học liệu | Học liệu chung | Học liệu bổ sung |
| Phản hồi | Cách trả lời chung | Response mode được phép |
| Sản phẩm | Sản phẩm chung | Sản phẩm mong đợi của HS |
| Đánh giá | Tiêu chí chung | Tiêu chí và mức hỗ trợ cần ghi nhận |

KHBD đầu ra phải:

- cho phép giáo viên sửa trước khi phê duyệt;
- giữ nội dung gốc để đối chiếu;
- đánh dấu rõ nội dung do hệ thống đề xuất;
- xuất DOCX để tiếp tục chỉnh sửa;
- có thể xuất PDF để in/chia sẻ.

## 7.6. Phiếu học tập và học liệu

Phiếu chỉ được sinh sau khi adaptation được giáo viên duyệt và phải gồm:

- mục tiêu rõ;
- ví dụ mẫu nếu cần;
- bài có hướng dẫn;
- bài độc lập;
- bài vận dụng nếu phù hợp;
- scaffold đúng với barrier;
- đáp án/rubric;
- trường ghi accuracy, error type và support level.

## 7.7. Phiếu ghi nhận sau tiết học

Biểu mẫu phải ngắn, gắn với đúng mục tiêu và nhiệm vụ của tiết học để giáo viên có thể nhập trong vài phút.

## 7.8. Báo cáo tiến bộ và khuyến nghị

Hệ thống hiển thị:

- kết quả theo thời gian;
- độ chính xác/chất lượng;
- mức hỗ trợ;
- loại lỗi;
- khả năng áp dụng sang nhiệm vụ mới;
- trạng thái `PROGRESSING`, `STALLED`, `ACHIEVED` hoặc `NEEDS_REVISION`;
- đề xuất giữ, tăng, giảm hoặc thay đổi scaffold.

Giáo viên xác nhận hành động tiếp theo.

---

# 8. Workflow end-to-end

## Giai đoạn A – Thiết lập hồ sơ

1. Giáo viên tạo mã học sinh.
2. Giáo viên nhập/tải hồ sơ và evidence.
3. Hệ thống trích xuất Student Math Profile.
4. Giáo viên sửa và xác nhận profile.
5. Giáo viên chọn mục tiêu hiện có hoặc duyệt bản nháp mục tiêu.

## Giai đoạn B – Chuẩn bị trước tiết dạy

6. Giáo viên tải KHBD đã soạn.
7. Hệ thống tách metadata, YCCĐ, hoạt động, nhiệm vụ và đánh giá.
8. Giáo viên sửa và xác nhận cấu trúc KHBD.
9. Hệ thống map bài học với yêu cầu chương trình, prerequisite và mục tiêu cá nhân.
10. Hệ thống phân tích từng hoạt động và đề xuất adaptation.
11. Giáo viên xem evidence và rationale, sau đó chấp nhận, sửa hoặc từ chối.
12. Hệ thống sinh KHBD hòa nhập, phiếu, đáp án và evidence form từ bản đã duyệt.

## Giai đoạn C – Sau tiết dạy

13. Giáo viên nhập kết quả, mức hỗ trợ, loại lỗi và ghi chú.
14. Hệ thống cập nhật trend và đề xuất hành động cho tiết sau.
15. Giáo viên xác nhận; hệ thống không tự sửa mục tiêu chính thức.

---

# 9. Quy tắc nghiệp vụ cốt lõi

| ID | Quy tắc |
|---|---|
| BR-01 | Không chẩn đoán học sinh từ hồ sơ hoặc bài làm. |
| BR-02 | Bắt đầu từ năng lực và evidence, không bắt đầu từ nhãn khuyết tật. |
| BR-03 | Nếu có thể đạt cùng concept với accommodation, ưu tiên `SUPPORT`. |
| BR-04 | Không giảm kiến thức vì khó khăn đọc, viết, tốc độ, bố cục hoặc trí nhớ nếu chúng không phải nội dung đang đo. |
| BR-05 | `REDUCE_SCOPE` phải nêu rõ phần giữ, phần giảm, evidence và goal liên quan. |
| BR-06 | `REPLACE` chỉ hợp lệ khi có mục tiêu thay thế rõ và vẫn cho phép tham gia hoạt động chung tối đa có thể. |
| BR-07 | `REDUCE_SCOPE` và `REPLACE` bắt buộc có người phê duyệt. |
| BR-08 | Thiếu evidence thì trả về `NEED_MORE_EVIDENCE`, không tự hạ mục tiêu. |
| BR-09 | Adaptation phải nằm trong KHBD chung, không mặc định tạo giáo án riêng. |
| BR-10 | Mỗi adaptation phải liên kết được với YCCĐ, evidence và mục tiêu cá nhân. |
| BR-11 | Phiếu học tập phải tạo được evidence cho mục tiêu đang đo. |
| BR-12 | Kết quả phải ghi cả độ chính xác và mức hỗ trợ. |
| BR-13 | Giáo viên sửa được mọi nội dung do AI đề xuất. |
| BR-14 | Phiếu phát cho lớp không chứa thông tin hồ sơ nhạy cảm nếu không cần. |
| BR-15 | Lưu bản gốc, bản AI đề xuất, bản giáo viên sửa và bản được duyệt. |

---

# 10. Yêu cầu chức năng

| ID | Ưu tiên | Yêu cầu |
|---|---|---|
| FR-01 | MUST | Tạo và quản lý hồ sơ tối thiểu của học sinh. |
| FR-02 | MUST | Nhập hồ sơ qua form và DOCX/PDF có lớp văn bản. |
| FR-03 | MUST | Trích xuất Student Math Profile và yêu cầu giáo viên xác nhận. |
| FR-04 | MUST | Lưu evidence kèm nguồn, ngày và điều kiện hỗ trợ. |
| FR-05 | MUST | Tạo/chuẩn hóa mục tiêu Toán cá nhân và lưu trạng thái phê duyệt. |
| FR-06 | MUST | Quản lý curriculum map và prerequisite của mạch số thập phân. |
| FR-07 | MUST | Map một bộ SGK pilot với yêu cầu chương trình. |
| FR-08 | MUST | Tải và phân tách KHBD thành YCCĐ, hoạt động, nhiệm vụ và đánh giá. |
| FR-09 | MUST | Cho giáo viên sửa kết quả phân tách KHBD. |
| FR-10 | MUST | Tạo alignment cho từng YCCĐ/hoạt động. |
| FR-11 | MUST | Đề xuất năm trạng thái điều chỉnh đã quy định. |
| FR-12 | MUST | Hiển thị rationale, evidence, goal và yêu cầu phê duyệt. |
| FR-13 | MUST | Cho giáo viên chấp nhận, sửa, từ chối và phê duyệt. |
| FR-14 | MUST | Chèn adaptation vào từng hoạt động mà không ghi đè nội dung gốc. |
| FR-15 | MUST | Sinh phiếu có đáp án/rubric và evidence fields. |
| FR-16 | MUST | Xuất KHBD dạng DOCX và phiếu dạng PDF. |
| FR-17 | MUST | Tạo biểu mẫu nhập kết quả sau tiết học. |
| FR-18 | MUST | Lưu performance, support level, error type và teacher note. |
| FR-19 | MUST | Hiển thị tiến bộ theo goal và đề xuất next action. |
| FR-20 | MUST | Lưu audit trail của toàn bộ quá trình. |
| FR-21 | SHOULD | Preview KHBD và phiếu trước khi xuất. |
| FR-22 | SHOULD | Tải ảnh bài làm làm evidence. |
| FR-23 | SHOULD | Tái sử dụng adaptation đã duyệt cho tiết có cấu trúc tương tự. |

---

# 11. Luồng màn hình tối thiểu

1. **Học sinh:** danh sách, tạo mới, trạng thái profile và goal.
2. **Hồ sơ năng lực Toán:** tải tài liệu, xem profile, evidence và xác nhận.
3. **Mục tiêu cá nhân:** xem, sửa và phê duyệt mục tiêu.
4. **Tải KHBD:** chọn bài/tiết, tải DOCX, sửa kết quả phân tách.
5. **Alignment và Adaptation:** KHBD gốc, evidence, decision và rationale cho từng hoạt động.
6. **Gói bài dạy:** preview, phê duyệt và xuất KHBD/phiếu/đáp án.
7. **Sau tiết học:** nhập performance, support level, error type và bài làm.
8. **Tiến bộ:** trend theo goal và recommendation cho tiết sau.

---

# 12. Tình huống demo bắt buộc

## 12.1. Bối cảnh

- Bài: Làm tròn số thập phân.
- KHBD thật có các hoạt động khởi động, hình thành kiến thức, luyện tập có hướng dẫn, luyện tập độc lập và vận dụng.

## 12.2. Dữ liệu học sinh

- đọc/viết được số thập phân;
- hiểu số nào gần mốc hơn khi có trục số;
- chưa ổn định giá trị hàng;
- dễ nhìn nhầm chữ số cần quan sát;
- làm tốt hơn khi có bảng giá trị hàng và visual cue;
- mục tiêu cá nhân liên quan đến xác định giá trị hàng.

## 12.3. Kết quả mong đợi

Hệ thống phải đề xuất `SUPPORT`, không tự giảm mục tiêu làm tròn.

KHBD điều chỉnh phải thêm vào đúng hoạt động:

- bảng giá trị hàng;
- highlight hàng cần làm tròn;
- khoanh chữ số bên phải;
- checklist quy trình;
- worked example;
- giảm dần scaffold ở phần độc lập.

Phiếu phải có trường ghi đúng/sai, bước sai, mức prompt và khả năng làm độc lập.

Sau khi nhập kết quả, hệ thống phải phân biệt được học sinh chưa hiểu concept với học sinh hiểu nhưng còn phụ thuộc scaffold.

---

# 13. Tiêu chí chấp nhận end-to-end

Một ca kiểm thử đạt khi:

1. Giáo viên tạo được học sinh và xác nhận Student Math Profile.
2. Mỗi kết luận quan trọng có evidence hoặc được đánh dấu chưa đủ evidence.
3. Giáo viên tải được một KHBD thật và sửa được kết quả phân tách.
4. Hệ thống xác định được YCCĐ và các hoạt động chính.
5. Ít nhất một yêu cầu bài học được liên kết với profile và goal.
6. Mỗi adaptation có decision, barrier, evidence, rationale và goal.
7. Hệ thống không giảm/thay mục tiêu chỉ vì học sinh có nhãn RLHT.
8. `REDUCE_SCOPE/REPLACE` không được coi là đã duyệt nếu thiếu xác nhận.
9. Giáo viên sửa được adaptation ở cấp từng hoạt động.
10. KHBD đầu ra giữ cấu trúc gốc và phân biệt rõ phần điều chỉnh.
11. Phiếu có đáp án/rubric và thu được evidence đúng mục tiêu.
12. Artifact cho học sinh không lộ dữ liệu nhạy cảm.
13. Giáo viên nhập được kết quả sau tiết học bằng một form ngắn.
14. Báo cáo tiến bộ hiển thị cả performance và support level.
15. Hệ thống lưu được bản gốc, bản đề xuất và bản giáo viên duyệt.

---

# 14. Yêu cầu phi chức năng tối thiểu

## 14.1. Khả dụng

- Giáo viên không phải nhập lại toàn bộ KHBD đã có.
- Thuật ngữ chuyên môn có diễn giải tiếng Việt dễ hiểu.
- Đề xuất sửa được trực tiếp, không chỉ có nút chấp nhận/từ chối.
- Form sau tiết học chỉ hỏi dữ liệu cần cho goal đang đo.

## 14.2. Giải thích và truy vết

- Mỗi adaptation trả lời được: YCCĐ nào, evidence nào, goal nào, vì sao và sẽ thu evidence gì.
- Rule quan trọng lưu `source_id`, `version` và loại nguồn.
- Nội dung do AI sinh không được hiển thị như kết luận chính thức trước khi duyệt.

## 14.3. Bảo mật

- Phân quyền tối thiểu theo giáo viên/người thẩm định.
- Tách hồ sơ học sinh khỏi phiếu phát cho lớp.
- Không đưa nhãn chẩn đoán và dữ liệu nhạy cảm vào file in nếu không cần.
- Lưu nhật ký người xem, sửa và phê duyệt.

## 14.4. Hiệu năng cho pilot

Mục tiêu nội bộ:

- phân tích một KHBD có cấu trúc trong tối đa 120 giây;
- tạo bản nháp adaptation và phiếu trong tối đa 120 giây sau khi đủ input;
- không mất dữ liệu giáo viên đã sửa khi tải lại trang.

Đây là ngưỡng kỹ thuật đề xuất, không phải yêu cầu pháp lý.

---

# 15. Kế hoạch chứng minh tính khả dụng

## 15.1. Đối tượng pilot đề xuất

- 3–5 giáo viên đang dạy Toán lớp 5;
- mỗi giáo viên chọn một học sinh phù hợp phạm vi;
- ba tiết có liên quan trong mạch số thập phân;
- ít nhất một người có chuyên môn giáo dục hòa nhập thẩm định output.

## 15.2. Cách tiến hành

1. Ghi baseline khi giáo viên thực hiện workflow thủ công.
2. Giáo viên dùng MVP chuẩn bị các tiết pilot.
3. Ghi thời gian, phần bị sửa và lý do từ chối đề xuất.
4. Triển khai ít nhất một số gói bài dạy trong lớp thật.
5. Thu evidence sau tiết học.
6. Phỏng vấn giáo viên về mức độ dễ hiểu, dễ sửa và khả năng tiếp tục sử dụng.

## 15.3. Ngưỡng go/no-go đề xuất

Các ngưỡng này là quyết định sản phẩm nội bộ, cần chốt trước pilot:

| Nhóm | Ngưỡng đề xuất |
|---|---|
| Hoàn thành workflow | Ít nhất 80% ca hoàn thành từ input đến gói bài dạy mà không cần đội phát triển can thiệp trực tiếp |
| Thời gian | Sau lần làm quen, trung vị không quá 15 phút cho một tiết |
| Khả dụng đầu ra | Ít nhất 70% adaptation được giữ nguyên hoặc chỉ sửa nhẹ |
| Dễ hiểu | Điểm trung bình ít nhất 4/5 cho việc hiểu lý do đề xuất |
| Có thể sử dụng | Điểm trung bình ít nhất 4/5 cho khả năng dùng để chuẩn bị tiết dạy |
| An toàn | Không có `REDUCE_SCOPE/REPLACE` được coi là đã duyệt khi thiếu xác nhận |
| Evidence loop | Ít nhất 80% tiết đã dạy có performance và support level |
| Hòa nhập | Không tách học sinh khỏi hoạt động chung một cách không cần thiết |

---

# 16. Dữ liệu phải chuẩn bị trước khi xây workflow

1. Danh sách `CurriculumRequirement` của mạch số thập phân.
2. Prerequisite graph tối thiểu.
3. Mapping bộ SGK pilot tới requirement và bài/tiết.
4. Taxonomy kỹ năng và lỗi.
5. Khoảng 10–20 rule adaptation đã được chuyên gia xem xét.
6. Thư viện scaffold cho giá trị hàng, so sánh, làm tròn và phép tính.
7. Template KHBD điều chỉnh.
8. Template phiếu, đáp án, rubric và evidence form.
9. Ít nhất ba ca mẫu end-to-end đã được thẩm định.

Không cần xây knowledge base cho toàn bộ Toán 5 hoặc các dạng khuyết tật khác để hoàn thành MVP.

---

# 17. Định nghĩa hoàn thành MVP

MVP hoàn thành khi:

- một giáo viên tự thực hiện được toàn bộ workflow;
- hệ thống xử lý được KHBD thật thay vì chỉ dùng template demo cố định;
- có ít nhất ba ca end-to-end trong mạch số thập phân;
- xuất được KHBD hòa nhập, phiếu, đáp án và evidence form;
- mọi quyết định có traceability;
- guardrail phê duyệt hoạt động đúng;
- ít nhất một gói bài dạy được dùng trong lớp thật;
- kết quả sau tiết học tạo được recommendation cho lần tiếp theo;
- có báo cáo pilot theo các chỉ số ở Mục 15.

Gói bằng chứng để trình bày với bên liên quan nên gồm:

1. KHBD gốc của giáo viên;
2. Student Math Profile đã ẩn danh;
3. báo cáo alignment và rationale;
4. KHBD hòa nhập đã được duyệt;
5. phiếu học tập đã sử dụng;
6. bài làm/evidence đã ẩn danh;
7. progress update;
8. phản hồi và thời gian thực hiện của giáo viên.

---

# 18. Quyết định cần chốt trước pilot

1. Bộ SGK và bài/tiết cụ thể của trường pilot.
2. Các mẫu KHBD thật dùng để kiểm thử parser.
3. Cách dùng nhãn `KHGDCN` hoặc `Kế hoạch hỗ trợ học tập cá nhân` cho từng ca.
4. Ai có quyền duyệt `REDUCE_SCOPE/REPLACE`.
5. Quy định lưu, ẩn danh và xóa dữ liệu học sinh.
6. Danh sách rule/template đã được chuyên gia chấp nhận.
7. Ngưỡng go/no-go chính thức thay cho các ngưỡng đề xuất.

---

# 19. Tóm tắt MVP trong một câu

> MVP là hệ thống giúp giáo viên lớp 5 tải hồ sơ học sinh và KHBD Toán đã soạn, nhận các đề xuất điều chỉnh có căn cứ cho từng hoạt động, phê duyệt một KHBD hòa nhập kèm học liệu, sau đó ghi minh chứng để theo dõi tiến bộ và giảm dần mức hỗ trợ của học sinh.
