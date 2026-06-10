# CattitudeFlow Benutzerhandbuch

## Inhaltsverzeichnis

1. [Überblick](#überblick)
2. [Bildschirmaufbau](#bildschirmaufbau)
3. [Startbildschirm](#startbildschirm)
4. [Notizen-Bildschirm](#notizen-bildschirm)
5. [Tickets-Bildschirm](#tickets-bildschirm)
6. [Fokus-Bildschirm](#fokus-bildschirm)
7. [OCR-Memo-Bildschirm](#ocr-memo-bildschirm)
8. [Einstellungsbildschirm](#einstellungsbildschirm)
9. [Referenz zur Suchsyntax](#referenz-zur-suchsyntax)
10. [Tastenkombinationen](#tastenkombinationen)
11. [Häufig gestellte Fragen (FAQ)](#häufig-gestellte-fragen-faq)
12. [Fehlerbehebung](#fehlerbehebung)

---

## Überblick

**CattitudeFlow** ist eine Desktop-Anwendung, die die Cornell-Methode für Notizen mit Ticketverwaltung kombiniert.

Der Notiztext kann im Markdown-Format geschrieben werden und unterstützt ein Layout nach der Cornell-Methode mit drei Bereichen: Cue, Note und Summary.  
Zu Tickets können mehrere **Memos** nach der Cornell-Methode hinzugefügt werden, damit detaillierte Aufzeichnungen zu Aufgaben erhalten bleiben.  
In v1.0.5 wurden neben der **OCR-Erfassung**, die auf dem Bildschirm angezeigten Text direkt in die App übernimmt, weitere Funktionen ergänzt: frei platzierbare **Notizzettel** auf dem Notiztext, eine **Präsentationsansicht** für die Bildschirmfreigabe sowie **Markdown-Mathematik (KaTeX)**.

---

## Bildschirmaufbau

### Header-Navigation

Im Header am oberen Rand der App werden die folgenden Navigationsschaltflächen angezeigt.

| Button | Beschreibung |
|--------|--------------|
| Home | Liste und Suche für Notizen, Tickets und TODOs |
| Notizen | Notizen nach der Cornell-Methode erstellen und bearbeiten |
| Tickets | Aufgaben und Tickets verwalten |
| Fokus | Nach Wichtigkeit sortierte Notizen/Tickets anhand eines Scores anzeigen |
| OCR-Memo | Liste und Bearbeitung der per OCR-Capture übernommenen Memos |
| Einstellungen | App-Einstellungen |

### InfoPill

Auf der rechten Seite des Headers werden die folgenden Informationen angezeigt.

- **Verbleibende Tage**: Verbleibende Tage des Testzeitraums (Beispiel: noch 7 Tage)
- **Freier Speicherplatz**: Status des freien Speicherplatzes (OK/Wenig)

### Fenstersteuerung

Wird beim Start als native App ganz rechts im Header angezeigt.

| Button | Aktion |
|--------|--------|
| `_` | Minimieren |
| `□` | Maximieren/Wiederherstellen |
| `×` | Schließen |

### Schnelltasten in der Titelleiste

| Button | Aktion |
|--------|--------|
| `✂` | Dialog zur Snippet-Verwaltung öffnen (`Ctrl+I`) |
| `☀` | Spotlight-Cursor ein-/ausschalten |
| `☀ ▾` | Aktuelles Spotlight-Preset umschalten |
| `🖥` Präsentationsansicht | **Präsentationsansicht** ein-/ausschalten, um die Lesbarkeit der Live-Vorschau/Vorschau zu verbessern (für die Bildschirmfreigabe) |

Auf der Snippet-Schaltfläche wird ein Badge mit der Anzahl registrierter Einträge angezeigt. Die Farbe der Spotlight-Schaltfläche ist mit der Farbe des aktuell ausgewählten Presets verknüpft.

Die **Präsentationsansicht** hebt Schriftgröße, Zeilenabstand und Kontrast der Live-Vorschau und der Vorschau hervor, damit sie auch bei der Bildschirmfreigabe gut lesbar bleiben. Der Ein/Aus-Zustand wird in der App gespeichert und wirkt sich weder auf die Themenfarben noch auf gespeicherte Daten aus.

### Taskleistenmenü

Wenn Sie das Symbol in der Taskleiste mit der rechten Maustaste anklicken, wird das folgende Menü angezeigt.

| Eintrag | Beschreibung |
|---------|--------------|
| Anzeigen / Ausblenden | Sichtbarkeit des Hauptfensters umschalten |
| Spotlight | Spotlight-Cursor ein-/ausschalten |
| Snippet | Dialog zur Snippet-Verwaltung öffnen |
| OCR | Bildschirm-Capture starten |
| Beenden | App beenden |

Rechts neben jedem Eintrag wird das aktuell festgelegte globale Hotkey angezeigt.  
Die Hotkeys können unter Einstellungen → Tastenkombinationen angepasst werden.

---

## Startbildschirm

Der Startbildschirm besteht aus drei Spalten: linkes Menü, mittlere Liste und rechte Peek-Vorschau.

### Linkes Panel (Menü)

**Filterliste**

| Eintrag | Beschreibung |
|---------|--------------|
| Notizen | Nur Notizen anzeigen |
| Tickets | Nur Tickets anzeigen |
| TODO | TODO-Elemente aus allen Notizen anzeigen |
| Bilder | Liste der angehängten Bilder anzeigen |
| Alle | Notizen + Tickets + TODO gemeinsam anzeigen |

Bei jedem Eintrag wird die Anzahl angezeigt. Wenn ein Tag ausgewählt ist, wird die Anzeige im Format `Tag-Anzahl / Gesamtanzahl` dargestellt.

**Tag-Filter**

Die Tags von Notizen und Tickets werden zusammengeführt und als Chips angezeigt.  
Wenn Sie auf ein Tag klicken, werden nur Elemente mit diesem Tag angezeigt. Mit `Alle` wird der Filter aufgehoben.

### Mittleres Panel (Liste)

**Suchleiste**

- Platzhalter: `Volltextsuche (Ctrl+K) Beispiel: has:url code:powershell foo`
- Fokus mit `Ctrl+K`
- Mit der Schaltfläche `Löschen` werden die Suchbegriffe zurückgesetzt
- Wenn `::` schnell eingegeben wird, kann ein Modal für angeheftete Snippets geöffnet werden

**Filter-Chips**

Unterhalb der Suchleiste werden Filter-Chips angezeigt (Alle / Notizen / Tickets / TODO).  
Wenn TODO ausgewählt ist, erscheint zusätzlich ein **Bereich**-Chip (Alle / Heute).  
Wenn ein Datumsfilter aktiv ist, wird ein Chip `date: YYYY-MM-DD ×` angezeigt, der per Klick entfernt werden kann.

**Listenbedienung**

| Aktion | Verhalten |
|--------|-----------|
| Einfachklick | Peek-Vorschau im rechten Bereich anzeigen |
| Doppelklick | Zum entsprechenden Notizen-/Tickets-Bildschirm wechseln |
| `Ctrl+Click` | Zum entsprechenden Bildschirm wechseln |
| `Enter` | Zum entsprechenden Bildschirm wechseln |

**Memo-Zeilen bei Tickets**

Wenn zu einem Ticket Memos registriert sind, werden diese unterhalb der Ticket-Zeile als untergeordnete Zeilen angezeigt.
Tickets mit Memos zeigen einen Schalter `▼ / ▶`, mit dem der Memo-Baum ein- oder ausgeklappt werden kann.

| Aktion | Verhalten |
|--------|-----------|
| Einfachklick | Zum Tickets-Bildschirm wechseln und das Memo öffnen |
| `⛶`（Vollbild-Schaltfläche） | Memo als Vollbildvorschau ohne Liste anzeigen |

**Bei ausgewählter Registerkarte Bilder**

- Es werden Bild-Thumbnail, Pfad, Erstellungsdatum, Größe und Anzahl der Referenzen angezeigt
- Eine spezielle Suchleiste (Suche nach uid / relPath) wird angezeigt
- Durch Scrollen bis ans Ende der Liste können weitere Einträge nachgeladen werden

### Rechtes Panel (Peek-Vorschau)

Wenn ein Element mit einem Einfachklick ausgewählt wird, erscheint die Vorschau im rechten Bereich.

- Notizen: Vorschau nach der Cornell-Methode (Cue / Note / Summary)
- Tickets: Vorschau der Ticketinformationen
- Bilder: Bildvorschau und Liste der referenzierenden Notizen/Tickets
- Ticket-Memos: Cornell-Vorschau des Memos (ohne Listenpanel)
- **Vollbild-Schaltfläche** (⛶): Vorschau im Vollbild anzeigen
- **Verkleinern/Vergrößern**: Größe der Cornell-Vorschau umschalten (eine Seite / besser lesbar)
- Auch in externen Editoren geänderte Dateien werden automatisch erkannt und in Liste und Vorschau übernommen

### Tastenkombinationen im Startbildschirm

| Tastenkombination | Aktion |
|-------------------|--------|
| `Ctrl+K` | Suchleiste fokussieren |
| `Ctrl+Shift+T` | Datumsfilter für heute anwenden und Monatskalender anzeigen |

---

## Notizen-Bildschirm

### Bildschirmaufbau

Der Notizen-Bildschirm besteht aus zwei Spalten: **linke Liste** und **rechter Editor**.

### Linkes Panel (Notizenliste)

**Neu erstellen**

- Mit der Schaltfläche `Neu` oder `+` wird der Dialog für eine neue Notiz geöffnet
- Im Dialog Titel und Datum eingeben (Standard: heute) und erstellen
- Existiert bereits eine Notiz mit demselben Titel, wird diese geöffnet

**Unternotiz erstellen**

- Wenn eine Notiz ausgewählt ist, wird mit `＋ Unternotiz` eine Unternotiz zur aktuell ausgewählten Notiz erstellt
- Unternotizen werden in der Liste als eingerückte Zeilen angezeigt
- Wenn die aktuell geöffnete Notiz bereits eine Unternotiz ist, wird stattdessen eine Geschwisternotiz mit demselben übergeordneten Element erstellt (Enkelnotizen werden nicht erstellt)

**Suche**

- Mit `/` wird die Suchleiste fokussiert
- Eine Volltextsuche über die Full-text search des Hosts innerhalb des Notizinhalts ist möglich

**Tag-Filter**

Durch Klicken auf einen Tag-Chip können Notizen nach Tags gefiltert werden.

**Anheften**

- Mit dem ★-Symbol in der Notizzeile wird das Anheften umgeschaltet
- Angeheftete Notizen werden ganz oben in der Liste angezeigt
- Anzeige getrennt in den Bereichen `Angeheftet` und `Alle`
- Angeheftete Einträge werden dauerhaft im Workspace gespeichert (maximal 100 Einträge)

### Rechtes Panel (Editor)

**Metadatenfelder**

| Feld | Beschreibung |
|------|--------------|
| Titel | Titel der Notiz (erforderlich) |
| Datum | Format YYYY-MM-DD (Beispiel: 2026-04-26) |
| Tags | Durch Kommas getrennt (Beispiel: ops, daily) |

**Editor nach der Cornell-Methode**

Der Notiztext besteht aus den folgenden drei Bereichen.

| Bereich | Zweck |
|---------|-------|
| **Cue** | Fragen, Schlüsselwörter, Hinweise |
| **Note** | Hauptinhalt, detaillierte Notizen |
| **Summary** | Zusammenfassung, Fazit |

**Anzeigemodus der Bereiche**

Mit dem Umschalter für den Bereichsmodus kann die Anzeige umgeschaltet werden.

| Modus | Anzeige |
|-------|---------|
| `1` | 1 Bereich (nur aktiver Bereich wird angezeigt) |
| `2` | 2 Bereiche |
| `3` | 3 Bereiche (alle Bereiche gleichzeitig sichtbar) ※ Standard |

Der umgeschaltete Modus wird sofort übernommen und beim nächsten Öffnen der Notiz wiederhergestellt.

**Registerkarten wechseln**

| Registerkarte | Beschreibung |
|---------------|--------------|
| Bearbeiten | CodeMirror-Editor |
| Vorschau | Markdown-Vorschau (mit Inhaltsverzeichnis) |

- Während der Bearbeitung kann mit `Ctrl+F` ein Suchpanel geöffnet werden, das zur Anzeigesprache der App passt
- Auf der Registerkarte Vorschau steht ein PDF-Export zur Verfügung, der die aktuelle Hintergrundfarbe übernimmt

**Markdown-Werkzeugleiste**

Über die Werkzeugleiste oberhalb der Registerkarte Bearbeiten können verschiedene Formatierungen eingefügt werden.

| Button | Format |
|--------|--------|
| Fett | `**Text**` |
| Kursiv | `*Text*` |
| Durchgestrichen | `~~Text~~` |
| Unterstrichen | `<u>Text</u>` |
| Textfarbe | `<span style="color:#XXXXXX">Text</span>`（20 Farben） |
| Aufzählung | `- Text` |
| Nummerierte Liste | `1. Text` |
| TODO-Liste | `- [ ] Text` |
| Tabelle | Tabellenvorlage einfügen |
| Alarmbox | GFM-Alerts (NOTE / TIP / IMPORTANT / WARNING / CAUTION) |
| Überschrift | H1 / H2 / H3 |

**Farbpalette (20 Farben)**

Rot / Karmesin / Orange / Bernstein / Gelb / Limette / Grün / Blaugrün / Cyan / Himmelblau /  
Blau / Indigo / Lila / Violett / Pink / Rosa / Braun / Schiefer / Grau / Schwarz

**Einfügen von Bildern**

Wenn ein Bild aus der Zwischenablage in den Editor eingefügt wird, wird es automatisch im Workspace gespeichert und in Markdown-Bildsyntax eingefügt.  
Während des Imports wird ein Overlay mit „Bild wird importiert…“ angezeigt.

**Notizzettel**

Sie können frei platzierbare Notizzettel über dem Notiztext anbringen. Klicken Sie mit der rechten Maustaste in den Editortext und wählen Sie im Kontextmenü `Notizzettel hinzufügen`.

- Ein neu hinzugefügter Notizzettel erhält automatisch den Fokus, sodass Sie sofort tippen können (der Fokus wird beim Tippen nicht entzogen)
- Ziehen Sie an der oberen Leiste, um ihn zu verschieben. Jeder Zettel ist an eine Position im Text verankert und folgt daher dem Scrollen und Bearbeiten
- Mit der Farbschaltfläche oben links wechseln Sie die Farbe (Gelb → Rosa → Blau → Grün, im Kreis)
- Ziehen Sie an der unteren rechten Ecke des Textbereichs, um die Größe zu ändern; die neue Größe wird gespeichert
- Klicken Sie auf die Schaltfläche `✕`, um ihn zu löschen (mit Bestätigungsdialog)
- Mit `Ctrl+;` fügen Sie das Datum, mit `Ctrl+Shift+;` die Uhrzeit ein
- Notizzettel werden im Notiztext gespeichert und sind daher auch in Zip-Sicherungen enthalten

**Mathematik (Math)**

Die Markdown-Vorschau und die Live-Vorschau unterstützen die Formeldarstellung mit KaTeX.

- Inline-Formel: `$E = mc^2$`
- Block-Formel: in eigenen Zeilen mit `$$` einschließen

```
$$
\int_0^1 x^2 dx = \frac{1}{3}
$$
```

**Speicherstatus**

Oben rechts wird der Speicherstatus angezeigt.

| Status | Anzeige |
|--------|---------|
| Gespeichert | `Gespeichert` |
| Ungespeichert | `Ungespeichert` |
| Wird gespeichert | `Speichern…` |

- Die Schriftart für Editor- und Vorschauinhalt kann unter Einstellungen → Editor geändert werden
- Wenn Notizdateien in einem externen Editor aktualisiert werden, werden sie ebenfalls automatisch neu geladen

**Löschen**

Mit dem Papierkorb-Symbol kann eine Notiz gelöscht werden. Wenn sie angeheftet ist oder noch nicht gespeicherte Änderungen enthält, wird eine Warnung angezeigt.  
Wenn Unternotizen vorhanden sind, erscheint ein Bestätigungsdialog, ob diese ebenfalls gelöscht werden sollen.

### Tastenkombinationen im Notizen-Bildschirm

| Tastenkombination | Aktion |
|-------------------|--------|
| `Ctrl+Enter` oder `Ctrl+S` | Speichern |
| `Ctrl+1` | Zum Cue-Bereich springen |
| `Ctrl+2` | Zum Note-Bereich springen |
| `Ctrl+3` | Zum Summary-Bereich springen |
| `Ctrl+E` | Zur Registerkarte Bearbeiten wechseln |
| `Ctrl+P` | Zur Registerkarte Vorschau wechseln |
| `/` | Notiz-Suchleiste fokussieren |

---

## Tickets-Bildschirm

Tickets dienen zur Verwaltung von Aufgaben und To-dos. Sie unterstützen Text nach der Cornell-Methode, Statusverwaltung, Kommentare und Memos.

### Linkes Panel (Ticketliste)

**Suche und Filterung**

| Aktion | Beschreibung |
|--------|--------------|
| `/`-Taste | Suchleiste fokussieren |
| Prioritätsfilter | Alle / P0 / P1 / P2 / P3 |
| Sortierung | Aktualisierungsdatum / Fälligkeit / Priorität |

**Neu erstellen**

- Mit der Schaltfläche `Neu` wird ein Eingabeformular für den Titel angezeigt
- Titel eingeben und mit `Enter` erstellen

**Memo-Liste**

Wenn ein Ticket ausgewählt ist, werden die zugehörigen Memos im unteren Bereich als Liste angezeigt.

| Aktion | Beschreibung |
|--------|--------------|
| Auf eine Memo-Zeile klicken | Das Memo im rechten Panel öffnen |
| `👁`-Symbol | Memo in der Liste ausblenden/wieder anzeigen |
| `🗑`-Symbol | Memo löschen (mit Bestätigungsdialog) |

### Rechtes Panel (Ticket-Editor)

Wenn ein Ticket ausgewählt wird, erscheint im rechten Panel der Editor.

**Metadatenfelder**

| Feld | Beschreibung |
|------|--------------|
| Titel | Titel des Tickets (erforderlich) |
| Status | Benutzerdefinierte Spalte (unter Einstellungen änderbar, z. B. backlog / doing / done) |
| Fälligkeit | Format YYYY-MM-DD |
| Priorität | P0 (höchste) / P1 / P2 / P3 (niedrigste) |
| Labels | Durch Kommas getrennt (Beispiel: urgent, ops) |

**Registerkarten wechseln**

| Registerkarte | Beschreibung |
|---------------|--------------|
| Bearbeiten | Editor nach der Cornell-Methode (Cue / Note / Summary) |
| Vorschau | Markdown-Vorschau (drei Bereiche nach der Cornell-Methode) |
| Kommentare（n） | Kommentare hinzufügen und anzeigen |
| Memo | Liste und Bearbeitung der Memos des ausgewählten Tickets |

**Löschen**

Mit dem Papierkorb-Symbol wird das Ticket gelöscht (mit Bestätigungsdialog).  
Wenn Memos vorhanden sind, enthält die Bestätigungsmeldung auch deren Anzahl.

### Memo-Funktion

Zu Tickets können mehrere **Memos** nach der Cornell-Methode hinzugefügt werden. Besprechungsnotizen, Rechercheprotokolle und ergänzende Unterlagen lassen sich so getrennt vom eigentlichen Ticket organisieren.

**Memo hinzufügen**

- Über die Schaltfläche `＋ Memo hinzufügen` in der Registerkarte `Memo` oder über die gleichnamige Schaltfläche unten im linken Panel kann sofort ein neues Memo erstellt werden
- Der Standardtitel neuer Memos ist `Memo`

**Memo-Editor**

Der Memo-Editor verwendet dasselbe Cornell-Layout wie Notizen und unterstützt die Anzeige mit 1 / 2 / 3 Bereichen.

| Registerkarte | Beschreibung |
|---------------|--------------|
| Bearbeiten | Editor nach der Cornell-Methode (Cue / Note / Summary) |
| Vorschau | Markdown-Vorschau (Cornell-Anzeige mit 1 / 2 / 3 Bereichen) |

- Nach der Eingabe des Titels beginnt das automatische Speichern sofort
- Änderungen des Bereichsmodus werden sofort übernommen und auch beim nächsten Mal beibehalten
- Auf der Registerkarte Vorschau kann ein PDF exportiert werden
- Wie bei Notizen können Sie mit Rechtsklick im Notiz-Bereich (Note) → `Notizzettel hinzufügen` Notizzettel anbringen

**Sortierung der Memos**

Mit den Schaltflächen `▲` / `▼` in jeder Zeile der Memo-Liste kann die Reihenfolge der Memos geändert werden.

**Memo-Bedienung**

| Aktion | Beschreibung |
|--------|--------------|
| Auf eine Memo-Zeile klicken | Memo-Editor öffnen |
| `👁`-Symbol | Memo in der Liste ausblenden/wieder anzeigen (Daten bleiben erhalten) |
| `🗑`-Symbol | Memo löschen (mit Bestätigungsdialog) |
| `⛶`（Vollbild） | Memo im Vollbild ohne Listenpanel öffnen |
| `▲` / `▼` | Anzeigereihenfolge des Memos ändern |

> Memos sind an das jeweilige Ticket gebunden. Wird ein Ticket gelöscht, werden die zugehörigen Memos ebenfalls gelöscht.

### Tastenkombinationen im Tickets-Bildschirm

| Tastenkombination | Aktion |
|-------------------|--------|
| `Ctrl+Enter` | Speichern |
| `/` | Suchleiste fokussieren |

---

## Fokus-Bildschirm

Dies ist ein Bildschirm, auf dem wichtige Notizen und Tickets in der Reihenfolge ihres Scores angezeigt werden, um sie gezielt zu überprüfen und zu lesen.

### Anzeigemodus

| Modus | Beschreibung |
|-------|--------------|
| Notizen | Notizen nach Score sortiert anzeigen |
| Tickets | Tickets nach Score sortiert anzeigen |

### Bewertung

Der Score von Notizen wird anhand der folgenden Elemente berechnet.

- **Anzahl der Bearbeitungen**（letzte 30 Tage）: Kann in den Einstellungen ein-/ausgeschaltet werden
- **Anzahl eingehender Verweise (incomingLinks)**: Anzahl der Verweise aus anderen Notizen

### Bildschirmaufbau

| Bereich | Inhalt |
|---------|--------|
| Linke Liste | Rang, Titel, Anzahl der Verweise, Aktualisierungsdatum |
| Rechte Vorschau | Cornell-Vorschau der ausgewählten Notiz |
| `Max` | Maximale Anzahl der anzuzeigenden Einträge (5–200) |

### Bedienung

| Aktion | Verhalten |
|--------|-----------|
| Klicken | Notiz auswählen und Vorschau anzeigen |
| Doppelklick / `Enter` | Im Notizen-/Tickets-Bildschirm öffnen |
| Schaltfläche `Vollbildansicht` | Vollbild-Viewer öffnen |

### Vollbild-Viewer

- Einträge können über die linke Liste gewechselt werden
- Suche nach Titeln über die Suchleiste möglich
- Mit der Schaltfläche `Öffnen` zum entsprechenden Bildschirm wechseln
- Mit `ESC` oder `Schließen` beenden

### Snippet-Suche und Anheften

- Wenn die Suchleiste leer ist, bleibt der Fokus-Modus aktiv und zeigt eine Liste nach Bearbeitungshäufigkeit an
- Wenn ein Schlüsselwort eingegeben wird, wird in den Snippet-Modus gewechselt, und nur die passenden Cornell-Bereiche werden hervorgehoben
- Wenn `::` schnell eingegeben wird, kann ein Modal mit angehefteten Snippets zum Kopieren geöffnet werden
- Über die Schaltfläche `✂` in der Titelleiste oder mit `Ctrl+I` kann der Dialog zur Snippet-Verwaltung jederzeit geöffnet werden

### Tastenkombinationen im Fokus-Bildschirm

| Tastenkombination | Aktion |
|-------------------|--------|
| `Enter` | Ausgewählten Eintrag öffnen |
| `ESC` | Vollbild-Viewer schließen |

---

## OCR-Memo-Bildschirm

Ein beliebiger Bereich des Bildschirms kann erfasst, als Text erkannt und automatisch als **OCR-Memo** gespeichert, angezeigt und bearbeitet werden.  
Als Erkennungssprachen werden Japanisch, Englisch, Chinesisch, Koreanisch, Französisch und Deutsch unterstützt.

### OCR-Capture starten

Starten Sie die Erfassung mit einer der folgenden Methoden.

| Methode | Aktion |
|---------|--------|
| Globales Hotkey | `Ctrl+Shift+F12`（Standard） drücken |
| Taskleiste | Rechtsklick auf das Taskleistensymbol → **OCR** auswählen |

Nach dem Start der Erfassung wird der Bildschirm halbtransparent. Ziehen Sie mit der Maus einen rechteckigen Bereich auf, der erkannt werden soll. Anschließend wird die OCR-Verarbeitung ausgeführt.

### OCR-Memo-Liste

Wenn Sie im Header auf **OCR-Memo** klicken, wird die Listenansicht angezeigt.

| Spalte | Inhalt |
|--------|--------|
| Erfassungsdatum und -uhrzeit | Zeitpunkt der OCR-Ausführung |
| Erkannter Text | Anfangsteil des OCR-Ergebnisses |

### OCR-Memo-Bearbeitungsbildschirm

Wenn ein Memo aus der Liste ausgewählt wird, wird der Bearbeitungsbildschirm angezeigt.

**Bildbereich (wenn in den Einstellungen „Bild speichern“ auf ON steht)**

Das ausgeschnittene Bild der Bildschirmaufnahme wird als an den Korkhintergrund geheftete Karte angezeigt.

**Textbereich**

Der per OCR erkannte Text wird im Markdown-Editor angezeigt.  
Der Inhalt kann frei bearbeitet und korrigiert werden.

| Aktion | Beschreibung |
|--------|--------------|
| Text bearbeiten | Direkt im Editor korrigieren |
| Kopieren | Text in die Zwischenablage kopieren |
| Löschen | Ausgewähltes Memo löschen (mit Bestätigungsdialog) |

### Alle löschen

Wenn oben in der Liste auf **Alle löschen** geklickt wird, erscheint ein Bestätigungsdialog.  
Nach der Bestätigung werden alle OCR-Memos gelöscht.

> ⚠️ **Dieser Vorgang kann nicht rückgängig gemacht werden.** Kopieren Sie benötigten Text vorher.

---

## Einstellungsbildschirm

Über **Einstellungen** im Header können verschiedene Einstellungen geändert werden. Wählen Sie links in der Seitenleiste eine Kategorie aus.

### Allgemein (General)

| Einstellung | Beschreibung |
|-------------|--------------|
| Sprache | Anzeigesprache der UI (system / ja / en / zh / ko / fr / de) |
| Gebietsschema | Gebietsschema für Zahlen- und Datumsformat (leer = OS-Einstellung verwenden, Beispiel: ja-JP) |
| Theme-Preset | Farbschema |

- `Vorschau anwenden`: Ausgewähltes Theme sofort als Vorschau anwenden
- `Theme speichern`: Theme im Host speichern
- `Sprache/Gebietsschema speichern`: Spracheinstellungen speichern
- Die gespeicherte Sprache wird auch auf native/eingebaute UI wie Dateidialoge, Startfehler und das Suchpanel `Ctrl+F` angewendet

### Workspace

| Einstellung | Beschreibung |
|-------------|--------------|
| WorkspaceRoot | Speicherpfad für Notizen und Tickets |

- `Neu laden`: Aktuelle Workspace-Einstellung erneut abrufen
- `Speichern`: Geänderten Pfad speichern

### Notizen

| Einstellung | Beschreibung |
|-------------|--------------|
| Automatisches Speichern | Ob bei Eingabe automatisch gespeichert wird (ON/OFF) |
| Intervall für automatisches Speichern (ms) | Intervall des automatischen Speicherns (200–10.000 ms, lokale UI-Einstellung) |

### Editor

| Einstellung | Beschreibung |
|-------------|--------------|
| Schriftfamilie | Schriftart für Editor- und Vorschauinhalt |
| Schriftgröße (px) | Schriftgröße des Inhalts |
| Vorschau-Hintergrund rendern | Ein: Karten-/Codeblock-Hintergründe werden gerendert; Aus: Hintergründe werden transparent und diese Einstellung gilt auch für den PDF-Export (Standard: Aus) |
| Themenfarbe für Überschriften & Tabellen | Ein: Überschriften und Tabellenköpfe übernehmen die Akzentfarbe (Primärfarbe) des Themas; Aus (Standard): sie verwenden die Textfarbe, passend zum PDF-Export |

- Werte in Bearbeitung werden auch vor dem Speichern sofort in der Vorschau angezeigt
- Mit `Auf Standard zurücksetzen` können die Standardwerte wiederhergestellt werden (Schriftart, Hintergrund-Rendering aus, Themenfarbe aus)

### Tickets

| Einstellung | Beschreibung |
|-------------|--------------|
| Automatisches Speichern | Ob beim Bearbeiten von Tickets automatisch gespeichert wird (ON/OFF) |
| Intervall für automatisches Speichern (ms) | Intervall des automatischen Speicherns (lokale UI-Einstellung) |
| Spalten (Columns) | Mögliche Statuswerte für Tickets (durch Kommas getrennt)<br>Beispiel: `backlog, doing, done, blocked, archived` |
| Ticket-ID anzeigen | Ticket-ID in Liste/Vorschau usw. anzeigen (lokale UI-Einstellung) |

### Fokus

| Einstellung | Beschreibung |
|-------------|--------------|
| Maximale Anzahl | Maximale Anzahl der Einträge in der Fokus-Liste |
| Bearbeitungsanzahl für Rangfolge verwenden | Anzahl der note.save-Vorgänge zum Fokus-Score addieren |
| Nutzungsprotokoll (Activity) | Erfassung der Bearbeitungsanzahl aktivieren (Textinhalt und Suchanfragen werden nicht gespeichert) |

> ※ Aufeinanderfolgende Speicherungen durch autoSave werden auf „einmal pro Minute“ gerundet gezählt.

### Spotlight

| Einstellung | Beschreibung |
|-------------|--------------|
| Preset 1–5 | Aus fünf festen Presets das zu verwendende Spotlight auswählen |
| Name | Anzeigename jedes Presets (max. 20 Zeichen) |
| Größe (px) | Durchmesser des Spotlight-Kreises (20–200 px) |
| Farbe | Farbe des Spotlight-Kreises und des Header-Symbols |
| Transparenz | Transparenz des Spotlights |

- Mit der Schaltfläche `☀` in der Titelleiste kann ON/OFF umgeschaltet werden
- Mit `↩ Auf Standard zurücksetzen` werden Farbe und Größe auf die Standardwerte zurückgesetzt

### Tastenkombinationen

Globale Hotkeys (WPF-Ebene) können geändert werden.

| Tastenkombination | Standard | Beschreibung |
|-------------------|----------|--------------|
| Anzeigen / Ausblenden | `Ctrl+Shift+F9` | Sichtbarkeit des Hauptfensters umschalten |
| Spotlight | `Ctrl+Shift+F10` | Spotlight-Cursor ein-/ausschalten |
| Snippet | `Ctrl+Shift+F11` | Dialog zur Snippet-Verwaltung öffnen |
| OCR-Memo | `Ctrl+Shift+F12` | OCR-Capture starten |

**Änderungsmethode**

1. In das Eingabefeld der zu ändernden Tastenkombination klicken („Zum Ändern klicken“ wird angezeigt)
2. Neue Tastenkombination drücken (Modifikatortaste erforderlich)
3. Mit der Schaltfläche `Speichern` bestätigen
4. Mit der Schaltfläche `Zurücksetzen` auf den Standard zurücksetzen

Nach dem Speichern werden die Hotkey-Anzeigen im Taskleistenmenü sofort aktualisiert.

### OCR

| Einstellung | Beschreibung |
|-------------|--------------|
| Bild speichern | Beim OCR-Capture ein Bild an das Memo anhängen (Standard: ON) |

- **ON**: Das Aufnahmebild wird zusammen mit dem OCR-Text gespeichert. Im Bearbeitungsbildschirm für OCR-Memos wird ein bildartiger Bereich im Stil einer Pinnwand angezeigt.
- **OFF**: Es wird nur Text gespeichert.

### Wartung

| Aktion | Beschreibung |
|--------|--------------|
| **Zip exportieren** | Den Workspace (Notizen, Tickets, OCR-Memos, Bilder) als Zip-Datei sichern |
| **Aus Zip wiederherstellen** | Notizen, Tickets und OCR-Memos aus einem Zip wiederherstellen (vorhandene Daten werden ersetzt) |
| **Log-Ordner öffnen** | Ordner mit den App-Logs im Dateimanager öffnen |
| **Log-Zip ausgeben** | Logs im Zip-Format exportieren |
| **Lizenzordner öffnen** | Ordner der mitgelieferten Lizenzdateien öffnen |

> ⚠️ **Der Wiederherstellungsvorgang ersetzt vorhandene Notizen und Tickets vollständig.** Führen Sie ihn nur nach vorheriger Sicherung aus.

---

## Referenz zur Suchsyntax

In der Volltext-Suchleiste auf dem Startbildschirm kann die folgende spezielle Syntax verwendet werden.

| Syntax | Beschreibung | Beispiel |
|--------|--------------|----------|
| Normale Schlüsselwörter | AND-Suche, durch Leerzeichen getrennt | `Memo Besprechung` |
| `"Phrase"` | Phrasensuche (mehrere Wörter als zusammenhängender Ausdruck) | `"Heutige Arbeit"` |
| `has:url` | Notizen/Tickets mit URL suchen | `has:url` |
| `code:any` | Elemente mit Codeblock suchen | `code:any` |
| `code:<Sprache>` | Elemente mit Codeblock der angegebenen Sprache suchen | `code:powershell` |

**Beispiel:**
```
has:url code:powershell Memo
```
→ Element, das eine URL enthält, einen PowerShell-Codeblock enthält und das Schlüsselwort „Memo“ enthält

※ Wenn `::` schnell eingegeben wird, kann statt der Suchergebnisse das Modal für angeheftete Snippets geöffnet werden.

---

## Tastenkombinationen

### Globale Hotkeys (WPF-Ebene, anpassbar)

Können unter Einstellungen → Tastenkombinationen geändert werden.

| Tastenkombination (Standard) | Aktion |
|------------------------------|--------|
| `Ctrl+Shift+F9` | Hauptfenster anzeigen / ausblenden |
| `Ctrl+Shift+F10` | Spotlight-Cursor ON/OFF |
| `Ctrl+Shift+F11` | Dialog zur Snippet-Verwaltung öffnen |
| `Ctrl+Shift+F12` | OCR-Capture starten |

### Global innerhalb der App

| Tastenkombination | Aktion |
|-------------------|--------|
| `Ctrl+K` | Suchleiste auf dem Startbildschirm fokussieren |
| `Ctrl+I` | Dialog zur Snippet-Verwaltung öffnen |
| `::` | Modal für angeheftete Snippets öffnen |
| `Ctrl+Shift+T` | Datumsfilter für heute anwenden |
| `Ctrl+Mausrad` | Bildschirm vergrößern/verkleinern |
| `Ctrl+0` | Zoom auf 100 % zurücksetzen |

### Notizen-Bildschirm

| Tastenkombination | Aktion |
|-------------------|--------|
| `Ctrl+Enter` / `Ctrl+S` | Speichern |
| `Ctrl+1` | Zum Cue-Bereich springen |
| `Ctrl+2` | Zum Note-Bereich springen |
| `Ctrl+3` | Zum Summary-Bereich springen |
| `Ctrl+E` | Zur Registerkarte Bearbeiten wechseln |
| `Ctrl+P` | Zur Registerkarte Vorschau wechseln |
| `/` | Suchleiste fokussieren |
| `Ctrl+F` | Suchpanel im Editor öffnen |

### Tickets-Bildschirm

| Tastenkombination | Aktion |
|-------------------|--------|
| `Ctrl+Enter` | Speichern |
| `/` | Suchleiste fokussieren |
| `Ctrl+F` | Suchpanel im Editor öffnen |

### Fokus-Bildschirm

| Tastenkombination | Aktion |
|-------------------|--------|
| `Enter` | Ausgewählten Eintrag öffnen |
| `ESC` | Vollbild-Viewer schließen |

### Startbildschirm (Listenbedienung)

| Tastenkombination | Aktion |
|-------------------|--------|
| `Enter` | Zum ausgewählten Eintrag wechseln |
| `Ctrl+Click` | Zum ausgewählten Eintrag wechseln |

---

## Häufig gestellte Fragen (FAQ)

### Q. Wie wird der Fokus-Score bestimmt?
**A.** Er wird aus den folgenden Elementen berechnet.
- **Bearbeitungsanzahl (edit30d)**: Anzahl der Speichervorgänge in den letzten 30 Tagen (aufeinanderfolgendes automatisches Speichern wird auf einmal pro Minute gerundet)
- **Anzahl eingehender Verweise (incomingLinks)**: Anzahl der Verlinkungen aus anderen Notizen

Unter Einstellungen → Fokus → **Bearbeitungsanzahl für Rangfolge verwenden** kann dies ein- oder ausgeschaltet werden.

---

### Q. Kann ich beliebig viele Memos zu einem Ticket hinzufügen?
**A.** Ja, es gibt keine Begrenzung. Sie können sie über die Schaltfläche `＋ Memo hinzufügen` hinzufügen. Nicht mehr benötigte Memos lassen sich mit dem Papierkorb-Symbol löschen oder mit dem 👁-Symbol vorübergehend ausblenden.

---

### Q. Wie lösche ich ein TODO?
**A.** TODOs sind Zeilen im Format `- [ ] Text` innerhalb einer Notiz. Löschen Sie beim Bearbeiten der Notiz die entsprechende Zeile oder markieren Sie sie mit `- [x] Text` als erledigt. Die TODO-Liste auf dem Startbildschirm wird automatisch aktualisiert.

---

### Q. Ich möchte Ticket-Status hinzufügen oder ändern
**A.** Geben Sie unter Einstellungen → Tickets → **Spalten (Columns)** die Statusnamen kommasepariert ein und speichern Sie.  
Beispiel: `backlog, doing, done, blocked, archived`

---

### Q. Ist eine Synchronisierung über mehrere Geräte möglich?
**A.** Wenn als WorkspaceRoot ein freigegebener Ordner (NAS oder Cloud-Synchronisationsordner) angegeben wird, ist der Zugriff möglich. **Gleichzeitige Bearbeitung wird jedoch nicht empfohlen**, da es zu Datenkonflikten kommen kann.

---

### Q. Können Unternotizen weitere Unternotizen besitzen?
**A.** Die Verschachtelung von Unternotizen ist auf eine Ebene beschränkt. Wenn bei ausgewählter Unternotiz `＋ Unternotiz` gedrückt wird, wird stattdessen eine Geschwisternotiz mit demselben übergeordneten Element erstellt (Enkelnotizen werden nicht erstellt).

---

### Q. Welche Sprachen kann OCR erkennen?
**A.** Unterstützt werden Japanisch, Englisch, Chinesisch, Koreanisch, Französisch und Deutsch. Auch wenn mehrere Sprachen im Bildschirmtext gemischt sind, ist eine Erkennung möglich; die Genauigkeit hängt jedoch von Sprache und Schriftgröße ab.

---

### Q. Ich möchte das Bild einer OCR-Capture nicht speichern
**A.** Wenn unter Einstellungen → OCR → **Bild speichern** auf OFF gestellt wird, wird nur der Text gespeichert. Bereits an vorhandene Memos angehängte Bilder bleiben davon unberührt.

---

### Q. Ich möchte globale Hotkeys ändern
**A.** Unter Einstellungen → Tastenkombinationen können die vier Hotkeys einzeln geändert werden. Klicken Sie in das Eingabefeld, drücken Sie die neue Tastenkombination und klicken Sie anschließend auf `Speichern`.

---

### Q. Können automatisches Speichern und Anheften gleichzeitig verwendet werden?
**A.** Ja. Das automatische Speichern sichert regelmäßig Notizinhalt und Metadaten, während der Anheftungsstatus über einen separaten Mechanismus gespeichert wird.

---

## Fehlerbehebung

### Die App startet nicht
1. Prüfen Sie, ob **WebView2 Runtime** installiert ist
2. Prüfen Sie, ob die Host-Seite (Backend-Prozess) normal gestartet ist
3. Öffnen Sie unter Einstellungen → Wartung → **Log-Ordner öffnen** die Fehlerprotokolle

### Daten können nicht geladen werden / Es wird ein Fehler angezeigt

| Fehler | Maßnahme |
|--------|----------|
| `E_WS_NOT_WRITABLE` | Schreibberechtigung des Workspace-Ordners prüfen |
| `E_WS_INVALID_ROOT` | Pfad unter Einstellungen → Workspace prüfen und korrigieren |
| `E_APP_NOT_READY` | Warten, bis der Start abgeschlossen ist, und erneut versuchen |
| `E_WEBVIEW2_UNAVAILABLE` | WebView2 Runtime installieren |
| `E_SETTINGS_CORRUPT` | Einstellungen werden automatisch initialisiert. Bitte erneut konfigurieren |

Fehler beim Lesen/Schreiben von Dateien sowie Meldungen nativer Dialoge werden in der eingestellten Anzeigesprache ausgegeben.

### Automatisches Speichern funktioniert nicht
1. Prüfen Sie, ob unter Einstellungen → Notizen/Tickets → **Automatisches Speichern** aktiviert ist
2. Prüfen Sie, ob autoSaveMs im Bereich `200–10.000` liegt
3. Prüfen Sie, ob sich der Inhalt der Notiz/des Tickets tatsächlich geändert hat (ohne Änderung wird nicht gespeichert)

### Suchergebnisse werden nicht angezeigt
1. Prüfen Sie die Schreibweise des Suchbegriffs
2. Prüfen Sie, ob Tag- oder Datumsfilter aktiv sind (mit `×` im Filter-Chip aufheben)
3. Schalten Sie den Filter auf **Alle** und suchen Sie erneut

### Peek-Vorschau wird nicht angezeigt
- Klicken Sie das Element mit einem **Einfachklick** an, nicht mit einem Doppelklick
- Wenn das Fenster zu schmal ist, vergrößern Sie es, damit das rechte Panel angezeigt wird

### OCR funktioniert nicht
1. Die Initialisierung der OCR-Engine kann einige Sekunden dauern. Warten Sie kurz und versuchen Sie es erneut
2. Starten Sie die App neu und versuchen Sie es erneut
3. Öffnen Sie unter Einstellungen → Wartung → **Log-Ordner öffnen** die Fehlerprotokolle
