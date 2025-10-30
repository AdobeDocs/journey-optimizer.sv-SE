---
source-git-commit: 08eaa7ae974c134ea2e920a1fa854dcf6a971e18
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 0%

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

3. Agenten kommer automatiskt att:
   - Testa SSH- och HTTPS-åtkomst
   - Använda arbetsmetoden
   - Vägled vid behov
4. Klart! ✨

**Obs!** Agenten identifierar automatiskt om du har SSH- eller HTTPS-åtkomst till `git.corp.adobe.com` och använder rätt metod. Om ingen av funktionerna fungerar visas en guidad konfiguration.

### Alternativ 2: Använda terminal

1. Öppna terminalen i databasroten
2. Kör:

   ```bash
   ./setup-agents.sh
   ```

   Skriptet kommer automatiskt att:
   - Testa SSH- och HTTPS-åtkomst
   - Använda arbetsmetoden
   - Visa installationsanvisningar om det behövs

   Eller manuellt (om du vet att din Git är konfigurerad):

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

Se [AGENTS.md](AGENTS.md) för en fullständig lista över tillgängliga agenter.

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
your-repo/
  ├── .cursor-agents/          ← Git submodule
  │   ├── agents/
  │   │   ├── draft-page-generator.md
  │   │   └── fix-grammar.md
  │   └── AGENTS.md
  ├── setup-agents.sh          ← Setup script
  └── your-content/
```

Undermodulen pekar på:
**https://git.corp.adobe.com/AdobeDocs/CursorAgents**

Detta garanterar att alla använder samma, aktuella agenter.

## För underhållare

### Lägga till i en ny databas

1. Lägg till undermodulen:

   ```bash
   git submodule add https://git.corp.adobe.com/AdobeDocs/CursorAgents.git .cursor-agents
   ```

2. Kopiera installationsfiler:
   - `setup-agents.sh`
   - `setup-agent.md` (placera i roten, inte i undermodulen)
   - `INSTALL.md`

3. Verkställ:

   ```bash
   git add .gitmodules .cursor-agents setup-agents.sh
   git commit -m "Add Cursor Agents submodule"
   ```

### Uppdaterar det centrala arkivet

Ändringar av agens bör göras i:
**https://git.corp.adobe.com/AdobeDocs/CursorAgents**

Alla databaser får uppdateringar via `git submodule update --remote`.

---

**Behöver du hjälp?** Kontakta dokumentationsteamets ledare eller kontrollera den interna wiki-instansen.
