# Capstone3

## Business Problem Understanding

**Context**  
Sebuah perusahaan perhotelan di Portugal ingin meningkatkan efisiensi biaya operasional dengan menganalisis data transaksi booking pelanggan. Data tersebut mencakup transaksi yang berhasil dan yang dibatalkan, serta berbagai metode booking seperti online, offline, dan melalui agen perjalanan. Perusahaan ingin mengidentifikasi pelanggan yang cenderung membatalkan transaksi dan yang tidak, sehingga mereka dapat meningkatkan layanan dan mengoptimalkan proses operasional untuk meningkatkan efisiensi anggaran.

Target :

0 : Transaksi Selesai

1 : Transaksi Dibatalkan

**Problem Statement :**

Proses persiapan fasilitas hotel, seperti kamar, memerlukan waktu dan sumber daya. Jika fasilitas disiapkan tetapi tidak digunakan, hotel akan mengalami kerugian. Sebaliknya, beberapa fasilitas, seperti makanan di restoran, dapat menurun kualitasnya jika disiapkan terlalu awal. Oleh karena itu, hotel perlu dapat menyiapkan fasilitas pada saat diminta.

**Goals :**

Dengan mempertimbangkan permasalahan tersebut, hotel ingin mampu memprediksi faktor-faktor yang menyebabkan pelanggan membatalkan pemesanan. Hal ini akan membantu hotel untuk fokus dalam menyiapkan fasilitas bagi pelanggan yang akan benar-benar menginap. Selain itu, jika terdapat pelanggan dalam daftar tunggu, hotel ingin dapat memberikan prioritas kepada pelanggan yang lebih cenderung untuk tidak membatalkan pemesanan. Dan juga, jika hotel memiliki pelanngan dalam waiting list , mereka dapat memprioritaskan pelanggan yang tidak dalam kriteria pelanggan yang mebatalkan booking.


**Analytic Approach :**

Kami akan menganalisis data untuk mengidentifikasi pola yang membedakan antara pengunjung yang akan menginap di hotel dan yang akan membatalkan pemesanan mereka. Setelah itu, kami akan membangun model klasifikasi yang dapat membantu hotel dalam memprediksi karakteristik pengunjung yang akan menginap atau membatalkan pemesanan mereka.


**Metric Evaluation**

Type 1 error : False Positive  
Konsekuensi: kehilangan calon customer yang benar benar loyal

Type 2 error : False Negative  
Konsekuensi: sia-sianya transaksi dalam segi waktu dan sumber daya

Berdasarkan konsekuensinya, fokus kami adalah menciptakan model yang dapat mengidentifikasi calon pelanggan yang cenderung membatalkan transaksi, dengan mengurangi sebanyak mungkin prediksi yang salah positif. Oleh karena itu, metrik utama yang akan kami gunakan adalah area di bawah kurva ROC (ROC AUC).


## Data Understanding
- Memiliki data awal 83573 dan memiliki 11 kolom

Features
-	country: Country of origin.
-	market_segment: Market segment designation. 
-	previous_cancellations: Number of previous bookings that were cancelled by the customer prior to the current booking.
-	booking_changes: Number of changes/amendments made to the booking from the moment the booking was entered on the PMS until the moment of check-in or cancellation.
-	deposit_type: Indication on if the customer made a deposit to guarantee the booking. 
-	days_in_waiting_list: Number of days the booking was in the waiting list before it was confirmed to the customer.
-	customer_type: Type of booking.
-	reserved_room_type: Code of room type reserved. Code is presented instead of designation for anonymity reasons.
-	required_car_parking_space: Number of car parking spaces required by the customer.
-	total_of_special_request: Number of special requests made by the customer (e.g. twin bed or high floor).
-	is_canceled: Value indicating if the booking was canceled (1) or not (0).


## Conclusion & Recommendation

Dalam kasus ini, laporan klasifikasi menunjukkan bahwa model Anda memiliki performa yang sangat baik, dengan nilai precision, recall, dan f1-score yang tinggi untuk setiap kelas, serta akurasi keseluruhan sebesar 1.00.

Terlihat bahwa model memiliki performa yang sangat baik dengan precision, recall, dan F1-score sebesar 1.00 untuk setiap kelas, serta akurasi keseluruhan sebesar 1.00. Ini menunjukkan bahwa model sangat baik dalam memprediksi kelas pada data pengujian.

Meskipun model memiliki performa yang sempurna dalam kasus ini, beberapa langkah rekomendasi yang dapat pertimbangkan adalah:

1. **Validasi Tambahan**: Meskipun model telah menghasilkan performa yang sangat baik pada data pengujian, penting untuk memvalidasi model pada data yang belum pernah dilihat sebelumnya (misalnya, dengan menggunakan validasi silang) untuk memastikan bahwa hasilnya konsisten dan tidak terlalu disesuaikan dengan data pengujian.

2. **Interpretasi Model**: Meskipun penting untuk memahami performa keseluruhan model, juga berguna untuk memahami faktor apa yang paling mempengaruhi prediksi model. Dapat melakukan interpretasi model untuk memahami fitur mana yang paling berpengaruh dalam membuat prediksi.

3. **Eksplanasi Prediksi**: Untuk kasus yang lebih kompleks, seperti dalam pengambilan keputusan yang memengaruhi manusia, penting untuk bisa menjelaskan prediksi model dengan cara yang bisa dimengerti oleh manusia. Teknik seperti LIME (Local Interpretable Model-agnostic Explanations) atau SHAP (SHapley Additive exPlanations) dapat membantu menjelaskan prediksi model.

4. **Pemeliharaan dan Pemantauan**: Terlepas dari performa awal yang sangat baik, model perlu dipelihara dan dipantau secara berkala. Ini bisa melibatkan penambahan data baru, penyesuaian parameter model, atau pemantauan untuk mendeteksi perubahan dalam distribusi data.

5. **Kebijakan Keselamatan**: Jika model digunakan dalam keputusan kritis (misalnya, dalam perawatan medis), penting untuk memastikan bahwa kebijakan keselamatan yang sesuai telah diimplementasikan. Ini mungkin melibatkan audit dan validasi tambahan, serta prosedur darurat jika model gagal.

Dengan mempertimbangkan langkah-langkah ini, dapat memastikan bahwa model tetap dapat diandalkan dan efektif dalam menangani kasus-kasus yang kompleks di masa depan.
  
