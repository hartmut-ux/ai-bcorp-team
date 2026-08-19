# B Corp Navigator · AI B Corp Team

> Zehn Claude Skills für die B Corp Zertifizierung und das laufende Reporting nach den B Lab Standards V2

[![B Lab Standards](https://img.shields.io/badge/B_Lab_Standards-V2.2_(20.02.2026)-green)](https://www.bcorporation.net)
[![Skills](https://img.shields.io/badge/Claude_Skills-10-blueviolet)](https://code.claude.com/docs/en/skills)
[![Lizenz](https://img.shields.io/badge/Lizenz-MIT-yellow)](LICENSE)

---

## Das Problem

Die B Lab Standards V2 umfassen über 1'200 Seiten, verteilt auf Foundation Requirements und
sieben Impact Topics. Dazu kommen ein Phasenansatz über Year 0, 3 und 5 sowie ein Tailoring
nach Unternehmensgrösse, Sektor und Branche. Für ein KMU ohne Nachhaltigkeitsabteilung ist
die Frage «Was gilt eigentlich für uns?» schon die erste Hürde.

## Die Lösung

Zehn spezialisierte Claude Skills, die als virtuelles B Corp Team arbeiten, von der
Eignungsprüfung bis zum jährlichen Impact Report. Jeder Skill deckt einen abgegrenzten
Teil der Standards ab und weiss, wann er an einen anderen übergibt.

## Die zehn Skills

| # | Skill | Funktion | B Lab Requirements |
|---|-------|----------|-------------------|
| 1 | [certification-navigator](skills/certification-navigator/) | Gesamtsteuerung, Eligibility, Roadmap | FR1–FR3 |
| 2 | [governance-purpose-architect](skills/governance-purpose-architect/) | Unternehmenszweck, Stakeholder-Governance | PSG1–PSG6 |
| 3 | [fair-work-analyst](skills/fair-work-analyst/) | Living Wage, Arbeitsverträge, Kultur | FW1–FW4 |
| 4 | [jedi-strategist](skills/jedi-strategist/) | Diversität, Chancengleichheit, Inklusion | JEDI1–JEDI2 |
| 5 | [human-rights-due-diligence](skills/human-rights-due-diligence/) | Menschenrechtliche Sorgfaltspflicht | HR1–HR4 |
| 6 | [climate-action-planner](skills/climate-action-planner/) | GHG-Bilanz, SBTi, Transition Plan | CA1–CA3 |
| 7 | [environmental-stewardship-manager](skills/environmental-stewardship-manager/) | Kreislaufwirtschaft, Biodiversität | ESC1–ESC5 |
| 8 | [public-affairs-collective-action](skills/public-affairs-collective-action/) | Lobbying, Steuern, kollektive Wirkung | GACA1–GACA3 |
| 9 | [impact-reporter](skills/impact-reporter/) | Jahresberichte, GRI- und ESRS-Mapping | PSG6, Querschnitt |
| 10 | [compliance-monitor](skills/compliance-monitor/) | Gap-Analyse, Fristen, Audit-Vorbereitung | alle |

## Architektur

```
                  certification-navigator
             (Eligibility · Tailoring · Roadmap)
                            |
      +---------------------+---------------------+
      |                                           |
  Sieben Impact Topics                    Zwei Querschnittsskills
  governance-purpose-architect            impact-reporter
  fair-work-analyst                       compliance-monitor
  jedi-strategist
  human-rights-due-diligence
  climate-action-planner
  environmental-stewardship-manager
  public-affairs-collective-action
```

Der Navigator klärt zuerst Grösse, Sektor, Branche und Jurisdiktion. Erst daraus ergibt
sich, welche Sub-Requirements überhaupt gelten und welcher Fachskill als Nächstes dran ist.

## Phasenansatz

| Phase | Zeitpunkt | Fokus |
|-------|-----------|-------|
| Year 0 | Erstzertifizierung | Foundation Requirements plus alle Year-0-Sub-Requirements |
| Year 3 | erste Rezertifizierung | zusätzliche Year-3-Sub-Requirements, etwa der Climate Transition Plan |
| Year 5 | zweite Rezertifizierung | vollständige Erfüllung aller Sub-Requirements |

## Installation

Jeder Skill liegt unter [`dist/`](dist/) als ZIP-Archiv mit der `SKILL.md` im Wurzelverzeichnis.

**Claude Web oder Claude Desktop**

1. Einstellungen → Capabilities → «Code execution and file creation» aktivieren
2. Customize → Skills → «Create skill» → «Upload a skill»
3. Die gewünschte ZIP-Datei aus `dist/` hochladen, zum Beispiel `certification-navigator.zip`

**Claude Code**

```bash
git clone https://github.com/hartmut-ux/ai-bcorp-team.git
cp -r ai-bcorp-team/skills/* ~/.claude/skills/
```

Der Skill meldet sich danach von selbst, sobald eine passende Frage kommt, etwa
«Können wir uns als B Corp zertifizieren lassen?». Aufrufen lässt er sich auch direkt
über seinen Namen.

`dist/ai-bcorp-team-alle-10-skills.zip` enthält alle zehn Ordner zum Entpacken. Für den
Upload in Claude braucht es die einzelnen ZIP-Dateien, weil dort die `SKILL.md` im
Wurzelverzeichnis liegen muss.

## FAQ-Agent zu den Standards

🔗 **[hartmut-ux.github.io/ai-bcorp-team](https://hartmut-ux.github.io/ai-bcorp-team/)**

Ein Chatbot, der die vollständigen B Lab Standards durchsuchbar macht. Er ergänzt die
Skills: die Skills führen durch den Prozess, der Chatbot beantwortet Detailfragen zum
Wortlaut der Standards.

| Komponente | Technologie |
|------------|-------------|
| Sprachmodell | [Apertus](https://www.apertus-ai.org/), offenes Schweizer Modell von EPFL, ETH Zürich und CSCS |
| RAG-Plattform | [Dify](https://dify.ai), self-hosted |
| Serverstandort | Frankfurt am Main |
| Wissensbasis | B Lab Standards, Body of Knowledge |

Warum Apertus: Trainingsdaten, Code, Gewichte und Alignment-Verfahren sind offengelegt.
Für Beratungsmandate mit vertraulichen Unternehmensdaten ist das ein Unterschied, der
sich argumentieren lässt. Die Verarbeitung bleibt nachvollziehbar und auf europäischer
Infrastruktur.

## Versionsstand

Die Skills sind gegen die B Lab Standards V2.2 vom 20. Februar 2026 geschrieben.
Zur Versionsgeschichte: V2.0 erschien am 8. April 2025, V2.1 am 12. August 2025.
V2.2 hat vor allem den Branchenausschluss in FR1.2 neu geregelt. Statt der Logik
«causing, contributing, linked» gelten nun abschliessende Branchenlisten.

Die Wissensbasis des FAQ-Agenten wird separat gepflegt. Der jeweils geladene Stand ist
auf der Chatseite ausgewiesen.

## Für wen

- KMU vor der Erstzertifizierung
- Bestehende B Corps im laufenden Reporting
- Beraterinnen und Berater, die B Corp Mandate begleiten
- Nachhaltigkeitsverantwortliche, die B Corp neben GRI, ESRS oder CDP führen

## Anschlussfähigkeit

Die Skills verweisen auf bestehende Rahmenwerke, statt eigene Kennzahlen zu erfinden:
GRI, ESRS, CDP, SBTi, UNGP, ILO-Kernarbeitsnormen und die einschlägigen ISO-Standards.
Wer bereits nach einem dieser Standards berichtet, kann Daten wiederverwenden.

## Grenzen

Die Skills sind ein Arbeitsinstrument, keine Zertifizierung und keine Rechtsberatung.
Verbindlich ist allein die Prüfung durch B Lab. Die Anpassung der Statuten für das
Legal Requirement gehört in juristische Hände. Und wie bei jedem KI-Werkzeug gilt:
Ergebnisse gegenlesen, bevor sie in ein Dossier wandern.

## Lizenz

MIT, frei für kommerzielle und nicht-kommerzielle Nutzung.

Entwickelt von [MMIND.ai](https://mmind.ai), Schaan, Liechtenstein.
