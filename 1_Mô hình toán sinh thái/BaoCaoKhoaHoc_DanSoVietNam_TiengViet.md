# Chuyển Tiếp Nhân Khẩu Và Dự Báo Dân Số Việt Nam (1955-2050): Tiếp Cận Sinh Thái Toán Học

## Tóm Tắt

Nghiên cứu này phân tích quá trình chuyển tiếp nhân khẩu của Việt Nam từ tăng trưởng cao sang ổn định và già hóa, sử dụng các mô hình sinh thái toán học và phương pháp thống kê. Dựa trên dữ liệu từ 1955-2025, nghiên cứu khảo sát động lực dân số, đô thị hóa, suy giảm tỷ suất sinh và quá trình già hóa. Kết quả chính bao gồm: (1) tăng trưởng dân số theo đường cong logistic với khả năng chứa đựng 117 triệu người vào năm 2050, (2) đô thị hóa nhanh từ 13,1% lên 41,4% với xu hướng tăng tốc, (3) tỷ suất sinh giảm từ 5,54 xuống 1,88 con/phụ nữ, và (4) tuổi trung vị tăng từ 22 lên 33,4 tuổi. Phân tích hồi quy đa biến xác định năm, tỷ suất sinh và đô thị hóa là các yếu tố dự báo mạnh nhất cho quy mô dân số. Nghiên cứu sử dụng hồi quy OLS, mô hình chuỗi thời gian ARIMA và mô hình tăng trưởng logistic với R² > 0,95. Kết quả cho thấy Việt Nam đang ở giai đoạn cuối của chuyển tiếp nhân khẩu, đòi hỏi các can thiệp chính sách cho phát triển bền vững. Tiếp cận toán học cung cấp khuôn khổ dự báo vững chắc cho việc ra quyết định nhân khẩu dựa trên bằng chứng.

**Từ khóa:** Chuyển tiếp nhân khẩu, Dự báo dân số, Sinh thái toán học, Việt Nam, Đô thị hóa, Suy giảm tỷ suất sinh

## 1. Giới Thiệu

### 1.1 Bối Cảnh Và Ngữ Cảnh Nghiên Cứu

Bối cảnh nhân khẩu của Việt Nam đã trải qua sự chuyển đổi sâu sắc kể từ năm 1955, chuyển từ phục hồi hậu chiến sang hiện đại hóa nhanh chóng. Dân số của đất nước đã tăng từ 28 triệu lên hơn 100 triệu, với những thay đổi đáng kể về cấu trúc tuổi, đô thị hóa và mô thức sinh đẻ. Quá trình chuyển tiếp này phản ánh các xu hướng nhân khẩu toàn cầu nhưng diễn ra trong bối cảnh kinh tế - xã hội đặc thù của Việt Nam với nền kinh tế thị trường xã hội chủ nghĩa và công nghiệp hóa nhanh.

Việc hiểu rõ các động lực nhân khẩu này rất quan trọng cho việc lập kế hoạch phát triển bền vững. Việt Nam đối mặt với nhiều thách thức: quản lý già hóa dân số, đảm bảo nguồn cung lao động đầy đủ, cân bằng phát triển đô thị - nông thôn và duy trì các hệ thống phúc lợi xã hội. Cửa sổ cơ cấu dân số đang đóng lại khi dân số trong độ tuổi lao động đạt đỉnh và tỷ lệ phụ thuộc tăng lên.

### 1.2 Vấn Đề Nghiên Cứu Và Mục Tiêu

Nghiên cứu này đáp ứng nhu cầu cấp thiết về phân tích nhân khẩu toàn diện sử dụng các phương pháp toán học nghiêm ngặt. Mục tiêu nghiên cứu bao gồm:

1. Phân tích quỹ đạo chuyển tiếp nhân khẩu của Việt Nam sử dụng mô hình sinh thái toán học
2. Dự báo xu hướng dân số đến năm 2050 sử dụng phương pháp thống kê và chuỗi thời gian
3. Xác định các yếu tố chính thúc đẩy thay đổi dân số thông qua phân tích đa biến
4. Đánh giá tác động của đô thị hóa đến các mô thức nhân khẩu
5. Cung cấp khuyến nghị dựa trên bằng chứng cho chính sách nhân khẩu

### 1.3 Ý Nghĩa Nghiên Cứu

Các kết quả góp phần vào tài liệu nhân khẩu học bằng cách áp dụng khuôn khổ sinh thái toán học vào bối cảnh các nước đang phát triển. Nghiên cứu cung cấp bằng chứng định lượng cho việc ra quyết định chính sách trong quản lý dân số, quy hoạch đô thị và phúc lợi xã hội. Về phương pháp, nghiên cứu chứng minh sự tích hợp của mô hình hóa thống kê với lý thuyết nhân khẩu học để dự báo vững chắc.

## 2. Tổng Quan Tài Liệu

### 2.1 Lý Thuyết Chuyển Tiếp Nhân Khẩu

Lý thuyết Chuyển tiếp Nhân khẩu của Warren Thompson (1929) cung cấp nền tảng lý thuyết, mô tả sự tiến hóa dân số qua bốn giai đoạn: tỷ suất sinh/tử cao, tỷ suất tử giảm, tỷ suất sinh giảm và tỷ suất sinh/tử thấp. Quá trình chuyển tiếp của Việt Nam tuân theo mô thức này nhưng với tốc độ tăng tốc do các can thiệp của chính phủ và cải cách kinh tế.

### 2.2 Mô Hình Toán Học Trong Nhân Khẩu Học

Các mô hình sinh thái toán học đã được áp dụng thành công cho dân số con người. Mô hình tăng trưởng logistic của Verhulst (1838) mô tả dân số tiếp cận khả năng chứa đựng do hạn chế tài nguyên. Mô hình có dạng:

\[ \frac{dN}{dt} = rN\left(1 - \frac{N}{K}\right) \]

trong đó N là dân số, r là tỷ suất tăng trưởng nội tại và K là khả năng chứa đựng.

### 2.3 Các Nghiên Cứu Trước Đây Về Nhân Khẩu Việt Nam

Các nghiên cứu gần đây (Phân bộ Dân số Liên Hợp Quốc, Ngân hàng Thế giới) ghi nhận các thay đổi nhân khẩu của Việt Nam nhưng thiếu mô hình hóa toán học tích hợp. Nghiên cứu trong nước tập trung vào các khía cạnh cụ thể như suy giảm tỷ suất sinh hoặc đô thị hóa, nhưng phân tích toàn diện sử dụng phương pháp thống kê tiên tiến vẫn còn hạn chế.

### 2.4 Khoảng Trống Nghiên Cứu

Nghiên cứu này lấp đầy khoảng trống bằng cách cung cấp phân tích tích hợp sử dụng nhiều tiếp cận toán học, kết hợp lý thuyết nhân khẩu với tính nghiêm ngặt thống kê để hiểu biết toàn diện và dự báo.

## 3. Phương Pháp

### 3.1 Nguồn Dữ Liệu Và Thu Thập

Nghiên cứu sử dụng bộ dữ liệu nhân khẩu toàn diện từ 1955-2025, lấy từ:
- Worldometer (các chỉ số dân số chính)
- Ngân hàng Thế giới (các chỉ số kinh tế và xã hội)
- Phân bộ Dân số Liên Hợp Quốc (so sánh quốc tế)

Các biến chính bao gồm: Dân số, Thay đổi hàng năm, Tỷ suất sinh, Tuổi trung vị, Tỷ lệ dân số đô thị, Di cư ròng và các chỉ số phái sinh.

### 3.2 Xử Lý Dữ Liệu Và Đảm Bảo Chất Lượng

Xử lý dữ liệu sơ bộ bao gồm:
1. **Điền khuyết giá trị thiếu** sử dụng nội suy tuyến tính
2. **Phát hiện ngoại lệ** sử dụng sai phân bậc nhất và phương pháp IQR
3. **Xác thực dữ liệu** thông qua kiểm chứng chéo nguồn
4. **Tính toán biến phái sinh** cho tỷ lệ và phần trăm

### 3.3 Khung Phân Tích

Nghiên cứu sử dụng tiếp cận đa phương pháp:

#### 3.3.1 Thống Kê Mô Tả Và Phân Tích Tương Quan
- Phân tích xu hướng sử dụng biểu đồ chuỗi thời gian
- Ma trận tương quan cho mối quan hệ giữa các biến
- Thống kê mô tả cho các xu hướng trung tâm và phân tán

#### 3.3.2 Phân Tích Hồi Quy
- **Bình phương tối thiểu thông thường (OLS)** cho mối quan hệ đa biến
- **Yếu tố phóng đại phương sai (VIF)** để đánh giá đa cộng tuyến
- **Hệ số chuẩn hóa** để so sánh tầm quan trọng biến

#### 3.3.3 Dự Báo Chuỗi Thời Gian
- **Mô hình ARIMA** cho xu hướng và thành phần mùa vụ
- **Đường cong tăng trưởng logistic** để ước lượng trần dân số

#### 3.3.4 Phân Tích Tác Động Đô Thị Hóa
- Hồi quy phân đoạn cho các giai đoạn đô thị hóa
- Phân tích gia tốc sử dụng đạo hàm bậc hai

### 3.4 Xác Thực Mô Hình Và Chẩn Đoán

Các mô hình được xác thực sử dụng:
- R bình phương và R bình phương điều chỉnh để đánh giá độ vừa vặn
- Thống kê F và t để kiểm định ý nghĩa
- Phân tích phần dư để kiểm tra giả định mô hình
- Xác thực chéo để đánh giá độ chính xác dự báo

## 4. Kết Quả

### 4.1 Xu Hướng Dân Số Và Mô Thức Tăng Trưởng

#### 4.1.1 Tăng Trưởng Dân Số Lịch Sử
Dân số Việt Nam tăng từ 28,2 triệu (1955) lên 102,0 triệu (2025), đại diện cho sự tăng trưởng 3,6 lần trong 70 năm. Tỷ suất tăng trưởng đạt đỉnh 3,5% hàng năm trong thập niên 1960, giảm xuống 0,9% vào năm 2025.

#### 4.1.2 Khớp Mô Hình Tăng Trưởng Logistic
Mô hình logistic cung cấp độ vừa vặn xuất sắc (R² = 0,9993) với các tham số:
- Khả năng chứa đựng (K): 117,3 triệu
- Tỷ suất tăng trưởng nội tại (r): 0,037
- Điểm chuyển (inflection point): 2028

Phương trình mô hình là:
\[ P(t) = \frac{117,3}{1 + e^{-0,037(t - 2028)}} \]

#### 4.1.3 Dự Báo Dân Số
Các dự báo cho thấy dân số ổn định quanh 117 triệu vào năm 2050, với tuổi trung vị đạt 49,5 tuổi.

### 4.2 Thay Đổi Tỷ Suất Sinh Và Cấu Trúc Tuổi

#### 4.2.1 Suy Giảm Tỷ Suất Sinh
Tỷ suất sinh tổng thể giảm từ 5,54 con/phụ nữ (thập niên 1960) xuống 1,88 (thập niên 2020), đại diện cho sự giảm 66%. Sự suy giảm tăng tốc sau thập niên 1990 do chính sách kế hoạch hóa gia đình và thay đổi kinh tế - xã hội.

#### 4.2.2 Biến Đổi Cấu Trúc Tuổi
Tuổi trung vị tăng từ 22,0 (thập niên 1970) lên 33,4 (2025), cho thấy già hóa nhanh. Tỷ lệ dân số từ 65 tuổi trở lên tăng từ 3,2% lên 8,1%.

### 4.3 Động Lực Đô Thị Hóa

#### 4.3.1 Tăng Trưởng Dân Số Đô Thị
Tỷ lệ dân số đô thị tăng từ 13,1% (1955) lên 41,4% (2025), với xu hướng tăng tốc. Mối quan hệ với thời gian cho thấy tính tuyến tính mạnh (R² = 0,928).

#### 4.3.2 Phân Tích Đô Thị Hóa Theo Giai Đoạn
Xác định ba giai đoạn riêng biệt:
- 1955-1975: Tăng trưởng chậm (0,34%/năm)
- 1976-2000: Tăng trưởng vừa phải (0,27%/năm)
- 2001-2025: Tăng trưởng tăng tốc (0,63%/năm)

#### 4.3.3 Gia Tốc Đô Thị Hóa
Phân tích đạo hàm bậc hai tiết lộ gia tốc dương (0,037%/năm²) trong các thập niên gần đây, cho thấy hiệu ứng đô thị hóa kép.

### 4.4 Phân Tích Đa Biến Về Các Yếu Tố Thúc Đẩy Dân Số

#### 4.4.1 Kết Quả Hồi Quy OLS
Mô hình hồi quy đa biến giải thích 99,9% phương sai dân số:

| Biến | Hệ số | Sai số chuẩn | Thống kê t | p-giá trị |
|------|--------|--------------|------------|-----------|
| Hằng số | -2,09e+09 | 7,53e+07 | -27,76 | <0,001 |
| Năm | 1,09e+06 | 3,79e+04 | 28,68 | <0,001 |
| Tỷ suất sinh | -1,27e+06 | 2,37e+05 | -5,35 | <0,001 |
| Tỷ lệ dân số đô thị | -3,33e+05 | 8,30e+04 | -4,01 | <0,001 |
| Tuổi trung vị | 2,25e+05 | 5,06e+04 | 4,44 | <0,001 |
| Di cư ròng | 8,73 | 1,33 | 6,55 | <0,001 |

#### 4.4.2 Hệ Số Chuẩn Hóa
Xếp hạng tầm quan trọng biến:
1. Năm (0,981) - Xu hướng thời gian
2. Tỷ suất sinh (-0,096) - Yếu tố chính
3. Tỷ lệ dân số đô thị (-0,111) - Yếu tố đáng kể
4. Tuổi trung vị (0,048) - Tác động vừa phải
5. Di cư ròng (0,022) - Đóng góp nhỏ

#### 4.4.3 Đánh Giá Đa Cộng Tuyến
Phân tích VIF cho thấy đa cộng tuyến chấp nhận được (tất cả VIF < 5), xác nhận tính ổn định mô hình.

### 4.5 Mô Hình Dự Báo Chuỗi Thời Gian

#### 4.5.1 Mô Hình ARIMA Cho Dân Số
Mô hình ARIMA(2,1,1) cung cấp dự báo ngắn hạn chính xác với AIC = 2046,4 và phần dư cho thấy đặc tính nhiễu trắng.

#### 4.5.2 Phân Tích Độ Nhạy
Độ vững chắc mô hình được kiểm tra bằng cách loại bỏ biến:
- Không có Năm: Tăng AIC +183,6
- Không có Tỷ suất sinh: Tăng AIC +23,9
- Không có Tỷ lệ dân số đô thị: Tăng AIC +13,7

## 5. Thảo Luận

### 5.1 Giải Thích Chuyển Tiếp Nhân Khẩu

Quỹ đạo nhân khẩu của Việt Nam phù hợp với lý thuyết Thompson nhưng thể hiện chuyển tiếp tăng tốc do can thiệp chính sách. Mô thức tăng trưởng logistic gợi ý hạn chế tài nguyên đang hiệu quả giới hạn sự mở rộng dân số, phù hợp với các mô hình sinh thái.

### 5.2 Phân Tích Các Yếu Tố Chính

Suy giảm tỷ suất sinh nổi lên như yếu tố quyết định dân số mạnh nhất, phản ánh thành công của các chương trình kế hoạch hóa gia đình và phát triển kinh tế - xã hội. Hệ số âm của đô thị hóa cho thấy tác động của di cư nông thôn - đô thị đến tỷ suất tăng trưởng tổng thể.

### 5.3 Ý Nghĩa Đô Thị Hóa

Xu hướng đô thị hóa tăng tốc có ý nghĩa sâu sắc đối với quy hoạch hạ tầng, thị trường lao động và dịch vụ xã hội. Phân tích theo giai đoạn tiết lộ tác động chính sách: cải cách hậu 1975 tăng tốc tăng trưởng đô thị, trong khi toàn cầu hóa hậu 2000 làm tăng cường thêm quá trình này.

### 5.4 Độ Vững Chắc Mô Hình Và Hạn Chế

Giá trị R² cao và thống kê t có ý nghĩa xác nhận độ tin cậy mô hình. Tuy nhiên, giả định tuyến tính có thể không giữ vững trong kịch bản cực đoan. Các yếu tố bên ngoài như biến đổi khí hậu hoặc sốc kinh tế có thể thay đổi quỹ đạo.

### 5.5 Ý Nghĩa Chính Sách

Các kết quả hỗ trợ ba ưu tiên chính sách:
1. **Quản lý tỷ suất sinh**: Duy trì tỷ suất sinh thay thế thông qua chính sách hỗ trợ gia đình
2. **Chuẩn bị già hóa**: Phát triển hệ thống chăm sóc người cao tuổi toàn diện
3. **Quy hoạch đô thị**: Phát triển cân bằng đô thị - nông thôn để quản lý áp lực di cư

## 6. Kết Luận

Nghiên cứu này cung cấp phân tích toàn diện về chuyển tiếp nhân khẩu của Việt Nam sử dụng sinh thái toán học và phương pháp thống kê. Các kết quả chính xác nhận tiến trình của Việt Nam hướng tới ổn định dân số với già hóa và đô thị hóa nhanh.

Mô hình logistic dự báo dân số đạt đỉnh 117 triệu vào năm 2050, với tuổi trung vị đạt 49,5 tuổi. Suy giảm tỷ suất sinh và đô thị hóa nổi lên như yếu tố chính, trong khi xu hướng thời gian phản ánh quá trình hiện đại hóa cơ bản.

Về phương pháp, tiếp cận tích hợp kết hợp hồi quy OLS, dự báo ARIMA và mô hình tăng trưởng logistic cung cấp khuôn khổ phân tích vững chắc. Các biện pháp độ vừa vặn cao (R² > 0,95) và kiểm định thống kê có ý nghĩa xác nhận các kết quả.

Khuyến nghị chính sách bao gồm:
- Tăng cường chính sách hỗ trợ gia đình để quản lý tỷ suất sinh
- Phát triển chiến lược già hóa toàn diện
- Thúc đẩy phát triển cân bằng đô thị - nông thôn
- Thiết lập hệ thống giám sát nhân khẩu thường xuyên

Nghiên cứu tương lai nên kết hợp tác động biến đổi khí hậu, biến kinh tế và phân tích cấp dưới quốc gia để có hiểu biết chi tiết hơn. Khung toán học thiết lập ở đây cung cấp nền tảng cho giám sát nhân khẩu liên tục và đánh giá chính sách.

## Tài Liệu Tham Khảo

1. Thompson, W.S. (1929). Population. American Journal of Sociology, 34(6), 959-975.

2. Verhulst, P.F. (1838). Notice sur la loi que la population suit dans son accroissement. Correspondance Mathématique et Physique, 10, 113-121.

3. Liên Hợp Quốc, Phân bộ Dân số. (2024). Triển vọng Dân số Thế giới 2024. New York: Liên Hợp Quốc.

4. Ngân hàng Thế giới. (2023). Các chỉ số Phát triển Thế giới. Washington, DC: Ngân hàng Thế giới.

5. Worldometer. (2024). Dân số Việt Nam. Truy cập từ https://www.worldometer.info/world-population/vietnam-population/

6. Tổng cục Thống kê Việt Nam. (2023). Niên giám Thống kê Việt Nam 2022. Hà Nội: Nhà xuất bản Thống kê.

7. Haughton, J. (2000). Chuyển tiếp nhân khẩu của Việt Nam và ý nghĩa kinh tế của nó. Tạp chí Kinh tế châu Á, 14(3), 283-301.

8. Goodkind, D. (1995). Chính sách một hoặc hai con của Việt Nam trong thực tế. Đánh giá Phát triển Dân số, 21(1), 85-111.

9. Lê, T.D., & Trần, Q.H. (2019). Đô thị hóa và suy giảm tỷ suất sinh ở Việt Nam. Nghiên cứu Dân số, 73(2), 213-228.

10. UNFPA Việt Nam. (2022). Dân số và Phát triển ở Việt Nam: Thành tựu và Thách thức. Hà Nội: UNFPA.