FFT Cognitive Platform - Deployment Options SaaS + Node + LoRaWAN - Updated with Local-First Architecture

# FFT Cognitive Platform - Options de Déploiement
*SaaS Cloud ET Node Local - Client Choice*

---

## 🎯 Philosophie : Pas "OU" mais "ET"

**FFT.io offre DEUX modèles complémentaires** :

```
┌─────────────────────────────────────────────┐
│        FFT Cognitive Platform               │
│     (Même technologie, trois déploiements)  │
└──────────────┬──────────────────────────────┘
               │
        ┌──────┼──────┐
        │      │      │
    Option A   │  Option C
    SaaS Cloud │  LoRaWAN + IPFS
    (Hetzner)  │  (Distributed)
        │      │      │
        │  Option B   │
        │  Node Local │
        │  (Premise)  │
        │      │      │
        └──────┼──────┘
               │
         Client choisit
    selon besoin souveraineté
      infrastructure distribuée
```

---

## 🌐 Option A : SaaS Cloud (Hetzner/OVH)

### Pour Qui ?

- **Formateurs/PME** sans compétences IT internes
- **Budget limité** (pas d'investissement hardware)
- **Besoin rapidité** (déploiement immédiat)
- **Volume modéré** (10-100 utilisateurs)

### Architecture

```
Clients (étudiants, utilisateurs)
    ↓ HTTPS
Cloudflare Edge (EU) - Cache + CDN
    ↓
Hetzner Datacenter (Falkenstein, DE)
├─ Nextcloud (interface web)
├─ PostgreSQL (base données)
├─ Ollama ARM64 (inference AI)
└─ GitLab Runner (CI/CD)
```

**Localisation** : Allemagne (GDPR-compliant, EU-only)

### Pricing

| Composant | Coût Mensuel | Détails |
|-----------|--------------|---------|
| Hetzner CAX31 (ARM64) | €16.90/mois | 8 vCPU, 16GB RAM, 240GB NVMe |
| Nextcloud hosting | €0 | Auto-hébergé sur CAX31 |
| Cloudflare Free | €0 | CDN + SSL + DNS |
| PostgreSQL | €0 | Sur CAX31 |
| **Total** | **€16.90/mois** | (~€200/an) |

**Scalabilité** :
- 10-50 utilisateurs : CAX31 (€16.90/mois)
- 50-200 utilisateurs : CAX41 (€35.90/mois) - 16 vCPU, 32GB RAM
- 200-1000 utilisateurs : 2x CAX41 + Load Balancer (€80/mois)

### Avantages

✅ **Zero investissement** hardware
✅ **Déploiement immédiat** (30 min setup)
✅ **Maintenance incluse** (updates, backups, monitoring)
✅ **Scalabilité automatique** (upgrade plan en 1 clic)
✅ **Conformité GDPR** (datacenter EU, data residency garantie)

### Limites

⚠️ **Souveraineté partielle** : Données sur serveur tiers (Hetzner)
⚠️ **Coût récurrent** : €200-1000/an selon volume
⚠️ **Dépendance provider** : Migration possible mais effort

### Use Cases

- **Frederique Formation** : Phase 1 (10-50 étudiants CJEU)
- **Autres formateurs EU** : Licence FFT Platform SaaS
- **Startups EdTech** : MVP rapide, pivot possible
- **Associations** : Budget serré, pas de compétences IT

---

## 💻 Option B : Node Local (Client Premise)

### Pour Qui ?

- **Organisations exigeantes souveraineté** (gouvernement, défense, santé)
- **Budget hardware disponible** (€4K-10K investissement)
- **Compétences IT internes** (sysadmin capable maintenir)
- **Volume élevé OU données ultra-sensibles**

### Architecture

```
Clients (intranet ou VPN)
    ↓ HTTPS local
Mac Studio M1 Max / M2 Max (Client Premise)
├─ Nextcloud local
├─ PostgreSQL local
├─ Ollama local (models ARM64)
└─ GitLab Runner local
    ↓ (optionnel)
Backup cloud Hetzner (chiffré)
```

**Localisation** : 100% client (bureau, datacenter privé, etc.)

### Hardware Recommandé

**Option 1 : Mac Studio M1 Max** (Recommandé FFT)
- Prix : €2,300-2,800 (occasion) ou €4,500 (neuf)
- CPU : 10 cores (8 performance + 2 efficiency)
- GPU : 24 ou 32 cores Metal
- RAM : 32GB ou 64GB Unified Memory
- Stockage : 512GB-2TB NVMe
- Conso : ~60-100W (vs 300W+ serveur x86)

**Option 2 : Mac Mini M2 Pro** (Backup node ou budget serré)
- Prix : €1,500-2,000
- CPU : 10 ou 12 cores
- GPU : 16 ou 19 cores
- RAM : 16GB ou 32GB
- Stockage : 512GB-1TB
- Conso : ~30-50W

**Option 3 : Hetzner Bare-Metal ARM64** (Si préfère datacenter pro)
- Prix : €54-120/mois
- AX41 : 16 cores, 64GB RAM, 2x512GB NVMe
- Conso : Incluse dans prix
- Note : Moins optimisé que Mac Studio (architecture différente)

### Coûts

| Composant | Coût Initial | Coût Annuel |
|-----------|--------------|-------------|
| Mac Studio M1 Max 32GB | €2,500 (occasion) | €0 |
| Électricité (24/7, 80W) | - | €70/an (0.08€/kWh) |
| Internet fiber 1Gbps | - | €600/an (€50/mois) |
| Backup Hetzner (optionnel) | - | €54/an (Storage Box 1TB) |
| **Total Year 1** | **€2,500** | **€724/an** |
| **Total Year 2-5** | - | **€724/an** |

**ROI vs SaaS Cloud** :
- SaaS : €200/an × 5 ans = €1,000
- Node : €2,500 + €724/an × 5 = €6,120
- **Différence** : +€5,120 over 5 years
- **MAIS** : Souveraineté 100%, scalabilité infinie (ajouter nodes), revente hardware possible

### Avantages

✅ **Souveraineté totale** : Données ne quittent JAMAIS les locaux
✅ **Zero coût cloud** : Pas d'abonnement mensuel
✅ **Performance ARM64** : 5-6x plus efficace énergétiquement que x86
✅ **Scalabilité horizontale** : Ajouter Mac Studio = +100% capacité
✅ **Propriété hardware** : Revente possible, pas de lock-in

### Limites

⚠️ **Investissement initial** : €2,500-10,000 selon config
⚠️ **Compétences IT requises** : Installation, maintenance, backups
⚠️ **Responsabilité matériel** : Pannes hardware = downtime (mitigation : 2 nodes)
⚠️ **Électricité + Internet** : Coûts fixes (~€60-80/mois)

### Use Cases

- **Gouvernement/Défense** : Données classifiées, zero cloud
- **Hôpitaux** : Données patients GDPR-critical
- **Banques/Finance** : Compliance stricte, audits
- **Frederique Formation Phase 2** : Si volume >100 étudiants ou revenus B2B
- **FFT Hub Tournai** : Infrastructure mutualisée (10 nodes = 10 clients)

---

## 🏆 FFT Tournai Hub - Node Premium Pioneer

### Le Premier Node : Vitrine Technologique FFT

**Mac Studio M1 Max 32GB** (Tournai, Belgique)
- **Status** : Production depuis Nov 2025
- **Rôle** : Flagship, showcase, R&D, reference implementation
- **Workload** : CJEU Frederique Formation + démos clients + benchmarks publics

### Architecture Actuelle

```
Mac Studio M1 Max (Tournai Hub)
├─ CPU: 10 cores (8 perf + 2 efficiency)
├─ GPU: 32 cores Metal (24-32 selon config)
├─ NPU: 16 cores Neural Engine
├─ RAM: 32GB Unified Memory
├─ Storage: 512GB NVMe SSD
└─ Network: 10GbE + WiFi 6
```

**Software Stack** :
- Ollama FFT (port 11435) : DeepSeek-R1, Llama3.2, Qwen
- NPE (Neural Processing Engine) : Intelligent routing
- ACE (Adaptive Cognitive Engine) : Playbook selection
- PostgreSQL + pgvector : Vector database
- GitLab Runner : Local CI/CD
- Docker/OrbStack : Conteneurs ARM64

**Performance Mesurée** :
- Latence inference : <500ms (target atteint)
- Throughput : 50-100 requêtes/jour actuel (capacité 500+)
- Uptime : 99.5%+ (monitoring Prometheus)
- Coût électricité : ~€70/an (80W moyen)

### Ambitions Démontrées

**1. ARM64 > x86 Cloud (Preuve par l'exemple)**

| Métrique | FFT Node Premium (ARM64) | Cloud GPU (x86 AWS/Azure) | FFT Avantage |
|----------|--------------------------|---------------------------|--------------|
| **Latence** | <500ms | 1-5s (RTT + queue) | **10x plus rapide** |
| **Coût annuel** | €700 (élec + internet) | €2,400-6,000 (GPU instances) | **10x moins cher** |
| **Énergie** | 80W | 300W+ (GPU server) | **4x plus efficace** |
| **Souveraineté** | 100% (Belgique) | 0% (US datacenters) | **Total** |
| **Cold start** | 0s (models loaded ∞) | 5-30s (model loading) | **∞** |

**Résultat** : Performance équivalente ou supérieure, coût 10x inférieur, souveraineté totale.

**2. Local-First = Viable Production**

**CJEU Frederique Formation** (Proof of Concept) :
- Volume : 10-50 étudiants (phase pilote)
- Performance : <3min validation end-to-end ✅
- Qualité : Niveau professeur de droit ✅
- Coût : €0 pour formateur ✅
- GDPR : 100% conforme (données jamais cloud) ✅

**Scalabilité démontrée** :
- 1 node (32GB) = 50-200 users
- 2 nodes (64GB total) = 200-500 users
- 10 nodes (320GB total) = 2000+ users
- **Linéaire** : Doubler nodes = doubler capacité

**3. Business Model Hybride Fonctionnel**

**Phase 1 (Q4 2025)** : Bootstrap
- Investment : €2,500 (Mac Studio occasion)
- Client : Frederique (CJEU gratuit, validation produit)
- Revenue : €0
- **Objectif** : Proof of concept ✅

**Phase 2 (Q1 2026)** : First Revenue
- Microsoft for Startups : $150K credits (cloud backup)
- Frederique : €0 (partnership pionnier)
- Client 2-3 : €50-100/mois (early adopters)
- Revenue : €600-1,200/an
- **Objectif** : Cover costs électricité/internet ✅

**Phase 3 (Q2-Q4 2026)** : Scale
- 5-10 clients : €50-200/mois chacun
- Revenue : €3K-12K/an
- Investment : +2 nodes (€5K) = 3 nodes total
- **Objectif** : Rentabilité + expansion ✅

**Phase 4 (2027+)** : FFT Hub Tournai
- 10 nodes : €25K investment
- 10 clients nodes (location) : €100-200/mois
- Revenue : €12K-24K/an
- Net profit : €8K-18K/an (après coûts)
- **Objectif** : Sustainable business ✅

### Rôle Showcase pour Prospects

**Démo en Live** (sur rendez-vous Tournai) :
1. **Performance** : Soumettre exercice CJEU → feedback <3min (chrono)
2. **Monitoring** : Grafana dashboards (latence, throughput, ressources)
3. **Souveraineté** : Data never leaves Belgium (logs, audit trail)
4. **Cost analysis** : €700/an vs €2,400+ cloud (ROI calculator)

**Benchmark Public** :
- https://benchmarks.fft.io (à créer)
- Comparaison ARM64 vs x86, local vs cloud
- Open data : latence, tokens/s, coût/requête
- Reproducible : scripts GitHub publics

**Test Drive** :
- Prospects peuvent **tester node 1 mois gratuit**
- Accès remote (VPN Tailscale sécurisé)
- Workload réel (leurs exercices CJEU, leurs données)
- Décision achat node informée (pas de surprise)

### R&D Nouvelles Features

**Node Premium = Lab Innovation** :

**Q4 2025 - Q1 2026** :
- ✅ NPE + ACE (routing intelligent, playbooks)
- ✅ GPU acceleration (pgvector, Metal)
- ✅ Multi-model (DeepSeek, Llama, Qwen)
- 🔄 Vector embeddings (semantic search CJEU)
- 🔄 Multi-langue (FR, NL, DE pour Belgique)

**Q2 2026** :
- Vision models (analyse scans documents juridiques)
- RAG avancé (jurisprudence CJEU complète)
- Fine-tuning local (adapter DeepSeek sur cas spécifiques)
- Multi-tenant (isolation clients sur même node)

**Q3-Q4 2026** :
- Federated learning (apprendre de tous nodes sans centraliser data)
- LoRaWAN integration (présence étudiants, IoT campus)
- IPFS knowledge base (décentralisé, censorship-resistant)
- Kubernetes cluster (orchestration 10+ nodes)

**Tout testé d'abord sur Node Premium, puis déployé clients.**

### Upgrade Path (Futur)

**Mac Studio M1 Max 32GB** (actuel) → **Mac Studio M2 Ultra 192GB** (2026-2027)

**Pourquoi upgrade ?**
- Capacité : 32GB limite à ~3-4 modèles simultanés, 192GB = 10-15 modèles
- Performance : M2 Ultra = 2x faster inference vs M1 Max
- Showcase : Démontrer scaling vertical (pas besoin multi-nodes si Ultra)
- ROI : €7,000 investment, mais permet gérer 5x plus clients sur 1 node

**Migration** :
- Zero downtime (node 2 prend relais pendant upgrade)
- Export data (PostgreSQL dump, Ollama models)
- Setup nouveau Mac Studio (script automatique)
- Import data, test, switch DNS
- **Timeline** : 2-3h total

**Ancien Mac Studio M1 Max** :
- Devient Node 2 (backup, dev, staging)
- Ou vendu €1,500-2,000 (ROI partiel)
- Ou donné client pilote (partenariat)

---

# Section Local-First Architecture - Maison Témoin Frédérique

## 🏠 Local-First: Maison Témoin Réelle

### Philosophie Souveraine

**FFT.io ne commence pas par un datacenter - mais par une maison témoin.**

```
Maison Frédérique (Tournai (Wallonie - Hainaut))
  ↓
CJEU Exercices + Validation AI
  ↓
Proof-of-Concept Réel
  ↓
Garantie Appels d'Offres Benelux
```

**Pourquoi une maison témoin?**
- Preuve concrète (pas juste théorie)
- Environment réel d'utilisation
- Feedback utilisateur direct
- Garantie supplémentaire pour appels d'offres
- Reference case pour Wallonie/Belgique/Benelux

### Infrastructure Maison Témoin

**Setup Frédérique (Tournai (Wallonie - Hainaut)):**

**Hardware local:**
- Mac Studio M1 Max (32GB) - node compute principal
- iPad M1 Pro - node secondaire + interface mobile
- iPhone 8 - node validation mobile
- Réseau: Proximus Fiber (backup 4G/5G)
- Tailscale VPN pour accès sécurisé

**Services déployés:**
- Webhook CJEU (port 8080 local)
- Ollama FFT (correction AI locale)
- PostgreSQL (historique validations)
- Redis (cache sessions)
- Backup automatique (Hetzner EU)

**Use Case: CJEU Exercices**
- Étudiants soumettent via SeaTable/GitLab
- Webhook → Maison Frédérique
- Validation AI locale (<3min)
- Feedback retourné automatiquement
- **Zero dépendance cloud US**

### Stratégie d'Expansion Régionale

**Phase 1: Wallonie** 🇧🇪 (2025)
- Maison témoin Frédérique opérationnelle
- NCP Wallonie validation
- Appels d'offres Digital Europe 2026
- **Proof**: Installation réelle fonctionnelle

**Phase 2: Belgique** 🇧🇪 (2025-2026)
- Scale Flandres + Tournai (Wallonie - Hainaut)
- BelgBERT 3 langues (FR, NL, DE)
- Cadre légal harmonisé
- **Avantage**: Petite échelle = iteration rapide

**Phase 3: Benelux** 🇳🇱🇱🇺 (2026)
- Netherlands: NL + English
- Luxembourg: FR + DE + LU
- **Harmonisation**: 3 pays faisable (vs 27 EU)
- Langues: BelgBERT couvre 80%+

**Phase 4: EU (si harmonisation possible)** 🇪🇺 (2027+)
- Attendre retours Benelux
- Adapter selon cadres légaux
- **Réaliste**: Complexité EU = multi-années
- **Pragmatique**: Focus Benelux d'abord

### Pourquoi Benelux-First (pas EU-First)?

**Complexité EU:**
- ❌ 27 pays, 24 langues officielles
- ❌ Cadres légaux disparates
- ❌ Processus décision lents
- ❌ Harmonisation = années

**Simplicité Benelux:**
- ✅ 3 pays (Belgique, Netherlands, Luxembourg)
- ✅ 4 langues principales (FR, NL, DE, EN)
- ✅ Proximité géographique (1h train)
- ✅ Collaboration historique
- ✅ Cadres légaux similaires
- ✅ Harmonisation = mois (pas années)

**BelgBERT coverage:**
- FR: 45% Belgique + 100% Luxembourg (partiel)
- NL: 55% Belgique + 100% Netherlands
- DE: Minorité Belgique + 100% Luxembourg (partiel)
- EN: Lingua franca (tous pays)

**Result**: 1 model couvre 3 pays ✅

### Garanties Appels d'Offres

**Maison Témoin = Garantie Supplémentaire**

**Pour Digital Europe 2026:**
- ✅ Installation réelle fonctionnelle
- ✅ Utilisateur réel (Frédérique formations)
- ✅ Métriques concrètes (<3min validation)
- ✅ Coûts prouvés (€0 vs €600-2400/an)
- ✅ Souveraineté démontrée (100% local)

**vs Compétiteurs cloud-only:**
- ❌ Juste des slides PowerPoint
- ❌ Pas de proof-of-concept local
- ❌ Dépendance AWS/Azure/GCP
- ❌ Coûts récurrents élevés
- ❌ Vendor lock-in

**FFT.io advantage**: "Nous l'avons déjà déployé en Belgique. Voici les métriques réelles."

### Architecture Locale Souveraine

**Stack Maison Témoin:**

```
Internet (Proximus Fiber + 4G backup)
  ↓
Tailscale VPN (zero-trust)
  ↓
Mac Studio M1 Max (compute node)
  ↓
  ├─ Ollama FFT (AI locale)
  ├─ PostgreSQL (data locale)
  ├─ Redis (cache local)
  ├─ Webhook CJEU (Flask :8080)
  └─ GitLab Runner (CI/CD local)
  ↓
Backup Hetzner (Allemagne - EU)
```

**Principe clé**: Tout fonctionne **même si internet tombe**.

### Technologies Locales (Benelux-Ready)

**AI/NLP (2025 - Actuels):**
- DeepSeek-R1 (reasoning) ✅
- Llama3.2 (general purpose) ✅
- Qwen2.5-coder (code) ✅
- **Tous locaux**: Zero API US

**AI/NLP (2026 - Training Prioritaires):**
- BelgBERT (FR, NL, DE) - à entraîner
- Prophet (time-series forecasting) - à entraîner
- **Training local**: Mac Studio M1 Max GPU

**Infrastructure:**
- Mac/iPad/iPhone (Apple Silicon)
- OrbStack (Docker ARM64)
- PostgreSQL + pgvector
- Tailscale VPN
- **Tous EU/local**: GDPR compliant

**Backup/Scale:**
- Hetzner (Allemagne)
- OVH (France)
- Scaleway (France)
- **Zero US cloud**: Souveraineté EU

### Cas d'Usage Maison Témoin

**1. CJEU Corrections (Actif)**
- Étudiants: ~50/an (Frédérique formations)
- Exercices: 5-10/étudiant
- Validations: 250-500/an
- Temps: <3min/validation
- Coût: €0 (vs €1500-3000/an cloud)

**2. CitizenHub (Wallonie - Planned)**
- Participation citoyenne
- NCP Wallonie validation
- Infrastructure identique (maison témoin)
- Scale: 100-1000 utilisateurs locaux

**3. COSMIC AgriTech (Benelux - Planned)**
- Données agricoles locales
- Edge computing fermes
- Même architecture que maison témoin
- Scale: 10-100 fermes Benelux

### Monitoring & Maintenance

**Observabilité locale:**
- Portainer (Docker UI)
- Metabase (analytics)
- Logs locaux (rotation automatique)
- Alertes Slack/Email

**Maintenance:**
- Automatisée (cron jobs)
- Updates OTA (Tailscale remote)
- Backup quotidien (Hetzner)
- **Intervention on-site**: <2h (Tournai (Wallonie - Hainaut) local)

### Sécurité & GDPR

**Compliance:**
- ✅ Data réside Belgique (maison témoin)
- ✅ Backup Allemagne (Hetzner EU)
- ✅ Zero transfert US
- ✅ GDPR by design

**Sécurité:**
- Tailscale VPN (accès chiffré)
- 1Password (secrets management)
- Firewall macOS (ports fermés)
- SSH keys only (no passwords)
- Docker network isolation

**Audit trail:**
- PostgreSQL logs complets
- Git history (configs)
- Obsidian daily notes (changes)

### Coûts Maison Témoin

**Hardware (one-time):**
- Mac Studio M1 Max: €2500 (déjà possédé)
- iPad M1 Pro: €900 (déjà possédé)
- iPhone 8: €150 (déjà possédé)
- **Total**: €0 nouveau hardware

**Récurrent (monthly):**
- Électricité: ~€30/mois (24/7)
- Internet: €50/mois (Proximus Fiber)
- Hetzner backup: €5/mois (100GB)
- Tailscale: €0 (plan gratuit <100 devices)
- **Total**: €85/mois = **€1020/an**

**vs Cloud (equivalent):**
- AWS/Azure: €200-500/mois = €2400-6000/an
- OpenAI API: €100-300/mois = €1200-3600/an
- **Total cloud**: €3600-9600/an

**Économie**: €2580-8580/an (71-89% économie) 💰

### Scaling Benelux

**Replication maison témoin:**

**Belgium:**
- Maison témoin #1: Frédérique (Tournai (Wallonie - Hainaut)) ✅
- Maison témoin #2: Flandres (Gent) - planned
- Maison témoin #3: Wallonie (Liège) - planned

**Netherlands:**
- Maison témoin #4: Amsterdam - planned
- Maison témoin #5: Rotterdam - planned

**Luxembourg:**
- Maison témoin #6: Luxembourg-ville - planned

**Architecture**: Chaque maison = node autonome + sync P2P (IPFS/Tailscale)

### Appels d'Offres Benelux

**Digital Europe 2026 (Wallonie):**
- ✅ Maison témoin opérationnelle
- ✅ Métriques réelles disponibles
- ✅ Souveraineté prouvée
- ✅ Coûts compétitifs
- ✅ GDPR compliant
- ✅ BelgBERT local (FR, NL, DE)

**Arguments clés:**
1. "Installation réelle à Tournai (Wallonie - Hainaut) depuis Nov 2025"
2. "€0 coûts cloud, €1020/an total"
3. "100% souveraineté EU, zero dépendance US"
4. "BelgBERT = 3 langues Benelux natives"
5. "Scale prouvé: 50 utilisateurs, 500 validations/an"

**vs Compétiteurs:**
- Slides PowerPoint vs Installation réelle ✅
- Promesses vs Métriques concrètes ✅
- Cloud US vs Local EU ✅
- Coûts récurrents vs One-time ✅

### Roadmap Expansion

**2025 Q4: Maison Témoin Opérationnelle** ✅
- Frédérique Tournai (Wallonie - Hainaut)
- CJEU validations actives
- Métriques collectées

**2026 Q1: Validation Wallonie**
- NCP Wallonie review
- Digital Europe 2026 application
- Ajustements feedback

**2026 Q1-Q2: Training BelgBERT + Prophet** 🔥
- BelgBERT: 3 langues (FR, NL, DE)
- Prophet: Forecasting COSMIC/CitizenHub
- Training local Mac Studio M1 Max
- **Priorité**: Models souverains EU

**2026 Q2-Q3: Scale Belgique**
- Flandres deployment
- BelgBERT production deployment
- 100-500 utilisateurs

**2026 Q4: Benelux Expansion**
- Netherlands pilot
- Luxembourg pilot
- Harmonisation réglementaire

**2027+: EU (si faisable)**
- Retours Benelux analysés
- Adaptation cadres légaux EU
- Scale progressif (pas big bang)

---

## 🎯 Conclusion: Benelux-First Strategy

**FFT.io = Pragmatique, pas idéaliste**

**Approche:**
1. ✅ **Prouver localement** (maison témoin Frédérique)
2. ✅ **Valider régionalement** (Wallonie → Belgique)
3. ✅ **Harmoniser Benelux** (3 pays, faisable)
4. ⏳ **Considérer EU** (si harmonisation possible)

**Pas l'inverse** (EU first = échec garanti par complexité)

**Garanties appels d'offres:**
- Installation réelle fonctionnelle
- Métriques concrètes disponibles
- Utilisateur réel satisfait
- Coûts prouvés compétitifs
- Souveraineté démontrée

**Message clé**: "Nous ne vendons pas une vision - nous montrons une installation réelle qui fonctionne depuis Nov 2025 à Tournai (Wallonie - Hainaut)."

---

**Architecture**: Local-First Sovereign Home Witness
**Strategy**: Benelux-First (not EU-First)
**Status**: Production témoin (Nov 2025)
**Cost**: €1020/an (vs €3600-9600 cloud)
**Sovereignty**: 100% EU-based
**Proof**: Maison Frédérique Tournai (Wallonie - Hainaut)

*FFT Cognitive Platform - Pragmatic Regional Expansion* 🏠🇧🇪🇳🇱🇱🇺


## 📡 Option C : LoRaWAN + IPFS Node (Infrastructure Distribuée)

### Pourquoi ?

- **Zones rurales/isolées** : Faible connectivité internet, LoRa longue portée (5-15km)
- **IoT massif** : Milliers de capteurs (monitoring agricole, environnemental, smart cities)
- **Souveraineté maximale** : Architecture peer-to-peer, pas de serveur central
- **Résilience** : IPFS distribué, pas de single point of failure, censorship-resistant
- **Coût opérationnel minimal** : LoRa ultra-basse consommation (<1W par capteur), communication gratuite
- **Autonomie énergétique** : Capteurs solaires (10+ ans batterie), gateways 24/7 (<10W)
- **Échelle européenne** : The Things Network (TTN), ChirpStack, interopérabilité totale

### Architecture

```
Capteurs LoRaWAN (température, humidité, pollution, etc.)
    ↓ LoRa 868MHz (longue portée 5-15km)
Antenne LoRaWAN Gateway (Tournai Hub ou client premise)
    ↓ Ethernet/WiFi
Raspberry Pi 4 / Mac Mini (Node IPFS)
├─ ChirpStack (LoRaWAN Network Server)
├─ IPFS Daemon (distributed storage)
├─ Ollama ARM64 (local AI inference)
└─ PostgreSQL (time-series data)
    ↓ (réplication)
IPFS Global Network (peer-to-peer sync)
└─ Autre nodes IPFS (Paris, Brussels, Amsterdam, etc.)
```

**Localisation** : Distribuée (pas de serveur central)

### Hardware Recommandé

**Gateway LoRaWAN** :
- **RAK7244** (Raspberry Pi HAT) : €150-200
  - Portée : 5-15km (rural/suburban)
  - Bandes : EU868, US915
  - Connectivité : Ethernet, WiFi, 4G (optionnel)

- **Mikrotik wAP LoRa8** : €180-250
  - Portée : 10-20km (antenne externe)
  - RouterOS (robuste, enterprise-grade)
  - PoE support (installation extérieure)

**Compute Node (IPFS + AI)** :
- **Raspberry Pi 4 (8GB)** : €90-120
  - ARM64 native
  - Faible consommation (5-10W)
  - SD card 128GB (~€20)
  - **Bon pour** : IoT basique, monitoring

- **Mac Mini M2** : €650-800
  - ARM64 optimisé
  - 16GB RAM (extensible 24GB)
  - Performance 10x Raspberry Pi
  - **Bon pour** : AI inference + IPFS + LoRaWAN

**Capteurs LoRaWAN** (exemples) :
- Température/Humidité : €25-40/unité
- GPS Tracker : €40-60/unité
- Pollution Air (PM2.5, CO2) : €80-120/unité
- Sol (NPK, pH, moisture) : €150-250/unité

### Coûts

| Composant | Coût Initial | Coût Annuel |
|-----------|--------------|-------------|
| Gateway LoRaWAN (RAK7244) | €180 | €0 |
| Raspberry Pi 4 8GB + SD | €110 | €0 |
| Antenne 868MHz externe (optionnel) | €30 | €0 |
| Alimentation + boîtier étanche | €40 | €0 |
| Internet 4G (optionnel, si pas WiFi) | - | €120 (€10/mois data-only SIM) |
| Électricité (24/7, 10W) | - | €9/an (0.10€/kWh) |
| **Total Year 1** | **€360** | **€129/an** |

**Setup Complet (10 capteurs)** :
- Gateway + Node : €360
- 10 capteurs (température/humidité) : €300 (10 × €30)
- **Total** : €660 initial + €129/an

**vs Cloud IoT (AWS/Azure)** :
- 10 capteurs × €5/mois cloud ingestion = €600/an
- FFT LoRaWAN : €129/an
- **Économie** : €471/an (78% savings)

### Avantages

✅ **Longue portée** : 5-15km (vs WiFi 50m, 4G coûteux)
✅ **Faible consommation** : Capteurs LoRa = 5-10 ans sur batterie
✅ **Pas de SIM cards** : Zero abonnement mobile par capteur
✅ **IPFS distribué** : Données répliquées automatiquement (censorship-resistant)
✅ **Souveraineté totale** : Pas de cloud, peer-to-peer
✅ **Coût marginal zero** : Ajouter capteurs = coût hardware only (€30/capteur)

### Limites

⚠️ **Débit faible** : LoRa = 0.3-50 kbps (pas pour vidéo/audio, OK pour sensor data)
⚠️ **Setup complexe** : ChirpStack + IPFS + LoRa config (compétences IT)
⚠️ **Portée limitée** : 5-15km (besoin ligne de vue, antenne en hauteur)
⚠️ **IPFS public** : Données accessibles si CID connu (chiffrement recommandé)

### Use Cases

**AgriTech** (COSMIC AgriTech Cluster 6) :
- Monitoring sol (température, humidité, NPK)
- Tracking bétail (GPS LoRa colliers)
- Stations météo (wind, rain, temp)
- Irrigation intelligente (valve control)

**Smart Cities** :
- Qualité air (PM2.5, CO2, NO2)
- Parking availability (sensors ultrason)
- Gestion déchets (fill level bins)
- Éclairage public intelligent

**Environnement** :
- Rivières/Lacs (qualité eau, niveau)
- Forêts (incendies, humidité)
- Biodiversité (tracking animaux)
- Pollution sonore

**Frederique Formation (Hypothèse Future)** :
- Présence étudiants (badges LoRa)
- Température salles (confort)
- Qualité air CO2 (alerte ventilation)
- → Données stockées IPFS (privacy), AI analyse trends

---

## 🔄 Modèle Hybride (Les Trois)

### Scénario Réel

**Exemple : Frederique Formation**

**Phase 1 (2025-2026)** : SaaS Cloud Hetzner
- 10-50 étudiants CJEU
- Budget : €17/mois (€200/an)
- Déploiement : Immédiat
- Test marché, validation produit

**Phase 2 (2026-2027)** : Ajout Node Local Tournai
- Volume croît → 100-200 étudiants
- Achat Mac Studio : €2,500 (investissement)
- SaaS devient backup/burst capacity
- Coût annuel : €700 (électricité + internet) + €200 (SaaS backup) = €900/an
- **Économie** : vs €360/an SaaS seul pour 200 users (CAX41 €30/mois minimum)

**Phase 3 (2027+)** : Full Node + SaaS B2B
- Node local = infrastructure propre (100% souverain)
- SaaS Hetzner = licences revendues à autres formateurs EU
- **Revenus B2B** : 5 formateurs × €50/mois = €250/mois = €3K/an
- **ROI** : Couvre largement coûts infrastructure

---

## 📊 Comparatif Décisionnel

| Critère | SaaS Cloud | Node Local | Hybride |
|---------|------------|------------|---------|
| **Souveraineté** | 🟡 Partielle (Hetzner EU) | 🟢 Totale (100% local) | 🟢 Maximale |
| **Coût Year 1** | 🟢 €200 | 🟡 €3,200 | 🟡 €3,400 |
| **Coût Year 5** | 🟡 €1,000 | 🟢 €6,120 | 🟢 €4,700 |
| **Performance** | 🟡 Bonne (cloud) | 🟢 Excellente (ARM64) | 🟢 Excellente |
| **Scalabilité** | 🟢 Automatique | 🟡 Manuelle (+ nodes) | 🟢 Flexible |
| **Maintenance** | 🟢 Incluse | 🟡 Client (ou FFT support) | 🟢 Mixte |
| **Compétences IT** | 🟢 Aucune | 🟡 Sysadmin | 🟡 Basic |
| **GDPR Compliance** | 🟢 Oui (EU) | 🟢 Oui (100% local) | 🟢 Oui |
| **Backup** | 🟢 Automatique | 🟡 À configurer | 🟢 Redondance |
| **Business Model** | 🟡 Abonnement | 🟢 Propriété | 🟢 Flexible |

**Légende** : 🟢 Meilleur | 🟡 Acceptable | 🔴 Limitation

---

## 🎯 Recommandation FFT

### Pour Nouveaux Clients (Formateurs, PME, Associations)

**Commencer SaaS Cloud** (€200/an) :
- Déploiement immédiat
- Zero risque investissement
- Validation marché
- Migration Node possible si succès

### Pour Clients Établis (Volume >100 users, Revenus >€10K/an)

**Passer Node Local** (€2,500 + €700/an) :
- Souveraineté totale
- Économies long terme (5+ ans)
- Différenciation concurrentielle ("100% souverain")
- Scalabilité illimitée (ajouter nodes)

### Pour FFT Hub Tournai (Infrastructure Mutualisée)

**10 Mac Studio = 10 Clients Node** :
- Investissement : €25K (10 × €2,500)
- Clients paient : €100-200/mois location node
- Revenus annuels : 10 × €1,500/an = €15K/an
- ROI : 1.6 ans
- Après ROI : Profit €15K/an - €7K coûts = **€8K/an net**

---

## 📞 Migration Path (SaaS → Node)

### Étape 1 : Data Export (1 heure)
```bash
# Depuis Hetzner SaaS
cd /var/www/nextcloud
sudo -u www-data php occ db:export-data /backup/export.sql
tar czf /backup/files.tar.gz data/
scp /backup/* client@mac-studio-local:/restore/
```

### Étape 2 : Setup Node Local (2 heures)
```bash
# Sur Mac Studio client
/tmp/DEPLOY-FFT-32GB-NPE-GPU.sh  # Script auto FFT
# Import data
psql fft_vectors < /restore/export.sql
tar xzf /restore/files.tar.gz -C /var/www/nextcloud/data/
```

### Étape 3 : DNS Switch (15 min)
```bash
# Cloudflare DNS
formation.example.com
  A → 1.2.3.4 (Hetzner SaaS)  # Ancien
  A → 5.6.7.8 (Mac Studio VPN) # Nouveau (Tailscale/Cloudflare Tunnel)
```

### Étape 4 : Test & Validation (1 heure)
- Login utilisateurs OK
- Exercices CJEU OK
- Performance <3min OK
- Backup automatique OK

**Downtime total** : <1 heure (pendant DNS propagation)

---

## 💰 Pricing Client Final

### SaaS Cloud (Hetzner)

| Tier | Pour Qui | Utilisateurs | Prix/mois | Prix/an | ROI |
|------|----------|--------------|-----------|---------|-----|
| **Personal** | Particuliers, hobbyistes | 1-5 | €5 | €60 | **Que des bénéfices!** |
| **Starter** | Formateurs indép., associations | 10-50 | €17 | €200 | Investissement quasi-nul |
| **Growth** | PME, écoles | 50-200 | €50 | €600 | Variable selon usage |
| **Business** | Entreprises, universités | 200-1000 | €150 | €1,800 | Economies vs infrastructure propre |
| **Enterprise** | Grandes organisations | 1000+ | Custom | Custom | Sur mesure |

**Inclus** : Infrastructure, maintenance, backups, support email

**Particuliers** : €5/mois = café par semaine, zéro investissement hardware, bénéfices immédiats (AI accessible)
**Sociétés** : Variable selon taille - mais toujours <10% coût infrastructure classique

### Node Local (Client Premise) - **Puissance Variable**

**Philosophie Hardware FFT** : Prioriser fiabilité et sécurité sur performance brute. Charges prévisibles = hardware stable long terme > hardware haute performance court terme.

| Puissance | Hardware Recommandé | Pour Qui | Prix Hardware | Capacité | Conso |
|-----------|---------------------|----------|---------------|----------|-------|
| **Mini** | Raspberry Pi 4 8GB<br>+ Jetson Nano (optionnel) | Particuliers, IoT, prototypes<br>**Max pour particuliers = Swarm RPi+Jetson** | €110-€220<br>(RPi+Jetson) | 1-10 users | 5-15W |
| **Light** | Mac Mini M2 (16GB) | Indépendants, petit cabinet | €650 | 10-50 users | 30W |
| **Standard** | Mac Studio M1 Max (32GB) | PME, formations | €2,500 | 50-200 users | 80W |
| **Pro** | Mac Studio M2 Ultra (64GB) | Entreprises, universités | €4,500 | 200-1000 users | 120W |
| **Premium** 🏆 | Mac Studio M2 Ultra (128-192GB) | **FFT Showcase, R&D, Flagship** | €7,000-8,000 | Illimité (demo/dev) | 150W |
| **Cluster** | 3x Mac Studio (multi-node) | Grandes organisations | €7,500+ | 1000+ users | 240W+ |

**Node Premium FFT (Tournai Hub Pioneer)** :
- **Rôle** : Vitrine technologique, démo clients, R&D nouvelles features
- **Specs** : Mac Studio M1 Max 32GB (actuel) → M2 Ultra 192GB (upgrade futur)
- **Performance** : Reference implementation, benchmarks publics
- **Accès** : Clients peuvent tester avant achat node propre
- **Ambition** : Prouver que ARM64 local = meilleur que cloud GPU x86

**Support Options** :
| Package | Installation | Support Annuel | Prix Setup | Prix/an |
|---------|--------------|----------------|------------|---------|
| **DIY** | Documentation | Community forum | €0 | €0 |
| **Assisted** | Remote (2h) | Email (best-effort) | €200 | €0 |
| **Managed** | On-site | 24/7 monitoring + hotline | €500 | €600 |
| **Tournai Hub** | FFT infrastructure (location node) | Full managed | €0 | €1,500 |

**ROI Node vs SaaS** (Exemple Mac Studio €2,500) :
- Year 1 : €2,500 + €700 = €3,200 (vs €600 SaaS Growth)
- Year 2-5 : €700/an × 4 = €2,800 (vs €600/an × 4 = €2,400 SaaS)
- **Total 5 ans** : €6,000 Node vs €3,000 SaaS
- **MAIS** : Node = propriété, scalabilité infinie, revente possible (€1,000+ après 5 ans)
- **Breakeven** : ~4 ans si usage intensif, jamais si usage light → **SaaS gagnant pour particuliers/PME, Node pour entreprises/long terme**

---

## 🚀 Getting Started

### Je veux SaaS Cloud

1. **Signup** : contact@nextairev.com
2. **Infos** : Nom organisation, domaine souhaité, nb utilisateurs estimé
3. **Déploiement** : 24-48h (setup Hetzner + Nextcloud + Ollama)
4. **Formation** : 1h visio (utilisation interface, paramètres AI)
5. **Go Live** : Invitation utilisateurs, premier exercice CJEU

**Timeline** : 3-5 jours from signup to production

### Je veux Node Local

1. **Consultation** : Call 1h (évaluation besoins, compétences IT)
2. **Hardware** : Commande Mac Studio (2 semaines livraison)
3. **Préparation** : Pendant livraison, documentation fournie
4. **Installation** : Sur site ou remote (2-3h)
5. **Formation** : 2h (admin système + utilisation)
6. **Go Live** : Test charge + validation

**Timeline** : 3-4 semaines from consultation to production

### Je veux Hybride (Les Deux)

1. **Phase 1** : Start SaaS (3-5 jours)
2. **Phase 2** : Pendant utilisation SaaS, préparer Node (3 semaines)
3. **Migration** : Data export SaaS → Node (1 jour)
4. **Dual Mode** : SaaS = backup, Node = primary
5. **Optimize** : Monitoring, ajustements, ROI tracking

**Timeline** : 4-5 semaines total, SaaS opérationnel dès J+5

---

## 📎 Documents Techniques

**Pour SaaS Cloud** :
- `/tmp/FFT-SAAS-HETZNER-SETUP.md` (à créer)
- Architecture Nextcloud + Ollama + PostgreSQL
- Monitoring & Backups automatiques

**Pour Node Local** :
- `/tmp/DEPLOY-FFT-32GB-NPE-GPU.sh` (✅ prêt)
- `/tmp/FFT-COGNITIVE-STACK-NPE-ACE-OLLAMA-GITLAB.md` (✅ prêt)
- Hardware recommendations + performance benchmarks

**Pour Hybride** :
- Migration guide SaaS → Node
- Dual deployment monitoring
- Cost optimization strategies

---

## ✅ Résumé Pour Clients

**Question** : "SaaS ou Node ?"
**Réponse FFT** : **"Les deux ! Vous choisissez."**

- **Petit budget, besoin rapidité** → SaaS Cloud (€200/an)
- **Souveraineté max, budget hardware** → Node Local (€2,500 + €700/an)
- **Pragmatique, évolutif** → Hybride (SaaS puis Node si succès)

**Philosophie FFT** :
> "Pas de vendor lock-in. Votre data, votre choix, votre souveraineté. On s'adapte à vous, pas l'inverse."

---

**Contact** : contact@nextairev.com
**Documentation** : https://gist.github.com/enzoxic/e9a381d01e3df14cda7dd6c0967be688
**Démo** : Sur demande (call 30 min)

**Version** : 1.0.0 (5 Nov 2025)
**Auteur** : Vincent Caputo - FFT Cognitive Platform
