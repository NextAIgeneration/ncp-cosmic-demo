# Pitch Deck Outline - NCP Wallonie (13-14 Nov 2025)

**Target Duration**: 15-20 minutes
**Audience**: Melina (NCP Wallonie), Horizon Europe reviewers
**Goal**: Prove technical feasibility + Blitzkrieg strategy viability

---

## Slide 1: Title + Hook (30 seconds)

**Visual**: FFT.io logo + COSMIC Projects logos

**Text**:
> **COSMIC Projects - NCP Wallonie Demo**
> Technical Feasibility + Blitzkrieg Cloud Credits Strategy
> Vincent Caputo (CTO FFT.io) + Frédérique Fourez (Lead CJEU Formation)
> 13-14 November 2025

**Hook**: "Nous avons l'infrastructure, les compétences, et les prototypes. Et nous avons 48h pour activer 536K€ de crédits cloud."

---

## Slide 2: Le Problème (1 minute)

**Visual**: Timeline showing AI bubble + cloud pricing explosion

**Points clés**:
- 🔴 **AI Bubble Peak**: NVIDIA +25% en 3 mois ($4T→$5T)
- 🔴 **Window Closing**: Cloud credits disponibles NOW, fermeront Q2 2026
- 🔴 **European Sovereignty**: 90% infrastructure AI = US cloud dependency
- 🔴 **Cost Crisis**: OpenAI/Mistral burn rates insoutenables (faillite probable 2026-2027)

**Message**: "Si nous ne bougeons pas maintenant, nous ratons la fenêtre d'opportunité."

---

## Slide 3: La Solution - Double Objectif (1 minute)

**Visual**: Venn diagram showing NCP Demo ∩ Blitzkrieg Strategy

**1️⃣ NCP Wallonie Demo (Feasibility Proof)**
- ✅ Mac Studio M1 Max 24/7 operational
- ✅ BelgBERT corpus ready (150K EPCs Belgian FR/NL/DE)
- ✅ LoRaWAN network deployed (Liège campus proto)
- ✅ CJEU Formation production system (30 students live)

**2️⃣ Blitzkrieg Strategy (536K€ → 6 months)**
- ✅ Activation samedi 16 Nov 2025
- ✅ Burn €90K/mois (Dec-Mai)
- ✅ Exit cloud Jun 2026
- ✅ 100% European sovereignty Aug 2026

**Message**: "D'une pierre deux coups : démonstration technique + stratégie économique."

---

## Slide 4: Architecture Technique (2 minutes)

**Visual**: Architecture diagram (Mermaid flowchart)

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

**Stack Technique**:
- BelgBERT (3 langues → 24 langues EU)
- Ollama local inference (<0.5s latency)
- Kubernetes (Traefik + 1Password + Tailscale)
- LoRaWAN + IPFS (distributed sovereignty)

**Message**: "Architecture anti-fragile : dernier debout post-bubble."

---

## Slide 5: Budget Consolidé (2 minutes)

**Visual**: Pie chart + Table from Sheet 1

**Total**: 1,101,400€ (24 mois)
- Personnel (69.6%): 765,000€
- Infrastructure net (11.6%): 128,000€ (après -365K€ crédits cloud)
- Déplacements (8.2%): 90,000€
- Autres coûts (10.8%): 118,400€

**Financement**:
- Contribution ULiège (40%): 440,560€
- **In-kind crédits cloud FFT (33.1%): 365,000€** ⬅️ **Clé!**
- Financement HE demandé (60%): 660,840€

**Leverage Effect**:
- 1€ cash ULiège génère **3.33€ valeur totale** (440K€ → 1.47M€)
- FFT investit 0€ cash, apporte 365K€ value (ROI infini)

**Message**: "Les crédits cloud = contribution in-kind valorisable. Financement HE réduit de 1.02M€ à 660K€."

---

## Slide 6: Timeline Blitzkrieg (2 minutes)

**Visual**: Gantt chart from `Blitzkrieg-6-Months.mmd`

**Critical Path**:
```
16 Nov 2025  → Activation 536K€ crédits (mission critique samedi!)
Dec 2025     → Setup infrastructure (burn €40K)
Jan-Apr 2026 → Training Phase 1 + Pilots (burn €270K)
Mai 2026     → Training Phase 2 + Scale (burn €226K final)
Jun-Jul 2026 → Migration hardware propre (€18K one-time)
Aug 2026     → 100% European Sovereignty ✅
```

**Comparaison Cloud vs Owned**:
- Cloud 3 ans: €16,560 (€460/mois × 36)
- Hardware owned: €18,000 one-time + €460/mois sustainable
- **Break-even**: 3.3 ans
- **ROI 10 ans**: 11-45x (vs OpenAI API $200/mois)

**Message**: "Aggressive burn 6 mois, puis souveraineté totale à coût marginal."

---

## Slide 7: Les 4 Projets COSMIC (3 minutes)

**Visual**: 2x2 grid with project cards

### COSMIC-1: BelgBERT RAG (NLP Multilingual)
- **Status**: Corpus ready (150K EPCs Belgian)
- **Phase 1**: 3 langues (FR/NL/DE)
- **Phase 2**: 24 langues EU
- **Target**: F1 0.92, API <200ms, 99.9% uptime

### COSMIC-2: AgriSurvey (LoRaWAN IoT)
- **Status**: 10 sensors proto (Liège campus)
- **Scale**: 50 farms, 100 sensors
- **KPIs**: €2M cost savings, 5K tons CO2 reduced

### COSMIC-3: CitizenHub (SmartCity Platform)
- **Status**: Architecture designed (Next.js + Azure Cosmos)
- **Scale**: 10 municipalities
- **Features**: Citizen engagement, participatory budgeting

### COSMIC-4: Econergy (Smart Grid Monitoring)
- **Status**: Prophet forecasting proto
- **Scale**: 75 buildings
- **Target**: 30% energy savings

**Message**: "4 projets, 1 infrastructure. Mutualisation maximale."

---

## Slide 8: Team & Resources (1 minute)

**Visual**: Team matrix from Sheet 3

**Total**: 118 person-months
- **ULiège** (45 PM): Researchers, domain experts
- **CETIC** (40 PM): Engineers, DevOps, IoT specialists
- **FFT.io** (33 PM): AI/ML, frontend, innovation management

**Skills Coverage**:
- ✅ NLP/ML (BelgBERT, RAG)
- ✅ IoT/Hardware (LoRaWAN, sensors)
- ✅ Cloud/DevOps (Kubernetes, Hetzner, Azure)
- ✅ Frontend/UX (Next.js, React, design systems)
- ✅ Legal/Ethics (GDPR, AI Act compliance)

**Message**: "Équipe multidisciplinaire complète. Zéro compétence manquante."

---

## Slide 9: KPIs & Success Metrics (2 minutes)

**Visual**: Dashboard mockup with 4 quadrants (from Sheet 4)

### Technical Excellence
- BelgBERT F1 0.92 (M24)
- API <200ms (M12)
- Uptime 99.9% (M24)

### Scale Achieved
- 100 sensors deployed (M24)
- 50 farms onboarded (M18)
- 10 municipalities live (M24)
- 75 buildings monitored (M24)

### Business Impact
- €500K revenue (M24)
- €2M cost savings (cumulative M24)
- 5K tons CO2 reduced (M24)

### Research Output
- 3 academic papers (M18-M24)
- 3 open-source releases (M12-M24)
- 2 patents filed (M24)

**Message**: "60+ métriques SMART. Chaque euro investi = impact mesurable."

---

## Slide 10: Anti-Fragile Philosophy (2 minutes)

**Visual**: Comparison table OpenAI/Mistral vs FFT

| Criteria | OpenAI/Mistral | FFT.io |
|----------|----------------|--------|
| **Infrastructure** | US cloud 100% | 100% EU by Aug 2026 |
| **Cost model** | $200+/mois API | €460/mois sustainable |
| **Dependencies** | Vendor lock-in | Open-source only |
| **Faillite risk** | Probable 2026-2027 | Impossible (hardware owned) |
| **GDPR compliance** | US Patriot Act risk | 100% compliant |
| **Code ownership** | Proprietary | MIT/Apache 2.0 |

**FFT Five Laws**:
1. ✅ Cognitive Sovereignty
2. ✅ Local-First Architecture
3. ✅ AI as Human Amplifier
4. ✅ Independence from Tech Monopolies
5. ✅ Optimal Performance (<0.5s latency)

**Message**: "Quand OpenAI/Mistral feront faillite, FFT sera le dernier debout."

---

## Slide 11: GDPR & Ethics (1 minute)

**Visual**: Shield icon + checklist

**GDPR Compliance**:
- ✅ Data minimization (collect only necessary)
- ✅ User rights (access, rectification, erasure)
- ✅ Consent management (explicit opt-in)
- ✅ Data sovereignty (100% EU by Aug 2026)
- ✅ Breach notification (<72h automated)

**AI Ethics**:
- ✅ Algorithmic transparency (explainable AI)
- ✅ Human oversight (99% autonomous, 0.1% human intervention)
- ✅ Fairness & bias mitigation (regular audits)
- ✅ Accountability (logs + audit trails)

**Message**: "Ethics by design, not compliance checkbox."

---

## Slide 12: Live Demo (Optional, 5 minutes)

**Si Melina veut une démo technique live**:

### Option 1: BelgBERT Inference (NLP)
```bash
curl -X POST http://localhost:11435/api/generate \
  -d '{"model": "belgbert-3lang-proto",
       "prompt": "Recommandations cultures maïs Wallonie 2026"}'
# Response <500ms (sub-0.5s latency target)
```

### Option 2: LoRaWAN Sensors (IoT Real-Time)
```bash
mosquitto_sub -h localhost -t "cosmic/sensors/#" -v
# Output: Temperature, humidity, CO2 real-time
```

### Option 3: CJEU Correction Automatique (Production)
- Interface sobre (UI Frédérique Fourez)
- Webhook GitLab → Ollama DeepSeek-R1 → Feedback AI
- <3min validation end-to-end

**Message**: "Ce n'est pas vaporware. C'est production-ready."

---

## Slide 13: Risks & Mitigation (1 minute)

**Visual**: Risk matrix (likelihood vs impact)

| Risk | Likelihood | Impact | Mitigation |
|------|-----------|--------|------------|
| Cloud credits révoqués | Low | High | Activation immédiate 16 Nov |
| BelgBERT training échec | Low | High | Fallback Llama3.2 fine-tuning |
| LoRaWAN network congestion | Medium | Medium | Multiple gateways + redundancy |
| Team attrition | Medium | High | Knowledge documentation + backups |
| GDPR violations | Low | Catastrophic | Legal review + 1Password secrets |

**Message**: "Chaque risque a un plan B documenté."

---

## Slide 14: Next Steps Post-NCP Event (1 minute)

**Immediate (Nov 2025)**:
- ✅ **Samedi 16 Nov**: Activation 536K€ crédits (mission critique)
- ✅ **Lundi 18 Nov**: Setup Azure Cosmos DB, Google TPUs, AWS IoT

**Short-term (Dec 2025)**:
- BelgBERT Phase 0 data prep
- COSMIC sensors proto deployment
- CJEU Formation scaling (30→100 students)

**Medium-term (Jan 2026)**:
- Kick-off officiel Horizon Europe (si accepté)
- First pilots deployment (10 farms, 5 buildings)

**Long-term (2027+)**:
- 100% European sovereignty achieved
- Revenue generation €500K
- Research output (papers + open-source)

**Message**: "Roadmap claire. Milestones mesurables. Exécution disciplinée."

---

## Slide 15: Call to Action (30 seconds)

**Visual**: Contact card + QR code to GitHub repo

**Ask**:
> "Nous demandons votre soutien pour la candidature Horizon Europe COSMIC Projects. Vous avez vu les preuves de faisabilité, la stratégie Blitzkrieg, et l'architecture anti-fragile. Nous sommes prêts à commencer samedi."

**Contact**:
- Vincent Caputo: vincent@fredfrenchtouch.com
- Frédérique Fourez: frederique@fredfrenchtouch.com
- GitHub: https://github.com/NextAIgeneration/ncp-cosmic-demo
- Website: https://www.fredfrenchtouch.com

**Final Line**: "European AI Sovereignty - Built in Belgium 🇧🇪"

---

## Appendix: Backup Slides (Si Questions)

### A1: Detailed Budget Breakdown
(Full table from Sheet 1)

### A2: Full Timeline Gantt
(Full chart from `COSMIC-Roadmap.mmd`)

### A3: Technical Architecture Diagram
(Mermaid flowchart with all services)

### A4: Team CVs & Expertise
(Detailed profiles ULiège/CETIC/FFT)

### A5: Competitor Analysis
(OpenAI, Mistral, Hugging Face comparison)

---

**Status**: ✅ Ready for presentation
**Last Updated**: 2025-11-12
**Version**: 1.0 (Blitzkrieg Edition)
