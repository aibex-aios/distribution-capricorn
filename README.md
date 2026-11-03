# distribution-capricorn

Distribution *Capricorn* von AIbex AIOS, Version 0.4.0 (Release-Kandidat 0.4.0-rc2): der Kernel AIOS 0.6.2 mit der Video-Analyse, der Bilderstellung, dem Capability-Tree, dem Abschluss einer Session mit `/cleanup` und der Assistentin Anja 0.3.0. Capricorn übernimmt den Inhalt von *Rothirsch* 1.1.0 und ergänzt die Skills `skill-image-generation`, (ab 0.2.0) `skill-capability-tree` und (ab 0.4.0) `skill-cleanup`.

| Teil | Version | kommt mit |
|---|---|---|
| Kernel `aios` | 0.6.2 | `kernel:` |
| `skill-video-analyse` | 0.2.1 | `depends` |
| `assistant-anja` | 0.3.0 | `depends` |
| `skill-image-generation` | 0.1.1 | `depends` |
| `skill-capability-tree` | 0.1.1 | `depends` |
| `skill-cleanup` | 0.1.1 | `depends` |
| `skill-5-8-zusammenfassung`, `skill-memo` | nach dem Resolver | Abhängigkeit der Video-Analyse |
| `worker-yt-dlp`, `worker-deno` | nach dem Resolver | Arbeitspferde der Video-Analyse |

## Installieren

```bash
~/.aios/bin/aios --install "distribution-capricorn==0.4.0-rc2" [<vault>]
```

Ohne Bereich wählt AIOS die höchste Release; einen Kandidaten holt nur ein Bereich, der ihn nennt.

Ein Plan, ein Ja: zuerst der **Rechner** (Kernel 0.6.2, falls er fehlt; die Arbeitspferde `worker-deno` und `worker-yt-dlp` mit ihren Paketen), dann der **Vault** (Bindung der Vault-Root an 0.6.2, Pakete holen, Skills registrieren). Ohne `<vault>` gilt der Vault des aktuellen Ordners. Derselbe Befehl aktualisiert auf eine neuere Version der Distribution.

Danach im Vault: einen YouTube-Link mit „Video-Analyse" in den Chat schicken, „Erstelle ein Bild nach folgender Idee: …" schreiben, mit „Capability tree" die Fähigkeiten eines Projekts als Baum zeigen lassen, Anja mit `/aios-assistant Anja` einem Projekt zuordnen, oder am Ende einer Session mit `/cleanup` aufräumen und die Übergabe schreiben. Für die Bilderstellung mit Codex braucht es die ChatGPT-App mit Codex; sonst übergibt der Skill den Prompt von Hand.

## Lizenz

Apache-2.0, siehe `LICENSE` und `NOTICE`.
