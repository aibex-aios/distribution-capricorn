# distribution-capricorn

Distribution *Capricorn* von AIbex AIOS, Version 0.3.0-rc4 (Release-Kandidat): der Kernel AIOS 0.6.1-rc4 mit der Video-Analyse, der Bilderstellung, dem Capability-Tree und der Assistentin Anja. Capricorn übernimmt den Inhalt von *Rothirsch* 1.1.0 und ergänzt die Skills `skill-image-generation` und (ab 0.2.0) `skill-capability-tree`.

| Teil | Version | kommt mit |
|---|---|---|
| Kernel `aios` | 0.6.1-rc4 | `kernel:` |
| `skill-video-analyse` | 0.2.1 | `depends` |
| `assistant-anja` | 0.2.1 | `depends` |
| `skill-image-generation` | 0.1.1 | `depends` |
| `skill-capability-tree` | 0.1.1 | `depends` |
| `skill-5-8-zusammenfassung`, `skill-memo` | nach dem Resolver | Abhängigkeit der Video-Analyse |
| `worker-yt-dlp`, `worker-deno` | nach dem Resolver | Arbeitspferde der Video-Analyse |

## Installieren

```bash
aios --install distribution-capricorn==0.3.0-rc4 [<vault>]
```

Ein Plan, ein Ja: zuerst der **Rechner** (Kernel 0.6.1-rc4, falls er fehlt; die Arbeitspferde `worker-deno` und `worker-yt-dlp` mit ihren Paketen), dann der **Vault** (Bindung der Vault-Root an 0.6.1-rc4, Pakete holen, Skills registrieren). Ohne `<vault>` gilt der Vault des aktuellen Ordners. Derselbe Befehl aktualisiert auf eine neuere Version der Distribution.

Danach im Vault: einen YouTube-Link mit „Video-Analyse" in den Chat schicken, „Erstelle ein Bild nach folgender Idee: …" schreiben, mit „Capability tree" die Fähigkeiten eines Projekts als Baum zeigen lassen, oder Anja mit `/aios-assistant Anja` einem Projekt zuordnen. Für die Bilderstellung mit Codex braucht es die ChatGPT-App mit Codex; sonst übergibt der Skill den Prompt von Hand.

## Lizenz

Apache-2.0, siehe `LICENSE` und `NOTICE`.
