# Bitnami Moodle System Documentation

This repository contains system analysis and documentation for a Bitnami Moodle installation.

## Files Included

- `CLAUDE.md` - Reference documentation for Claude Code
- `moodle_system_analysis.md` - Detailed system analysis in Markdown format
- `moodle_system_analysis.txt` - System analysis in plain text format
- `moodle_system_analysis.json` - System analysis in JSON format

## Quick Reference

### System Information
- **Moodle Version**: 5.0.1 (Build: 20250609)
- **PHP Version**: 8.2.29
- **Database**: MariaDB
- **Web Server**: Apache

### Important Directories
- Moodle Core: `/bitnami/moodle`
- Data Directory: `/bitnami/moodledata`
- Home Directory: `/home/bitnami`

### Database Access
```bash
/opt/bitnami/mariadb/bin/mysql -u bn_moodle -p bitnami_moodle
```

## Documentation

Please refer to the individual files for detailed system information:

1. **CLAUDE.md** - Contains essential information formatted for Claude Code reference
2. **moodle_system_analysis.md** - Human-readable detailed analysis
3. **moodle_system_analysis.json** - Machine-readable system configuration

## Last Updated

2025-08-01