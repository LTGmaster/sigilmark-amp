# Sigilmark AMP-sjabloon / Sigilmark AMP template

AMP 2.8 Generic-module template for the Sigilmark multiplayer lobby server (Linux x86_64, headless, no GPU).

Configuration Repository string: **`LTGmaster/sigilmark-amp:main`**

In the AMP Create Instance list the game appears as **Sigilmark**.

## Nederlands

Voeg dit toe als extra sjabloonbron in AMP (CubeCoders, 2.8):

1. Ga naar **Configuration → Instance Deployment**.
2. Voeg een **Configuration Repository** toe met exact: `LTGmaster/sigilmark-amp:main`
3. Klik op **Fetch** en ververs de browser.
4. Bij **Create Instance** staat **Sigilmark** in de lijst (de bron van CubeCoders blijft staan).
5. Maak de instance aan, kies **Update** (AMP haalt `SigilmarkServer-linux-x86_64.zip` van de nieuwste [release](https://github.com/LTGmaster/kolonie-releases/releases/latest)) en start.

Instellingen: **Server Name**, **Max Lobbies** (standaard 8), **Max Players per Lobby** (standaard 4). Standaardpoort is **UDP 24680** (alleen UDP; poorten van de lobbyprocessen zelf zijn intern en hoef je niet open te zetten). Spelers hebben exact dezelfde Sigilmark-versie nodig en verbinden in het spel via *Samen spelen* met `adres:24680`.

Elk nieuw spel vanaf deze server gebruikt een oneindige kaart. Netjes stoppen stuurt `stop` naar de console.

## English

Add this as an extra template source in AMP (CubeCoders, 2.8):

1. Go to **Configuration → Instance Deployment**.
2. Add a **Configuration Repository** with exactly: `LTGmaster/sigilmark-amp:main`
3. Click **Fetch** and refresh the browser.
4. **Sigilmark** then appears under **Create Instance** (the CubeCoders source stays in place).
5. Create the instance, choose **Update** (AMP downloads `SigilmarkServer-linux-x86_64.zip` from the latest [release](https://github.com/LTGmaster/kolonie-releases/releases/latest)), and start.

Settings: **Server Name**, **Max Lobbies** (default 8), **Max Players per Lobby** (default 4). Default port is **UDP 24680** (UDP only; per-lobby ports are internal and do not need to be opened). Players need the exact same Sigilmark version and connect in-game via *Play together* with `address:24680`.

Every new game started from this server uses an infinite map. A graceful stop sends `stop` to the console.

## Layout

AMP discovers lowercase `*.kvp` files in the repository root (same convention as [CubeCoders/AMPTemplates](https://github.com/CubeCoders/AMPTemplates)):

- `sigilmark.kvp` — Meta/App/Console/Limits (`Meta.DisplayName=Sigilmark`)
- `sigilmarkconfig.json` — settings manifest
- `sigilmarkmetaconfig.json` — empty (settings go on the command line)
- `sigilmarkports.json` — UDP GamePort 24680
- `sigilmarkupdates.json` — FetchURL of the latest Linux server zip, then SetExecutableFlag
- `sigilmark.png` — list image (`Meta.DisplayImageSource`)

The logo (`sigilmark.png`) is CC0 1.0 (Ltgnetwork). See `LICENSE-logo.txt`.
