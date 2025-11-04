# SAP MCP Server

Connect GitHub Copilot or Claude to your SAP system. Create, modify, and manage SAP objects using natural language.

📋 **[View Changelog](CHANGELOG.md)** | 🐳 **[Docker Hub](https://github.com/vaibhavgoel-github-1986/sap-mcp-server-docs/pkgs/container/sap-mcp-server)** | 🐛 **[Report Issues](https://github.com/vaibhavgoel-github-1986/sap-mcp-server-docs/issues)**

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

Add this to your VS Code MCP settings (`mcp.json`):

```json
{
  "servers": {
    "sap-mcp-server": {
      "type": "http",
      "url": "http://localhost:8001/mcp/",
      "headers": {
        "x-hostname": "https://your-sap-system.com:44300",
        "x-username": "your_username",
        "x-password": "${input:password}",
        "x-client": "110"
      }
    }
  },
  "inputs": [
    {
      "id": "password",
      "type": "promptString",
      "description": "Enter SAP Password",
      "password": true
    }
  ]
}
```

**Replace:**
- `https://your-sap-system.com:44300` with your SAP system URL
- `your_username` with your SAP username
- `110` with your SAP client number

**That's it!** Now you can ask GitHub Copilot to interact with your SAP system. It will prompt for your password when needed.

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
