<div align="center">

# Axiora

**Structured Japanese Financial Data API**

XBRL-parsed financials for 4,125 Japanese companies via REST API.
Exact data from official EDINET filings.

[Website](https://axiora.dev) · [API Docs](https://axiora.dev/en/docs) · [Changelog](https://axiora.dev/en/changelog) · [llms.txt](https://axiora.dev/llms.txt)

</div>

---

### Quick start

```python
import requests

resp = requests.get(
    "https://api.axiora.dev/v1/companies/E02144/financials",
    headers={"Authorization": "Bearer ax_live_YOUR_KEY"}
)

data = resp.json()["data"][0]
print(data["revenue"])     # 29929992000000
print(data["net_income"])  # 4944933000000
```

### What you get

- **4,125 companies** — every filer on EDINET with parsed financials
- **25 normalized metrics** — revenue, income, assets, cash flows, EPS, ROE
- **12,000+ filings** — annual, semi-annual, and quarterly reports
- **30-minute freshness** — automated EDINET polling during market hours
- **MCP server** — 19 tools for Claude, Cursor, and AI agents
- **Bilingual** — full English + Japanese support

### Endpoints

```
GET  /v1/companies              Search companies
GET  /v1/companies/:code/financials  Financial data
GET  /v1/companies/:code/ratios      ROE, margins, etc.
GET  /v1/companies/:code/growth      YoY growth & CAGR
GET  /v1/filings                Parsed filings
GET  /v1/screen                 Screen by criteria
GET  /v1/rankings/:metric       Top-N rankings
GET  /v1/compare                Side-by-side comparison
GET  /v1/timeseries             Time series data
GET  /v1/bulk/financials.csv    Bulk export
POST /v1/webhooks               Filing alerts
SSE  /mcp                       MCP server (AI tools)
```

### Pricing

| Tier | Price | Rate Limit |
|------|-------|-----------|
| Free | $0/mo | 10,000 req/day |
| Pro | $99/mo | 50,000 req/day |
| Institutional | $500/mo | 200,000 req/day |

All endpoints available on every tier. [Get a free API key →](https://axiora.dev/en/login)

### Links

- **Website**: [axiora.dev](https://axiora.dev)
- **Docs**: [axiora.dev/en/docs](https://axiora.dev/en/docs)
- **llms.txt**: [axiora.dev/llms.txt](https://axiora.dev/llms.txt)
- **Contact**: onkardahale@protonmail.com

---

*Data sourced from EDINET (Financial Services Agency of Japan). Axiora is not affiliated with FSA or EDINET.*
