# N8N Workflows

A collection of [n8n](https://n8n.io/) automation workflows — ready to import, configure, and run.

**Repository:** [github.com/muhammadumersheraz1/N8N](https://github.com/muhammadumersheraz1/N8N)

---

## Workflows

| # | Workflow | Description | Folder |
|---|----------|-------------|--------|
| 1 | **Website Status Monitor** | Check any website every 5 minutes and send Gmail alerts when up or down | [`website-status-monitor/`](./website-status-monitor/) |
| 2 | **Airtable Book Store AI Agent** | Chat with AI to search and update book inventory in Airtable | [`airtable-book-store-ai/`](./airtable-book-store-ai/) |

---

## Quick import

1. Clone this repo or download a workflow folder
2. Open n8n → **Workflows** → **Import from File**
3. Select the `workflow.json` inside the workflow folder
4. Follow the README in that folder for credentials and setup

---

## Structure

Each workflow folder contains:

```
workflow-name/
├── workflow.json          # Import into n8n
├── workflow-diagram.png   # Visual architecture
└── README.md              # Setup guide
```

---

<p align="center">
  <a href="https://n8n.io"><img src="https://img.shields.io/badge/n8n-Automation-EA4B71?style=for-the-badge&logo=n8n&logoColor=white" alt="n8n"></a>
</p>
