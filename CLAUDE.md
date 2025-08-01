# Bitnami Moodle System Information with SuperClaude

## System Overview
This document contains essential information about the Bitnami Moodle installation and SuperClaude Framework for Claude Code reference.

## System Environment
- **Platform**: Linux (container environment) - AWS EC2
- **Instance**: ip-172-31-36-216
- **External IP**: 15.164.117.175
- **Web Root**: `/bitnami/moodle` (symlink → `/opt/bitnami/moodle`)
- **Data Directory**: `/bitnami/moodledata`
- **Home Directory**: `/home/bitnami`
- **Analysis Date**: 2025-08-01

## Moodle Version
- **Version**: 5.0.1 (Build: 20250609)
- **Branch**: 500
- **Maturity**: MATURITY_STABLE
- **Internal Version**: 2025041401.00

## Server Stack
- **PHP**: 8.2.29 with Zend OPcache
- **Database**: MariaDB on port 3306
- **Web Server**: Apache on ports 80 (HTTP) and 443 (HTTPS)
- **PHP-FPM**: Enabled
- **Node.js**: 22.18.0
- **Python**: 3.11.2

## Database Configuration
- **Type**: MariaDB
- **Host**: 127.0.0.1:3306
- **Database Name**: bitnami_moodle
- **Username**: bn_moodle
- **Password**: f1f8ceff198c560307a453122015b939192d07196075754478bca45bb2dc4ea6
- **Table Prefix**: mdl_
- **Collation**: utf8mb4_unicode_520_nopad_ci

## SuperClaude Framework v3.0.0
SuperClaude is installed and configured to enhance Claude Code capabilities.

### SuperClaude Features
1. **19 Specialized Commands**:
   - Development: `/build`, `/code`, `/debug`
   - Analysis: `/analyze`, `/optimize`, `/refactor`, `/review`, `/audit`
   - Operations: `/deploy`, `/test`, `/monitor`, `/backup`, `/scale`, `/migrate`
   - Design: `/design`, `/plan`, `/document`, `/workflow`, `/research`

2. **9 Cognitive Personas**:
   - architect, frontend, backend, security, analyzer, qa, performance, refactorer, mentor

3. **Token Optimization**: 70% reduction in token usage

4. **MCP Integration**: Documentation, analysis, testing, and automation tools

### SuperClaude Installation
- **Virtual Environment**: `/home/bitnami/superclaude-env/`
- **Framework Location**: `/home/bitnami/superclaude/SuperClaude_Framework/`
- **Tools Directory**: `/home/bitnami/superclaude-tools/`
- **Configuration**: `/home/bitnami/.superclaude/config.json`

### Installed Development Tools
#### Documentation
- MkDocs with Material theme
- Sphinx with RTD theme

#### Code Analysis
- **Python**: Pylint, Black, isort, mypy, flake8
- **JavaScript**: ESLint, Prettier, TypeScript support

#### Testing
- **Python**: pytest, pytest-cov, pytest-mock
- **JavaScript**: Jest, Mocha, Chai

#### Automation
- Playwright with Chromium

### Tool Servers
- **Documentation Server**: http://localhost:3001
- **Analysis Server**: http://localhost:3002
- **Start Script**: `/home/bitnami/superclaude-tools/start-tools.sh`
- **Stop Script**: `/home/bitnami/superclaude-tools/stop-tools.sh`

## Important Paths
```
/bitnami/moodle/          # Moodle core files
/bitnami/moodledata/      # Moodle data files
├── cache/                # Cache files
├── filedir/              # Uploaded files
├── lang/                 # Language files
├── localcache/           # Local cache
├── muc/                  # MUC configuration
├── sessions/             # Session files
├── temp/                 # Temporary files
└── trashdir/             # Trash directory

/home/bitnami/
├── superclaude/          # SuperClaude Framework
├── superclaude-env/      # Python virtual environment
├── superclaude-tools/    # Development tools
├── moodle-system-docs/   # System documentation
└── .superclaude/         # SuperClaude config
```

## Running Services
- MariaDB server
- Apache HTTPD
- PHP-FPM workers
- Multiple Moodle cron jobs

## Installed Moodle Modules
Core modules installed and activated:
- assign, bigbluebuttonbn, book, choice, data, feedback, folder, forum
- glossary, h5pactivity, lesson, lti, quiz, resource, scorm, wiki
- workshop, subsection, page, label, url

## Known Issues and Notes
1. **Email**: sendmail not installed (email sending disabled)
2. **PATH**: Environment variable issues - use full paths for commands
3. **Cron**: Multiple cron processes running simultaneously
4. **Permissions**: File permissions set to 02775 for directories

## Common Commands
Due to PATH issues, use full paths:
```bash
# Set proper PATH
export PATH=/opt/bitnami/common/bin:/opt/bitnami/common/sbin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin

# Access MariaDB
/opt/bitnami/mariadb/bin/mysql -u bn_moodle -pf1f8ceff198c560307a453122015b939192d07196075754478bca45bb2dc4ea6 bitnami_moodle

# PHP CLI
/opt/bitnami/php/bin/php

# Python with SuperClaude environment
source /home/bitnami/superclaude-env/bin/activate

# Check processes
ps aux | grep -E '(apache|mysql|mariadb|php)'
```

## SuperClaude Usage Examples
```
# Code Analysis
/analyze
Analyze the performance bottlenecks in this Moodle system

# Optimization
/optimize
Suggest PHP-FPM configuration improvements for better performance

# Documentation
/document
Generate technical documentation for the current system architecture

# Security Audit
/audit
Check for security vulnerabilities in the current configuration
```

## Security
- Session storage: File-based in `/bitnami/moodledata/sessions/`
- Cache: File-based cache system
- Encryption: Sodium encryption key configured
- SuperClaude: 100% local execution, no external data transmission

## Network Configuration
- HTTP: Port 80 (all interfaces)
- HTTPS: Port 443 (all interfaces)  
- MySQL/MariaDB: Port 3306 (localhost only)
- Documentation Server: Port 3001 (localhost)
- Analysis Server: Port 3002 (localhost)

## GitHub Repository
- Repository: https://github.com/saminil1/gpc-system
- Documentation: `/home/bitnami/moodle-system-docs/`

## Quick Reference Commands
```bash
# Activate SuperClaude environment
source /home/bitnami/superclaude-env/bin/activate

# Start development tools
/home/bitnami/superclaude-tools/start-tools.sh

# Stop development tools
/home/bitnami/superclaude-tools/stop-tools.sh

# Access documentation
cd /home/bitnami/moodle-system-docs/
```

## PHP-Python Integration Bridge
Moodle (PHP)과 SuperClaude (Python) 간의 완벽한 통합을 위한 브리지 시스템

### Bridge Architecture
```
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│  Moodle (PHP)   │────▶│  Bridge (Flask) │────▶│SuperClaude (Py) │
│   Port 80/443   │ HTTP│    Port 5000    │     │  Virtual Env    │
└─────────────────┘     └─────────────────┘     └─────────────────┘
```

### Bridge Service
- **Service Name**: moodle-superclaude-bridge
- **API Endpoint**: http://localhost:5000/api
- **Status**: Active and running
- **Auto-start**: Enabled via systemd

### Bridge API Endpoints
```
GET  /api/health                          # Health check
GET  /api/analyze/course/{course_id}      # 코스 분석
GET  /api/analyze/user/{user_id}          # 사용자 패턴 분석
POST /api/optimize/query                  # 쿼리 최적화
POST /api/generate/content                # 컨텐츠 생성
POST /api/superclaude/command             # SuperClaude 명령 실행
```

### Moodle Plugin
- **Location**: `/bitnami/moodle/local/superclaude/`
- **Version**: 1.0.0
- **Features**:
  - 코스 분석 및 최적화
  - AI 기반 컨텐츠 생성 (레슨, 퀴즈, 과제)
  - 사용자 학습 패턴 분석
  - 성능 최적화 제안

### PHP Bridge Usage
```php
// Get bridge instance
$bridge = get_superclaude_bridge();

// Analyze course
$analysis = $bridge->analyze_course($courseid);

// Generate content
$content = $bridge->generate_content('Topic', $courseid, 'lesson');

// Get recommendations
$recommendations = $bridge->get_recommendations($userid);
```

### System Management Commands
```bash
# Bridge service control
sudo systemctl status moodle-superclaude-bridge
sudo systemctl restart moodle-superclaude-bridge
sudo journalctl -u moodle-superclaude-bridge -f

# Clear Moodle cache
sudo -u daemon php /bitnami/moodle/admin/cli/purge_caches.php

# Upgrade plugins
sudo -u daemon php /bitnami/moodle/admin/cli/upgrade.php
```

### Integration Files
```
/home/bitnami/moodle-superclaude-bridge/
├── bridge_system.py          # Flask bridge server
├── superclaude_wrapper.py    # SuperClaude wrapper
├── moodle_plugin.php         # PHP bridge interface
├── requirements.txt          # Python dependencies
└── INTEGRATION_COMPLETE.md   # Integration documentation

/bitnami/moodle/local/superclaude/
├── version.php               # Plugin version
├── lib.php                   # Plugin library
├── index.php                 # Main interface
├── course.php                # Course analysis
├── action.php                # Action handler
└── lang/en/                  # Language strings
```

## Claude Code Development Guide

### 필수 워크플로우 (Always Follow)

#### 1. PATH 설정 (모든 명령 전에 필수)
```bash
export PATH=/opt/bitnami/common/bin:/opt/bitnami/common/sbin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
```

#### 2. 코드 변경 후 순서
1. Python 코드 변경 시:
   ```bash
   sudo systemctl restart moodle-superclaude-bridge
   ```
2. PHP 코드 변경 시:
   ```bash
   sudo -u daemon php /bitnami/moodle/admin/cli/purge_caches.php
   ```
3. 플러그인 구조 변경 시:
   ```bash
   sudo -u daemon php /bitnami/moodle/admin/cli/upgrade.php --non-interactive
   ```

### 자주 사용하는 명령어 모음

#### 브리지 상태 확인 및 디버깅
```bash
# 빠른 상태 체크
curl http://localhost:5000/api/health

# 서비스 상태 및 로그
sudo systemctl status moodle-superclaude-bridge
sudo journalctl -u moodle-superclaude-bridge -f

# API 테스트
curl http://localhost:5000/api/analyze/course/1 | python3 -m json.tool
```

#### Moodle 플러그인 작업
```bash
# 플러그인 파일 위치
cd /bitnami/moodle/local/superclaude/

# 주요 파일 편집
vi lib.php        # 핵심 함수
vi index.php      # 메인 UI
vi action.php     # 액션 처리

# 변경 적용
sudo -u daemon php /bitnami/moodle/admin/cli/purge_caches.php
```

#### 데이터베이스 작업
```bash
# DB 접속 (비밀번호 포함)
/opt/bitnami/mariadb/bin/mysql -u bn_moodle -pf1f8ceff198c560307a453122015b939192d07196075754478bca45bb2dc4ea6 bitnami_moodle

# 유용한 쿼리들
SELECT * FROM mdl_config WHERE name LIKE '%superclaude%';
SELECT * FROM mdl_capabilities WHERE component = 'local_superclaude';
```

### 문제 해결 Quick Reference

| 증상 | 해결 방법 |
|------|----------|
| "Bridge not available" | `sudo systemctl restart moodle-superclaude-bridge` |
| 플러그인이 보이지 않음 | `sudo -u daemon php /bitnami/moodle/admin/cli/purge_caches.php` |
| PATH 명령어 오류 | 위의 PATH export 명령 실행 |
| DB 접속 오류 | MariaDB 서비스 확인: `sudo systemctl status mariadb` |

### 개발 시 주의사항
1. **절대 경로 사용**: PHP에서 브리지 파일 참조 시 항상 절대 경로 사용
2. **캐시 정리**: 모든 PHP 변경 후 캐시 정리 필수
3. **로그 확인**: 오류 시 브리지 로그와 Moodle 디버그 로그 모두 확인
4. **백업**: 중요 변경 전 백업 생성

## Last Updated
2025-08-01 - SuperClaude v3.0.0 with PHP-Python Bridge Integration Complete
- CLAUDE.md Development Guide 추가