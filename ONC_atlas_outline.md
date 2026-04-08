# ONC — Bilgi & Dosya Yönetim Sistemi
## Proje Outline v0.1

> Bu belge, ONC'nin kurumsal bilgi ve arşiv yönetim altyapısını tanımlayan kararlar, prensipler ve standartlar çerçevesini özetler. Her madde, CLI (AI) agent veya BIM manager ile detaylandırılacak bağımsız bir konu başlığıdır.

---

## 0. Sistem Felsefesi ve Kapsam

### 0.1 Temel prensipler (Stratejik)
Ofis yönetiminin dijital ikizi metadata üzerinden kurgulanır. 
- **Metadata-First:** Tüm operasyonel (koordinasyon, pafta takibi, muhasebe) kararlar metadata üzerinden alınır; fiziksel dosya (DWG/PDF) sadece bu verinin bir çıktısıdır.
- **Single Source of Truth (SSoT):** Her projenin tek bir "Dijital Kimliği" (onc_project.yaml) vardır; sistemler arası veri tutarlılığı bu kimlik üzerinden sağlanır.
- **Otomasyon & Standart:** İnsan inisiyatifi yerine "Sihirbaz" (Wizard) tabanlı yapılandırmalar ile sistemin kendi kendini denetlemesi ve beslemesi esastır.
- **Ayrık Mimari:** Veri kaynağı (NAS), Sistem Şartnamesi (Atlas/Git) ve Kullanıcı Arayüzü (External UI) birbirinden bağımsız ama protokollerle bağlı katmanlardır.

### 0.2 Kapsam sınırları
Sistemin ne yaptığı kadar ne yapmadığı da tanımlanır. Bu Atlas; proje koordinasyonu, pafta takibi ve arşiv yönetiminin **mimari ve mantıksal çerçevesini (Master Specification) - projenin anayasasını -** belirler. Günlük operasyonel işlemler (takvim, görev takibi, saat girişi) bu Atlas'ta tanımlanan protokollere uygun olarak **harici arayüzlerde (External Dashboards)** gerçekleştirilir. Arşiv, bilgi grafiği ve metadata yönetimi sistemin çekirdeğidir. Harici veri görselleştirme ve raporlama araçlarına (BI tools, Custom Dashboards) veri beslemek sistemin temel hedefleri arasındadır.

### 0.3 Orkestratör rolü ve yönetişim
Orkestratör, teknik altyapı ile ofis operasyonu arasındaki köprüdür.
- **Sistem Mimarı:** Metadata şemasını, veri standartlarını ve sistemin mantıksal mimarisini (Atlas/Spec) belirler.
- **Veri Denetçisi:** Harici arayüzlerdeki (DataViz/Dashboard) verilerin doğruluğunu ve "Master Metadata" (YAML) ile tutarlılığını denetler.
- **Yönetişim & İş Birliği:** BIM Manager ile pafta/model standartları; yönetim birimiyle ise muhasebe/koordinasyon çıktıları üzerinde iş birliği yapar. Karar alma ve yetki sınırları bu rolde merkezileşir.

### 0.4 Faz planı
Sistemin kurulumu üç ana faza yayılır:
- **Faz 1: Master Specification & Proto-Arşiv:** Atlas (Git/Obsidian) üzerinden şartnamenin (isimlendirme, şema, protokoller) dondurulması. Sihirbaz (Wizard) prototipinin geliştirilmesi ve NAS üzerindeki "Legacy" projelerin YAML dosyalarının oluşturulmaya başlanması.
- **Faz 2: Data Bridge & Reporting:** NAS'tan veriyi çeken "Indexer" (Dizinleyici) ve merkezi veritabanının (SQL) kurulması. Yönetim ve Muhasebe için veri görselleştirme ve raporlama arayüzlerinin yayına alınması.
- **Faz 3: Operational Ecosystem:** Ekip içi koordinasyon arayüzünün (Revizyon talebi, RFI, Pafta Takibi) tam fonksiyonel olarak devreye alınması. Çalışan ve saat takibi (Advanced Phase) modüllerinin entegrasyonu.

---

## 1. Varlık Taksonomisi

### 1.1 Varlık türlerinin sınıflandırılması
ONC arşivinde bulunan tüm dosya/belge türleri listelenir ve hiyerarşik olarak sınıflandırılır: çizimler, raporlar, yazışmalar, fotoğraflar, sözleşmeler, referans belgeleri vb. BIM manager'ın IFC/BIM varlıkları bu sınıflandırmaya nasıl oturur?

### 1.2 Proje yaşam döngüsü aşamaları
ONC'nin kullandığı proje aşamaları (kavram, ön proje, kesin proje, uygulama, yapım, teslim, arşiv) standart olarak tanımlanır. Bu aşamalar metadata'nın temel eksenlerinden biridir.

### 1.3 Disiplin ve uzmanlık alanları
Mimari, statik, mekanik, elektrik, peyzaj, iç mimari vb. disiplinlerin sisteme nasıl yansıyacağı belirlenir. BIM federation yapısıyla örtüşmesi tartışılır.

### 1.4 Belge statü ve olgunluk seviyeleri
WIP, paylaşılan, onaylı, revize, iptal, arşiv gibi statü geçişleri tanımlanır. ISO 19650'deki "suitability code" mantığına nasıl yaklaşılacağı tartışılır.

---

## 2. İsimlendirme Standardı

### 2.1 Dosya isimlendirme konvansiyonu
ONC genelinde geçerli olacak dosya adı yapısı belirlenir. Hangi alanlar zorunlu, hangisi opsiyonel? Örnek: `[ProjeKodu]_[Disiplin]_[Tip]_[Bölge]_[Aşama]_[No]_[Revizyon]`

### 2.2 Klasör isimlendirme konvansiyonu
NAS üzerindeki mevcut ve yeni klasör yapısının adlandırma mantığı standartlaştırılır. Mevcut 20 yıllık arşivle geriye dönük uyumluluk meselesi tartışılır.

### 2.3 Proje kodlama sistemi
Ofisteki her projeye özgün kod atanmasının kuralları belirlenir. Yıl, sıra numarası, tür bilgisi kombinasyonu. Mevcut kodlama sistemi varsa entegrasyonu değerlendirilir.

### 2.4 Revizyon ve versiyon notasyonu
Revizyonların nasıl gösterileceği (P01/C01, A/B/C, v1.0) ve çalışma sürümü ile yayınlanan sürüm arasındaki fark netleştirilir.

### 2.5 Geçici ve çalışma dosyaları kuralı
WIP dosyaları için isimlendirme kuralı ayrıca belirlenir; bunların arşive girmemesi için protokol oluşturulur.

---

## 3. Klasör Hiyerarşisi (NAS)

### 3.1 Kök yapısı ve ana dallar
NAS'taki en üst seviye klasör mantığı belirlenir: Projeler / Referans / Şablonlar / Arşiv / Geçici ayrımı. Her dalın sorumluluğu ve içerik kuralı tanımlanır.

### 3.2 Proje klasörü iç yapısı
Bir proje klasörünün standart iç yapısı şablon olarak belirlenir. Disiplin bazlı mı, aşama bazlı mı, yoksa hibrit mi olacağı kararlaştırılır. BIM manager'ın model yapısıyla çakışma noktaları tartışılır.

### 3.3 Referans ve kütüphane klasörleri
Detay, pafta şablonu, malzeme kataloğu, standart çizimler gibi paylaşılan kaynakların nerede ve nasıl tutulacağı belirlenir.

### 3.4 Mevcut arşivin haritalanması
20 yıllık NAS yapısının mevcut hali belgelenir. Hangi projeler, hangi formatlarda, hangi tutarlılıkta? Bu analiz metadata stratejisinin girdisidir.

### 3.5 Erişim izinleri matrisi
NAS üzerinde hangi kullanıcı grubunun hangi klasöre erişeceği belirlenir. Orkestratör dışında kimse doğrudan NAS'a yazmamalıdır — bu nasıl uygulanır?

---

## 4. CAD Standartları

### 4.1 Layer (katman) standardı
AutoCAD layer isimlendirme, renk ve çizgi tipi standartları belirlenir. AIA, BS1192 veya ONC'ye özel bir standart mı kullanılacak? Mevcut durumla fark analizi yapılır.

### 4.2 Çizim şablonları (template/DWT)
Standart çizim şablonları tanımlanır: sayfa boyutu, başlık bloğu, layer seti, ölçek notasyonu. Şablonların nasıl dağıtılacağı ve güncelleneceği protokolü kurulur.

### 4.3 Blok ve sembol kütüphanesi
Standart blokların (kapı, pencere, tesisat sembolü vb.) merkezi kütüphanesi nasıl yönetilecek? Kütüphane NAS'ta mı, repo'da mı tutulur?

### 4.4 Xref yönetimi
Dış referans (xref) kullanım kuralları belirlenir: göreli mi mutlak path mi, hangi durumlarda xref zorunludur, dosya taşınırken nasıl yönetilir?

### 4.5 Dosya formatı ve kaydetme protokolü
Hangi AutoCAD versiyonu esas alınır? DWG/DXF/PDF çıktı kuralları nelerdir? Kaydetmeden önce kontrol listesi tanımlanır.

### 4.6 Ölçek, birim ve koordinat sistemi
Proje bazında ölçek ve birim standardı belirlenir. Gerçek dünya koordinatı (georeferencing) kullanılacak mı? BIM modelleriyle koordinasyon bağlamında kritik bir karardır.

---

## 5. BIM Standartları

### 5.1 BIM kullanım hedefleri (BIM Uses)
ONC'nin hangi amaçlarla BIM kullandığı tanımlanır: koordinasyon, miktar hesabı, simülasyon, teslim, varlık yönetimi? Bu hedefler LOD ve model içerik kararlarını belirler.

### 5.2 LOD (Level of Development) matrisi
Proje aşamasına ve disipline göre beklenen LOD seviyeleri tablolanır. BIM manager'ın mevcut uygulamasıyla karşılaştırılır.

### 5.3 Model koordinasyon protokolü
Disiplinler arası clash detection ve koordinasyon toplantı döngüsü belirlenir. Federation dosyası kimin sorumluluğunda, ne sıklıkta güncellenir?

### 5.4 IFC çıktı standardı
IFC versiyon, export şeması ve property set kuralları belirlenir. Hangi bilgi IFC'ye taşınır, hangisi modelde kalır?

### 5.5 BIM — CAD — metadata üçgeninin yönetimi
BIM modeli, ilgili CAD çizimleri ve metadata kaydı arasındaki bağlantı nasıl kurulur ve senkronize tutulur? Bu üç katmanın çakışma ve çelişme noktaları yönetilir.

### 5.6 Model isimlendirme ve klasör yapısı
BIM modellerine özgü isimlendirme ve klasör yapısı, genel CAD standardıyla uyumlu biçimde belirlenir.

---

## 6. Metadata Şeması

### 6.1 Metadata mimarisi kararları
Flat vs. hiyerarşik metadata, zorunlu vs. opsiyonel alanlar, kontrollü kelime dağarcığı (controlled vocabulary) kullanımı kararlaştırılır. ISO 19650 property set mantığından ne kadar ilham alınır?

### 6.2 Ana Proje Künyesi (onc_project.yaml)
Her proje klasörünün kök dizininde bulunacak tekil metadata dosyası tanımlanır. Bu dosya projenin "Dijital Kimliği"dir.
- **Zorunlu Alanlar:** `uuid` (sistem genelinde tekil), `project_code` (ofis kodu), `project_name`, `client`, `status`, `phase`.
- **Lokasyon Verisi:** `nas_path`, `server_id`.
- **Sorumluluklar:** `project_lead_id`, `bim_manager_id`.

### 6.3 Gömülü Pafta ve Varlık Listesi
"Tek dosya" prensibi gereği, projeye ait tüm pafta listesi (Sheet List) ana künye dosyası (`onc_project.yaml`) içerisinde bir dizi (array) olarak tutulur.
- **Pafta Metadata Alanları:** `sheet_id`, `title`, `discipline`, `current_rev`, `issue_date`.
- **Hacim Yönetimi:** Çok sayıda pafta içeren projelerde YAML yapısının hiyerarşik organizasyonu belirlenir.

### 6.4 Etiket (tag) taksonomisi
Obsidian'da kullanılacak tag hiyerarşisi tasarlanır. Düz mı (`#yapim`) yoksa iç içe mi (`#aşama/yapim`)? Tag sayısı ve disiplini nasıl korunur?

### 6.5 İlişki ve bağlantı modeli
Varlıklar arası ilişkiler nasıl temsil edilir: `[[wikilink]]` mi, özel frontmatter alanı mı? Proje → belge → revizyon → ilgili belge hiyerarşisi kurulur.

### 6.6 Metadata girişi ve kalite kontrolü
Yeni bir varlık kaydı nasıl oluşturulur? Şablonlar, zorunlu alan kontrolü, tutarsız girişlerin tespiti için Dataview sorguları planlanır.

### 6.7 Harici Entegrasyon ve Raporlama (DataViz vb.)
Metadata şemasının, harici iş zekası araçlarına (PowerBI, Tableau, Custom Dashboards) girdi sağlayacak şekilde yapılandırılması planlanır. Verinin taşınabilirliği (JSON/CSV export) ve ilişkisel yapısının korunması bu başlık altında ele alınır.

---

## 7. Git Workflow ve Repo Yapısı

### 7.1 Repo mimarisi
Tek repo mu çoklu repo mu? Vault = repo mu, yoksa vault repo içinde mi? Remote (GitHub/GitLab/self-hosted) seçimi ve gerekçesi.

### 7.2 Branch stratejisi
Main branch her zaman stabil mi? Geliştirme (dev), deneme (feature) branch kullanımı tanımlanır. Orkestratör tek committer mi?

### 7.3 Commit konvansiyonu
Commit mesajlarının yapısı belirlenir: `[konu]: [değişiklik açıklaması]` formatı, anlamlı geçmiş oluşturmak için kurallar.

### 7.4 `.gitignore` stratejisi
Repo'ya girmemesi gereken her şey listelenir: sistem dosyaları, geçici Obsidian dosyaları, büyük binary'ler. Bu liste hem güvenlik hem temizlik için kritiktir.

### 7.5 Yedekleme ve felaket senaryoları
Remote repo yedek görevi görür mü yeterince? Ek yedekleme katmanı gerekli mi? NAS arızasında metadata ne kadar dayanıklıdır?

---

## 8. Obsidian Vault Yapısı

### 8.1 Vault tasarım prensipleri
Vault tek kişilik çalışma aracı olarak optimize edilir. Klasörler mi, linkler mi ağırlıklı yapı kurar? MOC (Map of Content) yaklaşımı benimsenir mi?

### 8.2 Plugin stratejisi
Zorunlu pluginler belirlenir: Dataview (sorgulama), Templater (şablon otomasyonu), Git (sync), MetaEdit veya muadili (frontmatter yönetimi). Her plugin bir karar gerektirir.

### 8.3 Şablon sistemi
Her varlık türü için Templater şablonu hazırlanır. Yeni kayıt oluştururken hangi alanlar otomatik doldurulur?

### 8.4 Dataview sorgu kütüphanesi
Sık kullanılacak sorgular tasarlanır: proje bazlı varlık listesi, statüye göre filtreleme, son güncellenenler, eksik metadata tespiti.

### 8.5 Graph view kullanım stratejisi
Graph'ın ne için kullanılacağı, ne için kullanılmayacağı belirlenir. Anlamlı bir görselleştirme için bağlantı stratejisi planlanır.

---

## 9. Güvenlik ve Erişim Mimarisi

### 9.1 NAS izolasyon protokolü
NAS'ın sistemin geri kalanından nasıl izole tutulacağı teknik olarak belirlenir. Okuma erişimi kimin üzerinden geçer?

### 9.2 Repo erişim kontrolü
Git repo'nun public/private durumu, kimin push yetkisi olduğu, gelecekte ekip arayüzü eklenince nasıl değişeceği planlanır.

### 9.3 Hassas veri politikası
Sözleşme bedelleri, kişisel veriler, müvekkil gizlilik gereksinimleri — bunlar metadata'ya girer mi, girerse nasıl korunur?

### 9.4 Felaket kurtarma planı
Sistemi kimin, ne zaman, nasıl yedekleyeceği. Orkestratör ofisten ayrılırsa ne olur — bilgi transferi protokolü.

### 9.5 Sistem Performansı ve Tarama Güvenliği
NAS üzerindeki metadata dosyalarının taranması (indexing) için güvenlik protokolleri belirlenir.
- **Read-Only Access:** İndeksleyici servislerin sadece okuma yetkisiyle sınırlandırılması.
- **Scheduled vs Event-Driven:** Devasa taramalar yerine olay bazlı (Wizard tetiklemeli) ve artımlı (incremental) tarama stratejilerinin uygulanması.

---

## 10. Gelecek Faz — Ekip Arayüzü

### 10.1 Arayüz gereksinimleri
Ekibin sistemden ne yapmasına ihtiyacı var: arama, filtreleme, belge kartı görüntüleme, path kopyalama, statü takibi? Teknik bilgi gerektirmeyecek.

### 10.2 Teknoloji seçenekleri
Statik site (Obsidian Publish, Jekyll, mkdocs), basit web app, ya da özel geliştirme? Repo'yu okuyan, NAS'a dokunmayan bir arayüz için seçenekler değerlendirilir.

### 10.3 Arama ve sorgulama motoru
Ekip nasıl arayacak? Full-text mi, metadata filtresi mi, tag navigasyonu mu? Arayüzün backend ihtiyacı değerlendirilir.

### 10.4 Onboarding stratejisi
Ekip arayüzünü nasıl öğrenecek? Eğitim materyali, yardım dokümantasyonu, değişim yönetimi planı.

---

## Ekler

### A. Referans standartlar
- ISO 19650 (BIM bilgi yönetimi)
- BS EN ISO 19650-2 (teslim aşaması)
- AIA CAD Layer Guidelines
- OmniClass / Uniclass sınıflandırma sistemleri
- RIBA Plan of Work aşama karşılıkları

### B. Karar günlüğü
Sistem geliştirme sürecinde alınan kararlar, gerekçeleri ve alternatifleriyle birlikte burada biriktirilir. Bu belge orkestratör + BIM manager toplantılarının çıktısıdır.

### C. Açık sorular
Henüz netleşmemiş, BIM manager veya yönetim kararı gerektiren maddeler listesi. Canlı belge olarak tutulur.

---

*Versiyon: 0.1 — Taslak*
*Sonraki adım: Her başlık için ayrı detay .md dosyası (CLI agent ile)*netimi)
- BS EN ISO 19650-2 (teslim aşaması)
- AIA CAD Layer Guidelines
- OmniClass / Uniclass sınıflandırma sistemleri
- RIBA Plan of Work aşama karşılıkları

### B. Karar günlüğü
Sistem geliştirme sürecinde alınan kararlar, gerekçeleri ve alternatifleriyle birlikte burada biriktirilir. Bu belge orkestratör + BIM manager toplantılarının çıktısıdır.

### C. Açık sorular
Henüz netleşmemiş, BIM manager veya yönetim kararı gerektiren maddeler listesi. Canlı belge olarak tutulur.

---

*Versiyon: 0.1 — Taslak*
*Sonraki adım: Her başlık için ayrı detay .md dosyası (CLI agent ile)*