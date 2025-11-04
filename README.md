# SAP MCP Server

Connect GitHub Copilot or Claude to your SAP system. Create, modify, and manage SAP objects using natural language.

## 🚀 Quick Start - 2 Options

### Option 1: One Command (Easiest)

```bash
docker run -d -p 8001:8001 --name sap-mcp-server ghcr.io/vaibhavgoel-github-1986/sap-mcp-server:latest
```

### Option 2: Docker Compose (Recommended)

1. Download the configuration:
```bash
curl -O https://raw.githubusercontent.com/vaibhavgoel-github-1986/sap-mcp-server-docs/main/docker-compose.yml
```

2. Start the server:
```bash
docker-compose up -d
```

---

## VS Code Configuration

Add this to your VS Code `settings.json`:

```json
{
  "mcp.servers": {
    "sap-mcp-server": {
      "url": "http://localhost:8001/sse",
      "transport": "sse"
    }
  }
}
```

**That's it!** Now you can ask GitHub Copilot to interact with your SAP system.

---

## Usage Examples

Ask Copilot:
- "Search for ABAP class Z_CUSTOMER_API"
- "Create a new CDS view for customer data"
- "Show me the code for program Z_SALES_REPORT"
- "Activate the object Z_MY_CLASS"
- Create an unit test class for ZCL_GET_PRODUCTS

---

## Configuration (Optional)

Pass SAP credentials via environment variables:

```bash
docker run -d -p 8001:8001 \
  -e SAP_HOST="https://your-sap-system.com:8000" \
  -e SAP_USERNAME="your_username" \
  -e SAP_PASSWORD="your_password" \
  -e SAP_CLIENT="110" \
  ghcr.io/vaibhavgoel-github-1986/sap-mcp-server:latest
```

Or pass them in HTTP headers when Copilot makes requests (safer).

---

## Features

- ✅ **Create & Modify** - ABAP classes, programs, CDS views, tables
- ✅ **Search** - Find objects across your SAP system
- ✅ **Execute** - Call OData APIs, preview data
- ✅ **Manage** - Activate objects, manage transports
- ✅ **Multi-platform** - Works on Mac (Intel & Apple Silicon), Windows, Linux

---

## Troubleshooting

**Port already in use?**
```bash
docker run -d -p 8002:8001 --name sap-mcp-server ghcr.io/vaibhavgoel-github-1986/sap-mcp-server:latest
```

**Check logs:**
```bash
docker logs sap-mcp-server
```

**Stop/restart:**
```bash
docker stop sap-mcp-server
docker start sap-mcp-server
```

---

## Support

🐛 Found a bug? [Open an issue](https://github.com/vaibhavgoel-github-1986/sap-mcp-server-docs/issues)

---

## License

MIT License - Free to use
