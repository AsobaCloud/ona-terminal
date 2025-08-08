# Ona Terminal - AI-Powered DevOps Platform

[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)
[![MCP Protocol](https://img.shields.io/badge/MCP-Model%20Context%20Protocol-green.svg)](https://modelcontextprotocol.io/)
[![MIT License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![AWS Bedrock](https://img.shields.io/badge/AWS-Bedrock%20Ready-orange.svg)](https://aws.amazon.com/bedrock/)

> **Transform your development workflow** with intelligent automation, infrastructure-as-code deployment, and comprehensive code analysis powered by cutting-edge AI models including Claude 4, Llama 4, and self-hosted fine-tuned models.

## 🚀 Quick Start

```bash
# 1. Clone the repository
git clone https://github.com/AsobaCloud/ona-terminal.git
cd ona-terminal

# 2. Run the install script (handles pip install + PATH setup)
./install.sh

# 3. Reload your shell configuration
source ~/.bashrc  # or ~/.zshrc, or restart terminal

# 4. Set up AWS credentials (for AI models)
export AWS_DEFAULT_REGION=us-east-1
# Configure AWS credentials via aws configure or environment variables

# 5. Optional: Set GitHub token for repository integration
export GITHUB_TOKEN=your_github_token_here

# 6. Start the terminal interface
ona-terminal  # Launches interactive mode (default)
# OR
ona-terminal --help  # Show available commands
```

### Manual Installation (Alternative)

If you prefer to install manually:

```bash
# Install with pip
pip install -e . --user

# Add to PATH (choose one):
# For current session only:
export PATH=$PATH:$HOME/.local/bin

# Or add permanently to ~/.bashrc or ~/.zshrc:
echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```

## 🏢 Windows Installation (Recommended)

For Windows users, we provide a **professional installer** with one-click setup:

### Download and Install

1. **Download** the latest installer: [ona-terminal-setup.exe](https://github.com/AsobaCloud/terminal/releases/latest)
2. **Run the installer** as Administrator
3. **Select components**:
   - ✅ **Core Application** (required)
   - ✅ **Add to PATH** (recommended for command-line access)
   - ✅ **Documentation** (optional)
4. **Complete installation** and launch

### Quick Verification
```cmd
# Test installation
ona-terminal --version
ona-terminal --help

# Start interactive mode  
ona-terminal
```

### Enterprise Deployment

For silent/automated installation:

```cmd
# Silent installation with all components
ona-terminal-setup.exe /S /D=C:\Program Files\OnaTerminal

# Silent installation with custom components
ona-terminal-setup.exe /S /COMPONENTS="core,path" /D=C:\Program Files\OnaTerminal
```

### Features Included
- **Professional installer** with Windows integration
- **Start Menu shortcuts** for easy access
- **Automatic PATH setup** (optional)
- **Complete uninstaller** for clean removal
- **Upgrade detection** with automatic handling

---

## 📋 Table of Contents

- [🏢 Windows Installation (Recommended)](#-windows-installation-recommended)
- [🎯 What is OnaTerminal?](#-what-is-onaterminal)
- [✨ Key Features](#-key-features)
- [🏗️ Architecture](#️-architecture)
- [📥 Installation](#-installation)
- [🎓 Getting Started Tutorial](#-getting-started-tutorial)
- [🖥️ MCP Servers Overview](#️-mcp-servers-overview)
- [💻 Terminal Interface](#-terminal-interface)
- [🤖 Agent Integration](#-agent-integration)
- [🤝 Contributing](#-contributing)
- [📚 Documentation](#-documentation)
- [🔌 GitHub Integration](#-github-integration)

## 🎯 What is OnaTerminal?

OnaTerminal is a **terminal-native development platform** built on the Model Context Protocol (MCP) that brings enterprise-grade AI automation to your DevOps workflows. It combines three powerful MCP servers with an intelligent terminal interface to automate complex software engineering tasks.

### Core Components

1. **🤖 AI Models Server** - Access to Amazon Nova Pro/Lite, Claude 4 Opus/Sonnet, Llama 4, DeepSeek-R1, and fine-tuned models with throttling resistance
2. **🐙 GitHub Integration Server** - Automated repository management, issue tracking, and PR workflows  
3. **🔍 Code Analysis Server** - Advanced static analysis, technical debt detection, and security scanning
4. **💬 Terminal Interface** - Claude Code-like conversational interface with natural language routing

## ✨ Key Features

### 🧠 Advanced AI Integration
- **✅ NEW: Amazon Nova Pro/Lite** - Primary models with superior availability and throttling resistance
- **Claude 4 Opus & Sonnet** - Latest Anthropic models for highest quality code generation and analysis  
- **Llama 4 Scout & Maverick** - Cutting-edge Meta models for reasoning and code tasks
- **DeepSeek-R1** - Specialized mathematical and logical reasoning
- **✅ NEW: Throttling-Resistant Architecture** - Availability caching, circuit breakers, exponential backoff
- **Intelligent Model Routing** - Automatically selects optimal model based on task complexity
- **Cost Optimization** - Routes simple tasks to cost-effective models, complex tasks to premium models

### 📋 Planning File Management
- **✅ NEW: .ona Directory System** - Automatic planning file management with git integration
- **Structured Planning** - System prompts automatically create planning files in `.ona/` directory
- **Git Integration** - Automatic `.gitignore` management to prevent tracking planning files
- **Timestamped Files** - UTC timestamps for all planning artifacts (insights, plans, analysis)
- **CLI Management** - Full command-line interface for planning file operations

### 🚀 Infrastructure-as-Code Automation
- **Multi-Cloud Support** - AWS, GCP, Azure infrastructure automation
- **Template Generation** - Automated CloudFormation, Terraform, and Kubernetes manifests
- **Compliance Ready** - SOC2, ISO27001, and security best practices built-in
- **GitHub Integration** - Issue-to-infrastructure deployment workflows

### 🔍 Comprehensive Code Analysis
- **Multi-Language Support** - Python, JavaScript, TypeScript, Rust, Go, Java, and more
- **Technical Debt Detection** - Automated identification and tracking
- **Security Scanning** - Vulnerability detection and remediation suggestions
- **Performance Analysis** - Complexity metrics and optimization recommendations

### 🤖 Intelligent Automation
- **Natural Language Interface** - Describe what you want, get working solutions
- **Context-Aware** - Maintains project context across sessions
- **Workflow Automation** - End-to-end task execution from planning to deployment
- **Error Recovery** - Intelligent retry and fallback mechanisms

## 🏗️ Architecture

### MCP-Based Distributed Architecture

OnaTerminal implements a distributed service architecture using the Model Context Protocol (MCP) with intelligent routing and multi-provider support:

```
┌─────────────────────────────────────────────────────────────┐
│                 Terminal Interface (CLI)                   │
│            Claude Code-like Conversational UI               │
├─────────────────────────────────────────────────────────────┤
│              Natural Language Router (ReAct)               │
│        Routes queries to appropriate MCP servers           │
├─────────────────────────────────────────────────────────────┤
│                   MCP Servers Layer                        │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────────────┐  │
│  │ AI Models   │  │   GitHub    │  │   Code Analysis     │  │
│  │   Server    │  │   Server    │  │      Server         │  │
│  └─────────────┘  └─────────────┘  └─────────────────────┘  │
├─────────────────────────────────────────────────────────────┤
│                  External Services                         │
│    AWS Bedrock   │   GitHub API   │   Static Analysis     │
│   Claude/Nova    │  Issues, PRs   │   Tools & Rules       │
└─────────────────────────────────────────────────────────────┘
```

### Multi-Provider AI Model Strategy

OnaTerminal supports multiple AI providers with intelligent routing:

- **Infrastructure Tasks** → Mistral Provider (30x cost reduction)
- **Complex Reasoning** → Bedrock Provider (Claude 4, Nova Pro)
- **Simple Code Gen** → Auto-selection based on availability
- **Fallback Strategy** → Circuit breaker patterns with availability caching

**Cost Optimization**:
- Infrastructure code generation: `~$0.03` (Mistral) vs `~$1.00` (Bedrock)
- Automatic provider selection based on task complexity
- Throttling-resistant architecture with exponential backoff

### Agent-Based Workflow System

**Single-Responsibility Agents**:
- `UploadAgent`: Data upload and processing pipeline monitoring
- `ForecastAgent`: Forecast generation and retrieval (mock implementation)

**Agent Design Pattern**:
- **Single Responsibility**: Each agent handles one specific workflow
- **Status Tracking**: Persistent state management with local tracking files
- **Real API Integration**: Direct integration with production endpoints where available
- **Rich UX**: Beautiful terminal displays with progress indicators

### Configuration Management

**Layered Configuration** (`configs/`):
```yaml
# Configuration Hierarchy (highest priority last)
default.yaml → {environment}.yaml → env vars → user_custom.yaml
```

**Key Features**:
- Environment-aware configuration with automatic detection
- AI provider auto-configuration based on available environment variables
- Type coercion and validation
- Caching for performance optimization

## 📥 Installation

### Prerequisites

- **Python 3.10 or higher** (required for FastMCP)
- **AWS Account** with Bedrock access (for AI models)
- **GitHub Token** (optional, for repository integration)
- **Git** for version control (Git for Windows recommended: https://git-scm.com/download/win)

### Method 1: Development Installation (Recommended)

#### Windows Command Prompt

```cmd
:: Clone the repository
git clone https://github.com/AsobaCloud/ona-terminal.git
cd ona-terminal

:: Create and activate virtual environment
python -m venv venv
call venv\Scripts\activate.bat

:: Install in development mode
pip install -e .

:: Add Scripts directory to PATH (for current session only)
set PATH=%%USERPROFILE%%\AppData\Roaming\Python\Python310\Scripts;%PATH%

:: Verify installation
ona-terminal --version
```

#### Windows PowerShell

```powershell
# Clone the repository
git clone https://github.com/AsobaCloud/ona-terminal.git
cd ona-terminal

# Create and activate virtual environment
python -m venv venv
.\venv\Scripts\Activate.ps1

# Install in development mode
pip install -e .

# Add to PATH (current session only)
$env:Path += ";$env:APPDATA\Python\Python310\Scripts"

# Verify installation
ona-terminal --version
```

#### Linux/macOS

```bash
# Clone the repository
git clone https://github.com/AsobaCloud/ona-terminal.git
cd ona-terminal

# Create and activate virtual environment
python3.10 -m venv venv
source venv/bin/activate

# Install in development mode
pip install -e .

# Add to PATH
export PATH="$HOME/.local/bin:$PATH"

# Make it permanent (add to ~/.bashrc or ~/.zshrc)
echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc

# Verify installation
ona-terminal --version
```

### Method 2: Docker Development Environment

```bash
# Start development environment
make dev

# Run tests
make test

# Clean up
make clean
```

### AWS Configuration

OnaTerminal requires AWS credentials to access Bedrock models:

```bash
# Method 1: AWS CLI
aws configure
# Enter your AWS Access Key ID, Secret, and Region (us-east-1 recommended)

# Method 2: Environment Variables
export AWS_ACCESS_KEY_ID=your_access_key
export AWS_SECRET_ACCESS_KEY=your_secret_key
export AWS_DEFAULT_REGION=us-east-1

# Method 3: IAM Roles (for EC2/ECS deployment)
# Attach appropriate IAM role with Bedrock permissions
```

### GitHub Configuration (Optional)

```bash
# Set GitHub token for repository integration
export GITHUB_TOKEN=ghp_your_github_personal_access_token

# Required permissions: repo, read:org, read:user
```

### Custom AI Models Configuration (Optional)

OnaTerminal supports custom fine-tuned models for cost optimization:

```bash
# Enable custom Mistral provider (30x cost reduction for infrastructure tasks)
export MISTRAL_STATUS_URL="http://your-mistral-server:8000/status"
export MISTRAL_FALLBACK_IP="your-server-ip"

# Advanced configuration
export AI_PROVIDER_STRATEGY="cost_optimized"  # Routes to cheapest model first
export AI_DEFAULT_PROVIDER="auto"             # Intelligent selection

# Alternative strategies:
# export AI_PROVIDER_STRATEGY="quality_first"  # Prefers Bedrock models
# export AI_PROVIDER_STRATEGY="bedrock_only"   # Bedrock only, no custom models
```

**Benefits of Custom Models**:
- **30x Cost Reduction**: Infrastructure tasks cost ~$0.03 instead of ~$1.00
- **Specialized Performance**: Fine-tuned for Terraform, Kubernetes, YAML
- **Graceful Fallback**: Automatically uses Bedrock if custom models unavailable
- **Zero Configuration**: Works out-of-box with Bedrock, custom models are optional

> 📖 **For detailed custom model integration**: See [Custom Model Integration Guide](docs/CUSTOM_MODEL_INTEGRATION.md) for complete setup instructions, code examples, and advanced configuration options.

## 🎓 Getting Started Tutorial

### Step 1: Verify Installation

```bash
# If you get "command not found", ensure PATH is set:
export PATH=$PATH:$HOME/.local/bin

# Check system status
ona-terminal status

# List available MCP servers
ona-terminal servers

# Show server health
ona-terminal servers --health
```

Expected output:
```
📊 OnaTerminal Status
📁 Config: configs
⏱️  Timeout: 60s
🖥️  Servers: 3 discovered
🐍 Python: 3.10+

🖥️  MCP Servers
Server                    Status    Capabilities
ai-models-server         running   generate_code, analyze_code, refactor_code
github-server            running   create_issue, manage_pr, repository_analysis  
code-analysis-server     running   analyze_complexity, detect_smells, security_scan
```

### Step 2: Basic AI Code Generation

```bash
# Generate simple Python code
ona-terminal ask "Create a function to calculate fibonacci numbers"

# Generate complex infrastructure code
ona-terminal ask "Create a Terraform configuration for a highly available web application on AWS"

# Analyze existing code
ona-terminal ask "Analyze this Python file for performance issues: /path/to/your/file.py"
```

### Step 3: GitHub Integration

```bash
# Analyze a repository structure
ona-terminal ask "Analyze the structure of my GitHub repository: owner/repo-name"

# Create technical debt issues
ona-terminal ask "Scan my repository for technical debt and create GitHub issues"

# Generate tests for a PR
ona-terminal ask "Generate comprehensive tests for pull request #123 in owner/repo-name"
```

### Step 4: Custom Model Usage (Optional Cost Savings)

```bash
# Enable your custom fine-tuned model for 30x cost reduction
export MISTRAL_STATUS_URL="http://your-server:8000/status"
export MISTRAL_FALLBACK_IP="your-server-ip"

# Infrastructure tasks will now use your custom model (much cheaper)
ona-terminal ask "Create a Terraform configuration for AWS VPC with auto-scaling"
# → Uses custom Mistral (~$0.03) instead of Bedrock (~$1.00)

# Complex reasoning still uses high-quality Bedrock models
ona-terminal ask "Design a distributed systems architecture with fault tolerance"
# → Automatically routes to Bedrock for quality

# Check which provider is being used
ona-terminal ask "Generate Kubernetes deployment and show me the cost breakdown"
```

### Step 5: Advanced Workflows

```bash
# Multi-step infrastructure deployment
ona-terminal ask "Deploy a microservices architecture with monitoring, logging, and auto-scaling on AWS"

# End-to-end code review workflow
ona-terminal ask "Review the latest commit, suggest improvements, and create a follow-up issue"

# Security audit
ona-terminal ask "Perform a comprehensive security audit of my codebase and generate a report"
```

## 🖥️ MCP Servers Overview

### 🤖 AI Models Server

**Purpose**: Multi-provider AI model access with intelligent routing and cost optimization

**Key Capabilities**:
- **Code Generation**: Python, Rust, Go, JavaScript, infrastructure code
- **Code Analysis**: Complexity, security, performance analysis  
- **Code Refactoring**: Automated improvements and optimizations
- **Multi-Provider Support**: AWS Bedrock + Custom fine-tuned models
- **Intelligent Routing**: Task-based provider selection with fallback
- **Cost Optimization**: 30x cheaper custom models for infrastructure tasks

**Provider Architecture**:
```
┌─────────────────────────────────────────────────────────────┐
│                  Provider Manager                          │
│              Intelligent Routing & Fallback                │
├─────────────────────────────────────────────────────────────┤
│  AWS Bedrock Provider    │    Custom Mistral Provider      │
│  ┌─────────────────────┐ │    ┌─────────────────────────┐    │
│  │ Claude 4 Opus       │ │    │ Fine-tuned Mistral 7B   │    │
│  │ Claude 4 Sonnet     │ │    │ Infrastructure-focused  │    │
│  │ Claude 3.5 Sonnet   │ │    │ 30x cost reduction      │    │
│  │ Llama 4 Scout       │ │    │ Self-hosted             │    │
│  │ DeepSeek-R1         │ │    │ Optional configuration  │    │
│  └─────────────────────┘ │    └─────────────────────────┘    │
└─────────────────────────────────────────────────────────────┘
```

**Available Models**:

*AWS Bedrock Provider (Default - Out-of-box)*:
```
Claude 4 Sonnet      → Complex reasoning, highest quality
Claude 3.5 Sonnet    → Code generation, balanced performance  
Llama 4 Scout        → Advanced reasoning tasks
DeepSeek-R1          → Mathematical and logical reasoning
```

*Custom Mistral Provider (Optional - Cost-effective)*:
```
Fine-tuned Mistral 7B → Infrastructure code, YAML, Terraform
                     → 30x cheaper than Bedrock
                     → Specialized for DevOps tasks
```

**Example Usage & Intelligent Routing**:
```bash
# Infrastructure tasks → Custom Mistral (30x cheaper)
ona-terminal ask "Create a Terraform configuration for AWS VPC"
ona-terminal ask "Generate Kubernetes deployment manifests"

# Simple Python code → Auto-selected based on availability
ona-terminal ask "Create a hello world function in Python"

# Complex reasoning → Bedrock Claude models (high quality)
ona-terminal ask "Create a distributed systems architecture in Rust"

# Security analysis → Bedrock models (maximum accuracy)
ona-terminal ask "Analyze this code for security vulnerabilities"
```

**Intelligent Provider Selection**:
- **Infrastructure Languages** (Terraform, YAML, Kubernetes) → Custom Mistral Provider
- **High Complexity Tasks** → Bedrock Provider (Claude models)
- **Cost-Optimized Strategy** → Tries custom models first, falls back to Bedrock
- **Quality-First Strategy** → Prefers Bedrock, uses custom models as backup
- **Automatic Fallback** → If custom models unavailable, seamlessly uses Bedrock

**Configuration Options**:
```bash
# Default: Bedrock only (out-of-box functionality)
# No configuration needed - works immediately

# Optional: Enable custom Mistral for cost savings
export MISTRAL_STATUS_URL="http://your-server:8000/status"
export MISTRAL_FALLBACK_IP="your-server-ip"
# System auto-enables Mistral when URLs are provided

# Advanced: Override default strategy
export AI_PROVIDER_STRATEGY="cost_optimized"  # or "quality_first"
export AI_DEFAULT_PROVIDER="auto"             # or "bedrock", "mistral"
```

### 🐙 GitHub Integration Server

**Purpose**: Automated repository management and workflow automation

**Key Capabilities**:
- **Repository Analysis**: Structure analysis, language detection, dependency mapping
- **Issue Management**: Automated technical debt issue creation and tracking
- **Pull Request Automation**: PR analysis, test generation, review assistance
- **Webhook Management**: Automated workflow triggers and notifications

**Available Tools**:
```python
create_technical_debt_issue()  # Auto-create issues from code analysis
create_automated_pr()          # Generate PRs for fixes and improvements  
analyze_pr_for_tests()         # Suggest tests for PR changes
get_repository_structure()     # Deep repository analysis
manage_webhooks()              # Automated workflow triggers
```

**Example Workflows**:
```bash
# Repository Health Check
ona-terminal ask "Analyze the health of my repository: username/repo-name"
# → Scans code quality, test coverage, dependencies, security issues

# Automated Technical Debt Management  
ona-terminal ask "Find technical debt in my repository and create GitHub issues"
# → Analyzes codebase, creates prioritized issues with detailed descriptions

# PR Review Assistance
ona-terminal ask "Review pull request #42 and suggest improvements"
# → Analyzes changes, suggests tests, identifies potential issues

# Release Preparation
ona-terminal ask "Prepare my repository for release: run checks, update docs, create PR"
# → Comprehensive pre-release automation
```

**Integration Features**:
- **Webhook Automation**: Trigger analysis on commits, PRs, releases
- **Issue Templates**: Standardized technical debt and bug reporting
- **PR Analysis**: Automated test suggestions and code quality checks
- **Release Management**: Automated changelog generation and version bumping

### 🔍 Code Analysis Server

**Purpose**: Advanced static analysis and code quality assessment

**Key Capabilities**:
- **Multi-Language Analysis**: Python, JavaScript, TypeScript, Java, Rust, Go
- **Complexity Metrics**: Cyclomatic, cognitive, and Halstead complexity
- **Code Smell Detection**: Automated identification of anti-patterns
- **Security Scanning**: Vulnerability detection and remediation
- **Technical Debt Scoring**: Quantified technical debt assessment

**Analysis Categories**:
```python
# Complexity Analysis
analyze_complexity()           # Comprehensive complexity metrics
calculate_cyclomatic()         # Cyclomatic complexity per function
measure_cognitive_load()       # Cognitive complexity assessment

# Code Quality  
detect_code_smells()          # Anti-patterns and code smells
analyze_maintainability()     # Maintainability index calculation
check_best_practices()        # Language-specific best practices

# Security Analysis
scan_vulnerabilities()        # Security vulnerability detection
check_dependencies()          # Dependency vulnerability scanning
analyze_data_flow()           # Data flow security analysis
```

**Example Analyses**:
```bash
# Comprehensive Code Audit
ona-terminal ask "Perform a comprehensive code quality audit of my Python project"
# → Complexity metrics, code smells, security issues, recommendations

# Security-Focused Scan
ona-terminal ask "Scan my web application for security vulnerabilities"
# → SQL injection, XSS, authentication issues, dependency vulnerabilities

# Performance Analysis
ona-terminal ask "Identify performance bottlenecks in my application"
# → Complexity hotspots, inefficient algorithms, optimization suggestions

# Technical Debt Assessment
ona-terminal ask "Calculate technical debt score for my codebase"
# → Quantified debt score, prioritized remediation plan, cost estimates
```

**Supported Languages & Features**:
| Language   | Complexity | Code Smells | Security | Best Practices |
|------------|------------|-------------|----------|----------------|
| Python     | ✅ Full    | ✅ Full     | ✅ Full  | ✅ Full        |
| JavaScript | ✅ Full    | ✅ Full     | ✅ Basic | ✅ Full        |
| TypeScript | ✅ Full    | ✅ Full     | ✅ Basic | ✅ Full        |
| Java       | ✅ Basic   | ✅ Basic    | ✅ Basic | ✅ Basic       |
| Rust       | ✅ Basic   | ✅ Basic    | ✅ Basic | ✅ Basic       |
| Go         | ✅ Basic   | ✅ Basic    | ✅ Basic | ✅ Basic       |

## 🔌 GitHub Integration

OnaTerminal provides seamless GitHub integration for repository management, issue tracking, and pull request workflows. The integration supports both interactive and non-interactive usage patterns.

### Prerequisites

- A GitHub Personal Access Token (PAT) with the following scopes:
  - `repo` - Full control of private repositories
  - `workflow` - For GitHub Actions workflows
  - `read:org` - For organization access
  - `user` - For user profile access

### Quick Start

1. **Generate a GitHub Personal Access Token**
   ```bash
   # 1. Go to GitHub → Settings → Developer Settings → Personal Access Tokens → Tokens (classic)
   # 2. Click "Generate new token" → "Generate new token (classic)"
   # 3. Name it (e.g., "OnaTerminal CLI")
   # 4. Select the required scopes (repo, workflow, read:org, user)
   # 5. Click "Generate token" and copy the token immediately
   ```

2. **Configure Authentication**
   ```bash
   # Interactive setup (recommended)
   ona-terminal github auth login
   
   # Or set token via environment variable
   export GITHUB_TOKEN=your_token_here
   ```

3. **Verify Authentication**
   ```bash
   ona-terminal github auth status
   ```
   This will display your GitHub username and current rate limits.

### Available Commands

#### Authentication
```bash
# Log in to GitHub (interactive)
ona-terminal github auth login

# Check authentication status
ona-terminal github auth status

# Log out (removes stored token)
ona-terminal github auth logout
```

#### Repository Management
```bash
# Get repository information
ona-terminal github repo info owner/repo

# List repository structure
ona-terminal github repo info owner/repo --details
```

#### Issues
```bash
# List issues in a repository
ona-terminal github issues list owner/repo

# Filter issues by state
ona-terminal github issues list owner/repo --state=closed
```

#### Pull Requests
```bash
# List pull requests
ona-terminal github pr list owner/repo

# Filter PRs by state
ona-terminal github pr list owner/repo --state=all
```

#### Webhooks
```bash
# List repository webhooks
ona-terminal github webhook list owner/repo
```

### Environment Variables

| Variable | Description | Example |
|----------|-------------|---------|
| `GITHUB_TOKEN` | GitHub Personal Access Token | `ghp_your_token_here` |
| `GITHUB_API_URL` | Custom GitHub API URL (for GitHub Enterprise) | `https://api.github.your-company.com` |

### Security Notes

- Tokens are stored in `~/.config/onaterminal/github_config.json` with restricted permissions (600)
- The token is never logged or displayed after entry
- For additional security, consider using GitHub's fine-grained access tokens with minimal required permissions
- The token is only sent to GitHub's API over HTTPS

### Troubleshooting

#### Authentication Issues
```bash
# Check if token is set
ona-terminal github auth status

# If authentication fails, try logging in again
ona-terminal github auth logout
ona-terminal github auth login
```

#### Rate Limiting
```bash
# Check current rate limits
ona-terminal github rate-limit

# If you hit rate limits:
# 1. Wait for the rate limit to reset
# 2. Consider using a token with higher rate limits (GitHub Pro/Enterprise)
# 3. Contact GitHub support if you need higher limits
```

For more advanced usage, refer to the [GitHub API documentation](https://docs.github.com/en/rest).

## 📋 Planning File Management (.ona)

OnaTerminal includes an intelligent planning file management system that automatically organizes AI-generated planning artifacts in a `.ona` directory. This system ensures that all planning files are properly tracked, versioned, and excluded from git tracking.

### Quick Start

```bash
# Set up .ona environment (automatic on first use)
ona-terminal ona setup

# List existing planning files
ona-terminal ona list

# Create a new planning file
ona-terminal ona create --content "Planning content here" --type plan
```

### Automatic Setup

The `.ona` system automatically:

1. **Creates `.ona/` directory** when the CLI starts
2. **Updates `.gitignore`** to exclude planning files from version control
3. **Detects git repositories** and manages gitignore appropriately
4. **Provides CLI commands** for managing planning files

### System Prompt Integration

All system prompts (simple, medium, OODA) have been updated to:

- **Create planning files** in `.ona/` directory automatically
- **Use UTC timestamps** for consistent file naming
- **Generate structured artifacts** (insights, plans, analysis)
- **Integrate with git** to prevent accidental commits

### Available Commands

#### Setup and Management
```bash
# Set up .ona environment
ona-terminal ona setup

# List all planning files
ona-terminal ona list

# Create planning files
ona-terminal ona create --content "Content" --type plan
ona-terminal ona create --content "Content" --type insights
```

#### File Types
- **`plan-*.md`** - Structured planning documents with objectives, steps, and success criteria
- **`insights-*.md`** - Analysis and observations with risks and opportunities
- **Custom types** - Any prefix can be used for specialized planning files

### Git Integration

The system automatically:

```bash
# Detects git repositories
# Adds .ona/ to .gitignore if missing
# Prevents accidental commits of planning files
# Maintains clean repository state
```

### Example Workflow

```bash
# 1. Start interactive mode (automatically sets up .ona)
ona-terminal

# 2. Ask for planning assistance
ona-terminal ask "Create a plan for implementing user authentication"

# 3. System automatically creates:
#    .ona/plan-20241201_143022.md
#    .ona/insights-20241201_143022Z-user.md

# 4. List planning files
ona-terminal ona list

# 5. Files are automatically gitignored
git status  # .ona/ directory won't appear in git status
```

### File Structure

```
project/
├── .ona/                    # Planning files directory
│   ├── plan-20241201_143022.md
│   ├── insights-20241201_143022Z-user.md
│   └── analysis-20241201_143022.md
├── .gitignore              # Updated with .ona/
└── src/
    └── ona_terminal/
        ├── utils/
        │   └── ona_manager.py  # .ona management utility
        └── prompts/system/
            ├── simple.md        # Updated with .ona instructions
            ├── medium.md        # Updated with .ona instructions
            └── ooda.md          # Updated with .ona instructions
```

### Advanced Usage

#### Custom Planning Files
```bash
# Create custom planning file types
ona-terminal ona create --content "Security analysis" --type security
ona-terminal ona create --content "Performance review" --type performance
```

#### Batch Operations
```bash
# List files by type
ona-terminal ona list | grep "plan-"

# Find recent files
ona-terminal ona list | head -5
```

#### Integration with Workflows
```bash
# Use in CI/CD pipelines
ona-terminal ona setup
ona-terminal ask "Analyze code quality and create improvement plan"
# → Creates planning files for review
```

## 💻 Terminal Interface

### Natural Language Commands

The terminal interface uses a **ReAct (Reasoning-Acting-Observing) architecture** to understand natural language and route requests to appropriate MCP servers.

**Command Patterns**:
```bash
# Direct commands
ona-terminal servers                    # List MCP servers
ona-terminal status                     # System health check
ona-terminal ask "your question"        # Natural language query

# Planning file management
ona-terminal ona setup                  # Set up .ona environment
ona-terminal ona list                   # List planning files
ona-terminal ona create --content "..." # Create planning file

# Natural language examples
ona-terminal ask "What can you help me with?"
ona-terminal ask "Show me the status of all servers"
ona-terminal ask "Generate a Python class for user authentication"
ona-terminal ask "Analyze my repository for technical debt"
ona-terminal ask "Create a Kubernetes deployment for my microservice"
```

### Session Management

- **Context Persistence**: Maintains conversation history and project context
- **Multi-Project Support**: Switch between different repositories and projects
- **Session Resume**: Continue previous conversations after restart
- **Configuration Memory**: Remembers preferences and commonly used settings

### Advanced Features

```bash
# Multi-step workflows
ona-terminal ask "Deploy my application: analyze code, run tests, create infrastructure, deploy to staging"

# Complex reasoning
ona-terminal ask "My application is slow. Analyze performance, identify bottlenecks, and suggest optimizations"

# Cross-server integration  
ona-terminal ask "Analyze my repository, create improvement issues, and generate PRs for critical fixes"

# Infrastructure management
ona-terminal ask "Scale my application to handle 10x traffic with auto-scaling and monitoring"
```

## 🤖 Agent Integration

OnaTerminal includes powerful **single-responsibility agents** that integrate with external APIs to automate data workflows and forecasting operations. These agents follow the **OODA Loop framework** (Observe-Orient-Decide-Act) for structured decision-making and provide real-time monitoring of complex processing pipelines.

### 🔄 OODA Framework Integration

The agent system is built around the **OODA Loop framework** for systematic decision-making:

- **🔍 Observe**: Gather data from uploads, forecasts, and system status
- **🧭 Orient**: Analyze patterns, risks, and opportunities
- **💡 Decide**: Create actionable plans based on insights
- **🎯 Act**: Execute approved plans with real-time monitoring

Each phase produces structured artifacts (`insights-*.md`, `plan-*.md`) for reproducibility and audit trails.

### 📤 Upload Agent

**Purpose**: Single-responsibility agent for data upload and processing pipeline monitoring

**Real API Integration**:
- ✅ **Ona Power Tools API** - Direct integration with production endpoints
- ✅ **S3 Upload Pipeline** - Automatic file processing and training triggers
- ✅ **CloudWatch Monitoring** - Real-time status tracking through log analysis

**Available Commands**:
```bash
# Upload data files for processing and training
/upload-inverter upload CUSTOMER_ID LOCATION MANUFACTURER SERIAL_NUMBER FILE_PATH REGION CLIENT_ID

# Check upload and training status
/upload-inverter status [UPLOAD_ID]

# List all recent uploads
/upload-inverter status
```

**Example Usage**:
```bash
# Upload inverter data for training
/upload-inverter upload SOLAR001 "Cape Town" "SolarEdge" SE12345 /data/inverter.csv af-south-1 client123

# Monitor processing status
/upload-inverter status SOLAR001_SE12345_1754151842
```

**Features**:
- **File Validation**: CSV format and existence checks
- **API Authentication**: Secure API key management
- **Pipeline Monitoring**: Tracks data ingestion → interpolation → training stages
- **Error Handling**: Graceful handling of API errors and timeouts
- **Rich Display**: Beautiful status tables with emojis and progress indicators

### 📈 Forecast Agent

**Purpose**: Single-responsibility agent for forecast generation and retrieval

**Current Status**: 
- 🚧 **Mock Implementation** - APIs exist but are placeholder only
- ✅ **Complete Structure** - Ready for real implementation when endpoints are available
- ✅ **OODA Integration** - Full framework implementation with artifact generation

**Available Commands**:
```bash
# Start forecast generation (MOCK)
/forecast-inverter start CUSTOMER_ID LOCATION MANUFACTURER SERIAL_NUMBER REGION FORECAST_TYPE HORIZON_DAYS FREQUENCY

# Retrieve forecast results (MOCK)
/forecast-inverter get CUSTOMER_ID LOCATION MANUFACTURER SERIAL_NUMBER REGION OUTPUT_DIR FORECAST_TYPE

# Check forecast status (MOCK)
/forecast-inverter status [REQUEST_ID]
```

**Example Usage**:
```bash
# Generate 7-day P50 forecast
/forecast-inverter start SOLAR001 "Cape Town" "SolarEdge" SE12345 af-south-1 P50 7 daily

# Get forecast results as CSV
/forecast-inverter get SOLAR001 "Cape Town" "SolarEdge" SE12345 af-south-1 /tmp/forecasts P50

# Check processing status
/forecast-inverter status forecast_SOLAR001_SE12345_P50_1754151842
```

**Features**:
- **Workflow Integration**: Checks training completion before forecast generation
- **Multiple Formats**: Support for P50, P90 forecasts with daily/hourly frequency
- **Structured Output**: Organized CSV files with timestamps and metadata
- **Status Tracking**: Real-time monitoring of forecast generation pipeline
- **Error Recovery**: Intelligent retry and fallback mechanisms

### 🔧 Agent Architecture

**Single-Responsibility Design**:
```
## 🏗️ Codebase Structure

### Core Modules

#### Terminal Interface & CLI (`src/ona_terminal/`)
```
cli.py                 # Main CLI entry point with Typer integration
terminal/
├── command_registry.py # Dynamic command registration and routing
└── __init__.py
```

#### MCP Servers (`src/ona_terminal/servers/`)
```
ai_models/
├── main.py           # MCP server entry point
├── providers/        # Multi-provider abstraction
│   ├── base.py       # Abstract provider interface
│   ├── bedrock.py    # AWS Bedrock integration
│   ├── mistral.py    # Self-hosted model support
│   └── manager.py    # Provider orchestration
├── routing.py        # Intelligent request routing
├── caching.py        # Response and availability caching
└── monitoring.py     # Performance and cost tracking

github/
├── main.py           # GitHub API integration server
├── auth.py           # Authentication management
├── issues.py         # Issue creation and tracking
├── pull_requests.py  # PR automation
└── repository.py     # Repository analysis

code_analysis/
├── main.py           # Static analysis server
├── parsers/          # Language-specific parsers
├── rules/            # Analysis rules and metrics
└── metrics/          # Complexity and quality metrics
```

#### Workflow Agents (`src/ona_terminal/agents/`)
```
upload_agent.py       # Data upload workflow (REAL API integration)
forecast_agent.py     # Forecast generation (MOCK implementation)
```

#### Configuration Management (`src/ona_terminal/config/`)
```
loader.py             # Hierarchical config loading
writer.py             # Dynamic configuration updates
```

#### Supporting Infrastructure (`src/ona_terminal/`)
```
client/
├── manager.py        # MCP client orchestration
└── __init__.py

prompts/
├── manager.py        # System prompt management
└── system/           # System prompt templates
    ├── simple.md     # Concise structured output
    ├── medium.md     # Vendor-neutral full output
    └── ooda.md       # OODA Loop framework

utils/
├── ona_manager.py    # .ona planning file management
└── __init__.py

services/
└── prompt_service.py # Centralized prompt processing
```

### Configuration Files
```
configs/
├── default.yaml      # Base configuration
├── development.yaml  # Dev environment overrides
└── production.yaml   # Production environment settings

pyproject.toml        # Project dependencies and build config
requirements-dev.txt  # Development dependencies
docker-compose.yml    # Development environment
```

### Testing Infrastructure
```
tests/
├── unit/             # Unit tests with mocking
├── integration/      # Integration tests with real APIs
├── terminal/         # CLI testing
└── conftest.py       # Pytest configuration
```

**Key Design Principles**:
- **Single Responsibility**: Each agent handles one specific workflow
- **Real API Integration**: Direct integration with production endpoints where available
- **Mock Boundaries**: Clear separation between working and placeholder code
- **Error Resilience**: Comprehensive error handling and graceful degradation
- **Rich UX**: Beautiful terminal displays with real-time status updates

### 📊 Integration Test Results

**✅ Working Components**:
- Upload Agent with real Ona Power Tools API integration
- S3 file upload via API Gateway
- CloudWatch log monitoring and status tracking
- Command registration and CLI integration
- OODA framework and system prompts

**🚧 Mocked Components** (ready for real implementation):
- Forecast generation API calls
- Forecast results retrieval  
- CloudWatch monitoring for forecast pipelines

**Example Test Results**:
```
✅ Upload Agent (REAL API): SUCCESS
   Upload ID: TEST_INTEGRATION_2303053195_1754151842
   S3 Key: historical/TEST_INTEGRATION/af-south-1/Cape Town/LuxPower/loadData.csv

✅ Forecast Agent (MOCK): SUCCESS
🚧 NOTE: Forecast APIs are mocked - real endpoints not yet implemented

✅ CLI Integration: SUCCESS
✅ OODA Framework: SUCCESS
```

### 🚀 Getting Started with Agents

**Prerequisites**:
- Ona Power Tools API key
- AWS credentials for CloudWatch monitoring
- Test CSV data files

**Setup**:
```bash
# Set API key
export ONA_API_KEY="your_ona_api_key_here"

# Test upload agent (real API)
/upload-inverter upload TEST_CUSTOMER "Test Location" "TestMfg" TEST123 /path/to/data.csv af-south-1 test_client

# Test forecast agent (mock)
/forecast-inverter start TEST_CUSTOMER "Test Location" "TestMfg" TEST123 af-south-1 P50 7 daily
```

**Next Steps**:
- Upload agents are production-ready for data processing workflows
- Forecast agents will become production-ready when API endpoints are implemented
- OODA framework guides structured decision-making across all operations

## 🤝 Contributing

We welcome contributions! OnaTerminal is designed to be extensible and community-driven.

### Development Setup

```bash
# Fork and clone the repository
git clone https://github.com/your-username/ona-terminal.git
cd ona-terminal

# Set up development environment
python3.10 -m venv venv
source venv/bin/activate
pip install -e ".[dev]"

# Run tests
pytest tests/ -v

# Run linting
ruff check src/
mypy src/

# Format code
black src/ tests/
```

### Contribution Areas

**🤖 AI Models Server**:
- Add support for new models (OpenAI, Cohere, local models)
- Improve model routing algorithms
- Add specialized tools (documentation generation, test creation)
- Optimize cost and performance

**🐙 GitHub Integration**:
- Add support for GitLab, Bitbucket
- Implement advanced workflow automation
- Add project management features
- Improve webhook handling

**🔍 Code Analysis**:
- Add support for new programming languages
- Implement new analysis rules and metrics
- Add IDE integrations
- Improve security scanning capabilities

**💻 Terminal Interface**:
- Enhance natural language understanding
- Add visual elements (charts, graphs)
- Improve session management
- Add plugin system

### Adding New MCP Servers

```python
# Template for new MCP server
from fastmcp import FastMCP

app = FastMCP("your-server-name")

@app.tool
def your_tool(param: str) -> dict:
    """Your tool description."""
    # Implementation
    return {"result": "success"}

if __name__ == "__main__":
    print("Your MCP Server starting...")
```

### Coding Standards

- **Follow CLAUDE.md**: Test-driven development with Explore → Plan → Code → Commit
- **Type Hints**: Full type annotation required
- **Documentation**: Comprehensive docstrings and examples
- **Testing**: >90% test coverage for new features
- **Security**: Security-first development practices

## 📚 Documentation

### 🌐 User Documentation
- **[Getting Started](https://docs.asoba.co)** - Interactive tutorials and quick start
- **[Command Reference](https://docs.asoba.co/endpoints.html)** - Complete CLI and slash commands  
- **[Custom Models](https://docs.asoba.co/custom-model-integration.html)** - 96% cost reduction setup
- **[Troubleshooting](https://docs.asoba.co/troubleshooting.html)** - Common issues and solutions

### 🔧 Developer Documentation  
- **[Installation Guide](docs/GETTING_STARTED.md)** - Detailed setup instructions
- **[API Reference](docs/API_REFERENCE.md)** - Complete API documentation
- **[Architecture Guide](docs/ARCHITECTURE_MCP.md)** - Technical architecture details
- **[MCP Server Development](docs/MCP_SERVER_DEVELOPMENT.md)** - Creating custom servers
- **[Model Integration](docs/MODEL_INTEGRATION.md)** - Adding new AI models

### 📁 Documentation Structure
The `docs/` directory contains:
- **Developer docs** - Technical documentation for contributors
- **[github-pages/](docs/github-pages/)** - User-facing website (Git submodule)
- **[README.md](docs/README.md)** - Documentation workflow guide

### Examples
- **[Code Generation Examples](examples/code-generation/)** - Real-world code generation
- **[Infrastructure Examples](examples/infrastructure/)** - IaC templates and deployments
- **[Analysis Examples](examples/analysis/)** - Code analysis and reports
- **[Workflow Examples](examples/workflows/)** - End-to-end automation

## 🚀 Roadmap

### ✅ Completed (Q4 2024)
- [x] **Planning File Management** - .ona directory system with git integration
- [x] **Real Boundary Testing** - Comprehensive validation without environment manipulation
- [x] **System Prompt Integration** - All prompts updated with .ona functionality
- [x] **CLI Management Commands** - Full ona command suite for planning files
- [x] **Git Integration** - Automatic .gitignore management for .ona directory

### Short Term (Q1 2025)
- [ ] **Plugin System**: Extensible plugin architecture for custom tools
- [ ] **Visual Interface**: Web-based dashboard for complex workflows
- [ ] **Team Features**: Multi-user support and collaboration tools
- [ ] **CI/CD Integration**: Jenkins, GitHub Actions, GitLab CI plugins

### Medium Term (Q2-Q3 2025)
- [ ] **Multi-Cloud**: GCP, Azure support in addition to AWS
- [ ] **Local Models**: Support for local LLM deployment
- [ ] **Advanced Analytics**: Project health dashboards and metrics
- [ ] **Enterprise Features**: SSO, audit logging, compliance reporting

### Long Term (Q4 2025+)
- [ ] **AI Agent Workflows**: Multi-agent collaboration for complex tasks
- [ ] **Predictive Analysis**: Proactive issue detection and prevention
- [ ] **Code Evolution**: Automated codebase modernization and refactoring
- [ ] **DevOps Optimization**: ML-driven infrastructure optimization

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **[Model Context Protocol](https://modelcontextprotocol.io/)** - Protocol foundation
- **[FastMCP](https://github.com/jlowin/fastmcp)** - MCP server framework
- **[Anthropic](https://www.anthropic.com/)** - Claude models and inspiration
- **[Meta](https://llama.meta.com/)** - Llama models
- **[DeepSeek](https://www.deepseek.com/)** - DeepSeek-R1 model

## 🔧 Troubleshooting

### Command Not Found Error

If you see `ona-terminal: command not found`, the issue is your PATH:

```bash
# Check if ona-terminal is installed
ls -la ~/.local/bin/ona-terminal

# If it exists, add to PATH:
export PATH=$PATH:$HOME/.local/bin

# Make it permanent:
echo 'export PATH=$PATH:$HOME/.local/bin' >> ~/.bashrc
source ~/.bashrc

# Alternative: Use full path
~/.local/bin/ona-terminal --help
```

### Python Version Issues

OnaTerminal requires Python 3.10+:

```bash
# Check your Python version
python3 --version

# If you have multiple Python versions, specify 3.10+
python3.10 -m pip install -e .
```

### AWS Credentials Issues

If AI models aren't working:

```bash
# Check AWS credentials
aws sts get-caller-identity

# If not configured:
aws configure
# OR set environment variables:
export AWS_ACCESS_KEY_ID=your_key
export AWS_SECRET_ACCESS_KEY=your_secret
export AWS_DEFAULT_REGION=us-east-1
```

### .ona Directory Issues

If planning files aren't being created:

```bash
# Check .ona setup
ona-terminal ona setup

# Verify .ona directory exists
ls -la .ona/

# Check .gitignore includes .ona/
grep ".ona/" .gitignore

# Manual setup if needed
mkdir -p .ona
echo ".ona/" >> .gitignore
```

### Validation Testing

Run the comprehensive validation suite:

```bash
# Run real boundary tests
python3.10 scripts/validation_script.py

# Expected output: 8/8 tests passing (100% success rate)
# Tests include: CLI availability, imports, file operations, interactive mode
```

### Common Issues

- **Dependency conflicts**: Use a virtual environment
- **FastMCP errors**: Ensure Python 3.10+ is being used
- **Model routing errors**: Check AWS Bedrock permissions
- **Planning file errors**: Ensure .ona directory is set up correctly

## 🔗 Links

- **Website**: [https://onaterminal.dev](https://onaterminal.dev)
- **Documentation**: [https://docs.onaterminal.dev](https://docs.onaterminal.dev)
- **Issues**: [GitHub Issues](https://github.com/AsobaCloud/ona-terminal/issues)
- **Discussions**: [GitHub Discussions](https://github.com/AsobaCloud/ona-terminal/discussions)
- **Discord**: [Join our community](https://discord.gg/asoba)

---

**Built with ❤️ by the OnaTerminal team and contributors**

*Empowering developers with AI-driven automation for the future of DevOps*