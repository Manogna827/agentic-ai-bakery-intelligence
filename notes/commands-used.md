# Commands Used During Setup

## Clone Repository
```bash
git clone https://github.com/google/mcp.git
```

## Navigate to Project
```bash
cd mcp/examples/launchmybakery
```

## Authenticate
```bash
gcloud auth application-default login
```

## Setup Environment
```bash
chmod +x setup/setup_env.sh
./setup/setup_env.sh
```

## Setup BigQuery
```bash
chmod +x ./setup/setup_bigquery.sh
./setup/setup_bigquery.sh
```

## Install ADK
```bash
pip install google-adk==1.28.0
```

## Run ADK Server
```bash
adk web --allow_origins 'regex:https://.*\.cloudshell\.dev'
```
