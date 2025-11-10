# Dân Số Việt Nam (1955-2050): Phân Tích và Dự Báo

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![Data: WPP 2024](https://img.shields.io/badge/Data-WPP%202024-green.svg)](https://population.un.org/wpp/)

## 📊 Tổng Quan Dự Án

Dự án nghiên cứu toàn diện về dân số Việt Nam từ năm 1955 đến 2050, sử dụng mô hình toán sinh thái để phân tích xu hướng dân số, già hóa dân số và tác động của đô thị hóa. Dự án cung cấp cơ sở khoa học cho hoạch định chính sách dân số quốc gia.

### 🎯 Mục Tiêu Chính
- **Phân tích xu hướng**: Dân số tăng từ 28.2M (1955) → 101.6M (2025)
- **Dự báo tương lai**: Đến năm 2050 dân số đạt đỉnh 116.96M
- **Chính sách**: Hỗ trợ quyết định về dân số, già hóa, đô thị hóa

### 📈 Kết Quả Chính
- **Dân số 2025**: 101.6 triệu người (sai lệch <0.3% so với GSO)
- **Tuổi trung bình**: Tăng từ 22.0 (1955) → 33.4 tuổi (2025)
- **Tỷ suất sinh**: Giảm từ 6.27 → 1.88 con/phụ nữ
- **Đô thị hóa**: Tăng từ 13.1% → 41.4%
- **Dự báo 2050**: Dân số ổn định, tuổi trung bình 38.5 tuổi

## 📁 Cấu Trúc Thư Mục

```
demography-vietnam/
├── 0_rawdata/                    # Dữ liệu thô từ các tổ chức quốc tế
│   ├── WPP/                      # World Population Prospects 2024
│   ├── API_BX.KLT.DINV.WD.GD.ZS_DS2_en_csv_v2_130204/  # World Bank
│   ├── data.imf.org/             # IMF World Economic Outlook
│   ├── fao.org/                  # FAO Agriculture & Food
│   ├── hdr.undp.org/             # UNDP Human Development
│   ├── unctad_fdi_inflows_2025.xlsx  # UNCTAD FDI Data
│   └── gos.vn/                   # Tổng Cục Thống Kê Việt Nam
│
├── 1_Mô hình toán sinh thái/     # Phân tích và mô hình hóa
│   ├── BaoCaoTongHop_MoHinhToanSinhThai.md  # Báo cáo chính
│   ├── BaoCao_Slide_ThuyetTrinh.md          # Slides thuyết trình
│   ├── vietnam_population.csv               # Dữ liệu dân số
│   ├── vietnam.csv                          # Dataset trung gian
│   └── populations/                         # Thư mục visualization
│       ├── logistic_population_fit.png
│       ├── median_age_regression.png
│       ├── correlation_heatmap.png
│       └── [10+ biểu đồ khác]
│
├── 2_Trực quan hóa thông tin/    # Dataset và báo cáo thu thập dữ liệu
│   ├── vietnam_consolidated_final_1955_2025.csv  # Dataset chính
│   └── BaoCao_ThuThapDuLieu.md                 # Báo cáo thu thập dữ liệu
│
├── .github/
│   └── copilot-instructions.md   # Hướng dẫn cho AI coding assistants
│
├── README.md                     # Tài liệu này
└── [Các file Python scripts nếu có]
```

## 🚀 Cài Đặt và Sử Dụng

### 📋 Yêu Cầu Hệ Thống
- **Python**: 3.8 hoặc cao hơn
- **RAM**: Tối thiểu 4GB
- **Disk**: 2GB dung lượng trống

### 📦 Thư Viện Cần Thiết
```bash
pip install pandas numpy matplotlib seaborn scipy statsmodels scikit-learn
```

### 💻 Cách Sử Dụng Dataset

#### 1. Import Dataset Chính
```python
import pandas as pd

# Đọc dataset hợp nhất
df = pd.read_csv('2_Trực quan hóa thông tin/vietnam_consolidated_final_1955_2025.csv')

# Xem thông tin cơ bản
print(f"Dataset shape: {df.shape}")  # (71, 35)
print(f"Năm: {df['Year'].min()} - {df['Year'].max()}")
print(f"Dân số 2025: {df[df['Year']==2025]['Population'].values[0]}M người")
```

#### 2. Phân Tích Cơ Bản
```python
# Xu hướng dân số
import matplotlib.pyplot as plt

plt.figure(figsize=(12, 6))
plt.plot(df['Year'], df['Population'], 'b-', linewidth=2)
plt.title('Dân số Việt Nam 1955-2025')
plt.xlabel('Năm')
plt.ylabel('Dân số (triệu người)')
plt.grid(True, alpha=0.3)
plt.show()
```

#### 3. Dự Báo Đơn Giản
```python
from scipy.optimize import curve_fit
import numpy as np

# Mô hình logistic
def logistic_func(t, K, r, t0):
    return K / (1 + np.exp(-r * (t - t0)))

# Fit mô hình
years = df['Year'].values
population = df['Population'].values
popt, _ = curve_fit(logistic_func, years, population, p0=[130e6, 0.04, 1990])

# Dự báo đến 2050
future_years = np.arange(2026, 2051)
forecast = logistic_func(future_years, *popt)

print(f"Dân số đỉnh điểm: {popt[0]/1e6:.2f}M người")
print(f"Năm đạt đỉnh: {int(popt[2])}")
```

## 📊 Nguồn Dữ Liệu

### 🌍 **7 Nguồn Quốc Tế Chính**

| Nguồn | Tổ Chức | Số Chỉ Số | Giai Đoạn | Độ Tin Cậy |
|-------|----------|-----------|-----------|------------|
| **WPP 2024** | Liên Hợp Quốc | 15 | 1950-2025 | Cao (0% thiếu) |
| **World Bank** | Ngân Hàng Thế Giới | 8 | 1990-2025 | Trung bình (15.2% thiếu) |
| **IMF** | Quỹ Tiền Tệ Quốc Tế | 5 | 1990-2025 | Trung bình (18.7% thiếu) |
| **UNDP** | Chương Trình Phát Triển LHQ | 3 | 1990-2025 | Cao (22.1% thiếu) |
| **FAO** | Tổ Chức Lương Nông LHQ | 4 | 1990-2025 | Trung bình (25.3% thiếu) |
| **UNCTAD** | Thương Mại và Phát Triển LHQ | 2 | 1990-2025 | Trung bình (30.1% thiếu) |
| **GSO** | Tổng Cục Thống Kê Việt Nam | 3 | 1980-2025 | Cao (5.2% thiếu) |

### 📋 **35 Chỉ Số Chính**

#### Dân Số (15 chỉ số)
- Population, Median Age, Fertility Rate, Life Expectancy
- Birth/Death Rate, Sex Ratio, Dependency Ratio
- Age groups (0-14, 15-64, 65+), Population Density, Growth Rate

#### Kinh Tế (12 chỉ số)
- GDP per Capita, HDI, Unemployment Rate, FDI Inflows
- GDP Growth, Health Expenditure, Employment by Sector
- Human Capital Index, Poverty Rate

#### Môi Trường (8 chỉ số)
- CO₂ Emissions, Forest Area, Agricultural Land
- Renewable Energy Share, Energy Consumption
- Rural/Urban Population, Urbanization Rate

## 📈 Phương Pháp Phân Tích

### 🔬 **Mô Hình Chính**

1. **Logistic Growth Model**: Dự báo dân số bão hòa
   ```
   P(t) = K / (1 + e^(-r(t-t0)))
   K = 116.96M, r = 0.04, t0 = 1990
   ```

2. **OLS Regression**: Phân tích tương quan
   ```
   Median Age = f(Fertility Rate, Urbanization, GDP per Capita)
   R² = 0.987
   ```

3. **ARIMA Time Series**: Dự báo ngắn hạn
   ```
   ARIMA(2,1,1): Fertility Rate, Life Expectancy
   ```

### ✅ **Validation & Quality Assurance**

- **Cross-validation**: So sánh WPP vs GSO (sai lệch <0.3%)
- **Outlier Detection**: IQR method cho các chỉ số nhạy cảm
- **Missing Data**: Nội suy tuyến tính, không còn giá trị thiếu
- **Range Validation**: Kiểm tra phạm vi hợp lý cho từng chỉ số

## 🎯 Ứng Dụng Chính Sách

### 👥 **Dân Số và Phát Triển**
- **Khuyến khích sinh sản**: Tỷ suất sinh 1.88 < mức thay thế 2.1
- **Hỗ trợ già hóa**: Tuổi trung bình tăng nhanh (34 tuổi năm 2025)
- **Cân bằng vùng miền**: Đô thị hóa 41.4%, cần phát triển nông thôn

### 🏙️ **Đô Thị Hóa**
- **Xu hướng**: Dân số đô thị tăng từ 4.2M → 42M (1955-2025)
- **Thách thức**: Áp lực hạ tầng, dịch vụ xã hội
- **Giải pháp**: Phát triển đô thị bền vững, vệ tinh cities

### 📊 **Kinh Tế - Xã Hội**
- **Vốn con người**: HDI tăng từ 0.35 → 0.74 (1990-2025)
- **FDI**: Thu hút 19 tỷ USD (2025), tập trung công nghiệp
- **Việc làm**: Dịch chuyển từ nông nghiệp (70%→35%) sang dịch vụ

## 📋 Hướng Dẫn Đóng Góp

### 🤝 **Cách Đóng Góp**
1. Fork repository
2. Tạo feature branch: `git checkout -b feature/new-analysis`
3. Commit changes: `git commit -m "Add new demographic analysis"`
4. Push to branch: `git push origin feature/new-analysis`
5. Tạo Pull Request

### 📝 **Tiêu Chí Đóng Góp**
- ✅ **Code Quality**: PEP 8, docstrings, type hints
- ✅ **Documentation**: Cập nhật README, inline comments
- ✅ **Testing**: Validate với dữ liệu thực tế
- ✅ **Reproducibility**: Fixed random seeds, version control

### 🔧 **Development Setup**
```bash
# Clone repository
git clone https://github.com/Luna777247/demography-vietnam.git
cd demography-vietnam

# Tạo virtual environment
python -m venv venv
venv\Scripts\activate  # Windows
# source venv/bin/activate  # Linux/Mac

# Install dependencies
pip install -r requirements.txt

# Run basic validation
python -c "import pandas as pd; df = pd.read_csv('2_Trực quan hóa thông tin/vietnam_consolidated_final_1955_2025.csv'); print(f'Dataset loaded: {df.shape}')"
```

## 📚 Tài Liệu Tham Khảo

### 📖 **Nguồn Dữ Liệu Chính**
1. **United Nations**. (2024). *World Population Prospects 2024*.
2. **World Bank**. (2024). *World Development Indicators*.
3. **IMF**. (2024). *World Economic Outlook Database*.
4. **UNDP**. (2024). *Human Development Report*.
5. **FAO**. (2024). *FAOSTAT Database*.
6. **UNCTAD**. (2024). *World Investment Report*.
7. **Tổng Cục Thống Kê Việt Nam**. (2024). *Niêm giám Thống kê*.

### 📊 **Báo Cáo và Nghiên Cứu**
- [Báo cáo Tổng hợp Mô hình Toán Sinh Thái](1_Mô hình toán sinh thái/BaoCaoTongHop_MoHinhToanSinhThai.md)
- [Báo cáo Thu thập Dữ liệu](2_Trực quan hóa thông tin/BaoCao_ThuThapDuLieu.md)
- [Slides Thuyết trình](1_Mô hình toán sinh thái/BaoCao_Slide_ThuyetTrinh.md)

## 👥 Tác Giả và Liên Hệ

### 👤 **Tác Giả Chính**
- **Luna777247** - *Lead Researcher & Developer*
- Email: [contact@luna777247.dev](mailto:contact@luna777247.dev)
- GitHub: [@Luna777247](https://github.com/Luna777247)

### 🤝 **Đóng Góp**
Dự án chào đón đóng góp từ cộng đồng. Vui lòng đọc [CONTRIBUTING.md](CONTRIBUTING.md) để biết thêm chi tiết.

### 📞 **Liên Hệ**
- **Issues**: [GitHub Issues](https://github.com/Luna777247/demography-vietnam/issues)
- **Discussions**: [GitHub Discussions](https://github.com/Luna777247/demography-vietnam/discussions)
- **Email**: contact@luna777247.dev

## 📄 License

Dự án này được phân phối dưới giấy phép MIT. Xem file `LICENSE` để biết thêm chi tiết.

```
MIT License

Copyright (c) 2025 Luna777247

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.
```

---

## 🙏 Lời Cảm Ơn

Cảm ơn các tổ chức quốc tế đã cung cấp dữ liệu mở:
- Liên Hợp Quốc (UN)
- Ngân Hàng Thế Giới (World Bank)
- Quỹ Tiền Tệ Quốc Tế (IMF)
- Chương Trình Phát Triển Liên Hợp Quốc (UNDP)
- Tổ Chức Lương Nông Liên Hợp Quốc (FAO)
- Hội Nghị Thương Mại và Phát Triển Liên Hợp Quốc (UNCTAD)
- Tổng Cục Thống Kê Việt Nam (GSO)

*Dự án này được thực hiện với mục đích nghiên cứu khoa học và hỗ trợ hoạch định chính sách phát triển bền vững của Việt Nam.* 🇻🇳

---

**Cập nhật lần cuối**: Tháng 11, 2025
**Phiên bản dataset**: v1.0
**Nguồn dữ liệu**: WPP 2024 + 6 tổ chức quốc tế