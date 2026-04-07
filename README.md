# Narada — Jagdishwaram Foundation Transparency Portal

**narada.jagdishwaram-office.org**

A public accountability portal tracking government RTI responses on institutional pendency
data. Each dashboard corresponds to one RTI application filed with a government authority.

---

## Live Dashboards

| Dashboard | Authority | RTI Reference | Status |
|---|---|---|---|
| [Palghar District Easement Case Pendency](palghar-mca/) | District Collector, Palghar | RTI/DC-PGH/2026/001 | Filing in progress |

---

## How to Update a Dashboard (After RTI Response)

1. Open `data/palghar-mca/rti_001.json`
2. Update the `meta` block:
   - Set `rti_filed_date` to actual filing date (YYYY-MM-DD)
   - Set `rti_response_due` to 30 days from filing
   - Set `status` to `"RTI_FILED"`, then `"RESPONSE_RECEIVED"`, then `"DATA_PUBLISHED"`
3. When response arrives, populate each taluka's `sec5` and `sec23` objects
4. Commit to `main` branch — Cloudflare Pages auto-deploys in ~60 seconds

**Status values:** `RTI_BEING_FILED` → `RTI_FILED` → `RTI_OVERDUE` (if no response) → `RESPONSE_RECEIVED` → `DATA_PUBLISHED`

---

## Data Schema

```json
{
  "sec5": {
    "total_filed": 68,
    "pending": 41,
    "disposed": 27,
    "avg_age_days": 612,
    "over_1yr_pct": 62
  }
}
```

---

## RTI Application Template

**[For copy into Chitragupta / draft.py]**

---

```
प्रति,                                                    दिनांक: [DATE]
मा. जन माहिती अधिकारी,
जिल्हाधिकारी कार्यालय, पालघर जिल्हा,
पालघर — ४०१ ४०१, महाराष्ट्र

विषय: माहिती अधिकार अधिनियम २००५ कलम ६ अन्वये माहिती मागणी —
       पालघर जिल्ह्यातील ममलतदार न्यायालय अधिनियम कलम ५ व कलम २३
       अंतर्गत प्रकरणांची तालुकानिहाय प्रलंबितता व निकाली अहवाल

महोदय/महोदया,

अर्जदार: जगदिश्वरम् फाउंडेशन, वसई, जिल्हा पालघर
संपर्क: ashish.j.naik@jagdishwaram-office.org

मी माहिती अधिकार अधिनियम २००५ च्या कलम ६(१) अन्वये खालील माहिती मागवत आहे:

माहिती मागणी:

१. पालघर जिल्ह्यातील प्रत्येक तालुक्यामध्ये (पालघर, वसई, डहाणू, तलासरी, वाडा,
   विक्रमगड, जव्हार, मोखाडा) ममलतदार न्यायालय अधिनियम १९०६ च्या कलम ५
   अन्वये दाखल, प्रलंबित व निकाली प्रकरणांची संख्या (दि. ०१/०४/२०२० ते
   दि. ३१/०३/२०२६ या कालावधीसाठी).

२. वरील प्रत्येक तालुक्यासाठी ममलतदार न्यायालय अधिनियम १९०६ च्या कलम २३
   (SDO स्तर) अन्वये दाखल, प्रलंबित व निकाली प्रकरणांची संख्या.

३. प्रत्येक तालुक्यासाठी सरासरी प्रकरण निपटारा कालावधी (दिवसांमध्ये).

४. एक वर्षापेक्षा अधिक काळ प्रलंबित असलेल्या प्रकरणांची टक्केवारी किंवा संख्या.

५. उपलब्ध असल्यास — प्रकरणनिहाय कारणाश्रेणीनुसार (अडथळे हटवणे, ताबा
   प्रदान, स्थिती-कायम इ.) वर्गीकरण.

कारण: हे विश्लेषण जगदिश्वरम् फाउंडेशनच्या "नारद पारदर्शकता दर्शक" या
सार्वजनिक उत्तरदायित्व प्रकल्पासाठी आहे, जो पालघर जिल्ह्यातील ममलतदार
न्यायालय प्रकरणांच्या सांस्थानिक विलंबाचे सार्वजनिकरीत्या मोजमाप करतो.
हे माहिती प्रकटीकरण RTI अधिनियम २००५ च्या कलम ४(१)(b) अन्वये
अनिवार्य आहे.

विनंती आहे की ३० दिवसांच्या वैधानिक मुदतीत उत्तर द्यावे.

आपला विश्वासू,
Ashish Jagdish Naik
जगदिश्वरम् फाउंडेशन, वसई
ashish.j.naik@jagdishwaram-office.org

संलग्न: IPO / Court Fee — ₹10/-
```

---

## About Jagdishwaram Foundation

Filed by: **Ashish Jagdish Naik** | ashish.j.naik@jagdishwaram-office.org
Mission: Making institutional delays in Maharashtra's revenue, judicial, and civic bodies
measured, mapped, and impossible to ignore — through RTI, data, and public accountability.

सत्यमेव जयते | Vasai, Palghar, Maharashtra
