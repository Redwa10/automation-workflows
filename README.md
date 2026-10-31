# ⚡ Production-Grade n8n Automation Workflows (50+)

A curated collection of over 50 production-ready, modular **n8n** automation workflows designed to streamline operations across healthcare, e-commerce, CRM, sentiment analysis, procurement, and clinical operations.

Each workflow includes sanitized JSON templates, custom JavaScript transformation nodes, error-handling routines, and integration recipes across popular platforms (Google Workspace, Slack, REST APIs, Webhooks, Databases).

---

## 📌 Featured Architecture: Clinical Communication Hub

An enterprise healthcare communication and triage pipeline built for dental and oral surgery practices.

### Key Capabilities
* **Dynamic Due-Date Engine:** Automatically calculates procedure-dependent lab deadlines (business days only) upon order submission and syncs statuses across Google Sheets and Slack.
* **Automated Post-Op Red Flag Triage:** Monitors post-operative survey entries in real time, screening for pain scores (>7) and high-risk medical keywords (e.g., *bleeding*, *swelling*, *infection*) to broadcast immediate priority alerts to emergency clinical channels.
* **Morning Huddle Generator:** Schedules a 7:30 AM daily briefing scanning surgical schedules for medical alerts (cardiac issues, blood thinners, hypertension) to prepare the surgical team with flagged risk profiles.
* **Global Fault Tolerance:** Centralized error-handling node logging workflow crashes and error traces directly to an administrative Slack channel.

```text
               ┌───────────────────────────────┐
               │    Google Sheets / Webhooks   │
               └──────────────┬────────────────┘
                              │
               ┌──────────────▼────────────────┐
               │  JavaScript Logic & Parsing   │
               │  - Business Day Calculations  │
               │  - Symptom & Keyword Triage   │
               └──────────────┬────────────────┘
                              │
         ┌────────────────────┼────────────────────┐
         │                    │                    │
┌────────▼────────┐  ┌────────▼────────┐  ┌────────▼────────┐
│  Lab Alerts &   │  │  Urgent PostOp  │  │ Morning Huddle  │
│ Tracking Update │  │ Clinical Alert  │  │ Briefing Channel│
└─────────────────┘  └─────────────────┘  └─────────────────┘
```

---

## 📂 Repository Directory Structure

```text
├── clinical-healthcare/
│   ├── clinical-communication-hub.json
│   ├── patient-intake-automation.json
│   └── appointment-reminder-engine.json
├── ecommerce-procurement/
│   ├── stockroom-inventory-sync.json
│   ├── shopify-order-fulfillment.json
│   └── supplier-invoice-processing.json
├── crm-sentiment/
│   ├── feedback-sentiment-routing.json
│   ├── referral-payout-engine.json
│   └── lead-enrichment-pipeline.json
├── operations-waste-management/
│   ├── route-pickup-optimizer.json
│   └── bin-sensor-telemetry.json
└── templates/
    └── standard-error-handler.json
```

---

## 🛠️ Workflow Domains Covered

| Category | Typical Integrations | Key Operations |
| :--- | :--- | :--- |
| **Healthcare & Clinics** | Google Sheets, Slack, Webhooks | Triage filtering, schedule briefs, lab SLA computation |
| **E-Commerce & Retail** | Shopify, Stripe, Airtable, Gmail | Inventory alerts, refund management, order lifecycle |
| **Customer Success** | Discord, Zendesk, PostgreSQL | Sentiment tagging, priority routing, automated CSAT |
| **DevOps & Internal Tools** | GitHub, Docker, Telegram, Slack | Webhook relays, uptime monitoring, incident dispatch |

---

## 🚀 Quickstart: How to Import

1. Clone this repository:
   ```bash
   git clone [https://github.com/](https://github.com/)<your-username>/<repo-name>.git
   ```
2. Open your self-hosted or cloud **n8n** instance.
3. In the left navigation bar, navigate to **Workflows**.
4. Click **Add Workflow** > **Import from File...** (or copy the raw contents of any `.json` file and paste directly into the n8n canvas using `Ctrl+V` / `Cmd+V`).
5. Configure your environment credentials (e.g., Google OAuth2, Slack API, Database tokens) for each node marked with missing credentials.
6. Toggle the workflow to **Active**.

---

## 🔒 Security & Data Hygiene

* **Zero Hardcoded Secrets:** All credentials, webhook tokens, and client secrets have been stripped and replaced with generic placeholder IDs (`OAuth2Api`, standard environment variables).
* **HIPAA / GDPR Best Practices:** Workflows transmitting personal identifying information (PII) utilize sanitized payload mapping and enforce targeted channel alerts rather than broad broadcasts.

---

## 📄 License

Distributed under the MIT License. See `LICENSE` for more information.
