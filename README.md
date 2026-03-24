# B Corp Navigator — AI B Corp Team

> 10 KI-Agenten für die B Corp Zertifizierung und das laufende Reporting nach B Lab Standards V2.2

[![B Lab Standards](https://img.shields.io/badge/B_Lab_Standards-V2.2_(Feb_2026)-green)](https://www.bcorporation.net)
[![Skills](https://img.shields.io/badge/Skills-10-blue)]()
[![Lizenz](https://img.shields.io/badge/Lizenz-MIT-yellow)](LICENSE)
[![Claude](https://img.shields.io/badge/Claude-Skills-blueviolet)](https://claude.ai)

---

## Das Problem

Die B Lab Standards V2.2 umfassen **1245 Seiten** mit 8 Requirement-Bereichen, einem Phasenansatz (Year 0/3/5) und Tailoring nach Unternehmensgrösse, Sektor und Branche. Für KMU ist die Komplexität eine zentrale Hürde — sowohl bei der Erstzertifizierung als auch beim laufenden Reporting.

## Die Lösung

10 spezialisierte KI-Agenten (Claude Skills), die als **virtuelles B Corp Team** die gesamte Zertifizierungsreise begleiten — von der Eignungsprüfung bis zum jährlichen Impact Report.

## Die 10 Skills

| # | Skill | Funktion | B Lab Requirements |
|---|-------|----------|-------------------|
| 1 | [Certification Navigator](skills/certification-navigator/) | Gesamtsteuerung, Eligibility, Roadmap | FR1, FR2, FR3 |
| 2 | [Governance & Purpose Architect](skills/governance-purpose-architect/) | Unternehmenszweck, Stakeholder-Governance | PSG1–PSG6 |
| 3 | [Fair Work Analyst](skills/fair-work-analyst/) | Living Wage, Arbeitsverträge, Culture | FW1–FW4 |
| 4 | [JEDI Strategist](skills/jedi-strategist/) | Diversity, Equity, Inklusion | JEDI1–JEDI2 |
| 5 | [Human Rights Due Diligence](skills/human-rights-due-diligence/) | Menschenrechts-Sorgfaltspflicht | HR1–HR4 |
| 6 | [Climate Action Planner](skills/climate-action-planner/) | GHG-Messung, SBTi, Transition Plan | CA1–CA3 |
| 7 | [Environmental Stewardship Manager](skills/environmental-stewardship-manager/) | Kreislaufwirtschaft, Biodiversität | ESC1–ESC5 |
| 8 | [Public Affairs & Collective Action](skills/public-affairs-collective-action/) | Lobbying, Steuern, kollektive Wirkung | GACA1–GACA3 |
| 9 | [Impact Reporter](skills/impact-reporter/) | Jahresberichte, GRI/ESRS-Mapping | PSG6 + Querschnitt |
| 10 | [Compliance Monitor](skills/compliance-monitor/) | Gap-Analyse, Fristen, Audit-Vorbereitung | Alle |

## Architektur

```
┌─────────────────────────────────────────────────────┐
│             CERTIFICATION NAVIGATOR                  │
│         (Steuerung · Roadmap · Tailoring)            │
├─────────────────────────────────────────────────────┤
│                                                     │
│  Governance &    Fair Work     JEDI       Human     │
│  Purpose         Analyst       Strategist Rights    │
│  Architect                                DD        │
│                                                     │
│  Climate Action  Environmental  Public Affairs      │
│  Planner         Stewardship    & Collective        │
│                  Manager        Action              │
│                                                     │
├─────────────────────────────────────────────────────┤
│  IMPACT REPORTER          COMPLIANCE MONITOR        │
│  (Reporting · GRI · ESRS)  (Gap-Analyse · Audit)    │
└─────────────────────────────────────────────────────┘
```

**Drei Ebenen:**
1. **Certification Navigator** — Steuert die Zertifizierungsreise (oben)
2. **7 Impact Topic Skills** — Je ein Agent pro Wirkungsbereich (Mitte)
3. **Impact Reporter + Compliance Monitor** — Querschnittsfunktionen (unten)

## Phasenansatz

Die Skills bilden den B Lab Phasenansatz ab:

| Phase | Zeitraum | Fokus |
|-------|----------|-------|
| **Year 0** | Erstzertifizierung | Foundation Requirements + alle Year-0-Sub-Requirements |
| **Year 3** | Vertiefung | Zusätzliche Sub-Requirements (z.B. Climate Transition Plan) |
| **Year 5** | Exzellenz | Vollständige Compliance mit allen B Lab Standards |

## Technologie

| Komponente | Technologie |
|------------|-------------|
| KI-Agenten | [Claude](https://claude.ai) Skills (Anthropic) |
| Agent-Protokoll | [MCP](https://modelcontextprotocol.io) (Model Context Protocol, Linux Foundation) |
| Datenhoheit | [Apertus](https://apertus.ai) (Schweizer Open Source AI, Infomaniak) |
| FAQ-Agent | [Dify](https://dify.ai) (Self-hosted, RAG auf B Lab Standards V2.2) |
| Skill-Format | `.skill` ZIP-Archive für Claude Desktop |

## Live Demo

🔗 **B Corp Navigator FAQ** — [Demnächst verfügbar]
Chatbot auf Basis der vollständigen B Lab Standards V2.2, gehostet auf Schweizer Infrastruktur mit Apertus als LLM-Backend.

## Für wen?

- **KMU**, die sich erstmals B Corp zertifizieren lassen möchten
- **Bestehende B Corps**, die das laufende Reporting effizient gestalten wollen
- **B Corp Berater**, die ihren Kunden ein KI-gestütztes Tool anbieten möchten
- **Nachhaltigkeitsmanager**, die B Corp neben GRI/ESRS/CDP parallel führen

## Preispositionierung

| | Enterprise B Corp Software | AI B Corp Team |
|---|---|---|
| Setup | CHF 20'000–80'000 | **CHF 25'000–40'000** |
| Jährlich | CHF 50'000–150'000 | **Token-basiert (niedrig)** |
| Datenhoheit | Cloud (oft US) | **Schweiz (Apertus/Infomaniak)** |
| Anpassung | Begrenzt | **Vollständig** |
| Interoperabilität | Proprietär | **GRI, ESRS, CDP, SBTi** |

## Interoperabilität

Die Skills referenzieren und ergänzen bestehende Standards:

- **GRI** (Global Reporting Initiative)
- **ESRS** (European Sustainability Reporting Standards)
- **CDP** (Climate Disclosure Platform)
- **SBTi** (Science Based Targets initiative)
- **UNGP** (UN Guiding Principles on Business and Human Rights)
- **ISO Standards** (Governance, Net Zero Guidelines)
- **ILO** (Arbeitsrechte und -standards)

## Installation

```bash
# Repository klonen
git clone https://github.com/hartmut-ux/ai-bcorp-team.git

# Skills in Claude Desktop laden
# Jeden Skill-Ordner als .skill ZIP-Archiv importieren
```

## Lizenz

MIT License — Frei verfügbar für kommerzielle und nicht-kommerzielle Nutzung.

## Kontakt

**MMIND.ai** — AI Transformation für KMU
- Web: [mmind.ai](https://mmind.ai)
- E-Mail: office@flowstatecyclist.com
- LinkedIn: [Hartmut Plass](https://linkedin.com/in/hartmutplass)

---

*Basierend auf B Lab Standards V2.2 (Februar 2026) · Erstellt mit Claude (Anthropic)*
