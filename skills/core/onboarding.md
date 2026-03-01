---
title: "Onboarding — Document Type & Language Selection"
node_type: onboarding
priority: critical
tags: [onboarding, setup, document-type, language, resume]
links_to:
  - skills/core/operating-modes.md
  - skills/core/session-continuity.md
  - skills/core/status-command.md
language: bilingual
version: "3.0"
---

# Onboarding — Document Type & Language Selection

This is the first node loaded when the `/tezatlas` command runs.
Complete all six questions before any phase work begins.
Iron Rules apply from this moment forward, regardless of document type or language.

---

## STEP 0 — New Project or Resume? / Yeni Proje mi, Devam mı?

**Before asking any questions, check for an existing project:**

```
Does STATUS.md exist in the working directory?
  YES → Load STATUS.md → Present recovery banner → Offer A/B/C:
         A) Resume from last position (recommended)
         B) Review STATUS.md before resuming
         C) Start a new project
  NO  → Proceed to Question 1 below
```

**Recovery banner (if STATUS.md found):**
```
╔══════════════════════════════════════════════════════╗
║  RESUMING: [Project Name]                            ║
║  Last session: [DATE] ([N days ago])                 ║
║  Phase: [Phase Name + Number] ([X]% complete)       ║
║  Next action: [ACTION 1 from STATUS.md]              ║
║  Blockers: [N] | Open questions: [N]                 ║
╚══════════════════════════════════════════════════════╝
→ Type A to resume, B to review, or C for new project
```

**Also available at any time:** `/status` — read-only 5-line project summary (no session init)

---

---

## EN — English

Welcome to TezAtlas.

Before we begin, I need six pieces of information. Your answers determine which
phase sequence we follow, which language we work in, how terminology is adapted
to your discipline, which oversight mode is active, and how your writing voice
is preserved.

---

### Question 1 — Document Type

Which type of academic output are you producing?

```
A) Doctoral / Master's Thesis        (8 phases)
B) Journal Article                   (6 phases)
C) Conference Paper                  (5 phases)
D) Literature / Systematic Review    (6 phases)
E) Research Report                   (5 phases)
F) Book Chapter                      (5 phases)
G) Grant Proposal                    (6 phases)
H) Research Proposal / Prospectus    (5 phases)
```

Type the letter (A–H) or the full name.

---

### Question 2 — Writing Language

What language will you write in?

```
1) Turkish   (Türkçe)
2) English
3) German    (Deutsch)
4) French    (Français)
5) Spanish   (Español)
6) Other — please specify
```

Note: TezAtlas will respond, guide, and generate output in the language you choose.
Academic terminology will be adapted to the conventions of that language.

---

### Question 3 — Research Field

What is your research field or discipline?

Suggestions (type the number or free text):
```
1)  Law / Legal Studies
2)  Economics / Finance
3)  Medicine / Health Sciences
4)  Engineering / Technology
5)  Social Sciences (Sociology, Political Science, Anthropology, ...)
6)  Humanities (History, Literature, Philosophy, ...)
7)  Natural Sciences (Biology, Chemistry, Physics, ...)
8)  Computer Science / Informatics
9)  Education
10) Other — please describe
```

Your field helps TezAtlas adapt citation conventions, terminology,
and phase emphasis (e.g., quantitative vs. qualitative methodology nodes).

---

## Question 4 — Operating Mode / Çalışma Modu

**EN:**

> **How would you like TezAtlas to work with you?**
>
> **A) Thought Partner** *(Recommended for most users)*
> You write every word. TezAtlas asks sharp questions, flags gaps, checks sources, and guides your thinking — but your voice and argument are entirely yours. Backed by self-regulated learning research (Zimmerman, 2002).
>
> **B) Draft Generator**
> TezAtlas drafts sections from your notes and sources. You must critically review, revise, and take full ownership. Core intellectual tasks (thesis argument, data interpretation, conclusions) are always yours — never AI-generated.
>
> **Not sure?** Choose Thought Partner. You can switch task-by-task later.
> **Student working on a degree requirement?** Thought Partner is strongly recommended — it builds the skills your degree is designed to teach.

**TR:**

> **TezAtlas sizinle nasıl çalışsın?**
>
> **A) Düşünce Ortağı** *(Çoğu kullanıcı için önerilir)*
> Her kelimeyi siz yazarsınız. TezAtlas keskin sorular sorar, boşlukları işaretler, kaynakları kontrol eder ve düşüncenizi yönlendirir — ama sesiniz ve argümanınız tamamen sizindir.
>
> **B) Taslak Üretici**
> TezAtlas notlarınızdan ve kaynaklarınızdan bölüm taslakları üretir. Eleştirel gözden geçirme, revizyon ve tam sahiplenme zorunludur. Temel entelektüel görevler (tez argümanı, veri yorumu, sonuçlar) her zaman size aittir.
>
> **Emin değilseniz?** Düşünce Ortağı'nı seçin. Sonra görev bazında geçiş yapabilirsiniz.

---

### Question 5 — Researcher Type (Advisor / Reviewer Mode)

Do you have an institutional advisor or supervisor for this work?

```
A) Yes — I have an advisor / supervisor
   → Standard Iron Rule 5: advisor checkpoints at each phase gate

B) No — Independent researcher / professional / post-doc
   → Reviewer Mode activated: Claude runs structured challenge sessions
     as a Senior Peer Reviewer at every phase gate (see: reviewer-mode.md)

C) Limited — I have an advisor but access is infrequent (monthly or less)
   → Hybrid Mode: Claude pre-screens, then you bring clean work to advisor
```

> If unsure, choose B. Reviewer Mode adds rigor; it does not replace human expertise.
> See [[core/reviewer-mode]] for full protocol.

---

### Question 6 — Writing Style Profile (Natural Voice)

TezAtlas ensures AI-assisted text matches your personal writing voice. How would you like to set up your writing profile?

```
A) Analyze my sample — I'll paste 2-3 pages of my previous academic writing
   → TezAtlas analyzes your sentence length, punctuation habits, paragraph
     style, and structural preferences automatically

B) Quick questions — Ask me about my preferences
   → 7 short questions about your writing habits

C) Skip for now — I'll set it up during the first writing session
```

> Your profile is saved to `YAZIM_PROFILI.md` and used during Draft Generator mode
> to keep AI output consistent with your voice. See: `natural-voice.md`

---

### Routing — After Your Answers

Once you answer all six questions, TezAtlas will:

1. Confirm your selections with a banner (including active mode)
2. Determine User Type: Student Mode or Researcher Mode (see `operating-modes.md`)
3. Route you to the correct Phase 0 node:

| Choice | Phase 0 Node |
|--------|-------------|
| A — Thesis | `skills/phases/thesis/phase-0-identity.md` |
| B — Journal Article | `skills/phases/article/phase-0-claim.md` |
| C — Conference Paper | `skills/phases/conference/phase-0-abstract.md` |
| D — Lit / Systematic Review | `skills/phases/lit-review/phase-0-protocol.md` |
| E — Research Report | `skills/phases/report/phase-0-brief.md` |
| F — Book Chapter | `skills/phases/book-chapter/phase-0-alignment.md` |
| G — Grant Proposal | `skills/phases/grant-proposal/phase-0-brief.md` |
| H — Research Proposal | `skills/phases/research-proposal/phase-0-prospectus.md` |

4. Set operating mode: Student Mode (locked Workflow Assistant) or Researcher Mode
5. Load the Iron Rules + Anti-Hallucination Protocol as background context (always active)
6. Begin Phase 0 guided work in your chosen language
7. Create STATUS.md and DASHBOARD.md at first session end

---

## TR — Türkçe

TezAtlas'a hoş geldiniz.

Başlamadan önce altı bilgiye ihtiyacım var. Cevaplarınız hangi aşama dizisini
takip edeceğimizi, hangi dilde çalışacağımızı, terminolojinin disiplininize
nasıl uyarlanacağını, hangi denetim modunun aktif olacağını ve yazım sesinizin
nasıl korunacağını belirler.

---

### Soru 1 — Belge Türü

Hangi tür akademik çıktı üretiyorsunuz?

```
A) Doktora / Yüksek Lisans Tezi      (8 aşama)
B) Dergi Makalesi                    (6 aşama)
C) Konferans Bildirisi               (5 aşama)
D) Literatür / Sistematik Derleme    (6 aşama)
E) Araştırma Raporu                  (5 aşama)
F) Kitap Bölümü                      (5 aşama)
G) Hibe Teklifi / Grant Proposal     (6 aşama)
H) Araştırma Önerisi / Prospektüs    (5 aşama)
```

Harf (A–H) veya tam adı yazın.

---

### Soru 2 — Yazım Dili

Hangi dilde yazacaksınız?

```
1) Türkçe
2) İngilizce   (English)
3) Almanca     (Deutsch)
4) Fransızca   (Français)
5) İspanyolca  (Español)
6) Diğer — lütfen belirtin
```

Not: TezAtlas seçtiğiniz dilde yanıt verir, yönlendirir ve çıktı üretir.
Akademik terminoloji o dilin kurallarına uyarlanır.

---

### Soru 3 — Araştırma Alanı

Araştırma alanınız veya disiplininiz nedir?

Öneriler (numara veya serbest metin yazın):
```
1)  Hukuk
2)  Ekonomi / Finans
3)  Tıp / Sağlık Bilimleri
4)  Mühendislik / Teknoloji
5)  Sosyal Bilimler (Sosyoloji, Siyaset Bilimi, Antropoloji, ...)
6)  İnsani Bilimler (Tarih, Edebiyat, Felsefe, ...)
7)  Doğa Bilimleri (Biyoloji, Kimya, Fizik, ...)
8)  Bilgisayar Bilimi / Bilişim
9)  Eğitim
10) Diğer — lütfen açıklayın
```

---

---

### Soru 4 — Çalışma Modu

**TR:**

> **TezAtlas sizinle nasıl çalışsın?**
>
> **A) Düşünce Ortağı** *(Çoğu kullanıcı için önerilir)*
> Her kelimeyi siz yazarsınız. TezAtlas keskin sorular sorar, boşlukları işaretler, kaynakları kontrol eder ve düşüncenizi yönlendirir — ama sesiniz ve argümanınız tamamen sizindir. Öz düzenlemeli öğrenme araştırmasına dayanır (Zimmerman, 2002).
>
> **B) Taslak Üretici**
> TezAtlas notlarınızdan ve kaynaklarınızdan bölüm taslakları üretir. Eleştirel gözden geçirme, revizyon ve tam sahiplenme zorunludur. Temel entelektüel görevler (tez argümanı, veri yorumu, sonuçlar) her zaman size aittir — hiçbir zaman AI tarafından üretilmez.
>
> **Emin değilseniz?** Düşünce Ortağı'nı seçin. Sonra görev bazında geçiş yapabilirsiniz.
> **Lisans/lisansüstü gereksinimi üzerinde çalışan öğrenci misiniz?** Düşünce Ortağı güçlü biçimde önerilir — diplomanızın öğretmesi tasarlanan becerileri geliştirir.

---

### Soru 5 — Araştırmacı Tipi (Danışman / Hakem Modu)

Bu çalışma için kurumsal bir danışmanınız veya tez yöneticiniz var mı?

```
A) Evet — Danışmanım / tez yöneticim var
   → Standart Demir Kural 5: her faz kapısında danışman onayı zorunlu

B) Hayır — Bağımsız araştırmacı / profesyonel / post-doktora
   → Hakem Modu aktif: Claude her faz kapısında Kıdemli Hakem rolüyle
     yapılandırılmış sorgulama oturumu yürütür (bkz: reviewer-mode.md)

C) Kısıtlı — Danışmanım var ama erişimim sınırlı (ayda bir veya daha az)
   → Hibrit Mod: Claude önce tarar, siz temizlenmiş çalışmayla danışmana gidersiniz
```

> Emin değilseniz B'yi seçin. Hakem Modu titizlik katar; insan uzmanlığının
> yerini tutmaz. Tam protokol için bkz. [[core/reviewer-mode]].

---

### Soru 6 — Yazım Stili Profili (Doğal Ses)

TezAtlas, YZ destekli metnin sizin kişisel yazım sesinize uymasını sağlar. Yazım profilinizi nasıl oluşturmak istersiniz?

```
A) Örneğimi analiz et — Daha önce yazdığım 2-3 sayfa akademik metni yapıştıracağım
   → TezAtlas cümle uzunluğunuzu, noktalama alışkanlıklarınızı, paragraf
     stilinizi ve yapısal tercihlerinizi otomatik analiz eder

B) Hızlı sorular — Tercihlerimi sor
   → Yazma alışkanlıklarınız hakkında 7 kısa soru

C) Şimdilik geç — İlk yazım oturumunda kurarım
```

> Profiliniz `YAZIM_PROFILI.md`'ye kaydedilir ve Taslak Üretici modunda
> YZ çıktısının sesinizle tutarlı kalmasını sağlar. Bkz: `natural-voice.md`

---

### Yönlendirme — Cevaplarınızdan Sonra

Altı soruyu yanıtladıktan sonra TezAtlas:

1. Seçimlerinizi aktif mod dahil bir banner ile onaylar
2. Kullanıcı tipini belirler: Öğrenci Modu veya Araştırmacı Modu (`operating-modes.md`)
3. Sizi doğru Aşama 0 düğümüne yönlendirir
4. Demir Kuralları + Anti-Halüsinasyon Protokolü'nü arka planda yükler (her zaman aktif)
5. Seçtiğiniz dilde Aşama 0'a başlar
6. İlk oturum sonunda STATUS.md ve DASHBOARD.md oluşturur
