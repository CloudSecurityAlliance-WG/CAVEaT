# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

CAVEaT (Cloud Adversarial Vectors, Exploits, and Threats) is a Cloud Security Alliance working group project that documents cloud-specific security threats, attack vectors, and mitigations. It produces standardized STIX 2.1 threat intelligence covering AWS, Azure, GCP, and Kubernetes. The published CTI data lives in a separate repository: https://github.com/cloudsecurityalliance/cti

**Status**: This project is currently on hiatus. It may be rebooted in the future as CAVEaT 2.0.

## Architecture

### Modular Prompt System (`/prompts/`)

The core of this project is a set of AI chatbot prompt modules (currently v4, dated 2025-04-29). The main entry point is `ChatBot-Main-2025-04-29.md`, which coordinates loading specialized modules on demand:

- **Research** — threat research methodology and cross-provider analysis
- **STIX Attack Vectors** — attack pattern, infrastructure, tool, malware objects
- **Vulnerability/CoA Core** — vulnerability and course of action fundamentals
- **Provider-specific CoA** — separate modules for AWS, Azure, GCP, and Kubernetes with platform-specific CLI/console/API mitigation steps
- **Threat Actors** — threat actor and campaign objects
- **Intelligence** — indicators, observed data, opinions, reports
- **Supporting Objects** — identity, location, and supporting objects
- **Visualization** — Mermaid diagram standards
- **File Management** — file saving, naming conventions, size management
- **Help** — interactive help system

Archived prompt versions (v2-v5) are in `/prompts/ARCHIVED/`.

### Data Flow

Research → STIX object generation (JSON) → Relationship mapping → Mermaid visualization → Markdown reports → Publish to CTI repo

### Key Conventions

- **STIX IDs**: Use human-readable descriptive IDs (e.g., `attack-pattern--cloud-slopsquatting`), not random UUIDs
- **Dual mitigations**: Every threat documents both customer-level mitigations (what orgs can do today) and platform-level mitigations (architectural changes providers could make)
- **Cross-provider coverage**: Threats are analyzed across AWS, Azure, GCP, and Kubernetes where applicable
- **Data format preference**: JSON > HTML/Markdown > plain text
- **File size target**: Keep individual files under 500KB; split large threats into separate object files
- **Date format**: YYYY-MM-DD in file names and outputs

## Repository Structure

- `/prompts/` — AI chatbot prompt modules (the main deliverable of this repo)
- `/data/CAVEaT-files/` — Legacy CAVEaT threat entries (markdown, HTML, CSV)
- `/data/MITRE/`, `/data/CSA/`, `/data/center-for-threat-informed-defense/` — Framework mapping data
- `/Chatbot-Example-Data-and-Reports/` — Complete worked examples of threat documentation with STIX objects and reports
- `/file-utils/` — Python scripts for data processing (HTML cleanup, format conversion, JSON comparison)
- `/mapping-attempts/` — Work-in-progress framework mapping efforts

## STIX 2.1 Format

All threat intelligence output uses STIX 2.1 bundles. See `STIX-2.1-Validation-Guide.md` for validation approaches. Key requirements:
- Every object needs: `type`, `id`, `spec_version` ("2.1"), `created`, `modified`
- Timestamps in RFC3339 format
- Relationships explicitly connect objects via `source_ref`/`target_ref`
- Custom properties use `x_` prefix (e.g., `x_caveat_extension`)
- Validation: `pip install stix2-validator` then `stix2_validator your-bundle.json`

## File Utilities

Python scripts in `/file-utils/` — no build system or package manager. Run individually:
```
python file-utils/clean-html.py          # HTML cleanup with BeautifulSoup
python file-utils/convert-CSVTOJSON.py   # CSV to JSON
python file-utils/convert-YAMLToJSON.py  # YAML to JSON
python file-utils/compare_json.py        # JSON file comparison
python file-utils/get-json-from-url.py   # Fetch JSON from URLs
```

## Framework Mappings

CAVEaT maps to: CSA CAIQ/CCM v4, MITRE ATT&CK, MITRE ATLAS, MITRE FIGHT, MITRE CWE/CVE, and Center for Threat-Informed Defense mappings.

## License

CC0 1.0 Universal (public domain).
