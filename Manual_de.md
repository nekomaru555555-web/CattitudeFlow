# CattitudeFlow Benutzerhandbuch

## Inhaltsverzeichnis

1. [Überblick](#überblick)
2. [Bildschirmaufbau](#bildschirmaufbau)
3. [Startbildschirm](#startbildschirm)
4. [Notizen-Bildschirm](#notizen-bildschirm)
5. [Tickets-Bildschirm](#tickets-bildschirm)
6. [Fokus-Bildschirm](#fokus-bildschirm)
7. [Einstellungsbildschirm](#einstellungsbildschirm)
8. [Referenz zur Suchsyntax](#referenz-zur-suchsyntax)
9. [Tastenkombinationen](#tastenkombinationen)
10. [FAQ](#faq)
11. [Fehlerbehebung](#fehlerbehebung)

---

## Überblick

**CattitudeFlow** ist eine Desktop-Anwendung, die Cornell-artiges Notieren mit Ticket- (Aufgaben-) Verwaltung kombiniert.

Notizen werden im Markdown-Format geschrieben und nach der Cornell-Methode in drei Bereiche — **Cue / Note / Summary** — strukturiert.  
Tickets unterstützen Cornell-artige **Memos**, sodass Sie mehrere strukturierte Notizen an jede Aufgabe anhängen können.

---

## Bildschirmaufbau

### Header-Navigation

Die Navigationsschaltflächen oben in der App sind wie folgt.

| Button | Beschreibung |
|--------|-------------|
| Home | Einheitliche Liste und Suche für Notizen, Tickets und TODOs |
| Notes | Cornell-artige Notizen erstellen und bearbeiten |
| Tickets | Aufgaben und Tickets verwalten |
| Focus | Nach Wichtigkeitspunktzahl sortierte Notizen/Tickets anzeigen |
| Settings | App-Konfiguration |

### InfoPill

Wird auf der rechten Seite des Headers angezeigt.

- **Verbleibende Tage**: Verbleibende Tage im Testzeitraum (z. B. noch 7 Tage)
- **Freier Speicherplatz**: Status des Speicherplatzes (OK / Niedrig)

### Fenstersteuerung

Wird ganz rechts im Header angezeigt, wenn die App als native App ausgeführt wird.

| Button | Aktion |
|--------|--------|
| `_` | Minimieren |
| `□` | Maximieren / Wiederherstellen |
| `×` | Schließen |

---

## Startbildschirm

Der Startbildschirm hat ein 3-Spalten-Layout: linkes Menü, mittlere Liste und rechte Peek-Vorschau.

### Linkes Panel (Menü)

**Filterliste**

| Item | Beschreibung |
|------|-------------|
| Notes | Nur Notizen anzeigen |
| Tickets | Nur Tickets anzeigen |
| TODO | TODO-Elemente aus allen Notizen anzeigen |
| Images | Eine Liste angehängter Bilder anzeigen |
| All | Notizen + Tickets + TODOs zusammen anzeigen |

Jedes Element zeigt eine Anzahl an. Wenn ein Tag ausgewählt ist, wird die Anzahl als `Tag-Anzahl / Gesamtanzahl` angezeigt.

**Tag-Filter**

Tags aus Notizen und Tickets werden zusammengeführt und als Chips angezeigt.  
Klicken Sie auf ein Tag, um nach Elementen mit diesem Tag zu filtern. Klicken Sie auf **All**, um den Filter zu löschen.

### Mittleres Panel (Liste)

**Suchleiste**

- Platzhalter: `Full-text search (Ctrl+K) e.g. has:url code:powershell foo`
- `Ctrl+K`, um den Fokus darauf zu setzen
- Schaltfläche `Clear`, um den Suchbegriff zurückzusetzen

**Filter-Chips**

Unterhalb der Suchleiste werden Filter-Chips angezeigt (All / Notes / Tickets / TODO).  
Wenn TODO ausgewählt ist, erscheint zusätzlich ein **Scope**-Chip (All / Today).  
Wenn ein Datumsfilter aktiv ist, wird ein Chip `date: YYYY-MM-DD ×` angezeigt, auf den zum Entfernen geklickt werden kann.

**Listenoperationen**

| Aktion | Verhalten |
|--------|----------|
| Einzelklick | Peek-Vorschau im rechten Bereich anzeigen |
| Doppelklick | Zum entsprechenden Notes-/Tickets-Bildschirm navigieren |
| `Ctrl+Click` | Zum entsprechenden Bildschirm navigieren |
| `Enter` | Zum entsprechenden Bildschirm navigieren |

**Zeilen für Ticket-Memos**

Wenn an ein Ticket Memos angehängt sind, wird jedes Memo als untergeordnete Zeile unter der Ticket-Zeile angezeigt.

| Aktion | Verhalten |
|--------|----------|
| Einzelklick | Den Tickets-Bildschirm mit ausgewähltem Memo öffnen |
| `⛶` (Vollbild-Schaltfläche) | Das Memo ohne Listenbereich in der Vollbildvorschau öffnen |

**Image-Tab**

- Zeigt für jedes Bild Thumbnail, Pfad, Erstellungsdatum, Größe und Anzahl der Referenzen an
- Eine eigene Suchleiste (Suche nach uid / relPath) wird angezeigt
- Scrollen Sie bis zum Ende der Liste, um mehr zu laden

### Rechtes Panel (Peek-Vorschau)

Einzelklick auf ein Element zeigt eine Vorschau im rechten Bereich an.

- Notizen: Cornell-artige Vorschau (Cue / Note / Summary)
- Tickets: Vorschau der Ticket-Informationen
- Bilder: Bildvorschau mit einer Liste referenzierender Notizen/Tickets
- Ticket-Memos: Cornell-artige Memo-Vorschau (ohne Listenbereich)
- **Vollbild-Schaltfläche** (⛶): Die Vorschau im Vollbild öffnen
- **Zoom-Umschalter**: Größe der Cornell-Vorschau umschalten (kompakt / lesbar)

### Tastenkombinationen im Startbildschirm

| Shortcut | Aktion |
|----------|--------|
| `Ctrl+K` | Die Suchleiste fokussieren |
| `Ctrl+Shift+T` | Den Datumsfilter für heute anwenden und den Kalender des aktuellen Monats anzeigen |

---

## Notizen-Bildschirm

### Layout

Der Notizen-Bildschirm hat ein 2-Spalten-Layout: **linke Liste** und **rechter Editor**.

### Linkes Panel (Notizenliste)

**Eine Notiz erstellen**

- Öffnen Sie den Dialog für eine neue Notiz über die Schaltfläche `New` oder `+`
- Geben Sie einen Titel und ein Datum ein (Standard: heute), um sie zu erstellen
- Wenn bereits eine Notiz mit demselben Titel existiert, wird diese Notiz geöffnet

**Eine untergeordnete Notiz erstellen**

- Klicken Sie auf die Schaltfläche `+ Child Note`, während eine Notiz ausgewählt ist, um ein Kind dieser Notiz zu erstellen
- Untergeordnete Notizen werden in der Liste als eingerückte Zeilen angezeigt
- Wenn die aktuell geöffnete Notiz bereits ein Kind ist, wird stattdessen eine Geschwister-Notiz (gleicher Elternknoten) erstellt (Enkelknoten sind nicht erlaubt)

**Suche**

- Drücken Sie `/`, um die Suchleiste zu fokussieren
- Volltextsuche im Inhalt der Notiz über den Host

**Tag-Filter**

Klicken Sie auf einen Tag-Chip, um Notizen nach diesem Tag zu filtern.

**Anheften**

- Klicken Sie auf das ★-Symbol in einer Notizzeile, um das Anheften umzuschalten
- Angeheftete Notizen erscheinen oben in der Liste
- Die Liste ist in die Bereiche `Pinned` und `All` unterteilt
- Der Pin-Status wird im Workspace gespeichert (bis zu 100 Einträge)

### Rechtes Panel (Editor)

**Metadatenfelder**

| Feld | Beschreibung |
|-------|-------------|
| Title | Notiztitel (erforderlich) |
| Date | Format YYYY-MM-DD (z. B. 2026-04-26) |
| Tags | Durch Kommas getrennt (z. B. ops, daily) |

**Cornell-Editor**

Der Notiztext ist in drei Bereiche unterteilt.

| Bereich | Zweck |
|------|---------|
| **Cue** | Fragen, Schlüsselwörter, Hinweise |
| **Note** | Hauptinhalt, detaillierte Notizen |
| **Summary** | Fazit, Erkenntnisse |

**Anzeigemodus der Bereiche**

Verwenden Sie den Umschalter für den Bereichsmodus, um zu wechseln, wie viele Bereiche angezeigt werden.

| Modus | Anzeige |
|------|---------|
| `1` | Einzelner Bereich (nur der aktive Bereich) |
| `2` | Zwei Bereiche |
| `3` | Drei Bereiche (alle Bereiche gleichzeitig sichtbar) ※ Standard |

**Tabs**

| Tab | Beschreibung |
|-----|-------------|
| Edit | CodeMirror-Editor |
| Preview | Markdown-Vorschau (mit Inhaltsverzeichnis) |

**Markdown-Symbolleiste**

Verwenden Sie die Symbolleiste über dem Bearbeitungsbereich, um Formatierungen einzufügen.

| Button | Format |
|--------|--------|
| Bold | `**text**` |
| Italic | `*text*` |
| Strikethrough | `~~text~~` |
| Underline | `<u>text</u>` |
| Text color | `<span style="color:#XXXXXX">text</span>` (20 Farben) |
| Bullet list | `- text` |
| Numbered list | `1. text` |
| TODO list | `- [ ] text` |
| Table | Tabellenvorlage einfügen |
| Alert box | GFM-Alerts (NOTE / TIP / IMPORTANT / WARNING / CAUTION) |
| Heading | H1 / H2 / H3 |

**Farbpalette (20 Farben)**

Rot / Karmesin / Orange / Bernstein / Gelb / Limette / Grün / Blaugrün / Cyan / Himmelblau /  
Blau / Indigo / Lila / Violett / Pink / Rosé / Braun / Schiefer / Grau / Schwarz

**Bilder einfügen**

Fügen Sie ein Bild aus der Zwischenablage in den Editor ein; es wird automatisch im Workspace gespeichert und als Markdown-Bildsyntax eingefügt.  
Während der Verarbeitung wird ein Overlay „Importing image…“ angezeigt.

**Speicherstatus**

Wird in der oberen rechten Ecke angezeigt.

| Status | Anzeige |
|-------|---------|
| Gespeichert | `Saved` |
| Ungespeichert | `Unsaved` |
| Speichert | `Saving…` |

**Löschen**

Klicken Sie auf das Papierkorb-Symbol, um eine Notiz zu löschen. Wenn die Notiz angeheftet ist oder ungespeicherte Änderungen hat, wird eine Warnung angezeigt.  
Wenn untergeordnete Notizen vorhanden sind, fragt ein Bestätigungsdialog, ob diese ebenfalls gelöscht werden sollen.

### Tastenkombinationen im Notizen-Bildschirm

| Shortcut | Aktion |
|----------|--------|
| `Ctrl+Enter` oder `Ctrl+S` | Speichern |
| `Ctrl+1` | Zum Cue-Bereich springen |
| `Ctrl+2` | Zum Note-Bereich springen |
| `Ctrl+3` | Zum Summary-Bereich springen |
| `Ctrl+E` | Zum Tab Edit wechseln |
| `Ctrl+P` | Zum Tab Preview wechseln |
| `/` | Die Notiz-Suchleiste fokussieren |

---

## Tickets-Bildschirm

Tickets dienen der Verwaltung von Aufgaben und To-dos. Sie unterstützen einen Cornell-artigen Textkörper, Statusverwaltung, Kommentare und Memos.

### Linkes Panel (Ticketliste)

**Suche und Filterung**

| Aktion | Beschreibung |
|--------|-------------|
| Taste `/` | Die Suchleiste fokussieren |
| Prioritätsfilter | All / P0 / P1 / P2 / P3 |
| Sortierung | Nach Aktualisierungsdatum / Fälligkeitsdatum / Priorität |

**Ein Ticket erstellen**

- Klicken Sie auf die Schaltfläche `New`, um das Formular zur Titeleingabe anzuzeigen
- Geben Sie einen Titel ein und drücken Sie `Enter`, um es zu erstellen

**Memo-Liste**

Wenn ein Ticket ausgewählt ist, werden seine zugehörigen Memos als Liste unter dem Ticket angezeigt.

| Aktion | Beschreibung |
|--------|-------------|
| Auf eine Memo-Zeile klicken | Dieses Memo im rechten Bereich öffnen |
| Symbol `👁` | Das Memo in der Liste ausblenden / anzeigen (Daten bleiben erhalten) |
| Symbol `🗑` | Das Memo löschen (Bestätigungsdialog wird angezeigt) |

### Rechtes Panel (Ticket-Editor)

Durch Auswahl eines Tickets wird der Editor im rechten Bereich geöffnet.

**Metadatenfelder**

| Feld | Beschreibung |
|-------|-------------|
| Title | Tickettitel (erforderlich) |
| Status | Benutzerdefinierte Spalte (in Settings konfigurierbar, z. B. backlog / doing / done) |
| Due date | Format YYYY-MM-DD |
| Priority | P0 (höchste) / P1 / P2 / P3 (niedrigste) |
| Labels | Durch Kommas getrennt (z. B. urgent, ops) |

**Tabs**

| Tab | Beschreibung |
|-----|-------------|
| Edit | Cornell-artiger Editor (Cue / Note / Summary) |
| Preview | Markdown-Vorschau (Cornell-Layout mit 3 Bereichen) |
| Comments (n) | Kommentare hinzufügen und anzeigen |

**Löschen**

Klicken Sie auf das Papierkorb-Symbol, um ein Ticket zu löschen (Bestätigungsdialog wird angezeigt).  
Wenn das Ticket Memos hat, enthält der Dialog in der Bestätigungsnachricht die Anzahl der Memos.

### Memo-Funktion

Tickets können mehrere Cornell-artige Memos angehängt haben. Sie sind nützlich für Besprechungsnotizen, Recherchen, Referenzen und jede strukturierte Information im Zusammenhang mit der Aufgabe.

**Ein Memo hinzufügen**

Klicken Sie unten im linken Bereich auf die Schaltfläche `+ Add Memo`. Das Memo wird sofort erstellt und der Memo-Editor wird im rechten Bereich geöffnet.

**Memo-Editor**

Der Memo-Editor verwendet dasselbe Cornell-Layout mit 3 Bereichen (Cue / Note / Summary) wie der Haupt-Ticket-Editor.

| Tab | Beschreibung |
|-----|-------------|
| Edit | Cornell-artiger Editor (Cue / Note / Summary) |
| Preview | Markdown-Vorschau (Cornell-Layout mit 3 Bereichen) |

- Automatisches Speichern beginnt, sobald ein Titel eingegeben wird
- Änderungen werden 800 ms nach der letzten Bearbeitung automatisch gespeichert

**Memo-Operationen**

| Aktion | Beschreibung |
|--------|-------------|
| Auf eine Memo-Zeile klicken | Den Memo-Editor öffnen |
| Symbol `👁` | Das Memo in der Liste ausblenden / anzeigen (Daten bleiben erhalten) |
| Symbol `🗑` | Das Memo löschen (Bestätigungsdialog wird angezeigt) |
| `⛶` (Vollbild) | Das Memo in der Vollbildansicht öffnen (verfügbar im Startbildschirm) |

> Memos gehören zu ihrem übergeordneten Ticket. Beim Löschen eines Tickets werden auch alle zugehörigen Memos gelöscht.

### Tastenkombinationen im Tickets-Bildschirm

| Shortcut | Aktion |
|----------|--------|
| `Ctrl+Enter` | Speichern |
| `/` | Die Ticket-Suchleiste fokussieren |

---

## Fokus-Bildschirm

Der Fokus-Bildschirm zeigt Ihre wichtigsten Notizen und Tickets nach Punktzahl sortiert zur fokussierten Durchsicht und zum Lesen an.

### Anzeigemodus

| Modus | Beschreibung |
|------|-------------|
| Notes | Nach Punktzahl sortierte Notizen |
| Tickets | Nach Punktzahl sortierte Tickets |

### Punktzahlberechnung

Die Punktzahlen der Notizen werden aus den folgenden Faktoren berechnet.

- **Bearbeitungsanzahl** (letzte 30 Tage): Kann in Settings ein-/ausgeschaltet werden
- **Eingehende Links**: Anzahl der Referenzen aus anderen Notizen

### Layout

| Bereich | Inhalt |
|------|---------|
| Linke Liste | Rang, Titel, Referenzanzahl, Aktualisierungsdatum |
| Rechte Vorschau | Cornell-artige Vorschau der ausgewählten Notiz |
| `Max` | Maximale Anzahl der angezeigten Elemente (5–200) |

### Operationen

| Aktion | Verhalten |
|--------|----------|
| Klicken | Ein Element auswählen und seine Vorschau anzeigen |
| Doppelklick / `Enter` | Im Notes-/Tickets-Bildschirm öffnen |
| Schaltfläche `Fullscreen` | Den Vollbild-Viewer öffnen |

### Vollbild-Viewer

- Elemente über die linke Liste wechseln
- Nach Titel mit der Suchleiste suchen
- Auf `Open` klicken, um zum entsprechenden Bildschirm zu navigieren
- Drücken Sie `ESC` oder klicken Sie auf `Close`, um zu beenden

### Tastenkombinationen im Fokus-Bildschirm

| Shortcut | Aktion |
|----------|--------|
| `Enter` | Das ausgewählte Element öffnen |
| `ESC` | Den Vollbild-Viewer schließen |

---

## Einstellungsbildschirm

Greifen Sie über die Schaltfläche **Settings** im Header auf die Einstellungen zu. Wählen Sie in der linken Seitenleiste eine Kategorie aus.

### Allgemein

| Einstellung | Beschreibung |
|---------|-------------|
| Language | Anzeigesprache der UI (system / ja / en / zh / ko / fr / de) |
| Locale | Locale für Zahlen- und Datumsformatierung (leer lassen, um die OS-Einstellung zu verwenden, z. B. en-US) |
| Theme preset | Farbthema |

- `Preview`: Das ausgewählte Thema sofort in der Vorschau anzeigen
- `Save theme`: Das Thema im Host speichern
- `Save language/locale`: Spracheinstellungen speichern

### Workspace

| Einstellung | Beschreibung |
|---------|-------------|
| WorkspaceRoot | Pfad, an dem Notizen und Tickets gespeichert werden |

- `Reload`: Aktuelle Workspace-Einstellungen erneut abrufen
- `Save`: Den geänderten Pfad speichern

### Notizen

| Einstellung | Beschreibung |
|---------|-------------|
| Auto-save | Ob bei Eingabe automatisch gespeichert wird (ON/OFF) |
| Auto-save interval (ms) | Intervall für automatisches Speichern (200–10,000 ms, lokale UI-Einstellung) |

### Tickets

| Einstellung | Beschreibung |
|---------|-------------|
| Auto-save | Ob bei Ticket-Bearbeitungen automatisch gespeichert wird (ON/OFF) |
| Auto-save interval (ms) | Intervall für automatisches Speichern (lokale UI-Einstellung) |
| Columns | Statusoptionen für Tickets (durch Kommas getrennt)<br>z. B. `backlog, doing, done, blocked, archived` |
| Show ticket ID | Ticket-IDs in Listen/Vorschauen anzeigen (lokale UI-Einstellung) |

### Focus

| Einstellung | Beschreibung |
|---------|-------------|
| Max items | Maximale Anzahl der Elemente in der Focus-Liste |
| Use edit count for ranking | Die Anzahl der Notiz-Speicherungen zur Focus-Punktzahl hinzufügen |
| Activity log | Verfolgung der Bearbeitungsanzahl aktivieren (Notizinhalte und Suchanfragen werden nicht gespeichert) |

> ※ Aufeinanderfolgende automatische Speicherungen werden als einmal pro Minute gezählt, um eine künstliche Erhöhung der Punktzahlen zu vermeiden.

### Wartung

| Aktion | Beschreibung |
|--------|-------------|
| **Export as Zip** | Den Workspace als Zip-Datei sichern |
| **Restore from Zip** | Notizen und Tickets aus einer Zip wiederherstellen (bestehende Daten werden ersetzt) |
| **Open log folder** | Den App-Log-Ordner im Datei-Explorer öffnen |
| **Export log Zip** | Logs als Zip-Datei exportieren |
| **Open license folder** | Den Ordner mit den mitgelieferten Lizenzdateien öffnen |

> ⚠️ **Der Wiederherstellungsvorgang ersetzt alle vorhandenen Notizen und Tickets vollständig.** Sichern Sie Ihre Daten immer, bevor Sie eine Wiederherstellung durchführen.

---

## Referenz zur Suchsyntax

Die Suchleiste im Startbildschirm unterstützt die folgende spezielle Syntax.

| Syntax | Beschreibung | Beispiel |
|--------|-------------|---------|
| Einfache Schlüsselwörter | UND-Suche mit Leerzeichen | `memo meeting` |
| `"phrase"` | Phrasensuche (mehrere Wörter als eine Einheit) | `"today's work"` |
| `has:url` | Notizen/Tickets finden, die eine URL enthalten | `has:url` |
| `code:any` | Elemente finden, die einen Codeblock enthalten | `code:any` |
| `code:<language>` | Elemente mit einem Codeblock in der angegebenen Sprache finden | `code:powershell` |

**Beispiel:**
```
has:url code:powershell memo
```
→ Elemente, die eine URL, einen PowerShell-Codeblock und das Schlüsselwort "memo" enthalten

---

## Tastenkombinationen

### Global

| Shortcut | Aktion |
|----------|--------|
| `Ctrl+K` | Die Home-Suchleiste fokussieren |
| `Ctrl+Shift+T` | Den Datumsfilter für heute anwenden |
| `Ctrl+Mouse Wheel` | Vergrößern / Verkleinern |
| `Ctrl+0` | Zoom auf 100 % zurücksetzen |

### Notizen-Bildschirm

| Shortcut | Aktion |
|----------|--------|
| `Ctrl+Enter` / `Ctrl+S` | Speichern |
| `Ctrl+1` | Zum Cue-Bereich springen |
| `Ctrl+2` | Zum Note-Bereich springen |
| `Ctrl+3` | Zum Summary-Bereich springen |
| `Ctrl+E` | Zum Tab Edit wechseln |
| `Ctrl+P` | Zum Tab Preview wechseln |
| `/` | Die Notiz-Suchleiste fokussieren |

### Tickets-Bildschirm

| Shortcut | Aktion |
|----------|--------|
| `Ctrl+Enter` | Speichern |
| `/` | Die Ticket-Suchleiste fokussieren |

### Fokus-Bildschirm

| Shortcut | Aktion |
|----------|--------|
| `Enter` | Das ausgewählte Element öffnen |
| `ESC` | Den Vollbild-Viewer schließen |

### Startbildschirm

| Shortcut | Aktion |
|----------|--------|
| `Enter` | Zum ausgewählten Element navigieren |
| `Ctrl+Click` | Zum ausgewählten Element navigieren |

---

## FAQ

### Q. Wie wird die Focus-Punktzahl berechnet?
**A.** Die Punktzahl wird aus den folgenden Faktoren berechnet:
- **Bearbeitungsanzahl (edit30d)**: Anzahl der Speicherungen in den letzten 30 Tagen (aufeinanderfolgende automatische Speicherungen zählen als einmal pro Minute)
- **Eingehende Links**: Anzahl der Referenzen aus anderen Notizen

Schalten Sie dies unter Settings → Focus → **Use edit count for ranking** ein oder aus.

---

### Q. Wie viele Memos kann ich zu einem Ticket hinzufügen?
**A.** Es gibt keine Begrenzung. Klicken Sie auf `+ Add Memo`, um so viele hinzuzufügen, wie Sie benötigen. Löschen Sie unerwünschte Memos mit dem Papierkorb-Symbol oder blenden Sie sie vorübergehend mit dem Symbol 👁 aus.

---

### Q. Wie lösche ich ein TODO-Element?
**A.** TODOs sind Zeilen im Format `- [ ] text` innerhalb einer Notiz. Löschen Sie die Zeile beim Bearbeiten der Notiz oder markieren Sie sie als erledigt mit `- [x] text`. Die TODO-Liste im Startbildschirm wird automatisch aktualisiert.

---

### Q. Wie füge ich Ticket-Status hinzu oder ändere sie?
**A.** Gehen Sie zu Settings → Tickets → **Columns** und geben Sie durch Kommas getrennte Statusnamen ein, dann speichern Sie.  
Beispiel: `backlog, doing, done, blocked, archived`

---

### Q. Kann ich über mehrere Geräte hinweg synchronisieren?
**A.** Sie können WorkspaceRoot auf einen freigegebenen Ordner (NAS oder cloud-synchronisierten Ordner) verweisen lassen, um auf Ihre Daten zuzugreifen, aber **gleichzeitiges Bearbeiten wird nicht empfohlen**, da es zu Datenkonflikten führen kann.

---

### Q. Kann eine untergeordnete Notiz eigene untergeordnete Notizen haben?
**A.** Die Verschachtelung ist auf eine Ebene begrenzt. Wenn Sie auf `+ Child Note` klicken, während eine untergeordnete Notiz ausgewählt ist, wird stattdessen eine Geschwister-Notiz (mit demselben Elternknoten) erstellt (Enkelknoten werden nicht erstellt).

---

### Q. Kann ich automatisches Speichern und Anheften gleichzeitig verwenden?
**A.** Ja. Das automatische Speichern verarbeitet Notizinhalte und Metadaten, während der Anheftungsstatus separat verwaltet wird.

---

## Fehlerbehebung

### Die App startet nicht
1. Prüfen Sie, ob **WebView2 Runtime** installiert ist
2. Prüfen Sie, ob der Host-Prozess (Backend) erfolgreich gestartet wurde
3. Gehen Sie zu Settings → Maintenance → **Open log folder**, um Fehlerprotokolle zu prüfen

### Daten werden nicht geladen / Ein Fehler wird angezeigt

| Error | Lösung |
|-------|---------|
| `E_WS_NOT_WRITABLE` | Prüfen Sie die Schreibberechtigungen für den Workspace-Ordner |
| `E_WS_INVALID_ROOT` | Prüfen und korrigieren Sie den Pfad unter Settings → Workspace |
| `E_APP_NOT_READY` | Warten Sie, bis die App vollständig gestartet ist, und versuchen Sie es dann erneut |
| `E_WEBVIEW2_UNAVAILABLE` | Installieren Sie WebView2 Runtime |
| `E_SETTINGS_CORRUPT` | Die Einstellungen werden automatisch zurückgesetzt. Konfigurieren Sie Ihre Einstellungen erneut |

### Automatisches Speichern funktioniert nicht
1. Prüfen Sie, ob Settings → Notes/Tickets → **Auto-save** aktiviert ist
2. Prüfen Sie, ob autoSaveMs innerhalb von `200–10,000` liegt
3. Stellen Sie sicher, dass sich der Inhalt tatsächlich geändert hat (es wird nicht gespeichert, wenn sich nichts geändert hat)

### Die Suche liefert keine Ergebnisse
1. Prüfen Sie die Schreibweise Ihres Suchbegriffs
2. Prüfen Sie, ob ein Tag-Filter oder Datumsfilter aktiv ist (klicken Sie auf `×` in den Filter-Chips, um ihn zu löschen)
3. Stellen Sie den Filter auf **All** und suchen Sie erneut

### Die Peek-Vorschau wird nicht angezeigt
- Klicken Sie Elemente mit einem **Einzelklick** an, nicht mit einem Doppelklick
- Wenn das Fenster zu schmal ist, verbreitern Sie es, damit der rechte Bereich sichtbar wird
