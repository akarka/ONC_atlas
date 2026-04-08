# ONC — Bilgi & Dosya Yönetim Sistemi
## Proje Outline v0.1

> Bu belge, ONC'nin kurumsal bilgi ve arşiv yönetim altyapısını tanımlayan kararlar, prensipler ve standartlar çerçevesini özetler. Her madde, CLI (AI) agent veya BIM manager ile detaylandırılacak bağımsız bir konu başlığıdır.

---

## 0. Sistem Felsefesi ve Kapsam

### [[0.1_temel_prensipler_stratejik|0.1 Temel prensipler (Stratejik)]]
### [[0.2_kapsam_sinirlari|0.2 Kapsam sınırları]]
### [[0.3_orkestrator_rolu_ve_yonetisim|0.3 Orkestratör rolü ve yönetişim]]
### [[0.4_faz_plani|0.4 Faz planı]]
---

## 1. Varlık Taksonomisi

### [[1.1_varlik_turlerinin_siniflandirilmasi|1.1 Varlık türlerinin sınıflandırılması]]
### [[1.2_proje_yasam_dongusu_asamalari|1.2 Proje yaşam döngüsü aşamaları]]
### [[1.3_disiplin_ve_uzmanlik_alanlari|1.3 Disiplin ve uzmanlık alanları]]
### [[1.4_belge_statu_ve_olgunluk_seviyeleri|1.4 Belge statü ve olgunluk seviyeleri]]
---

## 2. İsimlendirme Standardı

### [[2.1_dosya_isimlendirme_konvansiyonu|2.1 Dosya isimlendirme konvansiyonu]]
### [[2.2_klasor_isimlendirme_konvansiyonu|2.2 Klasör isimlendirme konvansiyonu]]
### [[2.3_proje_kodlama_sistemi|2.3 Proje kodlama sistemi]]
### [[2.4_revizyon_ve_versiyon_notasyonu|2.4 Revizyon ve versiyon notasyonu]]
### [[2.5_gecici_ve_calisma_dosyalari_kurali|2.5 Geçici ve çalışma dosyaları kuralı]]
---

## 3. Klasör Hiyerarşisi (NAS)

### [[3.1_kok_yapisi_ve_ana_dallar|3.1 Kök yapısı ve ana dallar]]
### [[3.2_proje_klasoru_ic_yapisi|3.2 Proje klasörü iç yapısı]]
### [[3.3_referans_ve_kutuphane_klasorleri|3.3 Referans ve kütüphane klasörleri]]
### [[3.4_mevcut_arsivin_haritalanmasi|3.4 Mevcut arşivin haritalanması]]
### [[3.5_erisim_izinleri_matrisi|3.5 Erişim izinleri matrisi]]
---

## 4. CAD Standartları

### [[4.1_layer_katman_standardi|4.1 Layer (katman) standardı]]
### [[4.2_cizim_sablonlari_template_dwt|4.2 Çizim şablonları (template/DWT)]]
### [[4.3_blok_ve_sembol_kutuphanesi|4.3 Blok ve sembol kütüphanesi]]
### [[4.4_xref_yonetimi|4.4 Xref yönetimi]]
### [[4.5_dosya_formati_ve_kaydetme_protokolu|4.5 Dosya formatı ve kaydetme protokolü]]
### [[4.6_olcek_birim_ve_koordinat_sistemi|4.6 Ölçek, birim ve koordinat sistemi]]
---

## 5. BIM Standartları

### [[5.1_bim_kullanim_hedefleri_bim_uses|5.1 BIM kullanım hedefleri (BIM Uses)]]
### [[5.2_lod_level_of_development_matrisi|5.2 LOD (Level of Development) matrisi]]
### [[5.3_model_koordinasyon_protokolu|5.3 Model koordinasyon protokolü]]
### [[5.4_ifc_cikti_standardi|5.4 IFC çıktı standardı]]
### [[5.5_bim_cad_metadata_ucgeninin_yonetimi|5.5 BIM — CAD — metadata üçgeninin yönetimi]]
### [[5.6_model_isimlendirme_ve_klasor_yapisi|5.6 Model isimlendirme ve klasör yapısı]]
---

## 6. Metadata Şeması

### [[6.1_metadata_mimarisi_kararlari|6.1 Metadata mimarisi kararları]]
### [[6.2_ana_proje_kunyesi_onc_project_yaml|6.2 Ana Proje Künyesi (onc_project.yaml)]]
### [[6.3_gomulu_pafta_ve_varlik_listesi|6.3 Gömülü Pafta ve Varlık Listesi]]
### [[6.4_etiket_tag_taksonomisi|6.4 Etiket (tag) taksonomisi]]
### [[6.5_iliski_ve_baglanti_modeli|6.5 İlişki ve bağlantı modeli]]
### [[6.6_metadata_girisi_ve_kalite_kontrolu|6.6 Metadata girişi ve kalite kontrolü]]
### [[6.7_harici_entegrasyon_ve_raporlama_dataviz_vb|6.7 Harici Entegrasyon ve Raporlama (DataViz vb.)]]
---

## 7. Git Workflow ve Repo Yapısı

### [[7.1_repo_mimarisi|7.1 Repo mimarisi]]
### [[7.2_branch_stratejisi|7.2 Branch stratejisi]]
### [[7.3_commit_konvansiyonu|7.3 Commit konvansiyonu]]
### [[7.4_gitignore_stratejisi|7.4 `.gitignore` stratejisi]]
### [[7.5_yedekleme_ve_felaket_senaryolari|7.5 Yedekleme ve felaket senaryoları]]
---

## 8. Obsidian Vault Yapısı

### [[8.1_vault_tasarim_prensipleri|8.1 Vault tasarım prensipleri]]
### [[8.2_plugin_stratejisi|8.2 Plugin stratejisi]]
### [[8.3_sablon_sistemi|8.3 Şablon sistemi]]
### [[8.4_dataview_sorgu_kutuphanesi|8.4 Dataview sorgu kütüphanesi]]
### [[8.5_graph_view_kullanim_stratejisi|8.5 Graph view kullanım stratejisi]]
---

## 9. Güvenlik ve Erişim Mimarisi

### [[9.1_nas_izolasyon_protokolu|9.1 NAS izolasyon protokolü]]
### [[9.2_repo_erisim_kontrolu|9.2 Repo erişim kontrolü]]
### [[9.3_hassas_veri_politikasi|9.3 Hassas veri politikası]]
### [[9.4_felaket_kurtarma_plani|9.4 Felaket kurtarma planı]]
### [[9.5_sistem_performansi_ve_tarama_guvenligi|9.5 Sistem Performansı ve Tarama Güvenliği]]
---

## 10. Gelecek Faz — Ekip Arayüzü

### [[10.1_arayuz_gereksinimleri|10.1 Arayüz gereksinimleri]]
### [[10.2_teknoloji_secenekleri|10.2 Teknoloji seçenekleri]]
### [[10.3_arama_ve_sorgulama_motoru|10.3 Arama ve sorgulama motoru]]
### [[10.4_onboarding_stratejisi|10.4 Onboarding stratejisi]]
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
*Sonraki adım: Her başlık için ayrı detay .md dosyası (CLI agent ile)*