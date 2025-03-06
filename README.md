# VS Script Examples ITS

Dieses Repository enthält Skript-Beispiele für Verteilte Systeme und Internet Transport Security (ITS), einschließlich Strukturen und Muster, die durch Submodule organisiert sind.

## Übersicht der Struktur

Das Repository ist in verschiedene Bereiche unterteilt, die als Git-Submodule implementiert sind:

- **Chapter_4_Supporting_Pattern**: Design Patterns für Verteilte Systeme (Submodul, verweist auf [VS_Pattern](https://github.com/scimbe/VS_Pattern_By_KI))
- **PracticalExam_MainDemo**: Baisi für doe praktische Prüfungsaufgaben für Verteilte Systeme (Submodul, verweist auf [CaDSPracticalExamVS](https://github.com/Transport-Protocol/CaDSPracticalExamVS))
- **PracticalExam_BRD_ITS_Examples**: Beispiele für das ITS BRD (Submodul, verweist auf [ITS-BRD-VSC](https://github.com/Transport-Protocol/ITS-BRD-VSC))

## Git-Submodule Befehle

### Repository mit Submodulen klonen

Um dieses Repository mit allen Submodulen zu klonen:

```bash
git clone --recurse-submodules https://github.com/scimbe/vs_script_examples_its.git
```

### Submodule nach einem normalen Klonen initialisieren

Falls das Repository bereits ohne Submodule geklont wurde:

```bash
git submodule init
git submodule update
```

### Status der Submodule prüfen

```bash
git submodule status
```

### Submodule aktualisieren

Um alle Submodule auf die neueste Version zu aktualisieren:

```bash
git submodule update --remote
git add .
git commit -m "Submodule auf neueste Version aktualisiert"
```

### Ein einzelnes Submodul aktualisieren

```bash
git submodule update --remote BRD_ITS_Examples
git add BRD_ITS_Examples
git commit -m "BRD_ITS_Examples auf neueste Version aktualisiert"
```

### In einem Submodul arbeiten

Um in einem Submodul Änderungen vorzunehmen (am Beispiel von Chapter_2):

```bash
cd Chapter_4_Supporting_Pattern 
# Änderungen vornehmen
git add .
git commit -m "Beschreibung der Änderungen"
git push
```

Anschließend im Hauptrepository:

```bash
cd ..
git add Chapter_4_Supporting_Pattern 
git commit -m "Submodul Chapter_4_Supporting_Pattern  aktualisiert"
git push
```

## Hinweise

- Submodule behalten ihre eigene Git-Historie bei
- Änderungen in Submodulen müssen separat gepusht werden
- Nach dem Auschecken eines Branches mit Submodulen immer `git submodule update` ausführen
- Bei Fehlern kann ein vollständiges Reset hilfreich sein: `git submodule update --init --recursive --force`
