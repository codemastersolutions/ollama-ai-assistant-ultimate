# 📚 Publisher Setup Guide

## 🏪 Setting up VS Code Marketplace Publisher

### 1. Create Microsoft Account

1. Go to [Visual Studio Marketplace](https://marketplace.visualstudio.com/)
2. Sign in with Microsoft account
3. Click "Publish extensions"

### 2. Create Publisher

1. Go to [Publisher Management](https://marketplace.visualstudio.com/manage)
2. Create new publisher with ID: `codemastersolutions`
3. Fill publisher details:
   - **Display Name**: Ollama AI Team
   - **Description**: Creators of the world's most advanced AI extension for VSCode
   - **Website**: https://ollama-ai-assistant.com

### 3. Generate Personal Access Token

1. Go to [Azure DevOps](https://dev.azure.com/)
2. User Settings → Personal Access Tokens
3. Create new token with:
   - **Name**: VSCode Marketplace Publisher
   - **Organization**: All accessible organizations
   - **Scopes**: Marketplace → Manage

### 4. Configure Environment

```bash
# Set environment variable
export VSCE_PAT="your-personal-access-token"

# Or create .env file (gitignored)
echo "VSCE_PAT=your-personal-access-token" > .env
```

## 🌐 Setting up Open VSX Registry

### 1. Create Eclipse Account

1. Go to [Eclipse Foundation](https://accounts.eclipse.org/)
2. Create account with same email as VS Code publisher

### 2. Request Publisher Namespace

1. Go to [Open VSX Publishing](https://github.com/eclipse/open-vsx/wiki/Publishing-Extensions)
2. Create issue to request namespace: `codemastersolutions`
3. Provide publisher details and verification

### 3. Generate Access Token

1. Go to [Open VSX Registry](https://open-vsx.org/)
2. Sign in with Eclipse account
3. User Settings → Access Tokens
4. Generate new token with publish scope

### 4. Configure Environment

```bash
export OVSX_PAT="your-openvsx-token"
```

## 🚀 Publishing Process

### Automatic (Recommended)

```bash
# Create and push a tag
git tag v0.3.0
git push origin v0.3.0

# GitHub Actions will automatically:
# 1. Build and test
# 2. Package extension
# 3. Publish to both marketplaces
# 4. Create GitHub release
```

### Manual Publishing

```bash
# Install tools
npm install -g @vscode/vsce ovsx

# Login to marketplaces
vsce login codemastersolutions
ovsx create-namespace codemastersolutions

# Package and publish
npm run package
npm run publish:marketplace
npm run publish:openvsx
```

## 📊 Marketplace Optimization

### Keywords for Discovery

- Primary: "ai", "assistant", "ollama", "copilot alternative"
- Features: "agents", "multimodal", "rag", "security", "performance"
- Languages: "typescript", "javascript", "python", "java"
- Categories: "code completion", "testing", "documentation", "review"

### Categories for Maximum Visibility

- Other (primary - required for AI extensions)
- Machine Learning
- Programming Languages
- Testing
- Linters
- Education

### Badges for Credibility

- Version badge (auto-updated)
- Download count
- Rating/reviews
- GitHub stars
- Build status

## 🎯 Growth Strategy

### Launch Phase (Week 1-2)

1. **Soft Launch**: Publish to Open VSX first (less restrictive)
2. **Documentation**: Complete setup guides and tutorials
3. **Community**: Share in relevant Discord/Reddit communities
4. **Feedback**: Gather initial user feedback

### Growth Phase (Week 3-8)

1. **VS Code Marketplace**: Official launch with announcement
2. **Content Marketing**: Blog posts, Twitter threads
3. **Influencer Outreach**: Tech YouTubers, developer advocates
4. **SEO Optimization**: Improve keywords and description

### Scale Phase (Month 2+)

1. **Feature Updates**: Regular releases with new capabilities
2. **Enterprise Outreach**: Target development teams
3. **Integration Partnerships**: Collaborate with Ollama team
4. **Conference Presence**: Present at developer conferences

## 📈 Success Metrics

### Week 1 Targets

- 100+ downloads
- 4.0+ rating
- 5+ reviews
- GitHub stars growth

### Month 1 Targets

- 1,000+ downloads
- 4.5+ rating
- 25+ reviews
- Featured in "trending" section

### Month 3 Targets

- 10,000+ downloads
- Top 3 in "AI assistant" search
- Case studies from enterprise users
- Partnership with Ollama project

## 🔧 Troubleshooting

### Common Issues

- **Token Expired**: Regenerate and update environment variables
- **Package Too Large**: Optimize bundle size, exclude dev dependencies
- **Validation Errors**: Check package.json required fields
- **Publishing Fails**: Ensure all badges/links are accessible

### Support Channels

- GitHub Issues: Technical problems
- Email: support@ollama-ai-assistant.com
- Discord: Community support
- Documentation: https://ollama-ai-assistant.com/docs
