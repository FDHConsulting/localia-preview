# localia-preview

# 🌐 **LocalIA — IA Souveraine, Agentique & Orchestrée**

### *Un écosystème complet d’IA locale, multimodale, auditable et gouvernable*

LocalIA est une **architecture IA souveraine**, conçue pour fonctionner **entièrement en local**, sans dépendance cloud, en utilisant des **LLM open source**, une **orchestration agentique**, un **bus REST JSON**, un **RAG totalement local**, et des **workflows automatisés n8n**.

L’écosystème est pensé pour :

* la **souveraineté technique**
* la **traçabilité**
* la **qualité GxP**
* la **gouvernance collaborative**
* et la **simplicité opérationnelle**

---

# 🎯 **Objectifs de LocalIA**

* Fournir une **architecture complète IA-first**, exécutable sur une seule machine locale.
* Créer un cadre d’**agents spécialisés** orchestrés via un **Agent-Bus REST**.
* Garantir une **auditabilité totale** : JSON-first, logs, endpoints health, événements traçables.
* Supporter des **pipelines multimodaux** (texte, audio, image, vidéo).
* Intégrer un **RAG local** robuste (AnythingLLM).
* Permettre une **orchestration no-code** (n8n).
* Supporter les environnements **régulés** (Finance, Pharma, Public).

---

# 🧠 **Architecture Globale**

Voici le flux fonctionnel et technique :

```
                ┌───────────────────┐
                │   Open WebUI      │
                │  (Interface IA)   │
                └─────────┬─────────┘
                          │ Prompt
                          ▼
           ┌────────────────────────────────┐
           │         LocalIA-Bus Flask      │
           │ (Agent Manager + Router REST)  │
           └───────────┬───────────┬────────┘
                       │           │
     ┌─────────────────┘           └──────────────────┐
     ▼                                                ▼
┌──────────────┐                              ┌────────────────┐
│ AgentQwen     │   (LLM locaux : Qwen,        │  RAG Engine    │
│ /AgentMistral │    Mistral, LocalAI/Ollama)  │ AnythingLLM    │
└──────────────┘                              └────────────────┘
        │                                               │
        ▼                                               ▼
┌────────────────┐                            ┌────────────────────┐
│ Whisper+Silero │→ pipeline audio           │ ComfyUI multimodal │
└────────────────┘                            └────────────────────┘

            ┌───────────────────────────────────┐
            │         n8n Workflows             │
            │  (Orchestration universelle)      │
            └──────────────────┬────────────────┘
                               ▼
                      ┌────────────────┐
                      │   Odoo API     │
                      │ (CRM / Project │
                      └────────────────┘
```

---

# 🏗️ **Composants Principaux**

## 🔵 1. **LLM locaux (GPU)**

* **LocalAI** (Qwen 8B, Mistral 7B)
* **Ollama** (fallback / testing)
* Paramétrage optimisé pour **RTX 5070**
* Support complet JSON Mode

## 🟣 2. **LocalIA-Bus**

*Le cœur de l’architecture agentique.*

* REST Router - Flask
* Agent Manager
* Workflow engine interne
* Endpoints : `/qualify`, `/retrieve`, `/generate`, `/agents/<name>`
* Traçabilité par événement

## 🟡 3. **Agents spécialisés**

* **AgentObsi** – Intégration Obsidian / Vault Markdown
* **AgentDatabase** – Persistance documents - Logs
* **AgentQwen** – LLM - Inférences Internes/Externes -> Génération texte/JSON 
* **AgentAnalyzer** – Analyse structurée et contextualisées (RAG)
* **AgentDispia** – Proxy API/REST - OpenAi Compatible
* Expandable : plugins JSON simples

## 🔴 4. **RAG local (AnythingLLM - Open-WebUI)**

* Indexation multi-dossiers
* Recherche hybride embedding + keyword
* Contexte totalement maîtrisé (données locales uniquement)
* Muli-modèles: Internes (LocalAi - Ollama) ou externes 
* Supporte schémas, documents, JSON, logs

## 🟢 5. **Multimodalité**

* **Whisper** : transcription locale
* **Silero VAD** : détection voix
* **ComfyUI** : génération image/vidéo, pipelines visuels
* **Couche OCR** : pdfPlumber,tesseract,transformers/all‑MiniLM‑L6‑v2,.. 

## 🟠 6. **Orchestration n8n**

* Health checks
* Webhooks
* Workflows agentiques
* Automatisation LocalIA → Odoo
* Pipelines “full IA-first” (Qualify → RAG → Generate → Action)

## 🟤 7. **Triple persistance**

* **database** : PostgeSQL, MongoDB
* **Vault Markdown Obsidian** (notes + contexte humain)
* **CLT structuré** (json + embedding + métadonnées)

---

# 🔒 **Compliance by Design**

LocalIA implémente les principes de conformité :

* **Audit trail complet**
* **JSON-first** (reproductibilité)
* **Health endpoints standardisés**
* **Séparation agent/activity**
* **Logs structurés**
* **Aucune dépendance cloud**
* **Traçabilité du contexte RAG**
* **Architecture modulaire validable**

---

# ⚙️ **Stack Technique**

* Docker Compose
* LocalAI (CPU/GPU)
* Ollama (CPU/GPU)
* AnythingLLM
* Open-Webui
* Whisper / Silero
* n8n Automations
* PostgreSQL
* Python agents (Flask Bus)
* ComfyUI
* FastAPI / microservices
* Odoo API (CRM / Project)

---

# 🚀 **Exemple de Workflow : Devis IA → Odoo**

```
Prompt → Qualify → RAG → Generate JSON → Odoo API → CRM / Project
```

Niveaux de sortie :

* Contact créé/récupéré
* Lead CRM créé
* Devis généré automatiquement - Localia
* Tâches Project mises à jour dans Odoo
* Processus entièrement traçable

---

# 🧬 **Philosophie LocalIA**

LocalIA est basé sur :

* **Triangle Gouvernail** (Démocratie — Distribution — Respect du Vivant)
* **Gouvernance distribuée (Holacratie)**
* **Clarté relationnelle (CNV)**
* **Souveraineté numérique**
* **Simplicité technique**
* **Auditabilité & Compréhensibilité** (anti-boîte noire)

---

# 👤 **À propos de l'auteur**

**Francis De Hertogh**
Architecte IA Souveraine & Agentique
25+ ans d’architecture logicielle (finance, pharma, public)
Certifié **GxP / Compliance by Design**
Créateur de l’écosystème LocalIA

---

# ✔️ **Ready for IA-First**

LocalIA est une démonstration un credo:
➡ une IA peut être **locale**, **éthique**, **agentique**, **auditable**, **souveraine**,
➡ tout en restant **simple à déployer** et **adaptée aux entreprises modernes**.

---

**⚠️ Limites & Portée Actuelle**

LocalIA est une architecture exploratoire, conçue initialement comme un
laboratoire personnel pour étudier :

l’orchestration agentique locale
la souveraineté technique
la RAG contrôlée
les pipelines multimodaux
la conformité par design

Il ne s’agit pas d’un produit “enterprise-ready”, mais d’une preuve de concept complète,
adaptée aux environnements :
individuels (dev IA, prototypage, recherche)
petits collectifs
petites structures / équipes R&D
démonstrations / ateliers IA souveraine

👉 L’architecture peut être industrialisée, mais ne prétend pas l’être aujourd’hui.
👉 LocalIA sert surtout de référence technique, d’exemple inspirant,
et d’outil personnel de production pour explorer les modèles locaux.
