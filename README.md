# COSMIC Projects - NCP Wallonie Demo (Nov 2025)

**For**: Melina (NCP Wallonie) - Event 13-14 November 2025
**From**: Vincent Caputo (FFT.io) + Frédérique Fourez (Lead CJEU Formation)
**Context**: Horizon Europe application + Cloud Credits Blitzkrieg Strategy

---

## 🎯 Double Objectif : NCP Demo + Blitzkrieg Faisabilité

### 1️⃣ **Démo Faisabilité Technique (NCP Wallonie)**
**Objectif**: Prouver que les 4 projets COSMIC sont **techniquement réalisables** avec ressources existantes FFT.io

**Preuves tangibles**:
- ✅ **COSMIC-1 RAG** : BelgBERT prototype (3 langues FR/NL/DE) - Corpus ready
- ✅ **COSMIC-2 AgriSurvey** : LoRaWAN proto (10 sensors Liège campus)
- ✅ **COSMIC-3 CitizenHub** : Platform architecture (Next.js + Azure Cosmos)
- ✅ **COSMIC-4 Econergy** : Smart grid monitoring (Prophet forecasting)

**Infrastructure disponible**:
- Mac Studio M1 Max 32GB (24/7, ARM64-optimized)
- Hetzner dedicated servers (EU, GDPR-compliant)
- Ollama local inference (<0.5s latency)
- LoRaWAN gateways (Belgium network)

### 2️⃣ **Stratégie Blitzkrieg 536K€ Crédits Cloud**
**Objectif**: Démontrer capacité à **brûler 536K€ de crédits cloud** en 6 mois (Dec 2025-Mai 2026) puis **migrer vers infrastructure EU souveraine** (Jun 2026)

**Timeline Blitzkrieg**:
```
16 Nov 2025  → Activation 536K€ crédits (Microsoft 138K, Google 230K, AWS 92K, NVIDIA 76K)
Dec 2025     → Setup infrastructure + BelgBERT data prep (burn €40K)
Jan-Apr 2026 → Training Phase 1 (3 langues) + Pilots (burn €270K)
Mai 2026     → Training Phase 2 (24 langues) + Scale (burn €226K final)
Jun-Jul 2026 → Migration hardware propre (€18K one-time investment)
Aug 2026     → 100% European Sovereignty ✅ (zero US cloud dependency)
```

**Économie réelle**: 365K€ appliqués aux projets COSMIC = **-35.6% coût infrastructure**

---

## 📂 Structure du Repo

```
ncp-cosmic-demo/
├── README.md                          (ce fichier - index principal)
├── docs/
│   ├── gists/                         (3 documents principaux)
│   │   ├── COSMIC-Ethics-GDPR.md      (286 lignes - GDPR + AI Ethics)
│   │   ├── FFT-Vision-Complete.md     (810 lignes - Architecture hybride)
│   │   └── FFT-Deployment-Options.md  (1075 lignes - SaaS/Node/LoRaWAN)
│   │
│   ├── sheets/                        (4 Google Sheets interactifs)
│   │   ├── 01-Budget-Consolide.csv    (Budget 1.1M€ + 536K crédits)
│   │   ├── 02-Planning-Timeline.csv   (Roadmap 2026-2028)
│   │   ├── 03-Ressources-Team.csv     (Team matrix 18 rôles)
│   │   └── 04-KPIs-Metrics.csv        (60+ métriques SMART)
│   │
│   ├── gantt/                         (Visualisation timeline)
│   │   ├── COSMIC-Roadmap.mmd         (Mermaid Gantt chart)
│   │   └── Blitzkrieg-6-Months.mmd    (Dec 2025-Jun 2026)
│   │
│   └── demo/                          (Assets pour présentation NCP)
│       ├── architecture-diagram.mmd   (Architecture technique)
│       ├── decision-tree.mmd          (Quelle option choisir)
│       └── pitch-deck-outline.md      (Structure pitch 13-14 Nov)
│
└── exports/                           (Formats portables)
    ├── COSMIC-Complete-Package.pdf    (Tout-en-un exportable)
    └── data/                          (CSV bruts pour import Excel/Sheets)
```

---

## 📊 Documents Clés (Quick Access)

### 1. **COSMIC Ethics & GDPR** ([docs/gists/COSMIC-Ethics-GDPR.md](docs/gists/COSMIC-Ethics-GDPR.md))
**Contenu**: 
- GDPR compliance détaillée (data minimization, rights implementation)
- AI Ethics & Algorithmic Transparency (BelgBERT, Prophet)
- Data Sovereignty Architecture (100% EU by Aug 2026)
- Security & Privacy Measures (1Password, Tailscale, E2E encryption)
- Human Oversight & Accountability (99% autonomy, 0.1% human intervention)

**Audience**: NCP Wallonie reviewers, ethics committee, GDPR officers

---

### 2. **FFT Vision Complète** ([docs/gists/FFT-Vision-Complete.md](docs/gists/FFT-Vision-Complete.md))
**Contenu**:
- Architecture hybride (SaaS + Node Local + LoRaWAN)
- Cas d'usage détaillés (CJEU Formation, AgriTech, SmartCity, LegalTech)
- FFT Tournai Hub (Mac Studio M1 Max flagship node)
- Pricing models (€5-€150/mois SaaS, €110-€8K hardware)
- Stratégie Blitzkrieg 536K€ cloud credits

**Audience**: Decision-makers, technical leads, investors

---

### 3. **FFT Deployment Options** ([docs/gists/FFT-Deployment-Options.md](docs/gists/FFT-Deployment-Options.md))
**Contenu**:
- Option A: SaaS Cloud Hetzner (€16.90/mois, 10-200 users)
- Option B: Node Local (€110-€8K hardware, sovereignty totale)
- Option C: LoRaWAN + IPFS (distributed, IoT/AgriTech/SmartCities)
- TCO Comparison (3 options sur 36 mois)
- Migration paths (cloud → hardware seamless)

**Audience**: Clients finaux, intégrateurs, partners techniques

---

### 4. **Google Sheets Interactifs**

#### Sheet 1: Budget Consolidé ([docs/sheets/01-Budget-Consolide.csv](docs/sheets/01-Budget-Consolide.csv))
- **Total**: 1,101,400€ (24 mois)
- **Personnel**: 765,000€ (69.6%)
- **Infrastructure**: 128,000€ net (après 365K€ crédits cloud)
- **Financement HE**: 660,840€ demandé (60%)
- **In-kind FFT**: 365,000€ crédits cloud (33.1%)

#### Sheet 2: Planning & Timeline ([docs/sheets/02-Planning-Timeline.csv](docs/sheets/02-Planning-Timeline.csv))
- **Phase 0**: Préparation (Nov-Dec 2025) - Activation crédits
- **Phase 1**: Foundation (Jan-Apr 2026) - First pilots
- **Phase 2**: Scaling + Exit Cloud (Mai-Aug 2026)
- **Phase 3**: Optimization (Sep-Dec 2026)
- **Phase 4**: Maturity (2027)

#### Sheet 3: Ressources & Compétences ([docs/sheets/03-Ressources-Team.csv](docs/sheets/03-Ressources-Team.csv))
- **Total**: 118 person-months
- **ULiège**: 45 PM (researchers, domain experts)
- **CETIC**: 40 PM (engineers, DevOps, IoT)
- **FFT.io**: 33 PM (AI/ML, frontend, innovation)

#### Sheet 4: KPIs & Métriques ([docs/sheets/04-KPIs-Metrics.csv](docs/sheets/04-KPIs-Metrics.csv))
- **Technical**: BelgBERT F1 0.92, API <200ms, uptime 99.9%
- **Scale**: 100 sensors, 50 farms, 10 municipalities, 75 buildings
- **Business**: €500K revenue, €2M cost savings, 5K tons CO2 reduced
- **Research**: 3 academic papers, 3 open-source releases

---

## 🎯 Pitch NCP Wallonie (13-14 Nov 2025)

### Key Messages

**1. Faisabilité Technique Prouvée**
> "Nous avons déjà l'infrastructure, les compétences et les prototypes. Les 4 projets COSMIC ne sont pas des concepts : ce sont des applications réelles prêtes à scaler."

**Preuves**:
- Mac Studio M1 Max opérationnel 24/7 (ARM64-native, <0.5s latency)
- BelgBERT corpus ready (150K EPCs Belgian, FR/NL/DE)
- LoRaWAN network deployed (Liège campus, 10 sensors proto)
- CJEU Formation live (30 students, real production system)

---

**2. Stratégie Blitzkrieg = Window Closing**
> "NVIDIA +25% en 3 mois ($4T→$5T) = AI Bubble peak. Cloud credits disponibles NOW, fermeront Q2 2026. FFT active samedi 16 Nov (536K€), burn 6 mois, exit cloud Jun 2026 = 100% souveraineté européenne."

**Timeline critique**:
- ✅ 16 Nov : Activation 536K€ (Microsoft 138K, Google 230K, AWS 92K)
- ✅ Dec-Mai : Aggressive burn (€90K/mois training BelgBERT + scaling)
- ✅ Jun-Jul : Migration hardware propre (€18K one-time)
- ✅ Aug 2026 : Zero US cloud dependency, €460/mois sustainable forever

---

**3. Économie Réelle = -35.6% Coûts Infrastructure**
> "Les 536K€ de crédits cloud ne sont pas du 'nice-to-have' : c'est une contribution in-kind FFT.io valorisable (365K€ appliqués aux projets COSMIC). Financement HE demandé réduit de 1.02M€ à 660K€."

**Leverage effect**:
- 1€ cash ULiège génère **3.33€ valeur totale** (440K€ → 1.47M€)
- 33% du budget total = contribution in-kind FFT.io (crédits cloud)
- ROI immédiat : 0€ cash FFT invested, 365K€ value delivered

---

**4. Anti-Fragile Stack = Last Man Standing Post-Bubble**
> "Quand OpenAI et Mistral feront faillite en 2026-2027 (burn rates insoutenables), FFT sera le dernier debout. Open-source only (Ollama, DeepSeek, Kubernetes), hardware owned, zero US dependency."

**Principe**:
- ❌ Mistral : Bulle VC, US investors dominant, faillite probable 2026
- ❌ OpenAI : $200+/mois API, $2B/year burn, faillite si bulle éclate
- ✅ FFT : Open-source MIT/Apache 2.0, portable stack, hardware €18K owned

---

**5. 100% European Sovereignty by Aug 2026**
> "Production GDPR (Hetzner EU), exit cloud US (Jun 2026), data sovereignty 100%, zero vendor lock-in. C'est ça la vraie souveraineté européenne."

**Architecture**:
```
Phase 1 (Dec 2025-Mai 2026): Hybrid
  ├─ Production: Hetzner EU (GDPR, sovereignty)
  ├─ Dev/Test: Azure/Google/AWS (crédits gratuits)
  └─ Training: Google TPU v4 (230K€ credits BelgBERT)

Phase 2 (Jun 2026+): 100% EU
  ├─ Mac Studio M2 Ultra (€8K, Bruxelles)
  ├─ Hetzner AX102 x2 (€10K, Helsinki Finland)
  └─ Cost: €460/month sustainable forever ♾️
```

---

## 🔥 Démo Live (Optionnel NCP Event)

Si Melina veut une **démo technique live** (5-10 min) :

### Option 1: BelgBERT Inference (NLP Multilingual)
```bash
# Local Mac Studio M1 Max
curl -X POST http://localhost:11435/api/generate \
  -d '{
    "model": "belgbert-3lang-proto",
    "prompt": "Recommandations cultures maïs Wallonie 2026",
    "stream": false
  }'

# Response <500ms (sub-0.5s latency target)
```

### Option 2: LoRaWAN Sensors (IoT Real-Time)
```bash
# Live data from 10 sensors Liège campus
mosquitto_sub -h localhost -t "cosmic/sensors/#" -v

# Output: Temperature, humidity, CO2 real-time
```

### Option 3: CJEU Correction Automatique (Production)
- Interface sobre (UI Frédérique)
- Webhook GitLab → Ollama DeepSeek-R1 → Feedback AI
- <3min validation end-to-end

---

## 📧 Contact

**Vincent Caputo**  
CTO Fred French Touch / Innovation Manager FFT.io  
📧 vincent@fredfrenchtouch.com  
🔗 https://www.fredfrenchtouch.com  
🐙 https://github.com/NextAIgeneration

**Frédérique Fourez**
Lead CJEU Formation / UX Designer FFT.io
📧 frederique@fredfrenchtouch.com

---

## 📜 License & Usage

**Documentation**: CC-BY-4.0 (libre usage avec attribution)  
**Code (quand applicable)**: MIT ou Apache 2.0 (open-source)  
**Données**: Propriété ULiège + CETIC + FFT.io (consortium)

**Pour NCP Wallonie**: Usage libre pour évaluation candidature Horizon Europe

---

## 🎯 Next Steps Post-NCP Event

1. ✅ **Samedi 16 Nov**: Activation 536K€ crédits cloud (mission critique)
2. **Lundi 18 Nov**: Setup Azure Cosmos DB, Google Cloud TPUs, AWS IoT Core
3. **Dec 2025**: BelgBERT Phase 0 data prep + COSMIC sensors proto
4. **Jan 2026**: Kick-off officiel Horizon Europe (si accepté)

---

**Status**: ✅ Ready for NCP Wallonie Demo (13-14 Nov 2025)  
**Last Updated**: 12 November 2025  
**Version**: 1.0 (Blitzkrieg Edition)

---

**FFT Five Laws Compliance**: ✅ All applied
1. **Cognitive Sovereignty**: 100% EU by Aug 2026
2. **Local-First**: Mac Studio + Hetzner, zero mandatory cloud
3. **AI as Amplifier**: Not replacement, BelgBERT augments human expertise
4. **Independence**: Open-source only, portable stack
5. **Performance**: Sub-0.5s latency target achieved

**🇪🇺 European AI Sovereignty - Built in Belgium 🇧🇪**
