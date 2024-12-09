# E-commerce Customer Churn Analysis

Created By: Aldira Putri Damayanti
**OUTLINE**

1. Business Problem Understanding
2. Data Understanding
3. Data Cleaning
4. Data Analysis
5. Data Preprocessing dan Feature Engineering
6. Modelling
7. Conclusion and Recommendation

**Business Problem Understanding**
**Introduction**
<br>
<br>

Dalam industri e-commerce yang kompetitif, menjaga pelanggan tetap loyal merupakan salah satu tantangan terbesar yang dihadapi oleh perusahaan. Penelitian menunjukkan bahwa biaya untuk mendapatkan pelanggan baru bisa mencapai lima hingga tujuh kali lipat lebih besar dibandingkan dengan mempertahankan pelanggan yang sudah ada. Oleh karena itu, mempertahankan pelanggan yang loyal menjadi strategi bisnis yang lebih efisien dan menguntungkan bagi perusahaan. 

Salah satu cara untuk meningkatkan loyalitas pelanggan adalah melalui pemberian promosi. Namun, tanpa strategi yang terarah dan data yang mendukung, promosi sering kali menjadi tidak efektif dan bahkan membebani anggaran perusahaan. Hal ini terjadi karena promosi dapat diarahkan pada pelanggan yang salah atau tidak memiliki dampak signifikan terhadap perilaku mereka, sehingga menimbulkan inefisiensi dari segi biaya maupun sumber daya.

Kehilangan pelanggan (customer churn) menjadi ancaman nyata bagi kelangsungan bisnis, terutama jika perusahaan tidak memiliki cara yang efektif untuk mengidentifikasi dan menangani risiko ini. Kemampuan untuk memprediksi apakah seorang pelanggan cenderung churn atau tetap loyal sangat penting untuk memastikan bahwa sumber daya promosi dapat diarahkan dengan lebih tepat sasaran. Selain itu, pemahaman terhadap faktor-faktor yang memengaruhi keputusan pelanggan untuk churn atau tetap loyal memberikan wawasan yang berharga bagi perusahaan dalam merancang pendekatan yang lebih efektif untuk mempertahankan pelanggan.

Dengan latar belakang ini, perusahaan e-commerce berkomitmen untuk membangun strategi berbasis data yang tidak hanya memungkinkan prediksi perilaku pelanggan tetapi juga memberikan pemahaman yang mendalam tentang variabel-variabel yang memengaruhi loyalitas mereka. Pendekatan ini bertujuan untuk meningkatkan efisiensi operasional, mengoptimalkan anggaran promosi, dan menciptakan hubungan jangka panjang yang lebih baik dengan pelanggan.

Sumber: Customer churn 101: What is it, types of churn, and what to do about it. (2024). paddle.com. https://www.paddle.com/resources/customer-churn

**Siapa Stakeholder yang Mengalami Masalah?**

- Perusahaan e-commerce (pemilik bisnis): Mereka yang menghadapi tantangan dalam mempertahankan pelanggan yang loyal, serta ingin meminimalkan biaya akuisisi pelanggan baru.
- Tim pemasaran dan penjualan: Tim yang bertanggung jawab untuk merancang dan melaksanakan strategi untuk mempertahankan pelanggan yang ada dan menarik pelanggan baru.
- Manajemen: Mereka yang perlu membuat keputusan strategis yang berfokus pada pengelolaan biaya dan meningkatkan profitabilitas dengan fokus pada retensi pelanggan.
- Pelanggan: Pelanggan yang sudah ada juga berperan dalam masalah ini, karena mereka menjadi sasaran utama dalam upaya peningkatan loyalitas.

**Problem Statment**
<br>
<br>
Mendapatkan pelanggan baru bisa menghabiskan biaya lima hingga tujuh kali lipat dibandingkan mempertahankan pelanggan lama. Oleh karena itu, perusahaan E-Commerce ingin mempertahankan aktivitas Customer loyal di platform e-commerce dapat dilakukan melalui pemberian promosi. Namun, tanpa adanya strategi yang tepat, promosi tersebut berisiko menjadi tidak efisien, baik dari segi biaya maupun sumber daya yang digunakan.

Masalah spesifik:

- Tingginya biaya akuisisi pelanggan baru yang bisa mencapai lima hingga tujuh kali lipat lebih tinggi daripada mempertahankan pelanggan yang sudah ada.
- Kehilangan pelanggan yang sudah ada, yang berarti potensi pendapatan yang lebih rendah dan berkurangnya nilai seumur hidup pelanggan (Customer Lifetime Value / CLV).
- Kurangnya strategi retensi yang efektif untuk meningkatkan loyalitas pelanggan.

**Goals**
<br>
<br>
Maka berdasarkan permasalahan tersebut, perusahaan ingin memiliki kemampuan untuk memprediksi kemungkinan seorang Customer akan/ingin Churn pada layanan tersebut atau tidak, sehingga dapat memfokuskan Promosi pada Customer yang tidak akan Churn (Non-Churn).

Selain itu, perusahaan juga ingin mengetahui apa/faktor/variabel apa yang membuat Customer Churn atau Non Churn pada layanan mereka, sehingga perusahaan dapat membuat rencana yang lebih baik dalam mendekati Customer Potensial (Customer yang Non Churn). 

**Analytical Approach**

Jadi yang akan kita lakukan adalah menganalisis data untuk menemukan pola yang membedakan Customer yang Churn dan Non Churn. 

Kemudian kita akan membangun model klasifikasi yang akan membantu perusahaan E-Commerce untuk dapat memprediksi probabilitas seorang kandidat akan/ingin Churn di layanan e-commerce tersebut atau tidak.

**Metrics Evaluation**

Target :
<br>
0 = Customer Non-Churn
<br>
1 = Customer Churn 

Type 1 Error : False Positive 
Konsekuensi: Promosi akan sia-sia, tidak 

Type 2 Error : False Negative
Konsekuensi: Kehilangan Customer (Churn)

Berdasarkan konsekuensinya, langkah yang tepat untuk pemilihan model adalah model yang mengurangi hilangnya Customer loyal (Churn), tetapi tetap memperhatikan pengeluaran biaya promosi untuk pelanggan yang kurang tepat. Recall dan precision yang diseimbangkan akan dari kelas positif (Customer churn). Metrik yang akan digunakan adalah ROC-AUC.