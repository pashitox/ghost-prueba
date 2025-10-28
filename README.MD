# 🚀 Ghost Migration Toolkit

**Professional tool for Ghost CMS migrations and deployments**  
*Master Ghost CMS operations - Perfect for professional practices*

![Ghost CMS](https://img.shields.io/badge/Ghost-CMS-brightgreen)
![Docker](https://img.shields.io/badge/Docker-Containers-blue)
![Automation](https://img.shields.io/badge/Automation-Scripts-orange)
![Bash](https://img.shields.io/badge/Bash-Scripting-yellow)

---

## 📖 Description

This project contains everything needed for successful Ghost CMS migrations between different environments. Developed during professional internships, it includes tested workflows, automated scripts and complete documentation.

## 🎯 What I Learned

### 💻 Technical Skills
- **Docker & Docker Compose**: Application containerization
- **Ghost CMS**: Content management and migration
- **SQLite/MySQL**: Database management in Ghost
- **Bash Scripting**: Process automation
- **Backup/Restore**: Backup and recovery strategies

### 🔄 Migration Flows
- Development → production migration
- Data export/import
- Version conflict resolution
- Data integrity maintenance

### 🛠️ Problem Solving
- Docker container diagnostics
- Import error handling
- Environment variable configuration
- Performance optimization

---

## 🏗️ Project Architecture

```
ghost-migration-toolkit/
├── 📁 ghost_data/                 # Application data
│   ├── data/ghost.db             # SQLite database
│   ├── images/                   # Media files
│   └── config.production.json    # Configuration
├── 🐳 docker-compose.yml         # Container orchestration
├── 📜 migration-scripts/         # Automation scripts
├── 📚 docs/                      # Technical documentation
└── 🔧 troubleshooting/           # Common problem solutions
```

---

## 🚀 Quick Start

### Prerequisites
```bash
# Verify installations
docker --version
docker-compose --version
git --version
```

### Quick Start
```bash
# 1. Clone project
git clone https://github.com/yourusername/ghost-migration-toolkit.git
cd ghost-migration-toolkit

# 2. Start environment
docker-compose up -d

# 3. Access application
echo "🌐 Frontend: http://localhost:2368"
echo "⚙️  Admin: http://localhost:2368/ghost"
```

---

## 🔄 Workflow Examples

### 📥 Data Migration (Development → Production)
```bash
# 1. Export from source
./scripts/export-backup.sh

# 2. Transfer file
scp backup-$(date +%Y-%m-%d).json user@production:/path/

# 3. Import at destination
./scripts/import-backup.sh
```

### 🗂️ Automated Backup
```bash
# Scheduled backup (add to crontab)
0 2 * * * /path/to/project/scripts/scheduled-backup.sh
```

### 🔍 Quick Diagnostics
```bash
# Check complete status
./scripts/health-check.sh
```

---

## 📋 Migration Checklist

### ✅ Before Starting:
- [ ] Docker installed
- [ ] `docker-compose.yml` file available
- [ ] Data backup available (if applicable)
- [ ] Admin credentials known

### ✅ During Migration:
- [ ] Start containers: `docker-compose up -d`
- [ ] Verify frontend: http://localhost:2368/
- [ ] Verify admin: http://localhost:2368/ghost/
- [ ] Import data (if backup available)
- [ ] Verify everything works

### ✅ After Migration:
- [ ] Test post creation
- [ ] Test configuration changes
- [ ] Document changes made
- [ ] Backup new state

---

## 🐳 Docker Compose Structure

```yaml
version: "3.9"

services:
  ghost:
    image: ghost:6-alpine
    container_name: ${PROJECT_NAME:-ghost_app}
    restart: unless-stopped
    ports:
      - "${HOST_PORT:-2368}:2368"
    environment:
      url: ${SITE_URL:-http://localhost:2368}
      database__client: sqlite3
      database__connection__filename: /var/lib/ghost/content/data/ghost.db
    volumes:
      - ./ghost_data:/var/lib/ghost/content
```

---

## 🛠️ Included Scripts

### 🔄 Migration
- `migrate-dev-to-prod.sh` - Complete environment migration
- `export-with-media.sh` - Export including media files
- `validate-backup.sh` - Backup integrity validation

### 🩺 System Health
- `container-health.sh` - Container diagnostics
- `database-integrity.sh` - Database verification
- `performance-check.sh` - Performance analysis

### 🔐 Security
- `rotate-credentials.sh` - Credential rotation
- `backup-encryption.sh` - Encrypted backups
- `access-audit.sh` - Access auditing

---

## 📞 Support

### 🆘 Need Help?
1. **Check documentation** in `/docs/`
2. **Review closed issues** for known solutions
3. **Run diagnostics**: `./scripts/health-check.sh`
4. **Create issue** with diagnostic output

### 🐛 Report Bugs
Always include:
```bash
# Environment information
./scripts/environment-info.sh
# Relevant logs
docker-compose logs ghost
```

---

## 📜 License

MIT License - See `LICENSE` file for details.

## 🙏 Acknowledgments

Developed during professional internships as part of the learning process in systems administration and DevOps.

---

**⭐ Found this project useful? Give the repo a star!**

---

*"The perfect migration is like art: it seems magical, but it's pure methodical process"* - Learned during professional internships 🎯