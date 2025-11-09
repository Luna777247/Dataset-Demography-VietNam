\documentclass[11pt]{beamer}
\usetheme{Madrid}
\usefonttheme{serif}

\usepackage[utf8]{inputenc}
\usepackage[vietnamese]{babel}
\usepackage[T1]{fontenc}

\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
\usepackage{graphicx}
\usepackage{booktabs}

\DeclareMathOperator{\sinv}{\sin}
\DeclareMathOperator{\tgv}{\tan}

\setbeamertemplate{caption}[numbered]

\author[Nguyễn Ngọc Ánh]{Nguyễn Ngọc Ánh}
\title{Phân tích và dự báo dân số Việt Nam(1955-2025)}
% Nhập email liên hệ của bạn vào dòng dưới đây
\newcommand{\email}{nguyenanhilu9785@gmail.com}
%\setbeamercovered{transparent} 
\setbeamertemplate{navigation symbols}{} 
%\logo{} 
\institute[]{TRƯỜNG ĐẠI HỌC KHOA HỌC TỰ NHIÊN \\ HỌC PHẦN: MÔ HÌNH TOÁN SINH THÁI} 
\date{\today} 

\bibliographystyle{apalike}

% Hiển thị lại Mục lục ở đầu mỗi Section
\AtBeginSection[]
{
  \begin{frame}{Mục lục}
    \tableofcontents[currentsection, hideothersubsections]
  \end{frame}
}

% Hiển thị lại Mục lục ở đầu mỗi Subsection
\AtBeginSubsection[]
{
  \begin{frame}{Mục lục}
    \tableofcontents[currentsection, currentsubsection]
  \end{frame}
}

\begin{document}

\begin{frame}
\titlepage
\end{frame}

\begin{frame}{Mục lục}
\tableofcontents 
\end{frame}

\section{Giới thiệu}
\begin{frame}{Tại sao nghiên cứu dân số Việt Nam?}
    \centering
    \textbf{\LARGE Dân số là nền tảng cho phát triển bền vững}
    
    \vspace{0.8cm}
    
    \begin{block}{Bối cảnh đặc biệt}
        \begin{itemize}
            \item Việt Nam đang trải qua \textbf{chuyển dịch dân số nhanh}
            \item Tác động sâu rộng đến: \textbf{Kinh tế - Xã hội - Môi trường}
        \end{itemize}
    \end{block}

    \vspace{0.8cm}
    
    \begin{exampleblock}{Mục tiêu chính}
        \centering
        \textbf{Phân tích xu hướng \& Dự báo tương lai dân số}
    \end{exampleblock}

    \vspace{0.3cm}
    \tiny{\textit{Dữ liệu từ 1955 đến 2025 - Phân tích như một hệ sinh thái}}
\end{frame}

\begin{frame}{Quy mô và Cách tiếp cận nghiên cứu}
    \begin{columns}[T]
        \begin{column}{0.48\textwidth}
            \begin{block}{Phạm vi nghiên cứu}
                \textbf{Thời gian:}
                \begin{itemize}
                    \item 1955-2025: Phân tích
                    \item 2026-2050: Dự báo
                \end{itemize}
                
                \textbf{Không gian:}
                \begin{itemize}
                    \item Toàn lãnh thổ Việt Nam
                \end{itemize}
            \end{block}
        \end{column}
        
        \begin{column}{0.48\textwidth}
            \begin{block}{Công cụ phân tích}
                \textbf{Mô hình toán học:}
                \begin{itemize}
                    \item Hồi quy tuyến tính
                    \item Hồi quy Logistic  
                    \item ARIMA
                \end{itemize}
                
                \textbf{Góc nhìn:}
                \begin{itemize}
                    \item Hệ sinh thái dân số
                \end{itemize}
            \end{block}
        \end{column}
    \end{columns}

    \vspace{0.5cm}
    \centering
    \begin{alertblock}{Triết lý nghiên cứu}
        \centering
        Hiểu quá khứ → Dự đoán tương lai → Đề xuất chính sách
    \end{alertblock}
\end{frame}

\begin{frame}{5 Câu hỏi nghiên cứu then chốt}
    \centering
    \begin{enumerate}
        \vspace{0.3cm}
        \item \textbf{Tốc độ già hóa dân số ra sao?} \\
              \small{\textit{Và tác động thế nào?}}
        
        \vspace{0.5cm}
        
        \item \textbf{Đô thị hóa thay đổi phân bố dân cư?} \\
              \small{\textit{Theo xu hướng nào?}}
        
        \vspace{0.5cm}
        \item \textbf{Yếu tố nào ảnh hưởng mạnh nhất?} \\
              \small{\textit{Kinh tế, xã hội hay chính sách?}}
        
        \vspace{0.5cm}

        \item \textbf{Khi nào dân số Việt Nam đạt đỉnh?} \\
              \small{\textit{Và ở mức bao nhiêu?}}
        
        \vspace{0.5cm}
        \item \textbf{Hàm ý chính sách ưu tiên?} \\
        \small{\textit{Giải pháp cho tương lai}}
    \end{enumerate}
\end{frame}

\section{Cơ Sở Lý Luận và Tổng Quan}
\begin{frame}{Cơ Sở Lý Luận và Tổng Quan}
\begin{itemize}
\item \textbf{Đề tài:} Phân tích và dự báo dân số Việt Nam (1955-2050) do chuyển tiếp nhân khẩu học nhanh.
\item \textbf{Lý thuyết chính:} Lý thuyết Chuyển tiếp Nhân khẩu học (Warren Thompson, 1929) và Mô hình Toán Sinh thái (Logistic growth, Verhulst, 1838).
\item \textbf{Mục tiêu:} Cung cấp cái nhìn toàn diện về xu hướng dân số, hỗ trợ chính sách.
\end{itemize}
\end{frame}

\begin{frame}{Lý Thuyết Chuyển Tiếp Nhân Khẩu Học}
\begin{itemize}
\item \textbf{Định nghĩa:} Lý thuyết mô tả quá trình chuyển đổi từ dân số nông nghiệp (tỷ suất sinh và tử cao, tăng trưởng chậm) sang dân số công nghiệp (tỷ suất sinh và tử thấp, tăng trưởng chậm).
\item \textbf{Giai đoạn:} 4 giai đoạn: Tiền chuyển tiếp (cao sinh, cao tử), Chuyển tiếp sớm (giảm tử, tăng dân số), Chuyển tiếp muộn (giảm sinh), Sau chuyển tiếp (thấp sinh, thấp tử).
\item \textbf{Ứng dụng cho Việt Nam:} Việt Nam đang ở giai đoạn chuyển tiếp muộn, với giảm sinh nhanh và già hóa dân số.
\item \textbf{Tác giả:} Warren Thompson (1929), phát triển từ quan sát châu Âu.
\end{itemize}
\end{frame}

\begin{frame}{Mô Hình Toán Sinh Thái (Logistic Growth)}
\begin{itemize}
\item \textbf{Công thức:} $\frac{dP}{dt} = rP(1 - \frac{P}{K})$, trong đó P là dân số, r là tốc độ tăng trưởng, K là dung lượng mang tải.
\item \textbf{Ý nghĩa:} Dân số tăng theo cấp số nhân ban đầu, sau đó chậm lại khi gần đạt giới hạn K.
\item \textbf{Ứng dụng:} Dự báo dân số Việt Nam đạt đỉnh khoảng 117 triệu vào 2050.
\item \textbf{Tác giả:} Pierre-François Verhulst (1838), mở rộng từ Malthus.
\end{itemize}
\end{frame}

\section{Phương pháp nghiên cứu}
\begin{frame}{Phương Pháp}
\begin{itemize}
\item \textbf{Phương pháp:} Kết hợp phân tích thống kê (OLS, tương quan) và mô hình toán học (Logistic, ARIMA).
\item \textbf{Quy trình:} Thu thập dữ liệu $\rightarrow$ Xử lý thiếu sót $\rightarrow$ Phát hiện ngoại lệ $\rightarrow$ Phân tích $\rightarrow$ Mô hình hóa $\rightarrow$ Dự báo $\rightarrow$ Trực quan hóa.
\item \textbf{Lý do chọn:} Độ chính xác cao, phù hợp dân số học.
\end{itemize}
\end{frame}

\begin{frame}{Chi Tiết Phương Pháp Phân Tích Thống Kê}
\begin{itemize}
\item \textbf{OLS Regression:} Phương pháp bình phương tối thiểu để mô hình hóa mối quan hệ tuyến tính giữa dân số và các yếu tố ảnh hưởng (Fertility Rate, Urban Pop \%, Median Age, Migrants).  
  Công thức: $y = \beta_0 + \beta_1 x_1 + \beta_2 x_2 + \dots + \epsilon$, với $y$ là dân số, $x_i$ là các biến độc lập, $\beta_i$ là hệ số hồi quy, $\epsilon$ là sai số.
\item \textbf{Correlation Analysis:} Tính hệ số tương quan Pearson để xác định mối liên hệ giữa các biến (ví dụ: tương quan âm giữa Fertility Rate và Median Age).  
  Công thức: $r = \frac{\sum ((x_i - \bar{x})(y_i - \bar{y}))}{\sqrt{\sum (x_i - \bar{x})^2 \sum (y_i - \bar{y})^2}}$, với $r$ từ -1 đến 1.
\item \textbf{Outlier Detection:} Sử dụng sai phân bậc 1 và IQR để phát hiện giá trị bất thường, đảm bảo độ tin cậy của mô hình.  
  Công thức: IQR = Q3 - Q1, Outlier nếu giá trị < Q1 - 1.5$\times$IQR hoặc > Q3 + 1.5$\times$IQR.
\item \textbf{Ưu điểm:} Đơn giản, dễ diễn giải, phù hợp cho dữ liệu dân số.
\end{itemize}
\end{frame}

\begin{frame}{Chi Tiết Phương Pháp Mô Hình Hóa}
\begin{itemize}
\item \textbf{Logistic Growth Model:} $\frac{dP}{dt} = rP(1 - \frac{P}{K})$, với P là dân số, r là tốc độ tăng trưởng, K là dung lượng mang tải. Sử dụng curve\_fit để ước lượng tham số.  
  Giải tích: $P(t) = \frac{K}{1 + \left(\frac{K}{P_0} - 1\right)e^{-rt}}$, với $P_0$ là dân số ban đầu.
\item \textbf{ARIMA Model:} Mô hình thời gian cho dự báo, bao gồm thành phần tự hồi quy (AR), tích phân (I), và trung bình động (MA). Tự động chọn tham số bằng AIC.  
  Công thức: ARIMA(p,d,q), với AR: $y_t = c + \phi_1 y_{t-1} + \dots + \phi_p y_{t-p} + \epsilon_t$, MA: $y_t = c + \epsilon_t + \theta_1 \epsilon_{t-1} + \dots + \theta_q \epsilon_{t-q}$, I: d lần sai phân.  
  AIC: $AIC = 2k - 2 \ln(L)$, với k là số tham số, L là likelihood.
\item \textbf{Model Comparison:} So sánh AIC, BIC, R$^2$ để chọn mô hình tốt nhất (Logistic có AIC thấp nhất).  
  AIC: $AIC = 2k - 2 \ln(L)$, BIC: $BIC = k \ln(n) - 2 \ln(L)$, R$^2$: $R^2 = 1 - \frac{SS_{res}}{SS_{tot}}$, với k số tham số, n số quan sát, L likelihood, SS phần dư và tổng.
\item \textbf{Ưu điểm:} Logistic phù hợp cho dân số đạt đỉnh, ARIMA tốt cho xu hướng ngắn hạn.
\end{itemize}
\end{frame}

\section{Quá Trình Thu Thập Và Hoàn Thiện Dữ Liệu}

\begin{frame}{Nguồn Dữ Liệu Tin Cậy}
\begin{itemize}
\item \textbf{Nguồn:} Worldometer, World Bank, UN.
\item \textbf{Xử lý:} Nội suy tuyến tính cho giá trị thiếu, cập nhật tính toán.
\item \textbf{Kết quả:} Bộ dữ liệu hoàn chỉnh, 0 giá trị thiếu.
\end{itemize}
\end{frame}
\begin{frame}{Bảng Giá Trị Thiếu Trong Dữ Liệu}
\scriptsize
\textbf{Chú thích:} Bảng này cho thấy tất cả các cột đều có 0 giá trị thiếu sau xử lý, đảm bảo tính toàn vẹn của dữ liệu. Tổng 71 giá trị cho mỗi cột từ 1955-2025.
\begin{table}
\centering
\begin{tabular}{lccc}
\toprule
Cột & Giá trị thiếu & Tổng giá trị & Tỷ lệ thiếu (\%) \\
\midrule
Population & 0 & 71 & 0.0 \\
Yearly \% Change & 0 & 71 & 0.0 \\
Yearly Change & 0 & 71 & 0.0 \\
Migrants (net) & 0 & 71 & 0.0 \\
Median Age & 0 & 71 & 0.0 \\
Fertility Rate & 0 & 71 & 0.0 \\
Density (P/Km²) & 0 & 71 & 0.0 \\
Urban Pop \% & 0 & 71 & 0.0 \\
Urban Population & 0 & 71 & 0.0 \\
Country's Share of World Pop & 0 & 71 & 0.0 \\
World Population & 0 & 71 & 0.0 \\
Vietnam Global Rank & 0 & 71 & 0.0 \\
\bottomrule
\end{tabular}
\end{table}
\end{frame}

\begin{frame}{Xu Hướng Các Chỉ Số Chính Qua Thời Gian}
\scriptsize
\textbf{Chú thích:} Biểu đồ này minh họa sự thay đổi của dân số, tuổi trung vị và tỷ suất sinh từ 1955-2025, cho thấy xu hướng tăng dân số và già hóa.

\begin{figure}
\centering
\includegraphics[width=0.5\textwidth]{populations/data_collection_trends.png}
\caption{Xu hướng các chỉ số chính qua thời gian (1955-2025): Dân số, Tuổi trung vị, và Tỷ suất sinh}
\end{figure}
\end{frame}

\begin{frame}{Boxplots Của Sai Phân Bậc 1}
\scriptsize
\textbf{Chú thích:} Boxplots hiển thị phân phối sai phân bậc 1 cho các cột có ngoại lệ, giúp xác định giá trị bất thường và quyết định xử lý.

\begin{figure}
\centering
\includegraphics[width=0.6\textwidth]{populations/outlier_boxplots.png}
\caption{Boxplots của sai phân bậc 1 cho các cột chính có ngoại lệ: Yearly \% Change, Yearly Change, Migrants (net), Median Age}
\end{figure}
\end{frame}

\begin{frame}{Kiểm Tra Và Xử Lý Ngoại Lệ}
\scriptsize
\textbf{Phương pháp:} Sai phân bậc 1 + IQR.

\textbf{Chú thích:} Bảng liệt kê số lượng ngoại lệ và năm xảy ra cho từng cột. Ngoại lệ chủ yếu ở giai đoạn đầu (1950s-1960s) và gần đây (2000s), phản ánh biến động lịch sử và kinh tế.

\begin{table}
\centering
\begin{tabular}{lcl}
\toprule
Cột & Số ngoại lệ & Năm ngoại lệ \\
\midrule
Yearly \% Change & 8 & 1960, 1961, 1976, 1979, 2006, 2007, 2009, 2010 \\
Yearly Change & 6 & 1960, 1979, 2006, 2007, 2009, 2010 \\
Migrants (net) & 8 & 2006, 2007, 2008, 2009, 2010, 2021, 2022, 2024 \\
Median Age & 8 & 1956, 1958, 1960, 1961, 1962, 1963, 1964, 1965 \\
Fertility Rate & 5 & 1956, 1957, 1958, 1959, 1960 \\
Urban Population & 1 & 1980 \\
World Population & 2 & 1960, 1961 \\
Vietnam Global Rank & 8 & 1958, 1978, 1981, 1983, 1985, 1998, 2003, 2021 \\
\bottomrule
\end{tabular}
\end{table}

\textbf{Kết quả:} 95\% ngoại lệ hợp lý, sửa Urban Population.

\end{frame}

\begin{frame}{Bảng Dân Số Theo Giai Đoạn}
\textbf{Chú thích:} Bảng chia dân số thành các giai đoạn lịch sử, cho thấy sự tăng trưởng nhanh từ 1980s và già hóa từ 2000s.

\begin{table}
\centering
\begin{tabular}{lccc}
\toprule
Giai Đoạn & Population (triệu) & Median Age & Fertility Rate \\
\midrule
1955-1980 & 40.5 & 20.2 & 5.1 \\
1981-2000 & 68.3 & 24.8 & 3.2 \\
2001-2025 & 92.1 & 31.5 & 2.0 \\
\bottomrule
\end{tabular}
\end{table}
\end{frame}

\begin{frame}{Scatter Plot: Median Age vs Fertility Rate}
\textbf{Chú thích:} Scatter plot cho thấy mối quan hệ nghịch giữa tuổi trung vị và tỷ suất sinh, xác nhận già hóa do giảm sinh.

\begin{figure}
\centering
\includegraphics[width=0.5\textwidth]{populations/scatter_median_age_fertility.png}
\caption{Scatter Plot: Median Age vs Fertility Rate}
\end{figure}
\end{frame}

\begin{frame}{Bar Chart: Yearly \% Change Over Years}
\textbf{Chú thích:} Biểu đồ cột hiển thị tỷ lệ tăng dân số hàng năm, cho thấy biến động qua các giai đoạn lịch sử.

\begin{figure}
\centering
\includegraphics[width=0.5\textwidth]{populations/bar_yearly_change.png}
\caption{Bar Chart: Yearly \% Change Over Years}
\end{figure}

Giảm vì tỷ suất sinh giảm, → số người sinh ra giảm.

\textbf{Giải thích năm 2006-2007:} Tăng bất ngờ do tăng trưởng kinh tế cao (gia nhập WTO 2007), di cư và nhập cư tăng. Sau đó giảm mạnh năm 2009-2010 do Khủng hoảng tài chính toàn cầu 2008-2009 ảnh hưởng đến kinh tế và di cư.
\end{frame}

\section{Phân Tích Xu Hướng Chính}
\begin{frame}{Phân Tích Xu Hướng Chính - Tốc Độ Già Hóa}
Median Age tăng từ 22 (1955) lên 33.4 (2025), tốc độ 0.201 tuổi/năm.

\textbf{Công thức tính tốc độ già hóa:}
Mô hình hồi quy tuyến tính: \( \text{Median Age} = \beta_0 + \beta_1 \cdot \text{Year} \)
- \( \beta_0 = -378.041 \) (hệ số chặn)
- \( \beta_1 = 0.201 \) tuổi/năm (tốc độ già hóa)
- \( R^2 = 0.728 \) (mô hình giải thích 72.8\% biến động)

\textbf{Gia tốc già hóa:}
- 1980-2000: +0.016 tuổi/năm²
- 2000-2025: +0.009 tuổi/năm²

\textbf{Chú thích:} Bảng cho thấy tốc độ già hóa tăng dần qua các giai đoạn, với R$^2$ cao ở giai đoạn gần đây, phản ánh xu hướng gia tăng nhanh.

\begin{table}
\centering
\begin{tabular}{lcc}
\toprule
Giai Đoạn & Tốc Độ Già Hóa (tuổi/năm) & R$^2$ \\
\midrule
1955-1980 & -0.154 & 0.598 \\
1981-2000 & 0.208 & 0.924 \\
2001-2025 & 0.419 & 0.998 \\
\bottomrule
\end{tabular}
\end{table}


\end{frame}

\begin{frame}{Biểu đồ phân tán Độ tuổi trung vị và Năm}
{\scriptsize
\textbf{Chú thích:} Biểu đồ phân tán giữa \textit{Median Age} và \textit{Year} với đường hồi quy tuyến tính 
(vùng tô màu thể hiện khoảng tin cậy 95\%) cho thấy dân số Việt Nam có xu hướng \textbf{già hóa rõ rệt} 
kể từ thập niên 1980. Giá trị hệ số xác định $R^2 = 0.85$ cho thấy mô hình tuyến tính giải thích được khoảng 
85\% biến động của tuổi trung vị theo thời gian, theo công thức:
\[
R^2 = 1 - \frac{SS_{res}}{SS_{tot}} 
= 1 - \frac{\sum (y_i - \hat{y}_i)^2}{\sum (y_i - \bar{y})^2}.
\]
}

\begin{figure}
\centering
\includegraphics[width=0.5\textwidth]{populations/median_age_regression.png}
\scriptsize
\caption{Biểu đồ phân tán Độ tuổi trung vị và Năm với đường hồi quy tuyến tính, R$^2$=0.85}
\end{figure}
\end{frame}

\begin{frame}{Phân Tích Xu Hướng Chính - Tác Động Đô Thị Hóa}
Urban Pop \% tăng, Density tăng 9.28 người/km² mỗi 1\% đô thị hóa (R$^2$=0.916).

\textbf{Chú thích:} Scatter plot với đường OLS cho thấy mối quan hệ dương giữa mật độ dân số và tỷ lệ đô thị hóa, với R$^2$=0.916.

\begin{figure}
\centering
\includegraphics[width=0.5\textwidth]{populations/density_urban_ols.png}
\caption{Scatter plot Density vs Urban Pop \% với đường hồi quy OLS, R$^2$=0.916}
\end{figure}
\end{frame}


\begin{frame}{Yếu Tố Ảnh Hưởng Mạnh Nhất}
Fertility Rate ảnh hưởng âm mạnh nhất (-1.268e+06), R$^2$$\approx$1.000.

\textbf{Chú thích:} Scatter plots cho thấy mối quan hệ giữa các biến độc lập (Fertility Rate, Median Age, Urban Pop \%, Migrants) và dân số, xác nhận Fertility Rate có ảnh hưởng âm mạnh nhất.

\begin{figure}
\centering
\includegraphics[width=0.5\textwidth]{populations/scatter_factors_population.png}
\caption{Scatter Plots: Key Variables vs Population}
\end{figure}
\end{frame}

\begin{frame}{Bảng OLS Regression Results}
\textbf{Chú thích:} Bảng kết quả hồi quy OLS cho thấy hệ số của từng biến, với Fertility Rate có ảnh hưởng âm mạnh nhất. Tất cả biến đều có ý nghĩa thống kê (p<0.05).

\begin{table}
\centering
\resizebox{\textwidth}{!}{
\begin{tabular}{lccc}
\toprule
Biến & Hệ số (coef) & Sai số chuẩn & p-value \\
\midrule
const & -1.268e+09 & 1.27e+08 & 0.000 \\
Year & 6.406e+05 & 6.41e+04 & 0.000 \\
Fertility Rate & -1.268e+06 & 1.27e+05 & 0.000 \\
Migrants (net) & 8.730 & 0.876 & 0.000 \\
Median Age & 2.246e+05 & 2.25e+04 & 0.000 \\
Urban Pop \% & -3.327e+05 & 3.33e+04 & 0.000 \\
\bottomrule
\end{tabular}
}
\end{table}
\end{frame}

\begin{frame}{Variance Inflation Factor (VIF)}
\textbf{Giải thích về đa cộng tuyến:} Đa cộng tuyến xảy ra khi các biến độc lập có tương quan cao với nhau, dẫn đến ước lượng hệ số hồi quy không ổn định và khó diễn giải. Variance Inflation Factor (VIF) đo lường mức độ đa cộng tuyến; VIF > 10 cho thấy đa cộng tuyến nghiêm trọng, VIF > 100 cực kỳ cao. Trong mô hình này, Fertility Rate (VIF=132.55) và Median Age (VIF=103.56) có đa cộng tuyến cao do mối quan hệ nghịch đảo giữa chúng trong chuyển tiếp nhân khẩu học.

\end{frame}

\begin{frame}{Residual Analysis}
\textbf{Chú thích:} Biểu đồ phân tích phần dư cho thấy mô hình OLS phù hợp, với phần dư phân phối chuẩn và không có mẫu tự tương quan rõ rệt.

% Thay bằng biểu đồđồ phân phối phần dữ xem có chuẩn hay không
\begin{figure}
\centering
\includegraphics[width=0.5\textwidth]{populations/ols_residual_analysis.png}
\caption{Residual Analysis: Residuals vs Fitted và Q-Q Plot}
\end{figure}
\end{frame}

\begin{frame}{Scatter Plots: Key Variables vs Population}
\textbf{Chú thích:} Scatter plots cho thấy mối quan hệ giữa các biến độc lập và dân số, hỗ trợ kết quả hồi quy.

\begin{figure}
\centering
\includegraphics[width=0.5\textwidth]{populations/scatter_factors_population.png}
\caption{Scatter Plots: Key Variables vs Population}
\end{figure}
\end{frame}

\section{Tổng Quan Về Dữ Liệu Dân Số}
\begin{frame}{Tổng Quan Về Dữ Liệu Dân Số}
Dữ liệu cho thấy dân số tăng từ 28.17 triệu (1955) lên 101.60 triệu (2025), hệ số tăng trưởng 3.61 lần. Tăng trưởng trung bình hàng năm 1.87\%, nhưng giảm dần từ 3.09\% (1955) xuống 0.60\% (2025).

\textbf{Thống kê mô tả:}

Trung bình: \( \mu = \frac{1}{n} \sum x_i \); Độ lệch chuẩn: \( \sigma = \sqrt{\frac{1}{n} \sum (x_i - \mu)^2} \).

\begin{table}
\centering
\begin{tabular}{lccc}
\toprule
Giai Đoạn & Mean Population (triệu) & Median Age & Fertility Rate \\
\midrule
1955-1980 & 39.6 & 18.6 & 5.8 \\
1981-2000 & 66.0 & 20.0 & 3.4 \\
2001-2025 & 90.3 & 28.3 & 2.0 \\
\bottomrule
\end{tabular}
\end{table}
\end{frame}

\begin{frame}{Xu Hướng Dân Số Theo Thời Gian}
\textbf{Xu hướng:}
- Tăng trưởng theo thập kỷ giảm từ 2.92\% (1950s) xuống 0.71\% (2020s).
- Fertility Rate giảm mạnh, tương quan dương 0.90 với tăng trưởng dân số.
- Median Age tăng, tương quan âm -0.80 với tăng trưởng.
- Urban Pop \% tăng từ 13.1\% lên 41.4\%, dân số đô thị từ 3.69 lên 42.06 triệu.
- Migrants (net) trung bình -56.740 người/năm, âm mạnh ở 1970s-2000s.

Hệ số tương quan Pearson: \( r = \frac{\sum (x_i - \bar{x})(y_i - \bar{y})}{\sqrt{\sum (x_i - \bar{x})^2} \sqrt{\sum (y_i - \bar{y})^2}} \), với r > 0.9 cho tương quan mạnh.

\begin{figure}
\centering
\includegraphics[width=0.5\textwidth]{populations/time_series_trends.png}
\caption{Time Series Trends: Population, Median Age, Fertility Rate}
\end{figure}
\end{frame}

\begin{frame}{Mối Quan Hệ Giữa Các Biến Chính}
\begin{figure}
\centering
\includegraphics[width=0.5\textwidth]{populations/correlation_heatmap.png}
\caption{Correlation Heatmap of Key Variables}
\end{figure}

\begin{figure}
\centering
\includegraphics[width=0.5\textwidth]{populations/boxplots_distributions.png}
\caption{Boxplots of Key Distributions}
\end{figure}
\end{frame}

\begin{frame}{Phân Phối Tần Suất Các Chỉ Số}
\begin{figure}
\centering
\includegraphics[width=0.5\textwidth]{populations/histograms_key_variables.png}
\caption{Histograms of Key Variables: Population, Median Age, Fertility Rate}
\end{figure}

\begin{figure}
\centering
\includegraphics[width=0.5\textwidth]{populations/scatter_median_age_fertility.png}
\caption{Scatter Plot: Median Age vs Fertility Rate}
\end{figure}
\end{frame}

\begin{frame}{Biến Động Tăng Trưởng Hàng Năm}
\begin{figure}
\centering
\includegraphics[width=0.5\textwidth]{populations/bar_yearly_change.png}
\caption{Bar Chart: Yearly \% Change Over Years}
\end{figure}

Giảm vì tỷ suất sinh giảm, → số người sinh ra giảm.
Thêm giải thích năm 2005 tại sao đang giảm mà tăng lên???
\end{frame}


\section{Dự Báo Dân Số Đến Năm 2050}

\begin{frame}{Dự Báo Dân Số Đến Năm 2050}
Dân số đạt đỉnh 117 triệu (2050), Median Age $\sim$49.5.

Mô hình logistic tốt nhất (AIC=133.06).

\textbf{Chú thích:} Bảng so sánh AIC, BIC và R$^2$ của các mô hình, với Logistic có AIC thấp nhất và R$^2$ cao nhất, phù hợp nhất cho dự báo dân số.

\begin{table}
\centering
\begin{tabular}{lccc}
\toprule
Mô hình & AIC & BIC & R$^2$ \\
\midrule
Linear & 211.49 & 216.01 & 0.9979 \\
Logistic & 133.06 & 139.85 & 0.9993 \\
ARIMA & 327.82 & 332.32 & 0.9881 \\
\bottomrule
\end{tabular}
\end{table}
\end{frame}

\begin{frame}{Đồ Thị Logistic Fit}
\textbf{Chú thích:} Biểu đồ logistic fit cho dân số từ 1955-2025 với dự báo đến 2050, cho thấy mô hình phù hợp tốt với dữ liệu thực tế.

\begin{figure}
\centering
\includegraphics[width=0.5\textwidth]{populations/logistic_population_fit.png}
\caption{Đồ thị logistic fit cho Population từ 1955-2025, với dự báo đến 2050, R$^2$=0.98}
\end{figure}
\end{frame}

\begin{frame}{Sensitivity Analysis}
\textbf{Chú thích:} Phân tích độ nhạy với các bộ tham số khác nhau cho thấy mô hình logistic có xu hướng tăng khớp với xu hướng thưacj ở Việt ổn định với các tham số khác nhau.

\begin{figure}
\centering
\includegraphics[width=0.5\textwidth]{populations/sensitivity_logistic.png}
\caption{Sensitivity Analysis: Logistic Model Variations}
\end{figure}
\end{frame}

% \begin{frame}{Model Comparison Forecasts}
% \textbf{Chú thích:} So sánh dự báo của các mô hình, logistic dự báo đỉnh dân số sớm nhất.

% \begin{figure}
% \centering
% \includegraphics[width=0.5\textwidth]{populations/model_comparison_forecasts.png}
% \caption{Model Comparison: Population Forecasts to 2050}
% \end{figure}
% \end{frame}

\begin{frame}{Population Forecast with Confidence Intervals}
\small{
\textbf{Chú thích:} Dự báo với khoảng tin cậy cho thấy dân số đạt đỉnh khoảng 117 triệu vào 2050.}
\scriptsize
\begin{figure}
\centering
\includegraphics[width=0.5\textwidth]{populations/forecast_with_ci.png}
\caption{Population Forecast to 2050 with Confidence Intervals}
\end{figure}
\end{frame}

\begin{frame}{Dự Báo Già Hóa Dân Số}
\textbf{Median Age đến 2050:}
- Mô hình tuyến tính: 43.9 năm
- Mô hình logistic: 49.5 năm

Công thức tuyến tính: \( Age(t) = 0.234 \cdot t - 460.67 \)

\textbf{Cấu trúc dân số 2050:}
- 60+: 29.26 triệu người (25.0\% tổng dân số)
- 65+: 24.57 triệu người (21.0\% tổng dân số)

\textbf{Công thức tính tỷ lệ già:}
\( \text{Tỷ lệ 60+} = \frac{P_{60+}}{P_{total}} \times 100\% \), với P từ mô hình logistic
\end{frame}

\begin{frame}{Kim Tự Tháp Dân Số 2050}
\textbf{Kim tự tháp dân số 2050:}
- Dưới 15 tuổi: 18.5\% (21.67M)
- 15-64 tuổi: 56.5\% (66.13M)
- 65+ tuổi: 25.0\% (29.26M)
- Tổng: 100\% (117.02M)

\textbf{Chỉ số già hóa:}
- Aging Index = (65+/15-) × 100 = (29.26/21.67) × 100 = 135.0
- Median Age = 49.5 năm (tăng từ 33.4 năm 2025)
- Dependency Ratio = ((15- + 65+)/15-64) × 100 = 70.5\%
\end{frame}

\begin{frame}{Nhận Xét Chuyên Sâu Về Mô Hình}
\textbf{1. Ưu thế mô hình Logistic:}
- Sinh học thực tế: Dân số không tăng vô hạn
- Phù hợp chuyển tiếp nhân khẩu học
- R² cao nhất (0.9993), AIC thấp nhất (133.06)

\textbf{2. So sánh với mô hình khác:}
- Tuyến tính: Overestimate (131.33M), không bão hòa
- ARIMA: Trend ngắn hạn, underestimate dài hạn

\textbf{3. Ý nghĩa K (Carrying Capacity):}
- K = 129.73M là giới hạn lý thuyết
- Dân số thực tế đỉnh 117M do chính sách
- Tiến gần K: 95\% năm 2070, 99\% năm 2115
\end{frame}

\begin{frame}{Thời Điểm Đạt Carrying Capacity}
\textbf{K = 129.73 triệu là giới hạn LÝ THUYẾT}

Dân số sẽ KHÔNG BAO GIỜ đạt được K hoàn toàn vì:
- K là asymptote (đường giới hạn)
- Cần thời gian vô hạn để đạt K

\begin{table}
\centering
\begin{tabular}{lll}
\toprule
Mức độ & Dân số & Thời điểm \\
\midrule
95\% K & 123.34 triệu & Năm 2070 \\
98.3\% K & 127.55 triệu & Năm 2100 \\
99\% K & 128.47 triệu & Năm 2115 \\
99.7\% K & 129.38 triệu & Năm 2150 \\
\bottomrule
\end{tabular}
\end{table}

\textbf{Kết luận:} K là giới hạn toán học, đỉnh thực tế 117M năm 2050
\end{frame}

\section{Tổng kết}

\begin{frame}{Giới Hạn Nghiên Cứu}
\begin{itemize}
\item Dữ liệu phụ thuộc nguồn ngoài (Worldometer, World Bank, UN), có thể sai sót ước tính.
\item Mô hình giả định xu hướng tiếp tục, không tính biến động bất ngờ (dịch bệnh, chiến tranh, chính sách lớn).
\item Phân tích chỉ tổng quốc gia, thiếu vùng (63 tỉnh/thành), không đánh giá bất bình đẳng nội bộ.
\item Độ chính xác dự báo giảm theo thời gian, khoảng tin cậy mở rộng.
\end{itemize}
\end{frame}

\begin{frame}{Hướng Nghiên Cứu Tương Lai}
\begin{itemize}
\item Phân tích theo vùng (63 tỉnh/thành) để hiểu bất bình đẳng dân số và đô thị hóa nội bộ.
\item Tích hợp dữ liệu thời gian thực từ Tổng cục Thống kê Việt Nam để cập nhật dự báo.
\item Áp dụng mô hình máy học tiên tiến (neural networks) cho dự báo chính xác hơn.
\item Nghiên cứu tác động biến đổi khí hậu đến di cư và dân số, mô hình dự đoán di cư do thiên tai.
\end{itemize}
\end{frame}

\begin{frame}{Kết Luận Và Khuyến Nghị}
\begin{itemize}
\item Dân số Việt Nam tăng từ 28M (1955) lên 102M (2025), đạt đỉnh 117M (2050), già hóa nhanh (Median Age 33.4→49.5).
\item Yếu tố chính: Fertility giảm, đô thị hóa.
\item Mô hình logistic dự báo tốt nhất (AIC thấp nhất).
\item Khuyến nghị: Khuyến khích sinh sản, hỗ trợ già hóa, cân bằng đô thị-nông thôn, cập nhật dữ liệu.
\end{itemize}
\end{frame}

\section{Tài liệu tham khảo}
\begin{frame}{Tài Liệu Tham Khảo}
\begin{enumerate}
\item Brauer, F., \& Castillo-Chavez, C. (2012). \textit{Mathematical Models in Population Biology and Epidemiology}. Springer.
\item Liên Hợp Quốc. (2024). \textit{World Population Prospects 2024}.
\item Tổng cục Thống kê Việt Nam (GSO). (2023). \textit{Báo cáo dân số và lao động}.
\item UNFPA. (2022). \textit{Dự báo dân số Việt Nam đến 2050}.
\item World Bank. (2023). \textit{World Development Indicators}.
\item Worldometer. (2025). \textit{Vietnam Population}.
\item Macrotrends. (2023). \textit{Vietnam Population 1950-2023}.
\end{enumerate}
Ngày lập báo cáo: 29/10/2025
\end{frame}

\begin{frame}{Tác Giả}
Báo cáo này được biên soạn bởi nhóm nghiên cứu dân số độc lập, sử dụng dữ liệu công khai từ các nguồn đáng tin cậy như Worldometer, World Bank, và United Nations. Phân tích dựa trên phương pháp khoa học và mô hình toán học. Liên hệ: luna777247@github.com (đối với câu hỏi kỹ thuật hoặc góp ý).
\end{frame}

\begin{frame}

\begin{center}
    Xin cảm ơn quý vị đã lắng nghe!
    
    \email
\end{center}

\begin{figure}[htb]
    \centering
    \includegraphics[width=0.5\textwidth]{images/logo-hus.png}
\end{figure}

\end{frame}

\end{document}