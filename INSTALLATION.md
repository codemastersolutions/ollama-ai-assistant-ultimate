# 🚀 Installation & Setup Guide

## 📋 Prerequisites

### System Requirements
- **VSCode**: Version 1.74.0 or higher
- **Node.js**: Version 16.0.0 or higher
- **Memory**: Minimum 8GB RAM (16GB recommended)
- **Storage**: 2GB free space for models

### Supported Operating Systems
- ✅ Windows 10/11
- ✅ macOS 10.15+ (Intel & Apple Silicon)
- ✅ Linux (Ubuntu, Debian, Fedora, Arch)

---

## 🛠️ Step 1: Install Ollama

### Windows
1. Download installer from [ollama.com/download](https://ollama.com/download)
2. Run `OllamaSetup.exe` as Administrator
3. Follow installation wizard
4. Verify: Open PowerShell and run `ollama --version`

### macOS
```bash
# Using Homebrew (recommended)
brew install ollama

# Or download installer
curl -fsSL https://ollama.com/install.sh | sh
```

### Linux
```bash
# Ubuntu/Debian
curl -fsSL https://ollama.com/install.sh | sh

# Fedora
sudo dnf install ollama

# Arch Linux
sudo pacman -S ollama

# Manual installation
wget https://github.com/jmorganca/ollama/releases/latest/download/ollama-linux-amd64
sudo mv ollama-linux-amd64 /usr/local/bin/ollama
sudo chmod +x /usr/local/bin/ollama
```

---

## 🧠 Step 2: Download AI Models

### Essential Models (Required)
```bash
# Core chat model (4GB)
ollama pull llama3.1

# Code completion model (4GB)
ollama pull codestral:7b

# Image analysis model (4GB)
ollama pull llava
```

### Optional Models (Enhanced Features)
```bash
# Advanced code analysis (7GB)
ollama pull deepseek-coder

# Lightweight vision model (2GB)
ollama pull moondream

# Alternative chat model (4GB)
ollama pull mistral
```

### Verify Installation
```bash
ollama list
# Should show all downloaded models

ollama serve
# Starts Ollama server on http://localhost:11434
```

---

## 📦 Step 3: Install VSCode Extension

### Method 1: VS Code Marketplace (Recommended)
1. Open VSCode
2. Go to Extensions (`Ctrl+Shift+X`)
3. Search "Ollama AI Assistant Ultimate"
4. Click **Install** on the extension by `codemastersolutions`
5. Reload VSCode when prompted

### Method 2: Command Line
```bash
code --install-extension codemastersolutions.ollama-ai-assistant-ultimate
```

### Method 3: Manual Installation
1. Download `.vsix` file from [GitHub Releases](https://github.com/codemastersolutions/ollama-ai-assistant-ultimate/releases)
2. In VSCode: `Ctrl+Shift+P` → "Extensions: Install from VSIX"
3. Select downloaded file

---

## ⚙️ Step 4: Configuration

### Basic Setup (Local)
No configuration needed! Extension works out of the box with default settings.

### Advanced Configuration
Open VSCode Settings (`Ctrl+,`) and search "ollama":

```json
{
  // Core Settings
  "ollamaAI.apiUrl": "http://localhost:11434",
  "ollamaAI.model": "llama3.1",

  // Code Completion
  "ollamaAI.codeCompletion.enabled": true,
  "ollamaAI.codeCompletion.model": "codestral:7b",
  "ollamaAI.codeCompletion.maxTokens": 100,

  // AI Agents
  "ollamaAI.agents.enabled": true,
  "ollamaAI.agents.maxConcurrent": 3,

  // Multimodal
  "ollamaAI.multimodal.enabled": true,
  "ollamaAI.multimodal.model": "llava",

  // RAG Knowledge Base
  "ollamaAI.rag.enabled": true,
  "ollamaAI.rag.indexingDepth": "standard",

  // Security Scanner
  "ollamaAI.security.enabled": true,
  "ollamaAI.security.realtime": false
}
```

---

## 🌐 Network & Remote Setup

### Network Configuration (Team Setup)
```json
{
  "ollamaAI.apiUrl": "http://192.168.1.100:11434",
  "ollamaAI.connectionTimeout": 45000,
  "ollamaAI.allowInsecureConnections": true
}
```

### Remote Server Setup
```json
{
  "ollamaAI.apiUrl": "https://ollama.yourcompany.com",
  "ollamaAI.apiKey": "your-api-key",
  "ollamaAI.customHeaders": {
    "Authorization": "Bearer your-token",
    "X-Custom-Header": "value"
  }
}
```

### Enterprise Proxy Setup
```json
{
  "ollamaAI.proxy": {
    "host": "proxy.company.com",
    "port": 8080,
    "auth": {
      "username": "user",
      "password": "pass"
    }
  }
}
```

---

## ✅ Step 5: Verification

### Test Connection
1. Open Command Palette (`Ctrl+Shift+P`)
2. Run "Ollama AI: Test Connection"
3. Should show: ✅ Connected (latency) - X models available

### Test Features
```bash
# Test code completion
# Start typing in any code file - suggestions should appear

# Test chat
Ctrl+Shift+P → "Chat with Ollama AI"

# Test image analysis
Right-click any .png/.jpg file → "Analyze Image"

# Test security scan
Ctrl+Shift+P → "Security Scan"

# Test RAG
Ctrl+Shift+P → "Index Project (RAG)"
Ctrl+Shift+P → "Query Knowledge Base"
```

---

## 🚨 Troubleshooting

### Connection Issues
```bash
# Check if Ollama is running
ps aux | grep ollama

# Start Ollama manually
ollama serve

# Test API directly
curl http://localhost:11434/api/tags
```

### Model Issues
```bash
# Re-download corrupted model
ollama rm llama3.1
ollama pull llama3.1

# Check available space
df -h

# Clear model cache
ollama prune
```

### Extension Issues
```bash
# Reset extension settings
Ctrl+Shift+P → "Preferences: Reset Settings"

# Reload extension
Ctrl+Shift+P → "Developer: Reload Window"

# Check extension logs
Ctrl+Shift+P → "Developer: Show Running Extensions"
```

### Performance Issues
```json
{
  // Reduce completion frequency
  "ollamaAI.codeCompletion.debounceMs": 1000,

  // Limit concurrent agents
  "ollamaAI.agents.maxConcurrent": 1,

  // Use smaller models
  "ollamaAI.codeCompletion.model": "codellama:7b",
  "ollamaAI.multimodal.model": "moondream"
}
```

---

## 🎯 Next Steps

### 📚 Learn More
- **Documentation**: [docs.ollama-ai-assistant.com](https://docs.ollama-ai-assistant.com)
- **Tutorials**: [YouTube Playlist](https://youtube.com/playlist?list=PLx-ollama-ai)
- **Examples**: [GitHub Repository](https://github.com/codemastersolutions/examples)

### 👥 Join Community
- **Discord**: [discord.gg/ollama-ai](https://discord.gg/ollama-ai)
- **Reddit**: [r/OllamaAI](https://reddit.com/r/OllamaAI)
- **Twitter**: [@OllamaAI](https://twitter.com/OllamaAI)

### 🔄 Stay Updated
- **GitHub**: Watch repository for updates
- **Marketplace**: Auto-updates in VSCode
- **Newsletter**: [Subscribe](https://ollama-ai-assistant.com/newsletter)

---

*Need help? Create an issue on [GitHub](https://github.com/codemastersolutions/ollama-ai-assistant-ultimate/issues) or join our [Discord](https://discord.gg/ollama-ai)*
