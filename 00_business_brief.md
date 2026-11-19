# TÀI LIỆU MÔ TẢ NHU CẦU NGHIỆP VỤ

**Chủ đề:** Ngăn chặn lừa đảo đang diễn ra khi khách hàng chuyển tiền
**Đơn vị đề xuất:** Khối Quản trị rủi ro, Ví điện tử SafePay
**Người nhận:** Bộ phận Phân tích nghiệp vụ (BA)
**Phiên bản:** 1.0 | **Ngày:** 19/11/2026

> **Lưu ý:** SafePay là doanh nghiệp giả định. Toàn bộ số liệu nội bộ của SafePay trong tài liệu này là số liệu giả định phục vụ dự án. Số liệu thị trường và quy định pháp luật là thông tin thật, có nguồn ở mục 10.

---

## 1. Giới thiệu doanh nghiệp và các bộ phận liên quan

SafePay là ví điện tử được cấp phép hoạt động tại Việt Nam, hiện có khoảng 2,5 triệu người dùng đang hoạt động hằng tháng. Dịch vụ chính là chuyển tiền giữa các ví SafePay, nạp và rút tiền qua ngân hàng liên kết, thanh toán hóa đơn. Chuyển tiền giữa các ví diễn ra 24/7 và tiền đến ví người nhận ngay lập tức.

Các bộ phận liên quan đến nhu cầu này:

| Bộ phận | Vai trò hiện tại |
|---|---|
| Khối Kinh doanh và Tăng trưởng | Phát triển người dùng, theo dõi số lượng và giá trị giao dịch |
| Trung tâm Chăm sóc khách hàng (CSKH) | Tổng đài 24/7, tiếp nhận khiếu nại qua tổng đài và ứng dụng |
| Phòng Chống gian lận | 4 chuyên viên và 1 trưởng nhóm, làm việc từ 8:00 đến 17:30, thứ Hai đến thứ Bảy. Điều tra giao dịch đáng ngờ, làm việc với cơ quan công an |
| Khối Quản trị rủi ro | Ban hành quy định rủi ro, đứng đầu là Giám đốc Rủi ro |
| Phòng Pháp chế và Tuân thủ | Bảo đảm tuân thủ quy định của Ngân hàng Nhà nước và pháp luật về dữ liệu cá nhân |
| Khối Công nghệ | Vận hành ứng dụng và hệ thống giao dịch |

## 2. Bối cảnh và vấn đề

### 2.1 Tình hình chung

Lừa đảo qua mạng tại Việt Nam ngày càng tinh vi. Công an thành phố Hà Nội đã công bố 25 kịch bản lừa đảo phổ biến năm 2026, trong đó nhiều kịch bản dựa trên việc giả danh công an, cơ quan thuế, nhà trường hoặc người thân để dẫn dắt nạn nhân **tự tay chuyển tiền**. Do chính chủ tài khoản thực hiện giao dịch và xác thực đầy đủ, các biện pháp xác thực không ngăn được loại lừa đảo này.

Ngành ngân hàng và ví điện tử đã triển khai một số biện pháp:
- Từ 01/7/2024, theo Quyết định 2345/QĐ-NHNN, giao dịch chuyển tiền hoặc nạp tiền vào ví điện tử trên 10 triệu đồng mỗi lần, hoặc khi tổng giá trị giao dịch trong ngày vượt 20 triệu đồng, phải xác thực sinh trắc học. Việc ngưỡng tổng 20 triệu đồng mỗi ngày áp dụng cụ thể thế nào với giao dịch chuyển tiền giữa các ví điện tử: [CẦN KIỂM CHỨNG].
- Hệ thống SIMO của Ngân hàng Nhà nước cảnh báo các tài khoản nghi ngờ lừa đảo. Tính đến 28/09/2026, SIMO đã phát hơn 5,6 triệu cảnh báo, hơn 1,9 triệu giao dịch được tạm dừng hoặc hủy, giữ lại hơn 6.300 tỷ đồng.

### 2.2 Vấn đề SafePay đang gặp

Số liệu nội bộ 6 tháng gần nhất (giả định):
- Trung bình **180 khiếu nại "bị lừa chuyển tiền" mỗi tháng**, số tiền thiệt hại trung vị khoảng 18 triệu đồng mỗi vụ.
- **62%** số vụ, ví nhận tiền **không có trong danh sách cảnh báo nào** tại thời điểm giao dịch.
- **71%** nạn nhân cho biết họ **đang nói chuyện điện thoại** với kẻ gian trong lúc chuyển tiền.
- **45%** nạn nhân chuyển từ 2 lần trở lên cho cùng một kẻ gian trong vòng 1 giờ.
- Thời gian trung bình từ lúc khách báo đến lúc phòng Chống gian lận bắt đầu xử lý là **2 ngày làm việc**. Đến lúc đó, gần như toàn bộ tiền đã bị rút khỏi ví nhận.

## 3. Mục tiêu kinh doanh

| Mã | Mục tiêu |
|---|---|
| MT-01 | Giảm 40% tổng số tiền khách hàng khiếu nại bị lừa chuyển đi, so với trung bình 6 tháng trước khi triển khai, đo sau 6 tháng triển khai |
| MT-02 | Rút thời gian từ lúc tiếp nhận báo cáo lừa đảo đến lúc bắt đầu xử lý xuống dưới 2 giờ |
| MT-03 | Nâng cao niềm tin của khách hàng đối với SafePay |
| MT-04 | Không làm ảnh hưởng đến trải nghiệm của khách hàng có giao dịch bình thường |
| MT-05 | 100% quyết định chặn, tạm giữ, cảnh báo được lưu vết và giải thích được khi cơ quan quản lý hoặc khách hàng yêu cầu |

## 4. Các bên liên quan và mối quan tâm

| Bên liên quan | Mối quan tâm |
|---|---|
| Khách hàng gửi tiền | Không bị mất tiền. Không muốn bị hỏi han, chờ đợi khi chuyển tiền cho người quen |
| Khách hàng nhận tiền (bao gồm hộ kinh doanh nhận tiền bán hàng qua ví) | Nhận tiền ngay. Không bị gắn nhầm là tài khoản lừa đảo, vì ảnh hưởng đến việc kinh doanh |
| Khối Kinh doanh và Tăng trưởng | Giữ tốc độ chuyển tiền là lợi thế cạnh tranh. Lo ngại mỗi bước cảnh báo hoặc chờ đợi làm giảm số giao dịch và khiến khách chuyển sang ví khác |
| Khối Quản trị rủi ro | Muốn chặn càng nhiều giao dịch rủi ro càng tốt, chấp nhận một tỷ lệ báo động nhầm. Giám đốc Rủi ro đề nghị thời gian tạm giữ tối thiểu 60 phút để nạn nhân có đủ thời gian bình tĩnh lại |
| Phòng Chống gian lận | Số lượng giao dịch cần xem xét phải vừa sức 5 người. Cần đủ thông tin để ra quyết định nhanh |
| Trung tâm CSKH | Lo ngại lượng cuộc gọi phàn nàn tăng mạnh khi giao dịch của khách bị giữ hoặc bị chặn |
| Phòng Pháp chế và Tuân thủ | Việc dùng thông tin "khách đang có cuộc gọi" là xử lý dữ liệu cá nhân, phải tuân thủ Luật Bảo vệ dữ liệu cá nhân. Mọi quyết định phải có căn cứ để giải trình |
| Ngân hàng Nhà nước, cơ quan công an | Nguồn cung cấp danh sách tài khoản nghi ngờ, nơi nhận báo cáo khi có yêu cầu |

## 5. Mô tả quy trình hiện tại và mong muốn

### 5.1 Quy trình hiện tại (as-is)

**Chuyển tiền.** Khách nhập ví người nhận và số tiền. Hệ thống đối chiếu ví nhận với danh sách cảnh báo. Nếu ví nhận nằm trong danh sách, ứng dụng hiện thông báo chung "Tài khoản có dấu hiệu rủi ro", khách bấm "Tiếp tục" là giao dịch được thực hiện ngay. Nếu không nằm trong danh sách, giao dịch được thực hiện ngay. Giao dịch trên 10 triệu đồng yêu cầu xác thực sinh trắc học.

**Cập nhật danh sách cảnh báo.** Mỗi thứ Hai, một chuyên viên Chống gian lận tải file danh sách từ nguồn của cơ quan quản lý, đối chiếu thủ công và nhập vào hệ thống. Tài khoản do SafePay tự phát hiện được ghi vào một file Excel riêng, chưa có quy trình đưa vào danh sách chính thức.

**Tiếp nhận báo cáo lừa đảo.** Khách gọi tổng đài. Nhân viên CSKH ghi nhận thông tin vào biểu mẫu, sau đó gửi email cho phòng Chống gian lận. Vì phòng Chống gian lận chỉ làm việc giờ hành chính, các báo cáo nhận vào buổi tối hoặc Chủ nhật phải chờ đến ngày làm việc tiếp theo. Phòng Chống gian lận theo dõi tiến độ xử lý các vụ việc trên một bảng tính dùng chung.

**Thay đổi quy định rủi ro.** Các ngưỡng cảnh báo được lập trình cứng trong hệ thống. Mỗi lần muốn thay đổi, Khối Quản trị rủi ro phải gửi yêu cầu cho Khối Công nghệ, thời gian chờ trung bình 3 tuần.

**Báo cáo.** Cuối tháng, Khối Quản trị rủi ro tổng hợp số liệu thủ công từ bảng tính của phòng Chống gian lận và dữ liệu giao dịch.

### 5.2 Mong muốn trong tương lai (to-be)

Ban điều hành mong muốn:

1. **Kiểm tra trước khi tiền rời khỏi ví.** Mỗi giao dịch chuyển tiền được kiểm tra rủi ro trước khi thực hiện, dựa trên cả thông tin người nhận lẫn tình huống của người gửi lúc giao dịch. Giao dịch bình thường vẫn hoàn tất ngay.
2. **Can thiệp theo mức độ rủi ro.** Tùy mức độ, khách hàng được cảnh báo kèm lý do cụ thể và phải xác nhận lại, hoặc giao dịch bị tạm giữ, hoặc bị chặn. Trong thời gian tạm giữ, tiền chưa đến người nhận và khách có thể hủy giao dịch. Theo đề nghị của Khối Quản trị rủi ro, thời gian tạm giữ tối thiểu là 60 phút. Hết thời gian tạm giữ, nếu khách không hủy, giao dịch tự động được thực hiện.
3. **Xem xét giao dịch bị tạm giữ, bị chặn.** Phòng Chống gian lận có một nơi tập trung để xem các giao dịch bị tạm giữ hoặc bị chặn, cùng lý do, và ra quyết định. Giao dịch có giá trị lớn cần trưởng nhóm phê duyệt thêm.
4. **Báo cáo lừa đảo được xử lý ngay.** Khách có thể tự báo cáo qua ứng dụng, ngoài kênh tổng đài. Mỗi báo cáo trở thành một hồ sơ được theo dõi từ lúc tiếp nhận đến lúc kết thúc: tiếp nhận, đang xác minh, chờ khách bổ sung thông tin, kết luận (xác nhận lừa đảo hoặc không đủ căn cứ), đóng hồ sơ. Nếu khách không bổ sung thông tin trong 7 ngày, hồ sơ được đóng. Khách có thể đề nghị mở lại hồ sơ trong vòng 30 ngày kể từ khi đóng. Khi hồ sơ được xác nhận là lừa đảo, ví nhận tiền được đưa vào danh sách nghi ngờ.
5. **Danh sách nghi ngờ được quản lý tập trung.** Một danh sách duy nhất gồm hai mức (cảnh báo và chặn), tổng hợp từ nguồn của cơ quan quản lý và kết quả điều tra nội bộ, có ghi nhận nguồn và lý do. Chủ ví bị đưa vào danh sách có thể đề nghị xem xét lại.
6. **Khối Quản trị rủi ro tự điều chỉnh quy định**, không phải chờ Khối Công nghệ, nhưng mọi thay đổi phải được phê duyệt.
7. **Báo cáo tự động** thay cho tổng hợp thủ công.

## 6. Quy định nghiệp vụ

| Mã | Quy định |
|---|---|
| QĐ-01 | Giao dịch đến ví nằm trong danh sách chặn thì không được thực hiện |
| QĐ-02 | Giao dịch đến ví nằm trong danh sách cảnh báo thì khách phải được cảnh báo và xác nhận lại trước khi thực hiện |
| QĐ-03 | Khách đang trong cuộc gọi, chuyển cho người nhận mới, số tiền từ 5.000.000 đồng trở lên thì giao dịch bị tạm giữ |
| QĐ-04 | Số tiền lớn hơn 3 lần giá trị giao dịch trung bình của khách trong 30 ngày gần nhất thì khách phải được cảnh báo |
| QĐ-05 | Thời gian tạm giữ giao dịch là 30 phút |
| QĐ-06 | Giao dịch bị tạm giữ chỉ được thực hiện khi chuyên viên Chống gian lận xác nhận giao dịch hợp lệ |
| QĐ-07 | Khách có từ 3 giao dịch đến người nhận mới trong vòng 60 phút thì từ giao dịch thứ 3 bị tạm giữ |
| QĐ-08 | Giao dịch trên 10.000.000 đồng, hoặc khi tổng giá trị giao dịch trong ngày của khách vượt 20.000.000 đồng, phải xác thực sinh trắc học (theo Quyết định 2345/QĐ-NHNN) |
| QĐ-09 | Khách hàng từ 60 tuổi trở lên được áp dụng mức bảo vệ cao hơn |
| QĐ-10 | Giao dịch chuyển tiền liên ngân hàng trên 50.000.000 đồng đến người nhận mới phải được cảnh báo |
| QĐ-11 | Khách có thể tự đánh dấu một người nhận là "người nhận tin cậy". Giao dịch đến người nhận tin cậy không bị tạm giữ |
| QĐ-12 | Giao dịch bị tạm giữ có giá trị từ 50.000.000 đồng trở lên cần trưởng nhóm Chống gian lận phê duyệt thêm sau khi chuyên viên xác nhận |
| QĐ-13 | Một giao dịch chỉ được trừ tiền một lần, kể cả khi khách gửi yêu cầu nhiều lần hoặc mạng bị lỗi |
| QĐ-14 | Tiền của giao dịch đang bị tạm giữ không được dùng cho giao dịch khác |
| QĐ-15 | Chỉ phòng Chống gian lận được thêm hoặc gỡ ví khỏi danh sách nghi ngờ. Mọi thay đổi phải ghi nguồn và lý do |
| QĐ-16 | Mọi thay đổi quy định rủi ro do Khối Quản trị rủi ro đề xuất phải được Giám đốc Rủi ro phê duyệt trước khi áp dụng. Người đề xuất không được tự phê duyệt |
| QĐ-17 | Chỉ sử dụng thông tin "khách đang trong cuộc gọi" khi khách đã đồng ý cho SafePay xử lý thông tin này |

Một giao dịch có thể cùng lúc thỏa nhiều quy định trên.

## 7. Yêu cầu phi chức năng

| Mã | Yêu cầu |
|---|---|
| PCN-01 | Việc kiểm tra rủi ro không làm thời gian xử lý giao dịch tăng thêm quá 1 giây |
| PCN-02 | Hệ thống kiểm tra rủi ro hoạt động 24/7. Khi kiểm tra rủi ro gặp sự cố, giao dịch không được thực hiện cho đến khi kiểm tra được |
| PCN-03 | Mỗi quyết định cảnh báo, tạm giữ, chặn phải ghi lại: thời điểm, các quy định đã kích hoạt, dữ liệu đầu vào, kết quả, người xử lý (nếu có). Dữ liệu lưu vết được lưu tối thiểu 5 năm (chính sách nội bộ giả định) |
| PCN-04 | Lý do cảnh báo hiển thị cho khách bằng tiếng Việt dễ hiểu. Lý do hiển thị cho chuyên viên phải nêu rõ quy định nào đã kích hoạt và giá trị cụ thể |
| PCN-05 | Phân quyền theo vai trò. Nhân viên CSKH xem được trạng thái giao dịch và hồ sơ của khách nhưng không được thay đổi quyết định của phòng Chống gian lận |
| PCN-06 | Dữ liệu cá nhân được xử lý theo Luật Bảo vệ dữ liệu cá nhân số 91/2025/QH15 |

## 8. Phạm vi

**Trong phạm vi**
1. Chuyển tiền giữa các ví SafePay có kiểm tra rủi ro
2. Cảnh báo và yêu cầu khách xác nhận lại
3. Tạm giữ giao dịch và cho phép khách hủy
4. Xem xét giao dịch bị tạm giữ, bị chặn, phê duyệt hai cấp với giao dịch giá trị lớn
5. Tiếp nhận và xử lý hồ sơ báo cáo lừa đảo
6. Quản lý danh sách nghi ngờ
7. Quản lý quy định rủi ro có phê duyệt
8. Báo cáo hiệu quả hằng tuần và hằng tháng

**Ngoài phạm vi**
- Chuyển tiền liên ngân hàng, nạp và rút tiền, thanh toán hóa đơn
- Kết nối thật với SIMO, cơ quan công an, hệ thống ngân hàng (dùng dữ liệu giả lập)
- Xác thực sinh trắc học thật (giả lập kết quả xác thực)
- Gửi SMS, thông báo đẩy thật (giả lập)
- Thu hồi tiền đã bị chuyển khỏi SafePay
- Chấm điểm rủi ro bằng mô hình học máy

**Nhu cầu báo cáo**
- Hằng tuần, cho phòng Chống gian lận: số giao dịch bị tạm giữ, bị chặn; số giao dịch đang chờ xem xét; thời gian xử lý trung bình.
- Hằng tháng, cho Ban điều hành: tổng số tiền đã được giữ lại, số tiền khách khiếu nại bị lừa, tỷ lệ giao dịch bị tạm giữ nhưng sau đó xác nhận hợp lệ, tỷ lệ khách hủy giao dịch sau khi được cảnh báo, số hồ sơ báo cáo lừa đảo theo từng trạng thái.

## 9. Thuật ngữ

| Thuật ngữ | Giải thích |
|---|---|
| Lừa đảo đang diễn ra | Tình huống nạn nhân đang bị kẻ gian dẫn dắt và tự thực hiện giao dịch |
| Danh sách nghi ngờ | Danh sách ví có dấu hiệu liên quan đến lừa đảo, gồm danh sách cảnh báo và danh sách chặn |
| Tạm giữ | Tiền được giữ lại trong ví người gửi, chưa chuyển cho người nhận |
| Người nhận tin cậy | Người nhận do khách tự đánh dấu là tin cậy |
| SIMO | Hệ thống giám sát, cảnh báo tài khoản nghi ngờ lừa đảo của Ngân hàng Nhà nước |
| Hồ sơ báo cáo lừa đảo | Hồ sơ được tạo khi khách báo cáo mình bị lừa, theo dõi đến khi đóng |

## 10. Nguồn tham khảo

- Từ 01/7/2024, chuyển khoản trên 10 triệu đồng phải xác thực sinh trắc học, LuatVietnam: https://luatvietnam.vn/tin-van-ban-moi/tu-2024-chuyen-khoan-tren-10-trieu-dong-phai-xac-thuc-sinh-trac-hoc-186-96491-article.html
- Phân loại giao dịch ngân hàng phải xác thực sinh trắc học theo Quyết định 2345/QĐ-NHNN, Thị trường Tài chính Tiền tệ: https://thitruongtaichinhtiente.vn/phan-loai-giao-dich-ngan-hang-phai-xac-thuc-sinh-trac-hoc-theo-quyet-dinh-2345-qd-nhnn-58169.html
- Chuyển tiền thấy cảnh báo đỏ, đây là việc cần làm ngay lập tức (số liệu SIMO đến 28/09/2026), CafeF: https://cafef.vn/chuyen-tien-thay-canh-bao-do-day-la-viec-can-lam-ngay-lap-tuc-188261104190434579.chn
- Ngân hàng đồng loạt triển khai tính năng cảnh báo khi chuyển tiền, DNSE: https://www.dnse.com.vn/senses/tin-tuc/ngan-hang-dong-loat-trien-khai-tinh-nang-canh-bao-khi-chuyen-tien-35154379
- Nhận diện 25 kịch bản lừa đảo trên không gian mạng năm 2026, CafeF: https://cafef.vn/nhan-dien-25-kich-ban-lua-dao-tren-khong-gian-mang-nam-2026-188260912081234057.chn
- Luật Bảo vệ dữ liệu cá nhân 2025 (số 91/2025/QH15) có hiệu lực khi nào, LuatVietnam: https://luatvietnam.vn/dan-su/luat-bao-ve-du-lieu-ca-nhan-2025-co-hieu-luc-khi-nao-568-103652-article.html
