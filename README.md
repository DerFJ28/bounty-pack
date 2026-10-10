# bounty-pack

Resource Pack für das **BountyPlugin** (Minecraft Java 1.21.11). Es gibt den eigenen Items des Plugins eigene Texturen. Ohne dieses Pack funktioniert das Plugin trotzdem, die Items sehen dann nur aus wie ihre Vanilla-Grundlage.

Dieses Repo enthält nur das **fertige Pack** (als Release und als Datei `bountypack.zip`). Quellen, Build-Script und das Plugin selbst liegen im privaten Repo `bounty-code`.

## Was du bekommst

Eine Zip-Datei mit 10 Item-Texturen (16×16) und den passenden Modellen:

| Item | Grundlage im Spiel | Custom Model Data |
|---|---|---|
| Diamant-Dolch | Diamant-Schwert | 1001 |
| Phantom-Helm | Diamant-Helm | 1002 |
| Trugbild-Helm | Diamant-Helm | 1003 |
| Grappling Hook | Angel | 1004 |
| God Boots / Leggings / Chestplate / Helm | Netherit-Stiefel / -Hose / -Brustpanzer / -Helm | 1011 / 1012 / 1013 / 1014 |
| Phantom-Gleiter (zu / offen) | Papier | 1020 / 1021 |

Alle anderen Items bleiben unverändert. Das Pack ersetzt keine normalen Items, nur solche, die das BountyPlugin mit der passenden Custom Model Data erzeugt.

**Kompatibilität:** nur Minecraft **1.21.11** (`pack_format` 94). Auf anderen Versionen zeigt Minecraft eine Warnung oder lädt das Pack nicht.

## Installation

### Auf einem Server mit BountyPlugin (der normale Fall)

In `plugins/BountyPlugin/config.yml` eintragen und den Server neu starten:

```yaml
resource-pack:
  url: 'https://github.com/DerFJ28/bounty-pack/releases/download/v1.0.0/bountypack.zip'
  sha1: '101643ab1d0fae0b6c065e6bfdc75660c7c24b07'
```

Das Plugin schickt das Pack dann jedem Spieler beim Beitritt. Die Spieler müssen beim ersten Mal das Server-Pack annehmen und brauchen sonst nichts zu tun. Es ist nicht erzwungen: wer ablehnt, kann trotzdem spielen.

Die Werte für jede Version stehen bei den [Releases](https://github.com/DerFJ28/bounty-pack/releases). **URL und SHA-1 müssen zur selben Version gehören.** Stimmt die Prüfsumme nicht, lädt der Client das Pack nicht.

Die Installation des Plugins selbst steht in der README von `bounty-code` (privates Repo).

### Manuell im eigenen Client (zum Anschauen)

1. `bountypack.zip` aus dem [neuesten Release](https://github.com/DerFJ28/bounty-pack/releases/latest) laden. **Nicht entpacken.**
2. In den Ordner `resourcepacks` deines Minecraft-Verzeichnisses legen (im Spiel: Optionen → Ressourcenpakete → Packordner öffnen).
3. Im Spiel unter Optionen → Ressourcenpakete aktivieren.

Man sieht die Texturen aber nur an Items, die das BountyPlugin erzeugt hat. Allein macht das Pack nichts Sichtbares.

### Prüfsumme prüfen (optional)

```bash
sha1sum bountypack.zip      # Linux
shasum bountypack.zip       # macOS
```

Das Ergebnis muss mit dem SHA-1 des Releases übereinstimmen (siehe oben bzw. Release-Beschreibung).

## Neues Pack veröffentlichen (für Entwickler)

1. Im Repo `bounty-code` das Pack bauen: `bash tools/build-resourcepack.sh`. Das Script legt `bountypack.zip` an und gibt die SHA-1 aus.
2. Hier einen neuen Release anlegen (neue Versionsnummer, z. B. `v1.1.0`) und die Zip als Datei anhängen. Die SHA-1 in die Release-Beschreibung schreiben.
3. Auf dem Server `resource-pack.url` und `resource-pack.sha1` auf die neue Version setzen und den Server neu starten.

Die Datei `bountypack.zip` im Branch `main` ist nur eine Kopie des aktuellen Stands. Maßgeblich sind die Releases.

## Lizenz und Herkunft

Die Texturen wurden mit dem Script `tools/generate_textures.py` (in `bounty-code`) für das Projekt erzeugt. Eine Lizenz ist noch nicht festgelegt.
