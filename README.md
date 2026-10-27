# distribution-capricorn

Distribution *Capricorn* von AIbex AIOS, Version 0.1.0: der Kernel AIOS 0.5.1 mit der Video-Analyse, der Bilderstellung und der Assistentin Anja. Capricorn übernimmt den Inhalt von *Rothirsch* 1.0.0 und ergänzt den Skill `skill-image-generation`.

| Teil | Version | kommt mit |
|---|---|---|
| Kernel `aios` | 0.5.1 | `kernel:` |
| `skill-video-analyse` | 0.2.0 | `depends` |
| `assistant-anja` | 0.2.0 | `depends` |
| `skill-image-generation` | 0.1.0 | `depends` |
| `skill-5-8-zusammenfassung`, `skill-memo` | nach dem Resolver | Abhängigkeit der Video-Analyse |
| `worker-yt-dlp`, `worker-deno` | nach dem Resolver | Arbeitspferde der Video-Analyse |

## Installieren

```bash
aios --install distribution-capricorn [<vault>]
```

Ein Plan, ein Ja: zuerst der **Rechner** (Kernel 0.5.1, falls er fehlt; die Arbeitspferde `worker-deno` und `worker-yt-dlp` mit ihren Paketen), dann der **Vault** (Bindung der Vault-Root an 0.5.1, Pakete holen, Skills registrieren). Ohne `<vault>` gilt der Vault des aktuellen Ordners. Derselbe Befehl aktualisiert auf eine neuere Version der Distribution.

Danach im Vault: einen YouTube-Link mit „Video-Analyse" in den Chat schicken, „Erstelle ein Bild nach folgender Idee: …" schreiben, oder Anja mit `/aios-assistant Anja` einem Projekt zuordnen. Für die Bilderstellung mit Codex braucht es die ChatGPT-App mit Codex; sonst übergibt der Skill den Prompt von Hand.

## Lizenz

Apache-2.0, siehe `LICENSE` und `NOTICE`.
