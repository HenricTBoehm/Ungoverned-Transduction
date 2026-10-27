# Änderungs- und Prüfprotokoll — Ungoverned Transduction v0.3

**Datum:** 27. Oktober 2026  
**Prüfnorm:** *Michelle Pre-Submission Review System* (MPRS) v0.3.2, 24. Oktober 2026  
**Dokumenttyp:** konzeptionelle, methodische Concept Note; eigenständiger synthetischer Modelltest.  
**Modus:** AI-unterstützte redaktionelle Nachprüfung; keine unabhängige wissenschaftliche Begutachtung oder Freigabe durch den Autor.

## Revisionsgrundlage und Kernwertung

Der vorgelegte Fremd-/Nachprüfbericht zu v0.2 bewertet die Kernrubrik mit **27/30 (Strong Core)** und identifiziert vier vorrangige Korrekturen. Eine unabhängige Neubewertung aller 15 Kriterien in v0.3 wurde hier **nicht** vorgenommen. Die frühere AI-Selbstbewertung (28/30) wird nicht als höherwertig ausgegeben. Die MPRS-Kernpunkte ersetzen keine Release-Gates.

## Umsetzung der vier Hauptbefunde

| Befund | Korrektur in v0.3 | Ergebnis der lokalen Nachprüfung |
|:--|:--|:--|
| G_e anfangs als A/NA/NE, später numerisch; undefiniertes G_W; E_W wie Boolesch verwendet | Einheitliche Domänen `E_W, G_e ∈ {1, 0, ⊥}`; Klassifikationen nur als `(E_W=1) ∧ (G_e=0/1)`; `G_W` entfernt; getrennte Verdict-Labels Adm, NAdm, NE | Textprüfung: PASS |
| Modellartefakte waren im Erstpaket nicht vorhanden | Unveränderte, zuvor unabhängig gegengeprüfte Dateien `UT_v0_2_finite_model.py` und `UT_v0_2_finite_cases.csv` plus README, erwarteter Output und SHA-256 in einem ZIP | Python-Ausführung: PASS; 8/8 deklarierte Fälle; CSV byte-identisch |
| Baseline-PERMIT bei U2/O1 zeitlich undeutlich | Tabellenspalte zur *Execution Decision* erklärt; zusätzlicher Absatz: Policy-Entscheidung ex ante, Effektklasse ex post; O1 nur hypothetische Policy-Auswertung, keine tatsächliche Invocation | Textprüfung: PASS |
| Akronyme und PADC-Linie nicht ausreichend definiert | OTAA = Output-to-Action Admissibility; historisch PADC = Pre-Action Differentiation Cascade v0.4.0; gegenwärtig PADC = Pre-Action Differentiation and Control; DEA = Distinction, Execution, and Adjudication; ausdrückliche **Nicht-Behauptung** einer bereits erfolgten Baseline-Konformität | Textprüfung: PASS |

Weitere Korrekturen: Titel zu **When AI Effect Outruns Authority**; NAdm statt missverständlichem NA; NIST SP 800-162 als **2014, aktualisiert am 2. August 2019** nach amtlicher Verlagsseite; vorsichtigere Abgrenzung zum nur auf Abstract-/Metadatenebene überprüften Shadow-AI-Artikel.

## Technischer Reproduktionsbefund (eng begrenzt)

- `python3 UT_v0_2_finite_model.py` benötigt nur die Python-Standardbibliothek (Python ≥ 3.9).
- Programmlauf im separaten Testverzeichnis mit Exit-Code 0, Assertions bestanden.
- Neugenerierte Ergebnis-CSV mit Original `cmp` byte-identisch.
- SHA-256 Skript: `3e27387f95e95e964e7558bf22f6eba43313c763a65eaf4e7bb472ebd113584d`
- SHA-256 CSV: `a4f1d0fae7eeb6dd4a9d4321795fb1a963be645d0174ed814e69b0cce49cb21b`
- v0.3 ändert **keinen** Quellcode und keine Fallklassifikation. Der neue Text korrigiert nur Beschreibung, Notation, temporale Einordnung und Provenienz.

Damit ist **S2 für genau dieses endliche Modell reproduzierbar**. Es wurde keine Vollständigkeit über sämtliche Eingabebelegungen, keine empirische Externvalidität und keine praktische Leistungsüberlegenheit geprüft.

## MPRS-Gates und verbleibende Sperren

**Gezielt nachgeprüft:** H3 Terminologie, H4 Evidence-to-Status und S2 Modellreproduzierbarkeit sind hinsichtlich der festgestellten Mängel jetzt *provisorisch erfüllt*. H2 Methode und die übrigen Core-Gates wurden hier nicht vollumfänglich erneut auditiert. Die Dokumente tragen weiterhin ausdrücklich, dass ein kompetentes End-to-End-ABAC-/Workflow-Modell das konstruierte Problem ebenfalls erkennt.

**Offen:** S1-Literaturabdeckung und neuerliche Prüfung des vollständigen Shadow-AI-Artikels; Crosswalk-Abgleich mit der *aktuellen* PADC-Control-Baseline und dem DEA-Publication-Master; S4-Autorbestätigung zu Finanzierung/Interessenkonflikten und AI-Disclosure je Venue; unabhängige adversariale Begutachtung und Journal-Overlay. Claim UT-C4 (zusätzlicher PADC-Nutzen) bleibt eine **ungetestete empirische Hypothese**, kein Modellergebnis.

**Disposition:** Die konkret gemeldeten redaktionellen/technischen Hindernisse sind in v0.3 korrigiert. **Submission Ready ist nicht erreicht.** Eine formelle **Release Candidate**-Entscheidung setzt den dokumentierten Abschluss sämtlicher anwendbarer interner Gates sowie die Freigabe des zuständigen Release Owners voraus; diese Entscheidung wird durch die AI-gestützte Nachprüfung nicht vorweggenommen. Gegenwärtig: **Revise (nur verbleibende externe/provenienzbezogene Prüfaufträge)**, nicht Hold und nicht Restructure.

## Bewertungsgrenzen

Der Test prüft kodierte Semantik und 8 Fälle, nicht die Eignung der Policies für reale Unternehmen. W1 ist ein Existenzzeuge bei unvollständiger lokaler Autorisierung, **kein Gegenbeispiel** zu korrekter end-to-end Autorisierung und **kein dokumentierter Fall** des Shadow-AI-Artikels. Die Bezeichnung `baseline_decision` im unveränderten CSV stammt aus v0.2; ihre zeitliche und hypothetische Interpretation ist nun in v0.3 dokumentiert.
