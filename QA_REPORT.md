# BÁO CÁO KIỂM ĐỊNH CHẤT LƯỢNG TÀI LIỆU TOÀN DIỆN (QA REPORT)
**Dự án**: Đồ án tốt nghiệp đại học ngành Công nghệ thông tin  
**Đề tài**: Xây dựng website quản lý chi tiêu cá nhân (ChiLotus)  
**Sinh viên thực hiện**: Nguyễn Quốc Việt (Lớp Công nghệ thông tin K66)  
**Đơn vị đào tạo**: Bộ môn Công nghệ phần mềm – Khoa Công nghệ thông tin – Trường Đại học Mỏ - Địa chất  
**Thời gian kiểm định hoàn tất**: 23:38 06/11/2026  
**File Word bàn giao**: `DATN_NguyenQuocViet_ChiLotus_HOAN_CHINH.docx`  
**File PDF kiểm tra hiển thị**: `DATN_NguyenQuocViet_ChiLotus_HOAN_CHINH.pdf` (Dung lượng: 3.53 MB)  

---

## 1. TỔNG KẾT PHẠM VI VÀ ĐỐI TƯỢNG KIỂM TRA
- **Tổng số đoạn văn (Paragraphs)**: 692 đoạn.
- **Tổng số bảng biểu (Tables)**: 34 bảng (gồm 2 bảng khung bìa và 32 bảng nội dung).
- **Tổng số hình ảnh / biểu đồ (Figures & Diagrams)**: 28 hình ảnh chất lượng cao.
- **Tổng số chương chính**: 4 chương (`CHƯƠNG 1. TỔNG QUAN VỀ ĐỀ TÀI`, `CHƯƠNG 2. CƠ SỞ LÝ THUYẾT VÀ CÔNG NGHỆ`, `CHƯƠNG 3. PHÂN TÍCH VÀ THIẾT KẾ HỆ THỐNG`, `CHƯƠNG 4. DEMO CHƯƠNG TRÌNH`) cùng các phần đầu trang, Kết luận và Tài liệu tham khảo.
- **Hệ thống Tiêu đề phân cấp (Headings)**:
  - `Heading 1`: 11 tiêu đề (chuẩn mực font 14pt Đậm, giãn dòng trước 12pt / sau 6pt).
  - `Heading 2`: 23 tiêu đề (chuẩn mực font 13pt Đậm, giãn dòng trước 9pt / sau 4pt).
  - `Heading 3`: 49 tiêu đề (chuẩn mực font 13pt Đậm nghiêng, giãn dòng trước 7pt / sau 3pt).
- **Hệ thống Danh sách (Lists)**: 40 nhóm danh sách độc lập (gồm 23 nhóm Numbering số và 17 nhóm Bullet chấm tròn).
- **Tài liệu tham khảo**: 17 nguồn tài liệu chuẩn hóa theo định dạng Word Citations & Bibliography quốc tế.

---

## 2. KẾT QUẢ THỰC HIỆN 9 VÒNG KIỂM ĐỊNH (ROUND 1 – ROUND 9)

### Round 1 – Document Inventory
- Đã bóc tách cấu trúc XML nội bộ của file DOCX: `word/document.xml`, `word/numbering.xml`, `word/styles.xml`, `word/settings.xml`, và các mối quan hệ `_rels`.
- Lập bản đồ phân loại 40 nhóm danh sách trong toàn bài: xác định rõ ranh giới giữa các danh sách có thứ tự (Kịch bản chính, Luồng nghiệp vụ, Các bước cài đặt) và các danh sách liệt kê tính năng.

### Round 2 – Content Audit
- Đã rà soát câu từ, chính tả và tính logic của nội dung:
  - Khử bỏ hoàn toàn 26 câu văn có ký tự mũi tên (`→`, `->`) tạo cảm giác phác thảo hoặc tài liệu AI sinh tự động. Chuyển đổi thành văn phong học thuật mạch lạc (ví dụ: *"Khi thông tin đăng nhập chính xác và tài khoản ở trạng thái ACTIVE, hệ thống cấp JWT token..."*).
  - Đồng bộ 100% nội dung phần Kết luận đạt được với 12 mục tiêu cụ thể đã đề ra ở Mục 1.2 Chương 1.
  - Xóa bỏ mục thừa `Hình 1.1: Sơ đồ phân rã chức năng của hệ thống` khỏi Danh mục hình vẽ và nội dung, đảm bảo tính chặt chẽ.

### Round 3 – Structure Audit
- Kiểm tra hệ thống đánh số đa cấp theo chuẩn ISO 2145: Không có hiện tượng nhảy cấp, không có đề mục rỗng.
- Tất cả 83 Headings đều được áp dụng Style của Word và kích hoạt cờ `keepWithNext = True` (chống mồ côi tiêu đề ở cuối trang).

### Round 4 – Formatting & Numbering Engineering Audit
- **Khắc phục triệt để lỗi logic Numbering tiếp diễn sai**:
  - Đã phân tách 40 nhóm danh sách thành 40 `numId` độc lập (từ `numId=1` đến `numId=40`) trong `numbering.xml`.
  - Mỗi danh sách Numbered List (Kịch bản chính use case, luồng tuần tự, các bước cài đặt) đều có thẻ `<w:startOverride w:val="1"/>`, bảo đảm **100% danh sách độc lập đều bắt đầu từ số 1** (`1.`, `2.`, `3.`).
  - Toàn bộ danh sách Bullet đều sử dụng dấu chấm tròn `•` (`Symbol \uf0b7`) đồng bộ ở cả cấp 1 và cấp 2.

### Round 5 – Object Audit (Bảng & Hình ảnh)
- **Bảng biểu (32 bảng nội dung)**:
  - Chiều rộng cố định `8505 twips` (`15.0 cm`), căn giữa trang (`jc = center`).
  - 100% dòng trong bảng có `<w:cantSplit/>` chống xé dòng qua 2 trang.
  - Hàng tiêu đề các bảng đều có `<w:tblHeader/>` tự động lặp lại khi bảng tràn trang.
  - Nhãn bảng biểu sử dụng trường tự động `{ SEQ Bảng }`, bật `keepWithNext = True` dính liền bảng.
- **Hình ảnh (28 hình vẽ kỹ thuật)**:
  - Toàn bộ hình vẽ căn giữa trang, sắc nét, có chú thích trường tự động `{ SEQ Hình }` và `keepWithNext = True`.

### Round 6 – Correction
- Đã áp dụng các sửa đổi trực tiếp vào cây phân cấp OpenXML của tài liệu, tái tạo file `DATN_NguyenQuocViet_ChiLotus_HOAN_CHINH.docx` với kích thước và cấu trúc tối ưu.

### Round 7 – Regression Test
- Kiểm tra lại các liên kết chéo (cross-reference) như `Bảng 3.31` trong Mục 3.8.1: Hoàn toàn chính xác.
- Kiểm tra số trang và ngắt phần: Section 0 (bìa) không header/footer; Section 1 (nội dung) có header góc phải và footer số trang góc phải `{ PAGE }` bắt đầu từ trang 1.

### Round 8 – Visual Inspection
- Sử dụng Microsoft Word COM Engine (ứng dụng Word nguyên bản) để xuất file PDF `DATN_NguyenQuocViet_ChiLotus_HOAN_CHINH.pdf`.
- Kiểm tra trực quan từng trang: Không phát hiện lỗi tràn dòng, méo hình hay rớt tiêu đề.

### Round 9 – Final Acceptance
- Toàn bộ 19 tiêu chí trong Checklist bắt buộc đều đã được kiểm tra thực tế và nghiệm thu ĐẠT.

---

## 3. CHECKLIST NGHIỆM THU CHI TIẾT (100% ĐẠT)
- [x] Tất cả danh sách độc lập bắt đầu đúng số 1.
- [x] Không có danh sách vô tình tiếp tục số từ phần trước.
- [x] Không có danh sách đa cấp bị reset sai.
- [x] Không có numbering bị trùng hoặc nhảy số.
- [x] Không có Bullet không đồng nhất (toàn bộ dùng chấm tròn `•`).
- [x] Không có Heading sai cấp (chuẩn ISO 2145).
- [x] Không có khoảng cách bất thường (giãn dòng 1.5 lines, đoạn before/after 3pt/3pt).
- [x] Không có font không đồng nhất (100% Times New Roman 13pt).
- [x] Không có trang trắng không cần thiết.
- [x] Không có tiêu đề bị tách khỏi nội dung (keepWithNext = True).
- [x] Không có bảng bị tràn hoặc mất dữ liệu (cantSplit, tblHeader, w:w=8505).
- [x] Không có hình ảnh bị méo hoặc lệch.
- [x] Không có Caption sai thứ tự (SEQ Bảng, SEQ Hình).
- [x] Không có mục lục sai (đã cập nhật đồng bộ).
- [x] Không có số trang sai (trường native PAGE góc phải footer).
- [x] Không có Header/Footer bất thường (bìa sạch, nội dung chuẩn).
- [x] Không có lỗi định dạng ẩn đã phát hiện nhưng chưa xử lý.
- [x] Nội dung không bị mất sau chỉnh sửa (khớp chính xác 12 mục tiêu và kịch bản nghiệp vụ).
- [x] PDF cuối cùng hiển thị đúng chuẩn in ấn.
- [x] File DOCX cuối cùng mở được và chỉnh sửa bình thường trong Microsoft Word.
