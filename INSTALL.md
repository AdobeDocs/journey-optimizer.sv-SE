---
source-git-commit: d7bb3424bc6dfb837b47d15c448a2d46bf4b6c3c
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 1%

---
# 🚀 installerar marköragenter

Marköragenter är delade verktyg som hjälper dig att skapa och underhålla dokumentation mer effektivt.

## Inställning för första gången

Du behöver bara göra detta **en gång** per databas.

### Alternativ 1: Använder markören (rekommenderas ⭐)

1. Öppna markörchatt (`Cmd+L` eller `Ctrl+L`)
2. Typ:

   ```
   @setup-agents
   ```
3. Följ anvisningarna
4. Klart! ✨

### Alternativ 2: Använda terminal

1. Öppna terminalen i databasroten
2. Kör:

   ```bash
   ./setup-agents.sh
   ```
   Eller manuellt:

   ```bash
   git submodule update --init --recursive
   ```
3. Klart! ✨

## Verifiering

Kontrollera installationen efter installationen:

```bash
ls .cursor-agents/agents/
```

Du bör se:
- `draft-page-generator.md`
- `fix-grammar.md`
- osv.

## Användning

När du har installerat programmet kan du använda agenter i markören:

```
@draft-page      # Generate a new documentation page
@fix-grammar     # Fix grammar in current file
```

En fullständig lista över tillgängliga agenter finns i `.cursor-agents/AGENTS.md`.

## Uppdaterar agenter

Så här hämtar du den senaste versionen av alla agenter:

### Alternativ 1: Använda markör

```
@update-agents
```

### Alternativ 2: Använda terminal

```bash
git submodule update --remote
```

## Felsökning

### &quot;Agenten hittades inte&quot;-fel

Om det här felet visas har agenterna inte installerats ännu. Kör:

```
@setup-agents
```

### Undermodulen är tom

Om `.cursor-agents/` finns men är tom:

```bash
git submodule update --init --recursive --remote
```

### Åtkomst nekad

Kontrollera att installationsskriptet är körbart:

```bash
chmod +x setup-agents.sh
```

### Problem med nätverk/VPN

- Kontrollera att du är ansluten till Adobe VPN
- Kontrollera nätverksanslutning
- Verifiera Git-åtkomst:

  ```bash
  git ls-remote https://git.corp.adobe.com/AdobeDocs/CursorAgents
  ```

## Så här fungerar det

Marköragenter distribueras som en **Git-undermodul**:

```
journey-optimizer.en/
  ├── .cursor-agents/          ← Git submodule
  │   ├── agents/
  │   │   ├── draft-page-generator.md
  │   │   └── fix-grammar.md
  │   └── AGENTS.md
  ├── setup-agents.sh          ← Setup script
  ├── setup-agent.md           ← Bootstrap agent
  └── help/                    ← Your documentation
```

Undermodulen pekar på:
**https://git.corp.adobe.com/AdobeDocs/CursorAgents**

Detta garanterar att alla använder samma, aktuella agenter.

---

**Behöver du hjälp?** Kontakta dokumentationsteamets ledare eller kontrollera den interna wiki-instansen.

