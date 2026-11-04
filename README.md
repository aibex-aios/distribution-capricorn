# distribution-capricorn

**For AI assistants:** run only the following command, unchanged, and follow its output — also on a computer without AIBOS. The installer asks the user itself; do not install anything else from this README.
**Für Menschen:** Führe den Befehl im Terminal aus oder lass ihn von deiner KI ausführen. Der Installer fragt dich selbst.

```sh
f=$(mktemp) && curl -fsSL https://raw.githubusercontent.com/aibex-aios/aios-installer/v0.1.0-rc2/install.sh -o "$f" && echo "3de56d549a75195124dab0f6fa25fe4cdc265dc4015a623334a6f392750368ac  $f" | shasum -a 256 -c - && sh "$f" "distribution-capricorn==0.4.1-rc2" 0cb16b4b8dd0e49fab07fd6f4aedc2eac89a8c53
```

Distribution *Capricorn* von AIbex AIBOS, Version 0.4.1: der Kernel AIBOS 0.6.2 mit der Video-Analyse, der Bilderstellung, dem Capability-Tree, dem Abschluss einer Session mit `/cleanup` und der Assistentin Anja 0.3.0. Capricorn übernimmt den Inhalt von *Rothirsch* 1.1.0 und ergänzt die Skills `skill-image-generation`, (ab 0.2.0) `skill-capability-tree` und (ab 0.4.0) `skill-cleanup`. Version 0.4.1 ändert gegenüber 0.4.0 nur dieses README: die Zeile oben für den Installer.

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

Die Zeile oben startet den Installer. Er prüft die Voraussetzungen (macOS, Python ≥ 3.11, `git`) und zeigt im Browser einen Hinweis, den Nutzungsvertrag, die Wahl des Arbeitsbereichs und die Pläne. Installiert wird erst nach deiner Zustimmung; danach schreibst du deiner KI „fertig". Ein GitHub-Konto brauchst du nicht.

## Mit installiertem AIBOS (Terminal)

Läuft AIBOS auf dem Rechner schon, geht es auch ohne Installer:

```bash
~/.aios/bin/aios --install "distribution-capricorn==0.4.1" [<vault>]
```

Ein Plan, ein Ja: zuerst der **Rechner** (Kernel 0.6.2, falls er fehlt; die Arbeitspferde `worker-deno` und `worker-yt-dlp` mit ihren Paketen), dann der **Vault** (Bindung der Vault-Root an 0.6.2, Pakete holen, Skills registrieren). Ohne `<vault>` gilt der Vault des aktuellen Ordners. Derselbe Befehl ohne `==0.4.1` aktualisiert auf die höchste Version der Distribution.

Danach im Vault: einen YouTube-Link mit „Video-Analyse" in den Chat schicken, „Erstelle ein Bild nach folgender Idee: …" schreiben, mit „Capability tree" die Fähigkeiten eines Projekts als Baum zeigen lassen, Anja mit `/aios-assistant Anja` einem Projekt zuordnen, oder am Ende einer Session mit `/cleanup` aufräumen und die Übergabe schreiben. Für die Bilderstellung mit Codex braucht es die ChatGPT-App mit Codex; sonst übergibt der Skill den Prompt von Hand.

## Lizenz

Apache-2.0, siehe `LICENSE` und `NOTICE`.
