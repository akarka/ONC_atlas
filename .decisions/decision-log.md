# Decision Log

### 2026-04-09: Bölüm 2 Konsolidasyonu (İsimlendirme ve Kodlama)
- **Summary:** 2.1, 2.2, 2.3 ve 2.4 maddeleri "İsimlendirme ve Kodlama Standartları" altında tek maddede birleştirildi. 20 yıllık arşiv (Legacy) için metadata zorunluluğu esnetilerek "Active/Legacy" ayrımı getirildi. 2.5 maddesi 2.2 olarak re-numaralandırıldı.
- **Affected Files:**
  - `ONC_atlas_outline.md`
  - `Atlas_Maddeler/2.1_isimlendirme_ve_kodlama_standartlari.md` (Yeni)
  - `Atlas_Maddeler/2.2_gecici_ve_calisma_dosyalari_kurali.md` (Güncellendi)
  - `Atlas_Maddeler/2.1...2.4...` (Silindi)

### 2026-04-10: RDBMS (PostgreSQL) Mimarisine Geçiş
- **Summary:** Sistemin operasyonel yönetimi için merkezi bir ilişkisel veritabanı (PostgreSQL) kullanılmasına karar verildi. `Projects` ve `Assets` tabloları için çekirdek şemalar tanımlandı. NAS üzerindeki YAML dosyaları ile DB arasında UUID tabanlı bir senkronizasyon (Hybrid/Sync) modeli kurgulandı.
- **Affected Files:**
  - `Atlas_Maddeler/6.1_metadata_mimarisi_kararlari.md`
  - `Atlas_Maddeler/6.2_ana_proje_kunyesi_onc_project_yaml.md`
  - `Atlas_Maddeler/6.5_iliski_ve_baglanti_modeli.md`
  - `Atlas_Maddeler/10.2_teknoloji_secenekleri.md`

### 2026-04-10: DWGPROPS ve SSM Tabanlı Varlık Takibi
- **Summary:** "Save As" kaynaklı dosya ismi değişikliklerini takip edebilmek için `DWGPROPS` (Custom Properties) içine UUID gömme stratejisi benimsendi. Veritabanında "Mantıksal Varlık" (Logical Asset) ve "Fiziksel Dosya" (Physical Asset) ayrımı yapılarak varlık soyağacı (lineage) korundu. C# ile geliştirilen `ssm-editor` aracılığıyla `.dst` (Sheet Set) dosyalarının bu verilerle otomatik güncellenmesi planlandı.
- **Affected Files:**
  - `Atlas_Maddeler/6.3_gomulu_pafta_ve_varlik_listesi.md`
  - `Atlas_Maddeler/6.5_iliski_ve_baglanti_modeli.md`
