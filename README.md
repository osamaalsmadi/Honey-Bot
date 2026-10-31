# Honey-Bot | Honeypot Monitoring

A Django project for exploring security-event monitoring through a web dashboard.

**Python · Django · SQLite · HTML/CSS**

## Project areas

| Area | Source |
| --- | --- |
| Event and account models | [models.py](honeybot-project/dashboard/models.py) |
| Dashboard and account views | [views.py](honeybot-project/dashboard/views.py) |
| Page templates | [templates](honeybot-project/dashboard/templates) |
| Project configuration | [settings.py](honeybot-project/honeypot_monitor/settings.py) |

The source includes dashboard, logs, alerts, reports, account pages, and training-related templates. Their presence does not imply that every workflow has been verified end to end.

## Local setup

See [LOCAL_SETUP.md on the improvement branch](https://github.com/osamaalsmadi/Honey-Bot/blob/docs/project-presentation/LOCAL_SETUP.md) for environment variables, virtual-environment setup, migrations, and development startup. The setup guide accompanies the configuration changes on the improvement branch; use it with those changes.

## Configuration and data

- Provide secrets through environment variables.
- Review email delivery settings before enabling SMTP.
- The repository contains a tracked SQLite database, an archive, and Python caches. A .gitignore does not remove already tracked material.
- Revoke the previously exposed email app password at its provider; editing a file does not erase Git history.

## Validation

Targeted syntax and configuration checks were performed on the improvement branch. Full Django startup and end-to-end dashboard workflows still require validation in a configured environment.

---

Part of [Osama Alsmadi’s project portfolio](https://github.com/osamaalsmadi).
