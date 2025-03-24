Metro Rota Bulucu
Proje Açıklaması
Bu proje, metro ağında en az aktarma ve en kısa süreli rotayı bulmak için iki farklı algoritma kullanmaktadır:

BFS (Breadth-First Search - Genişlik Öncelikli Arama): En az aktarma sayısı ile hedefe ulaşan rotayı belirler.
A benzeri Dijkstra algoritması*: En kısa sürede hedefe ulaşan rotayı belirler.
Proje, Python programlama dili ile geliştirilmiş olup heapq ve collections gibi standart kütüphanelerden faydalanmaktadır.

Kullanılan Teknolojiler ve Kütüphaneler
Python 3.x: Projenin geliştirilmesi için kullanılan ana programlama dili.
collections.deque: BFS algoritması için kuyruk veri yapısını verimli şekilde kullanmak amacıyla kullanıldı.
heapq: En hızlı rota hesaplamasında öncelik kuyruğunu yönetmek için kullanıldı.
defaultdict: Metro ağı verilerini saklamak ve hatları kolay yönetmek için kullanıldı.
Algoritmaların Çalışma Mantığı
BFS (En Az Aktarma Bulma)
Nasıl Çalışır?

Bir kuyruk (FIFO yapısı) kullanılarak en kısa aktarma rotası araştırılır.
İlk istasyon kuyruğa eklenir ve komşularına genişletilir.
Hedef istasyona ulaşıldığında en az aktarmalı rota elde edilir.
Neden BFS?

Aktarma sayısını en aza indirmek için idealdir.
Ağırlıkların (sürelerin) önemi olmadığı durumlarda kullanılır.
A* Benzeri Dijkstra Algoritması (En Hızlı Rota Bulma)
Nasıl Çalışır?

Bir öncelik kuyruğu (heap) ile en kısa süreli yollar hesaplanır.
Her istasyon için süre maliyeti hesaplanarak en kısa süreli istasyon seçilir.
Hedefe ulaşılınca en hızlı rota belirlenir.
Neden A veya Dijkstra?*

Metro ağına en uygun ve güvenilir kısa yol algoritmalarından biridir.
Her kenarın farklı bir süresi olduğu için Dijkstra öncelikli seçilmiştir.
Örnek Kullanım ve Test Sonuçları
Örneğin, M1 istasyonundan K4 istasyonuna gitmek için aşağıdaki fonksiyonlar kullanılabilir:

python rota = metro.en_az_aktarma_bul("M1", "K4") if rota: print("En az aktarmalı rota:", " -> ".join(i.ad for i in rota))

sonuc = metro.en_hizli_rota_bul("M1", "K4") if sonuc: rota, sure = sonuc print(f"En hızlı rota ({sure} dakika):", " -> ".join(i.ad for i in rota))

Projeyi Geliştirme Fikirleri
Metro hatlarına dinamik ekleme ve silme özelliği eklenebilir.
Grafiksel bir arayüz ile metro haritası görselleştirilebilir.
Algoritmalara yoğunluk veya tren bekleme süresi gibi değişkenler eklenebilir.
Gerçek zamanlı veri kullanılarak daha doğru süre hesaplamaları yapılabilir.
