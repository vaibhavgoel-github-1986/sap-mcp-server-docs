# Changelog

All notable changes to SAP MCP Server will be documented in this file.

## [1.0.0] - 2025-11-03

### Initial Release

#### Features
- 🚀 24+ MCP tools for SAP development
- 🔧 ABAP object management (classes, programs, CDS views, tables, RAP APIs, Service Def, Service Binding)
- 🔍 Object search and discovery
- 📝 Source code operations (get, set, format, syntax check)
- 🔒 Object locking and activation
- 🧪 Unit test execution and creation
- 📊 Data preview and SQL query execution
- 🚚 Transport management
- 🌐 OData service integration (v2 and v4)
- 🐳 Multi-platform Docker support (AMD64, ARM64)
- 🔐 Secure credential handling via HTTP headers

#### Supported Platforms
- macOS (Intel x86_64 and Apple Silicon ARM64)
- Windows (via Docker Desktop)
- Linux (AMD64 and ARM64)

#### Integration
- GitHub Copilot (VS Code)
- Claude Desktop
- Any MCP-compatible client

---

## How to Update

### Check Current Version
```bash
docker inspect ghcr.io/vaibhavgoel-github-1986/sap-mcp-server:latest | grep version
```

### Update to Latest
```bash
docker pull ghcr.io/vaibhavgoel-github-1986/sap-mcp-server:latest
docker stop sap-mcp-server
docker rm sap-mcp-server
docker run -d -p 8001:8001 --name sap-mcp-server ghcr.io/vaibhavgoel-github-1986/sap-mcp-server:latest
```

### With Docker Compose
```bash
docker-compose pull
docker-compose down
docker-compose up -d
```

---

## Version Format

We follow [Semantic Versioning](https://semver.org/):
- **MAJOR** version for incompatible API changes
- **MINOR** version for new functionality (backwards compatible)
- **PATCH** version for bug fixes (backwards compatible)
