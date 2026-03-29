# Oktopus MCP Server - Binaries

Pre-built binaries for the Oktopus MCP Server.

## Quick Start

### Linux (x86_64)
```bash
curl -L -o oktopus-mcp-server https://github.com/OktopUSP/mcp-server-public/releases/latest/download/oktopus-mcp-server-linux-amd64
chmod +x oktopus-mcp-server
./oktopus-mcp-server
```

### Linux (ARM64)
```bash
curl -L -o oktopus-mcp-server https://github.com/OktopUSP/mcp-server-public/releases/latest/download/oktopus-mcp-server-linux-arm64
chmod +x oktopus-mcp-server
./oktopus-mcp-server
```

### macOS (Intel)
```bash
curl -L -o oktopus-mcp-server https://github.com/OktopUSP/mcp-server-public/releases/latest/download/oktopus-mcp-server-darwin-amd64
chmod +x oktopus-mcp-server
./oktopus-mcp-server
```

### macOS (Apple Silicon)
```bash
curl -L -o oktopus-mcp-server https://github.com/OktopUSP/mcp-server-public/releases/latest/download/oktopus-mcp-server-darwin-arm64
chmod +x oktopus-mcp-server
./oktopus-mcp-server
```

### Windows (PowerShell)
```powershell
Invoke-WebRequest -Uri "https://github.com/OktopUSP/mcp-server-public/releases/latest/download/oktopus-mcp-server-windows-amd64.exe" -OutFile "oktopus-mcp-server.exe"
.\oktopus-mcp-server.exe
```

## Verify Downloads

To verify the integrity of downloaded binaries:

```bash
# Download checksums
curl -L -o SHA256SUMS https://github.com/OktopUSP/mcp-server-public/releases/latest/download/SHA256SUMS

# Verify (macOS/Linux)
sha256sum -c SHA256SUMS

# Verify (Windows PowerShell)
Get-FileHash oktopus-mcp-server-windows-amd64.exe
```

## Available Versions

See [Releases](https://github.com/OktopUSP/mcp-server-public/releases) for all available versions.