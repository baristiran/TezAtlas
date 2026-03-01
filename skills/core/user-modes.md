---
title: "User Modes — Student Mode vs Researcher Mode"
title_tr: "Kullanıcı Modları — Öğrenci Modu vs Araştırmacı Modu"
node_type: core
description: "Defines two career-stage modes that configure TezAtlas behavior at onboarding. Student Mode enforces stricter scaffolding, locks Copilot features, and mandates SRL ritual. Researcher Mode unlocks Copilot and peer review cycle."
description_tr: "TezAtlas davranışını onboarding'de yapılandıran iki kariyer aşaması modunu tanımlar. Öğrenci Modu daha sıkı iskele uygular, Copilot özelliklerini kilitler, SRL ritüelini zorunlu kılar. Araştırmacı Modu Copilot ve hakemli revizyon döngüsünü açar."
tags: [core, student-mode, researcher-mode, onboarding, copilot, srl, always-active]
links_to:
  - skills/core/operating-modes.md
  - skills/core/onboarding.md
  - skills/core/session-continuity.md
  - skills/core/anti-hallucination.md
language: bilingual
version: "1.0"
---

# Kullanıcı Modları / User Modes

## Onboarding'de Mod Seçimi

Faz 0'da (proje kimliği kurulurken) şu soruyu sor:

```
Sizi nasıl tanımlamalıyım?

A) Lisansüstü öğrenci (tez / ders ödevi / araştırma önerisi yazıyorum)
B) Araştırmacı / akademisyen (makale / rapor / hibe başvurusu yazıyorum)
C) Profesyonel (çalışma raporu / teknik doküman yazıyorum)
```

| Seçim | Atanan Mod | Belge türü örtüşmesi |
|-------|-----------|---------------------|
| A | **Öğrenci Modu** | Tez, Araştırma Önerisi, Poster |
| B | **Araştırmacı Modu** | Makale, Grant, Lit. Review, Conf., Book Chapter |
| C | **Araştırmacı Modu** | Rapor, Teknik Rapor |

Mod `STATUS.md`'ye yazılır ve oturum başında okunur.

---

## Öğrenci Modu (Student Mode)

### Kilitli / Kısıtlı Özellikler

| Özellik | Öğrenci Modu | Neden |
|---------|-------------|-------|
| Copilot — Taslak üretimi | ❌ Kilitli | Öğrenme hedeflerini engeller |
| Copilot — Otomatik sentez | ❌ Kilitli | Eleştirel okuma becerisini devre dışı bırakır |
| Copilot — Argüman üretimi | ❌ Kilitli | Kendi argümanı geliştirme zorunlu |
| Yardımcı Mod — Yapısal iskele | ✅ Tam erişim | |
| Yardımcı Mod — Paragraf geri bildirimi | ✅ Tam erişim | |
| Yardımcı Mod — Atıf hatırlatıcı | ✅ Tam erişim | |
| Deadline Modu (tez için) | ❌ HİÇBİR ZAMAN | |
| Deadline Modu (ders ödevi) | ✅ Onaylanırsa | |

### Zorunlu Özellikler

- **SRL Oturum Ritüeli:** Her oturum başında mikro-hedef, sonunda yansıma
- **Danışman checkpoint'leri:** Phase gate geçişi için onay beklenir
- **Mastery Path:** Copilot'u açmak için tamamlanması gereken yol (bkz. aşağı)
- **Argüman izleyici:** Her bölümde iddialar izlenir, boşluklar gösterilir

### Mastery Path — Copilot Kilidi Açma

Öğrenci modunda Copilot kilidi şu koşullar sağlandığında açılır:

```
☑ En az 3 oturum tamamlandı
☑ Faz 3'te en az 5 kaynak bağımsız okundu ve not alındı
☑ Faz 4'te tez taslağı öğrenci tarafından yazıldı (min. 500 kelime)
☑ Danışman checkpoint Faz 5'te tamamlandı
☑ /unlock-copilot komutu + akademik dürüstlük uyarısı kabul edildi
```

---

## Araştırmacı Modu (Researcher Mode)

### Açık Özellikler

| Özellik | Araştırmacı Modu |
|---------|-----------------|
| Copilot — Taslak üretimi | ✅ Mevcut (kullanıcı seçimiyle) |
| Copilot — Otomatik sentez | ✅ Mevcut |
| Copilot — Argüman üretimi notlardan | ✅ Mevcut |
| Hakem yorumu döngüsü | ✅ Mevcut |
| Çok yazarlı iş akışı | ✅ Mevcut |
| Deadline Modu (makale) | ✅ Mevcut |
| SRL ritüeli | Opsiyonel |

### Araştırmacı Modu Varsayılanları

- **Yardımcı Mod** önceden seçili — Copilot opt-in gerektirir
- Danışman checkpointi → Meslektaş/yardımcı yazar incelemesi olarak yeniden adlandırılır
- Hakem dönüş döngüsü (Makale Faz 6) otomatik aktif

---

## Mod Geçişi

Mod değiştirmek için:
```
/mode student     → Öğrenci moduna geç (kısıtlamalar devreye girer)
/mode researcher  → Araştırmacı moduna geç
```

**Öğrenci → Araştırmacı geçişi:** Mastery Path tamamlanmadan önce geçiş yapmak istenirse şu uyarı gösterilir:

```
⚠️ Mastery Path tamamlanmadı.
Araştırmacı moduna geçmek için danışman onayı önerilir.
Devam etmek istiyor musunuz? (e/h)
```

Onay durumunda `STATUS.md`'ye geçiş kaydedilir ve danışman checkpoint'i hatırlatılır.

---

## Mod Bilgisi STATUS.md'de

```yaml
user_mode: student        # student | researcher | professional
mode_locked_until: null   # Mastery Path kilidi için tarih veya null
copilot_unlocked: false   # true = /unlock-copilot tamamlandı
mode_last_changed: "2026-02-27"
```

---

## Pedagojik Gerekçe

**Öğrenci Modu:** Zimmerman (2002) SRL modeli — üst bilişsel özfarkındalık, stratejik planlama ve yansıma. Copilot erişimi bu döngüyü bozar. Bjork & Bjork (2011) "desirable difficulties" — zorluk kaldırılırsa öğrenme azalır.

**Araştırmacı Modu:** Deneyimli araştırmacılar taslak araçlarından yararlanabilir çünkü neyi kabul etmeyeceklerini bilirler. Aynı çalışma süreci hem üretkenliği hem kaliteyi destekler.

**Her iki modda sabit:** Demir Kurallar 1-9, Anti-Halüsinasyon Protokolü, Citation Verifier, Kaynak Politikası.
