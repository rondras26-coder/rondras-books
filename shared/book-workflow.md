# Book Writing Workflow

## Der strenge Prozess

Jedes Buch durchläuft diese Phasen **nacheinander**. Kein Schritt wird übersprungen.

### Phase 1: KONZEPT
- **Autor**: Erstellt Logline + Outline (3-5 Sätze)
- **Speicher**: `buecher/buch-YYYY-MM-DD-[autor]-KONZEPT.md`
- **state.json**: `status="concept"`, `phase="concept"`, `step=1`
- **→ Lektor-Feedback →**

### Phase 2: CHARAKTERE
- **Autor**: Erstellt Charakterbögen (3-5 Hauptcharaktere)
- **Speicher**: `buecher/buch-YYYY-MM-DD-[autor]-CHARAKTERE.md`
- **state.json**: `status="characters"`, `phase="characters"`, `step=2`
- **→ Lektor-Feedback →**

### Phase 3: BEATS
- **Autor**: Erstellt detaillierte Beat-Sheet / Szenen-Übersicht
- **Speicher**: `buecher/buch-YYYY-MM-DD-[autor]-BEATS.md`
- **state.json**: `status="beats"`, `phase="beats"`, `step=3`
- **→ Lektor-Feedback →**

### Phase 4: KAPITEL (einzeln!)
- **Autor**: Schreibt **EIN** Kapitel nach dem anderen
- **Nach jedem Kapitel**:
  - Speicher: `buecher/buch-YYYY-MM-DD-[autor]-kapitel-X.md`
  - state.json: `status="writing"`, `current_chapter=X`
  - **→ Lektor-Feedback →** (jedes einzelne Kapitel!)
- **Erst wenn Kapitel X genehmigt** → Nächstes Kapitel

### Phase 5: FERTIG
- **state.json**: `status="completed"`, `phase="done"`
- Buch ist fertig lektoriert

---

## WICHTIG

1. **NIE alles auf einmal schreiben** – Schritt für Schritt
2. **Nach jedem Schritt: Lektor-Feedback** – erst dann weiter
3. **state.json steuert den Prozess** – nie überspringen
4. **Git Push nach jedem Schritt** – volle Historie

---

## Cron-Jobs

| Job | Zeitplan | Funktion |
|-----|----------|----------|
| `daily-book-generator` | Täglich 00:00 | Neues Buch starten |
| `book-editor` | Alle 4h | The Hesitation weiterschreiben |
| `autoscribe-weekly` | So 10:00 | Wochen-Update |

Alle Cron-Jobs pushen nach GitHub.
