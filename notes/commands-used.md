# Setup & Execution Commands

This section contains all key commands used to set up, configure, and run the AI agent in Google Cloud Shell.

---

## 1. Clone Repository

```bash
git clone https://github.com/google/mcp.git
cd mcp/examples/launchmybakery
```

---

## 2. Google Cloud Authentication

```bash
gcloud auth login
gcloud config set project YOUR_PROJECT_ID
gcloud auth application-default login
```

---

## 3. Verify Cloud Environment

```bash
gcloud auth list
gcloud config get project
```

---

## 4. Enable Setup Scripts

```bash
chmod +x setup/setup_env.sh
chmod +x setup/setup_bigquery.sh
```

---

## 5. Configure Environment (APIs + Keys)

```bash
./setup/setup_env.sh
```

This sets up:
- Google Maps API key
- Required APIs
- Environment variables

---

## 6. Setup BigQuery Infrastructure

```bash
./setup/setup_bigquery.sh
```

This creates:
- Dataset: `mcp_bakery`
- Tables: demographics, prices, sales, foot traffic
- Cloud Storage bucket

---

## 7. Create Virtual Environment

```bash
python3 -m venv .venv
source .venv/bin/activate
```

---

## 8. Install ADK

```bash
pip install google-adk==1.28.0
```

---

## 9. Run Agent

```bash
cd adk_agent/
adk web --allow_origins 'regex:https://.*\.cloudshell\.dev'
```

Then open:
```
http://127.0.0.1:8000
```

---

## 10. Cleanup Resources (Important)

```bash
chmod +x cleanup/cleanup_env.sh
./cleanup/cleanup_env.sh
```

This removes:
- BigQuery datasets
- Cloud Storage buckets
- API keys
