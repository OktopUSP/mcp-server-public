# Oktopus MCP Server - Binaries

Pre-built binaries for the Oktopus MCP Server.

## Getting Started

Follow these steps in order to download, configure, and run the Oktopus MCP Server:

### Step 1: Download the Binary

Choose the appropriate binary for your operating system and architecture:

#### Linux (x86_64)
```bash
curl -L -o oktopus-mcp-server https://github.com/OktopUSP/mcp-server-public/releases/latest/download/oktopus-mcp-server-linux-amd64
chmod +x oktopus-mcp-server
```

#### Linux (ARM64)
```bash
curl -L -o oktopus-mcp-server https://github.com/OktopUSP/mcp-server-public/releases/latest/download/oktopus-mcp-server-linux-arm64
chmod +x oktopus-mcp-server
```

#### macOS (Intel)
```bash
curl -L -o oktopus-mcp-server https://github.com/OktopUSP/mcp-server-public/releases/latest/download/oktopus-mcp-server-darwin-amd64
chmod +x oktopus-mcp-server
```

#### macOS (Apple Silicon)
```bash
curl -L -o oktopus-mcp-server https://github.com/OktopUSP/mcp-server-public/releases/latest/download/oktopus-mcp-server-darwin-arm64
chmod +x oktopus-mcp-server
```

#### Windows (PowerShell)
```powershell
Invoke-WebRequest -Uri "https://github.com/OktopUSP/mcp-server-public/releases/latest/download/oktopus-mcp-server-windows-amd64.exe" -OutFile "oktopus-mcp-server.exe"
```

### Step 2: Verify the Binary (Optional but Recommended)

To verify the integrity of the downloaded binary:

```bash
# Download checksums
curl -L -o SHA256SUMS https://github.com/OktopUSP/mcp-server-public/releases/latest/download/SHA256SUMS

# Verify (macOS/Linux)
sha256sum -c SHA256SUMS

# Verify (Windows PowerShell)
Get-FileHash oktopus-mcp-server-windows-amd64.exe
```

### Step 3: Configure Environment Variables

Before running the binary, you must set the required environment variables:

#### Required Variables

- **`API_BASE_URL`**: Base URL of the Oktopus Controller API (e.g., `http://localhost:8000`)
- **`MCP_AUTH_TOKEN`**: Authentication token from Oktopus Controller login

#### Transport Configuration

- **`MCP_TRANSPORT`**: Communication protocol - `stdio` or `http` (default: `stdio`)

#### HTTP Transport Variables (when `MCP_TRANSPORT=http`)

- **`MCP_HTTP_ADDR`**: HTTP server listening address (e.g., `:8090`)
- **`MCP_ENDPOINT_PATH`**: MCP endpoint path (e.g., `/mcp`)
- **`MCP_PUBLIC_BASE_URL`**: Public HTTPS URL of the service (e.g., `https://mcp.example.com`) - **required for production**

#### Optional Variables

- **`MCP_ALLOWED_ORIGINS`**: Comma-separated list of allowed CORS origins
- **`MCP_OAUTH_SCOPES`**: OAuth scopes (default: `mcp:access`)
- **`MCP_OAUTH_AUTHORIZATION_CODE_TTL`**: Authorization code TTL (default: `5m`)
- **`MCP_OAUTH_SESSION_TTL`**: Session TTL (default: `30m`)

### Step 4: Run the Binary

Choose the appropriate instructions for your operating system:

#### Linux/macOS (stdio transport)
```bash
export API_BASE_URL=http://localhost:8000
export MCP_AUTH_TOKEN=your_token_here
export MCP_TRANSPORT=stdio
./oktopus-mcp-server
```

#### Linux/macOS (HTTP transport)
```bash
export API_BASE_URL=http://localhost:8000
export MCP_AUTH_TOKEN=your_token_here
export MCP_TRANSPORT=http
export MCP_HTTP_ADDR=:8090
export MCP_ENDPOINT_PATH=/mcp
export MCP_PUBLIC_BASE_URL=https://mcp.example.com
./oktopus-mcp-server
```

#### Windows (PowerShell - stdio transport)
```powershell
$env:API_BASE_URL = "http://localhost:8000"
$env:MCP_AUTH_TOKEN = "your_token_here"
$env:MCP_TRANSPORT = "stdio"
.\oktopus-mcp-server.exe
```

#### Windows (PowerShell - HTTP transport)
```powershell
$env:API_BASE_URL = "http://localhost:8000"
$env:MCP_AUTH_TOKEN = "your_token_here"
$env:MCP_TRANSPORT = "http"
$env:MCP_HTTP_ADDR = ":8090"
$env:MCP_ENDPOINT_PATH = "/mcp"
$env:MCP_PUBLIC_BASE_URL = "https://mcp.example.com"
.\oktopus-mcp-server.exe
```

## Available Versions

See [Releases](https://github.com/OktopUSP/mcp-server-public/releases) for all available versions.