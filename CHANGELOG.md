# Changelog

All notable changes to SAP MCP Server will be documented in this file.

## [1.0.0] - 2025-11-03

### Initial Release

#### Features
- 🚀 **24+ MCP tools** for comprehensive SAP development
- 🔧 **Complete ABAP object management** (classes, programs, CDS views, tables, RAP APIs, Service Definitions, Service Bindings)
- 🔍 **Advanced object search** and discovery with filtering
- 📝 **Full source code operations** (get, set, format, syntax check)
- 🔒 **Object locking and activation** workflow
- 🧪 **Unit test execution** and creation
- 📊 **Data preview and SQL query** execution
- 🚚 **Transport management** (check, create, list)
- 🌐 **OData service integration** (v2 and v4)
- 🐳 **Multi-platform Docker support** (AMD64, ARM64)
- 🔐 **Secure credential handling** via HTTP headers

#### Complete Tool List (24 Tools)

**Connection & Authentication:**
- `connect_to_sap` - Initialize SAP system connection with pooled sessions

**Object Discovery & Management:**
- `get_creatable_object_types` - List all creatable SAP object types
- `search_object` - Search objects by name/pattern with type filtering
- `create_object` - Create any SAP object (classes, programs, CDS views, tables, etc.)
- `delete_object` - Delete objects with proper locking
- `get_object_structure` - Get object structure (includes, methods, attributes)

**Source Code Operations:**
- `get_object_source` - Retrieve source code (active/inactive versions)
- `set_object_source` - Update source code with transport integration
- `format_source_code` - Format ABAP code using SAP's pretty printer
- `syntax_check` - Validate ABAP syntax before activation

**Object Locking & Activation:**
- `lock_object` - Lock objects for editing with transport assignment
- `unlock_object` - Release object locks
- `activate_object` - Activate objects after modifications

**Testing & Quality:**
- `run_unit_test` - Execute ABAP unit tests with structured results
- `create_test_class_include` - Create test class includes for ABAP classes

**Data Operations:**
- `get_ddic_object_metadata` - Get metadata/schema for tables and CDS views
- `preview_ddic_data` - Execute SQL queries against tables/CDS views (up to 1000 rows)

**Transport Management:**
- `transport_check` - Check available transport requests for objects
- `create_transport_and_assign` - Create new transports and assign objects
- `list_transports` - List transport requests with filters

**OData & Service Integration:**
- `get_metadata` - Get OData service metadata (v2/v4)
- `call_sap_api_generic` - Call OData APIs with any HTTP method (GET/POST/PUT/PATCH/DELETE)
- `get_service_binding_types` - Get available service binding types
- `create_and_publish_service_binding` - Create and publish complete service bindings

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
docker inspect ghcr.io/vaibhavgoel-github-1986/sap-mcp-server:latest --format='{{.Created}}'
```

### Update Image
```bash
docker pull ghcr.io/vaibhavgoel-github-1986/sap-mcp-server:latest
```

### Restart Container (to use updated image)
```bash
docker restart sap-mcp-server
```

### With Docker Compose
```bash
docker-compose pull && docker-compose up -d --force-recreate
```

---

## Version Format

We follow [Semantic Versioning](https://semver.org/):
- **MAJOR** version for incompatible API changes
- **MINOR** version for new functionality (backwards compatible)
- **PATCH** version for bug fixes (backwards compatible)
