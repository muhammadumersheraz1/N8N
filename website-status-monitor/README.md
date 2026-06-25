# Website Status Monitor (Every 5 Min)

n8n workflow that checks a website every **5 minutes** and sends a Gmail alert based on the HTTP status code.

## Flow

![Workflow diagram](./workflow-diagram.png)

```
Every 5 Minutes → Check Website → Status Code 200?
                                      ├─ Yes → Gmail: Website is ok
                                      └─ No  → Gmail: Website is down
```

## What it does

| Step | Node | Description |
|------|------|-------------|
| 1 | **Every 5 Minutes** | Schedule trigger — runs every 5 minutes |
| 2 | **Check Website** | Sends HTTP GET request to your website |
| 3 | **Status Code 200?** | Checks if response status is `200` |
| 4 | **Gmail - Website OK** | Sends email: *"Website is ok"* |
| 5 | **Gmail - Website Down** | Sends email: *"Website is down"* |

**Recipient:** `muhammadumersheraz@gmail.com`

## Files

| File | Description |
|------|-------------|
| `workflow.json` | n8n workflow — import this into n8n |
| `workflow-diagram.png` | Visual diagram of the workflow |
| `README.md` | This documentation |

## Import into n8n

1. Open n8n → **Workflows** → **Import from File**
2. Select `workflow.json`
3. Configure the settings below
4. Toggle workflow **Active**

## Configuration

### 1. Website URL

In the **Check Website** node, replace:

```
https://example.com
```

with your actual website URL. Also update the URL in both Gmail message bodies.

### 2. Gmail credentials

1. Open either **Gmail** node
2. Click **Credential** → **Create new** → **Gmail OAuth2**
3. Click **Sign in with Google** and authorize your account
4. Use the same credential on both Gmail nodes

### 3. Activate

Toggle the workflow to **Active** in the top-right corner.

## Email messages

**When status is 200:**
```
Website: https://example.com
Status Code: 200

Website is ok
```

**When status is not 200 or site is unreachable:**
```
Website: https://example.com
Status Code: No response / connection failed

Website is down
```

## Requirements

- [n8n](https://n8n.io/) instance (self-hosted or cloud)
- Google account with Gmail OAuth connected in n8n

## Notes

- Emails are sent **every 5 minutes** regardless of status (OK or DOWN).
- To alert only when the site goes down, add a filter or memory node before the Gmail nodes.
- Default website URL is `https://example.com` — change it before activating.
