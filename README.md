# 📦 Mağaza Stok Erken Uyarı Paneli (MVP)

Bu proje, mağaza yöneticilerinin stok tükenme risklerini önceden tespit etmelerini ve tedarik süreçlerini optimize etmelerini sağlayan bir **Erken Uyarı ve Karar Destek Paneli** prototipidir.

🔗 **Canlı Demo:** (https://berkanbodurr-arch.github.io/magaza-stok-uyari-paneli/)

## 🎯 İş Değeri ve Problem Tanımı
Mağaza yöneticilerinin Excel üzerinden manuel hesaplama yapması operasyonel efor kaybına, popüler ürünlerin stoksuz kalmasına ve ciro kaybına yol açmaktadır. Bu panel, dinamik veri modeliyle acil sipariş ihtiyacını anlık olarak görünür kılar.

---

## ⚙️ Temel İş Kuralları ve Algoritma

* **Tüketim Tahmini:**  
  $$\text{Kalan Gün} = \frac{\text{Mevcut Stok}}{\text{Günlük Ortalama Satış}}$$
* **Dinamik Kritik Eşik (Lead Time Entegrasyonu):**  
  Ürün bazlı tedarik süresi baz alınır. `Kalan Gün <= Tedarik Süresi` olan ürünler sistem tarafından **🔴 KRİTİK** olarak işaretlenir.
* **Veri Temizleme (Edge Case Filtering):**  
  Mevcut stoğu `0` olan veya günlük satışı `0` olan ürünler sipariş aksiyonu oluşturmadığı için tabloya dahil edilmez.
* **Önceliklendirme:**  
  Panel varsayılan olarak **Kalan Gün (ASC)** artan sıralamayla yüklenir; en acil müdahale gerektiren ürün en tepede yer alır.

---

## 🗺️ Kapsam Yönetimi (Scope Boundary)

* **Faz 1 (MVP - Teslim Edilen):**
  - KPI Özet Kartları (Kritik ve Güvenli ürün sayaçları)
  - Dinamik durum renklendirmesi (Kırmızı / Yeşil rozetler)
  - Ürün arama ve "Yalnızca Acil Ürünleri Göster" filtresi
* **Faz 2 (Roadmap):**
  - "Sipariş Ver" butonu üzerinden açılan adet onay modalı
  - ERP / Depo yönetim sistemi sipariş servisi entegrasyonu

