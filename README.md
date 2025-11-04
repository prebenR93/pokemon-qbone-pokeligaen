# Pokémon Qbone - Pokéliga Edition

<div align="center">

![Project Status](https://img.shields.io/badge/status-in%20development-yellow)
![License](https://img.shields.io/badge/license-MIT-blue)
![Platform](https://img.shields.io/badge/platform-Game%20Boy%20Advance-red)

**Et lokaltilpasset Pokémon-spill basert på Vennesla**

*Utviklet av Robstad Interactive Solutions (R-I&S)*

</div>

---

## 📖 Om Prosjektet

**Pokémon Qbone - Pokéliga Edition** er et ambisiøst ROM-hacking prosjekt som tar klassisk Pokémon-gameplay og transplanterer det til den virkelige geografien i Vennesla, Norge. Spillet kombinerer nostalgisk Pokémon-mekanikk med lokal identitet, humor og historiske referanser.

### Kjernevisjon

Spillet starter i huset på **Venneslavegen 276**, hvor spilleren møter **Olaf** som første NPC. Derfra utfolder eventyret seg gjennom et detaljert kart basert på virkelig geografi, med kjente landemerker, bygninger og steder fra Vennesla-området.

### Tonalitet

- **Nostalgisk**: Ekte Pokémon-følelse fra Gen 3-æraen
- **Lokal identitet**: Gjenkjennelige steder og referanser
- **Humoristisk**: Litt rampete, men respektfull
- **Historisk**: Autentiske detaljer fra området

---

## 🎮 Spillfunksjoner

### Planlagte Features

- ✅ **Vennesla-basert verdenskart** med autentisk geografi
- ✅ **Lokale landemerker** som gyms og viktige lokasjoner
- ✅ **Egenutviklede NPCs** basert på lokale karakterer
- ✅ **Custom storyline** tilpasset Vennesla-settingen
- ✅ **Pokéliga-system** for konkurranser og turneringer
- ✅ **Norsk lokalisering** med dialektinnslag
- ✅ **Custom sprites og tilesets** for autentisk atmosfære

### Tekniske Features

- Basert på **Pokémon FireRed/Emerald** decomp-prosjekt
- Moderne ROM-hacking med full kildekode-tilgang
- Kompilerbar med DevkitARM
- Kompatibel med mGBA og andre moderne emulatorer
- Git-basert versjonskontroll for samarbeid

---

## 🗺️ Kartdesign

### Startområde: Venneslavegen 276

Spillerens hjem og startpunkt for eventyret. Huset er detaljert modellert etter den virkelige lokasjonen.

**Første NPC:** Olaf  
**Første rute:** Ut fra huset og mot sentrum

### Planlagte Lokasjoner

1. **Vennesla sentrum** - Hovedby med PokéCenter og Mart
2. **Hunsfoss** - Industriområde med spesielle encounters
3. **Øvrebø** - Landlig område med gårder
4. **Grovane** - Skogsområde med ville Pokémon
5. **Otra** - Elv med vannbaserte Pokémon

*(Flere lokasjoner under planlegging)*

---

## 👥 Karakterer

### Hovedkarakter: Preben

Spillerens avatar, en ung trener fra Vennesla som starter sitt Pokémon-eventyr.

### Viktige NPCs

- **Olaf** - Første NPC, veileder og nabo
- *(Flere karakterer under utvikling)*

---

## 🛠️ Teknisk Informasjon

### Basert på

- **Decomp-prosjekt**: pokeemerald/pokefirered
- **Base ROM**: Pokémon FireRed (USA)
- **Språk**: C (decomp), Assembly (patches)

### Utviklingsverktøy

- **Kartredigering**: Porymap
- **Sprite-redigering**: Aseprite, GIMP
- **Emulator**: mGBA
- **Kompilering**: DevkitARM, Make
- **Versjonskontroll**: Git, GitHub

### Systemkrav for Utvikling

```bash
# Linux/macOS
sudo apt-get install build-essential binutils-arm-none-eabi git
# DevkitARM installasjon kreves

# Windows
# Installer DevkitPro med DevkitARM
# Git for Windows
```

---

## 🚀 Kom i Gang

### For Spillere

*(Kommer snart - første playable build under utvikling)*

### For Utviklere

```bash
# Klon repositoriet
git clone https://github.com/prebenR93/pokemon-qbone-pokeligaen.git
cd pokemon-qbone-pokeligaen

# Installer avhengigheter (se docs/setup.md)

# Kompiler ROM
make

# Test i emulator
mgba pokemon-qbone.gba
```

---

## 📁 Prosjektstruktur

```
pokemon-qbone-pokeligaen/
├── README.md                 # Denne filen
├── LICENSE                   # Lisensinformasjon
├── Makefile                  # Build-system
├── docs/                     # Dokumentasjon
│   ├── design-document.md    # Designdokument
│   ├── technical-spec.md     # Teknisk spesifikasjon
│   ├── setup.md              # Oppsettguide
│   └── progress-log.md       # Fremgangssporing
├── src/                      # Kildekode
│   ├── maps/                 # Kartdata
│   ├── scripts/              # Event scripts
│   └── pokemon/              # Pokémon-data
├── assets/                   # Spillressurser
│   ├── maps/                 # Kartfiler (Porymap)
│   ├── sprites/              # Sprite-grafikk
│   ├── tilesets/             # Tileset-grafikk
│   └── audio/                # Lydeffekter og musikk
├── data/                     # Spilldata
│   ├── vennesla-locations.json  # Lokasjonsdatabase
│   ├── npc-data.json         # NPC-informasjon
│   └── pokemon-encounters.json  # Encounter-tabeller
├── tools/                    # Utviklingsverktøy
│   └── map-converter/        # Verktøy for kartkonvertering
└── build/                    # Kompilerte filer (gitignored)
```

---

## 📊 Utviklingsstatus

### Nåværende Fase: **Fundamentering**

| Komponent | Status | Fremgang |
|-----------|--------|----------|
| Prosjektstruktur | 🟡 I gang | 30% |
| Dokumentasjon | 🟡 I gang | 20% |
| Kartdesign | 🔴 Planlegging | 5% |
| Sprite-utvikling | 🔴 Ikke startet | 0% |
| Decomp-integrasjon | 🔴 Ikke startet | 0% |
| Build-system | 🔴 Ikke startet | 0% |
| Testing | 🔴 Ikke startet | 0% |

**Samlet fremgang:** ~8%

---

## 🤝 Bidra

Dette er et aktivt utviklingsprosjekt. Bidrag er velkomne!

### Hvordan bidra

1. Fork repositoriet
2. Opprett en feature branch (`git checkout -b feature/amazing-feature`)
3. Commit endringene dine (`git commit -m 'Add amazing feature'`)
4. Push til branchen (`git push origin feature/amazing-feature`)
5. Åpne en Pull Request

### Bidragsområder

- 🗺️ Kartdesign og lokasjonsbeskrivelser
- 🎨 Sprite-kunst og grafikk
- 💬 Dialog og storyline-skriving
- 🐛 Bug-testing og rapportering
- 📖 Dokumentasjon og oversettelse
- 🔧 Teknisk utvikling og optimalisering

---

## 📜 Lisens

Dette prosjektet er lisensiert under MIT License - se [LICENSE](LICENSE) filen for detaljer.

**Viktig:** Dette er et fan-made prosjekt. Pokémon og alle relaterte varemerker tilhører Nintendo, Game Freak og The Pokémon Company. Dette prosjektet er ikke kommersielt og er laget utelukkende for utdannings- og underholdningsformål.

---

## 🔗 Lenker

- **Hovedprosjekt**: [Robstad Interactive Solutions](https://github.com/prebenR93)
- **mGBA Emulator**: [mgba.io](https://mgba.io/)
- **Pokémon Decomp**: [pret/pokeemerald](https://github.com/pret/pokeemerald)
- **Porymap**: [porymap.github.io](https://porymap.github.io/)

---

## 📞 Kontakt

**Prosjektleder:** Preben Robstad  
**Organisasjon:** Robstad Interactive Solutions (R-I&S)  
**GitHub:** [@prebenR93](https://github.com/prebenR93)

---

## 🙏 Takk til

- **pret** for pokeemerald decomp-prosjektet
- **Pokémon ROM-hacking community** for verktøy og ressurser
- **mGBA-teamet** for den utmerkede emulatoren
- **Vennesla kommune** for inspirasjon og geografi

---

<div align="center">

**Laget med ❤️ i Vennesla**

*"Gotta map 'em all!"*

</div>
