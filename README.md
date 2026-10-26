# AI-Driven Financial Data Lake & Tax Compliance Engine

An enterprise-grade, end-to-end financial data engineering platform designed to ingest, normalize, and analyze complex fiscal data for a portfolio of **120 corporate clients**. Built using the **Software Driven Development (SDD)** method, this platform integrates multi-channel ETL pipelines, a centralized cloud data lake, and Generative AI agents to execute predictive tax reform simulations, validate multi-model invoice compliance, and automate corporate cost modeling.

## 🚀 Core Value Proposition & Business Impact
* **Rapid Strategic Modeling:** Accelerated a multi-scenario tax cost analysis (comparing Simplified, Threshold-Breached, and Presumed Profit regimes under the new tax reform) from 8+ billable hours to seconds using real-time Data Lake queries.
* **Proactive Tax Compliance:** Automated structural invoice validation against upcoming CBS and IBS frameworks to mitigate fiscal penalties before book-closing.
* **Zero-Touch Ingestion:** Replaced manual reporting workflows with automated API aggregators and scheduled cron scripts handling digital certificates and third-party gateways.

---

## 🏗️ System Architecture & Data Flow

### 1. Multi-Channel Ingestion & ETL Layer
The orchestration layer handles diverse structural and unstructured financial vectors:
* **Government API Integration:** Direct integration with the National Service Invoice (NFSe) portal, leveraging a secure centralized digital certificate vault to fetch issued and received service data.
* **Third-Party Gateways:** Direct REST API consumption of the "SIEG" platform to automate the collection of Model 55 Fiscal Invoices (NF-e).
* **Automated File Routing:** Scheduled cron jobs partition and deposit harvested XML/JSON data streams into client-specific local server directory structures mapped by client ERP IDs, month, and fiscal year.
* **Orchestration Pipelines (n8n):** Three standalone workflows handle automated enrichment:
  * **Workflow A:** Continuous monitoring and lookup of client/supplier fiscal profiles (Simples Nacional vs. Normal Regime) via external API.
  * **Workflow B:** Automated ingestion of PGDAS data via the "Integra Contador" API wrapper.
  * **Workflow C:** Automated trigger mechanisms for the National NFSe retrieval loop.

### 2. Centralized Cloud Data Lake
* **Storage Engine:** Fully architected on **Supabase** (PostgreSQL-backed), utilizing strict relational constraints, optimized indexing for quick client-ERP tracking, and secure environment isolation for company metadata and certificate authentication.

### 3. AI Coprocessor & Analytics Framework
The platform exposes database vectors to Advanced LLMs (Anthropic Claude / OpenAI GPT) through semantic prompts to perform specialized tasks:
* **Dynamic Rule Extraction:** Automatically parses PGDAS ledger text streams to extract active PIS and COFINS baseline rates for historical tax simulation inputs.
* **Compliance Mapping:** Validates legacy invoice line-items against projected rules for CBS (Contribuição sobre Bens e Serviços) and IBS (Imposto sobre Bens e Serviços).
* **Ad-hoc Cost Optimization:** Feeds real-time inventory and pricing parameters straight from the data lake into the LLM context window to automatically compile structural product costing sheets across competing tax regimes.

---

## 🧠 The SDD Approach (Software Driven Development)

This system was developed entirely under the **SDD methodology**, utilizing AI-assisted pair programming (via Cursor) to ensure that code architecture maps explicitly to domain-specific accounting rules. 

Instead of treating software constraints as the starting point, **the domain rules (Tax Code, IFRS-adjacent guidelines, and Fiscal Deadlines) directly drove the schema definitions, API contracts, and agent behaviors.** This guarantees absolute alignment between database states and legal corporate compliance requirements.

---

## 🛠️ Tech Stack

* **Backend & Orchestration:** Python, RESTful APIs, n8n Automation Framework.
* **Database & Data Lake:** Supabase (PostgreSQL), Cloud Storage Vaults.
* **AI & LLM Integration:** Claude API, OpenAI API, Cursor IDE Ecosystem.
* **OS & Automation:** Task Scheduler / Cron Utilities, Secure Local File Directories.

## 📈 Enterprise Production Capabilities
* **Client Portfolio Size:** ~120 active managed corporate accounts.
* **Data Scenarios Handled:** Historical data uploads, Real-time API streaming, Digital Certificate-based verification loops.
