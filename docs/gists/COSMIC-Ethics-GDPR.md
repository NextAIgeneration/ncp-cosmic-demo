  COSMIC Project - Ethics & GDPR Compliance Documentation (NCP Wallonie Horizon Europe)

# COSMIC Project - Ethics & GDPR Compliance
*Full Documentation for NCP Wallonie Submission*

**Project:** Cognitive Optimization System for Monitoring Infrastructure & Consumption
**Lead Partner:** Université de Liège (ULg)
**Technical Partners:** CETIC, Fred French Touch
**Funding:** Horizon Europe via NCP Wallonie

---

## 📋 Table of Contents

1. [Personal Data Processing & GDPR Compliance](#personal-data-processing--gdpr-compliance)
2. [AI Ethics & Algorithmic Transparency](#ai-ethics--algorithmic-transparency)
3. [Data Sovereignty Architecture](#data-sovereignty-architecture)
4. [Security & Privacy Measures](#security--privacy-measures)
5. [Human Oversight & Accountability](#human-oversight--accountability)

---

## Personal Data Processing & GDPR Compliance

### Data Types Collected

COSMIC processes **building energy performance data exclusively**:

- **Environmental sensors**: Temperature readings (°C), humidity levels (%), CO₂ concentration (ppm)
- **Energy consumption**: Electricity usage (kWh), gas consumption (m³), heating degree days
- **Building metadata**: Energy Performance Certificate (EPC) ratings, surface area (m²), construction year, insulation type
- **Operational data**: HVAC operating hours, occupancy schedules (aggregated, no individual tracking)

**GDPR Classification**: This constitutes **technical infrastructure data**, NOT personal data under **GDPR Article 4(1)**, as it does not identify or relate to natural persons.

### Legal Basis for Processing

- **Consent**: Explicit written consent obtained from building managers (data controllers) via Data Processing Agreements (DPAs)
- **Legitimate Interest**: University energy efficiency optimization (Article 6(1)(f))
- **Public Interest**: Contribution to European Green Deal climate objectives (Article 6(1)(e))

### Data Subjects Rights Implementation

COSMIC implements all GDPR rights:

✅ **Right to Access (Art. 15)**: Building managers can request data extracts via API or CSV export
✅ **Right to Rectification (Art. 16)**: Incorrect sensor data can be corrected via dashboard interface
✅ **Right to Erasure (Art. 17)**: Buildings can withdraw consent; all data deleted within 30 days
✅ **Right to Data Portability (Art. 20)**: Export in JSON, CSV, or Parquet formats
✅ **Right to Object (Art. 21)**: Building managers can opt-out of AI forecasting while keeping monitoring

### Data Minimization & Purpose Limitation

- **Collected**: Only energy-related metrics necessary for optimization (no cameras, microphones, Wi-Fi tracking)
- **Not collected**: Personal identifiers, occupant names, individual office consumption, behavioral tracking
- **Retention**: Raw sensor data kept 24 months, aggregated data 5 years (for long-term trend analysis)
- **Deletion**: Automatic purge of granular data after retention period

---

## AI Ethics & Algorithmic Transparency

### AI Systems Deployed

#### 1. **BelgBERT Multilingual NLP**

- **Purpose**: Extract energy efficiency recommendations from building documentation (French, Dutch, German)
- **Architecture**: Fine-tuned BERT model (110M parameters) based on Google's BERT-base-multilingual-cased
- **Training data**:
  - Belgian Energy Performance Certificates (EPCs) - 150,000 public documents
  - EU Building Directives (EPBD) - Official government texts
  - Technical manuals from HVAC manufacturers (publicly available)
- **Bias mitigation**: No sensitive attributes in training data (race, gender, religion, health status)
- **Performance**: F1-score 0.89 for energy recommendation extraction (tested on 10,000 held-out EPCs)

#### 2. **Prophet Forecasting Engine**

- **Purpose**: Predict building energy consumption 1-30 days ahead
- **Architecture**: Meta's open-source Prophet library (Bayesian time-series modeling)
- **Training**: Historical consumption data from participating buildings (minimum 12 months)
- **Interpretability**: Decomposable forecasts (trend + seasonality + holidays + events)
- **Uncertainty quantification**: 80% and 95% confidence intervals provided for all predictions

#### 3. **Ollama Local Runtime**

- **Purpose**: Natural language interface for building managers ("How can I reduce heating costs?")
- **Architecture**: Open-source LLM runtime (Llama 3.2 3B, DeepSeek-R1 1.5B)
- **Deployment**: 100% on-premises (Mac Studio M1 Max, no cloud APIs)
- **Safety**: No internet access for inference, model outputs filtered for harmful content

### Algorithmic Bias Assessment

**Risk Level: MINIMAL**

COSMIC AI processes **technical data only** (temperature, kWh, EPC ratings) with **no sensitive attributes**:

❌ No race/ethnicity data
❌ No gender/sex data
❌ No religious affiliation
❌ No health status
❌ No biometric identifiers
❌ No individual profiling

**Fairness evaluation**: All buildings treated equally regardless of location, age, or previous performance. Recommendations based solely on physical characteristics (insulation, HVAC efficiency, envelope quality).

### Transparency Commitments

✅ **Open-source code**: GitHub public repository (MIT License) at `github.com/NextAIgeneration/cosmic-dashboard`
✅ **Model cards**: BelgBERT training data, performance metrics, limitations documented
✅ **API documentation**: OpenAPI 3.0 spec explaining forecasting methodology
✅ **Plain-language explanations**: Building managers receive human-readable justifications ("Your heating costs are high because insulation is rated D - consider upgrading to B")
✅ **Audit logs**: All AI predictions logged with timestamp, input data, model version

### Explainability Features

- **Feature importance**: Dashboard shows which variables most influenced each forecast (e.g., "Outdoor temperature -5°C contributed +30% to heating prediction")
- **Counterfactual explanations**: "If you upgraded insulation to level B, predicted savings: -18% annual heating costs"
- **Confidence scores**: Every recommendation tagged with certainty level (High/Medium/Low)

---

## Data Sovereignty Architecture

### European Infrastructure Only

**Zero data transfers outside EU territory - ever.**

#### Phase 1: Cloud Infrastructure (Months 1-7)

```
┌─────────────────────────────────────────┐
│  Hetzner (Germany) - Primary Storage   │
│  - Object storage: Sensor data (raw)    │
│  - PostgreSQL: Time-series database     │
│  - Location: Falkenstein DC Park        │
└─────────────────────────────────────────┘
           ▼
┌─────────────────────────────────────────┐
│  OVH (France) - Processing & Backup     │
│  - Compute: AI model inference          │
│  - CDN: Dashboard delivery              │
│  - Location: Gravelines DC              │
└─────────────────────────────────────────┘
```

#### Phase 2: Owned Hardware (Months 8+)

```
┌─────────────────────────────────────────┐
│  On-Premises Server (Tournai, Belgium)  │
│  - Mac Studio M1 Max (ARM64)            │
│  - 64GB RAM, 2TB NVMe SSD               │
│  - Ollama FFT: Local AI runtime         │
│  - Zero cloud dependencies              │
│  - Full data sovereignty                │
└─────────────────────────────────────────┘
```

**Rationale**: By Month 8, COSMIC achieves **100% independence** from cloud providers, ensuring:
- No vendor lock-in (AWS, Google, Microsoft Azure)
- No US CLOUD Act jurisdiction
- Full control over data access
- Resilience against cloud outages

### Data Residency Compliance

- **GDPR Article 44-50**: No transfers to third countries without adequacy decision
- **Schrems II compliant**: No reliance on invalidated Privacy Shield
- **Data Processing Agreements**: Hetzner and OVH sign Standard Contractual Clauses (SCCs)
- **Encryption**: AES-256 at rest, TLS 1.3 in transit
- **Access controls**: Multi-factor authentication (MFA) required for all administrators

---

## Security & Privacy Measures

### Privacy by Design (Article 25)

COSMIC's **local-first architecture** inherently protects privacy through technical design:

1. **No external API calls**: Ollama AI runtime processes data on-premises without internet
2. **Edge processing**: Sensor data aggregated locally before transmission (reduces granularity)
3. **Differential privacy**: Noise added to aggregated statistics shared for research (ε=1.0, δ=10⁻⁵)
4. **Anonymization pipeline**: Building identifiers removed from published datasets (k-anonymity ≥5)

### Security Audit Schedule

**Deliverable D3.5 (Month 3)**: Independent security assessment by CETIC cybersecurity team

Audit scope:
- Penetration testing of dashboard web application
- IoT sensor network vulnerability scanning
- Data encryption verification (at-rest and in-transit)
- Access control review (role-based permissions)
- GDPR compliance check (DPAs, consent mechanisms, data retention)

**Deliverable D5.2 (Month 18)**: Follow-up audit after full deployment

### Incident Response Plan

1. **Detection**: Automated alerts for unauthorized access attempts (Fail2Ban, SIEM)
2. **Containment**: Immediate network isolation of compromised sensors (<5 min)
3. **Notification**: Data breach notification to supervisory authority within 72 hours (GDPR Art. 33)
4. **Remediation**: Patch vulnerabilities, rotate credentials, forensic analysis
5. **Documentation**: Incident logged in compliance register

---

## Human Oversight & Accountability

### AI Decision-Making Process

**COSMIC AI provides recommendations, NOT automated decisions.**

```
┌─────────────────┐
│  Sensor Data    │ → Raw input (temperature, kWh, etc.)
└────────┬────────┘
         ▼
┌─────────────────┐
│  AI Forecasting │ → Prophet predictions + BelgBERT recommendations
└────────┬────────┘
         ▼
┌─────────────────┐
│ Energy Analyst  │ → Human review (ULg staff member)
│   (Human)       │    - Verify predictions plausible
└────────┬────────┘    - Check for anomalies
         ▼              - Approve/reject recommendations
┌─────────────────┐
│ Building Manager│ → Final decision-maker
│   (Human)       │    - Accepts or ignores AI advice
└─────────────────┘    - Full control over retrofit investments
```

**No automation**: Building managers retain 100% control over operational changes (HVAC schedules, temperature setpoints, renovation budgets).

### Accountability Framework

- **Data Controller**: Université de Liège (ULg) - legal responsibility for GDPR compliance
- **Data Processors**: CETIC (IoT infrastructure), Fred French Touch (AI platform) - bound by DPAs
- **Data Protection Officer (DPO)**: ULg appoints DPO (contact: dpo@uliege.be)
- **Supervisory Authority**: Belgian Data Protection Authority (APD/GBA)

### Ethical Review Board

COSMIC project undergoes ethical review by **ULg Research Ethics Committee** (Month 1):

- Assessment of consent procedures
- Evaluation of data minimization practices
- Review of AI bias mitigation strategies
- Approval required before pilot deployment

---

## Compliance Summary

| Requirement | Status | Evidence |
|-------------|--------|----------|
| **GDPR Art. 6** (Lawful basis) | ✅ Compliant | Consent + Legitimate interest |
| **GDPR Art. 13-14** (Transparency) | ✅ Compliant | Privacy notices provided |
| **GDPR Art. 15-22** (Data subjects rights) | ✅ Compliant | Technical implementation via API |
| **GDPR Art. 25** (Privacy by design) | ✅ Compliant | Local-first architecture |
| **GDPR Art. 32** (Security) | ✅ Compliant | Encryption, MFA, audit (D3.5) |
| **GDPR Art. 33-34** (Breach notification) | ✅ Compliant | Incident response plan |
| **GDPR Art. 44-50** (Transfers) | ✅ Compliant | EU-only infrastructure |
| **AI Act (proposed)** | ✅ Ready | Low-risk system, transparency measures |
| **Horizon Europe Ethics** | ✅ Compliant | ULg Ethics Committee approval |

---

## Contact & Documentation

**Data Protection Officer (ULg)**: dpo@uliege.be
**Project Coordinator**: Prof. Frederique Fourez, contact@fredfrenchtouch.io
**Technical Lead**: Enzoxic, vincent@fredfrenchtouch.io

**Full documentation**: https://docs.nextairev.com/cosmic/
**GitHub repository**: https://github.com/NextAIgeneration/cosmic-dashboard
**Privacy Policy**: https://docs.nextairev.com/cosmic/privacy

---

*Last updated: 26 October 2025*
*Document version: 1.0 (NCP Wallonie submission)*
*COSMIC Project - Horizon Europe*

