# Pokémon Qbone - Pokéliga Edition: Teknisk Spesifikasjon

**Versjon:** 1.0  
**Dato:** 4. november 2025  
**Forfatter:** Robstad Interactive Solutions (R-I&S)

---

## 1. Systemarkitektur

### 1.1 Overordnet Struktur

```
┌─────────────────────────────────────────┐
│         Pokémon Qbone ROM               │
│  (Kompilert .gba-fil)                   │
└─────────────────────────────────────────┘
                 ▲
                 │
┌─────────────────────────────────────────┐
│      Build System (Make)                │
│  - Kompilering                          │
│  - Asset-integrasjon                    │
│  - Linking                              │
└─────────────────────────────────────────┘
                 ▲
                 │
┌─────────────────────────────────────────┐
│    Decomp Source Code (C)               │
│  - Game logic                           │
│  - Map data                             │
│  - Scripts                              │
└─────────────────────────────────────────┘
                 ▲
                 │
┌─────────────────────────────────────────┐
│    Assets & Data                        │
│  - Graphics (PNG)                       │
│  - Maps (Porymap)                       │
│  - Audio                                │
└─────────────────────────────────────────┘
```

### 1.2 Teknologistack

| Komponent | Teknologi | Versjon |
|-----------|-----------|---------|
| Base ROM | Pokémon FireRed (USA) | Rev 1.0 |
| Decomp | pokefirered | Latest |
| Språk | C, ARM Assembly | C99 |
| Compiler | DevkitARM | Latest |
| Build | GNU Make | 4.3+ |
| Kartredigering | Porymap | 5.4.0+ |
| Grafikk | PNG (indexed) | - |
| Versjonskontroll | Git | 2.40+ |
| Emulator (testing) | mGBA | 0.10+ |

---

## 2. Utviklingsmiljø

### 2.1 Systemkrav

#### Minimum
- **OS:** Linux, macOS, Windows 10+
- **RAM:** 4 GB
- **Disk:** 2 GB ledig
- **CPU:** Dual-core 2.0 GHz

#### Anbefalt
- **OS:** Linux (Ubuntu 22.04+)
- **RAM:** 8 GB
- **Disk:** 5 GB ledig
- **CPU:** Quad-core 3.0 GHz

### 2.2 Avhengigheter

#### Linux (Ubuntu/Debian)
```bash
sudo apt-get update
sudo apt-get install -y \
    build-essential \
    binutils-arm-none-eabi \
    git \
    libpng-dev \
    pkg-config \
    python3 \
    python3-pip
```

#### DevkitARM
```bash
# Følg instruksjoner på devkitpro.org
wget https://github.com/devkitPro/pacman/releases/latest/download/devkitpro-pacman.amd64.deb
sudo dpkg -i devkitpro-pacman.amd64.deb
sudo dkp-pacman -S gba-dev
```

#### Python-pakker
```bash
pip3 install pillow pyyaml
```

### 2.3 Oppsett

```bash
# Klon repositoriet
git clone https://github.com/prebenR93/pokemon-qbone-pokeligaen.git
cd pokemon-qbone-pokeligaen

# Initialiser submodules (hvis brukt)
git submodule update --init --recursive

# Sett miljøvariabler
export DEVKITPRO=/opt/devkitpro
export DEVKITARM=$DEVKITPRO/devkitARM
export PATH=$DEVKITARM/bin:$PATH

# Kompiler
make
```

---

## 3. Prosjektstruktur

### 3.1 Mappestruktur

```
pokemon-qbone-pokeligaen/
│
├── .git/                      # Git versjonskontroll
├── .github/                   # GitHub Actions CI/CD
│   └── workflows/
│       └── build.yml
│
├── src/                       # Kildekode
│   ├── main.c                 # Hovedinngang
│   ├── overworld.c            # Overworld-logikk
│   ├── battle/                # Kampsystem
│   ├── pokemon/               # Pokémon-data
│   ├── maps/                  # Kartdata (generert)
│   ├── scripts/               # Event scripts
│   └── data/                  # Spilldata
│       ├── trainers.c
│       ├── encounters.c
│       └── items.c
│
├── include/                   # Header-filer
│   ├── global.h
│   ├── constants/
│   └── structs/
│
├── asm/                       # Assembly-kode
│   ├── macros.inc
│   └── functions/
│
├── data/                      # Rå data-filer
│   ├── maps/                  # Porymap-prosjekt
│   │   ├── vennesla_by/
│   │   ├── venneslavegen_276/
│   │   └── layouts.json
│   ├── vennesla-locations.json
│   ├── npc-data.json
│   └── pokemon-encounters.json
│
├── assets/                    # Spillressurser
│   ├── graphics/
│   │   ├── tilesets/          # Tileset PNG-er
│   │   ├── sprites/           # Sprite PNG-er
│   │   │   ├── overworld/
│   │   │   ├── pokemon/
│   │   │   └── trainers/
│   │   └── ui/                # UI-grafikk
│   ├── audio/
│   │   ├── music/
│   │   └── sfx/
│   └── text/
│       └── dialog/
│
├── tools/                     # Utviklingsverktøy
│   ├── mapjson/               # Map JSON-parser
│   ├── gbagfx/                # Grafikk-konverter
│   ├── scaninc/               # Include-scanner
│   └── map-converter/         # Custom kartverktøy
│
├── build/                     # Kompilerte filer (gitignored)
│   ├── objects/
│   └── intermediate/
│
├── docs/                      # Dokumentasjon
│   ├── design-document.md
│   ├── technical-spec.md
│   ├── setup.md
│   └── progress-log.md
│
├── Makefile                   # Build-system
├── README.md                  # Hovedoversikt
├── LICENSE                    # Lisens
├── .gitignore                 # Git ignore-regler
└── pokemon-qbone.gba          # Kompilert ROM (gitignored)
```

### 3.2 Filtyper

| Filtype | Beskrivelse | Eksempel |
|---------|-------------|----------|
| `.c` | C kildekode | `overworld.c` |
| `.h` | C header-filer | `global.h` |
| `.s` | ARM Assembly | `functions.s` |
| `.inc` | Include-filer (ASM) | `macros.inc` |
| `.json` | Data-filer | `layouts.json` |
| `.png` | Grafikk (indexed) | `tileset.png` |
| `.bin` | Binære data | `audio.bin` |
| `.gba` | Kompilert ROM | `pokemon-qbone.gba` |

---

## 4. Build-system

### 4.1 Makefile-struktur

```makefile
# Hovedvariabler
ROM := pokemon-qbone.gba
ELF := $(ROM:.gba=.elf)
MAP := $(ROM:.gba=.map)

# Compiler
CC := arm-none-eabi-gcc
AS := arm-none-eabi-as
LD := arm-none-eabi-ld
OBJCOPY := arm-none-eabi-objcopy

# Flags
CFLAGS := -O2 -mthumb -mthumb-interwork -Wall -Werror
ASFLAGS := -mthumb -mthumb-interwork
LDFLAGS := -Map $(MAP)

# Source-filer
C_SRCS := $(wildcard src/*.c src/**/*.c)
ASM_SRCS := $(wildcard asm/*.s asm/**/*.s)

# Object-filer
C_OBJS := $(C_SRCS:.c=.o)
ASM_OBJS := $(ASM_SRCS:.s=.o)
OBJS := $(C_OBJS) $(ASM_OBJS)

# Hovedmål
all: $(ROM)

$(ROM): $(ELF)
	$(OBJCOPY) -O binary $< $@
	@echo "ROM kompilert: $(ROM)"

$(ELF): $(OBJS)
	$(LD) $(LDFLAGS) -o $@ $^

# Kompileringsregler
%.o: %.c
	$(CC) $(CFLAGS) -c $< -o $@

%.o: %.s
	$(AS) $(ASFLAGS) $< -o $@

# Utility-mål
clean:
	rm -f $(OBJS) $(ELF) $(MAP) $(ROM)

test: $(ROM)
	mgba $(ROM)

.PHONY: all clean test
```

### 4.2 Build-kommandoer

```bash
# Kompiler ROM
make

# Rens build-filer
make clean

# Kompiler og test
make test

# Parallel kompilering (raskere)
make -j$(nproc)

# Verbose output
make VERBOSE=1
```

### 4.3 CI/CD Pipeline

#### GitHub Actions Workflow

```yaml
name: Build ROM

on:
  push:
    branches: [ main, develop ]
  pull_request:
    branches: [ main ]

jobs:
  build:
    runs-on: ubuntu-latest
    
    steps:
    - uses: actions/checkout@v3
    
    - name: Install DevkitARM
      run: |
        wget https://github.com/devkitPro/pacman/releases/latest/download/devkitpro-pacman.amd64.deb
        sudo dpkg -i devkitpro-pacman.amd64.deb
        sudo dkp-pacman -Sy --noconfirm gba-dev
    
    - name: Build ROM
      run: |
        export DEVKITPRO=/opt/devkitpro
        export DEVKITARM=$DEVKITPRO/devkitARM
        make
    
    - name: Upload ROM artifact
      uses: actions/upload-artifact@v3
      with:
        name: pokemon-qbone-rom
        path: pokemon-qbone.gba
```

---

## 5. Kartutvikling

### 5.1 Porymap-integrasjon

**Porymap** er det primære verktøyet for kartutvikling.

#### Prosjektstruktur
```
data/maps/
├── layouts.json           # Layout-definisjoner
├── map_groups.json        # Kartgrupper
├── vennesla_by/
│   ├── map.json           # Kartdata
│   ├── scripts.inc        # Event scripts
│   └── text.inc           # Dialog
└── venneslavegen_276/
    ├── map.json
    ├── scripts.inc
    └── text.inc
```

#### Map JSON-format
```json
{
  "id": "MAP_VENNESLAVEGEN_276",
  "name": "Venneslavegen276",
  "layout": "LAYOUT_VENNESLAVEGEN_276",
  "music": "MUS_LITTLEROOT",
  "region_map_section": "MAPSEC_VENNESLA",
  "requires_flash": false,
  "weather": "WEATHER_RAIN",
  "map_type": "MAP_TYPE_TOWN",
  "allow_cycling": true,
  "allow_escaping": true,
  "allow_running": true,
  "show_map_name": true,
  "connections": [
    {
      "direction": "down",
      "offset": 0,
      "map": "MAP_VENNESLA_BY"
    }
  ],
  "object_events": [
    {
      "graphics_id": "OBJ_EVENT_GFX_OLAF",
      "x": 10,
      "y": 8,
      "elevation": 0,
      "movement_type": "MOVEMENT_TYPE_WANDER_AROUND",
      "script": "VenneslavegOlaf_EventScript"
    }
  ]
}
```

### 5.2 Tileset-utvikling

#### Tileset-spesifikasjoner
- **Format:** PNG (indexed color)
- **Palett:** 16 farger per tileset
- **Tile-størrelse:** 8x8 pixels
- **Tileset-størrelse:** Variabel (typisk 128x256 pixels)

#### Tileset-typer
1. **Primary:** Grunnleggende terreng (gress, vann, fjell)
2. **Secondary:** Bygninger, objekter, dekorasjoner

#### Eksempel-struktur
```
assets/graphics/tilesets/
├── primary/
│   ├── general.png        # Standard terreng
│   ├── vennesla.png       # Vennesla-spesifikk
│   └── general.pal        # Palett-fil
└── secondary/
    ├── buildings.png      # Bygninger
    ├── objects.png        # Objekter
    └── buildings.pal
```

### 5.3 Kartkonvertering

**Verktøy:** Custom Python-script for å konvertere OpenStreetMap-data.

```python
# tools/map-converter/osm_to_porymap.py
import json
import requests

def fetch_vennesla_data(bbox):
    """Hent OSM-data for Vennesla"""
    overpass_url = "http://overpass-api.de/api/interpreter"
    query = f"""
    [out:json];
    (
      way["building"]({bbox});
      way["highway"]({bbox});
      node["amenity"]({bbox});
    );
    out body;
    """
    response = requests.post(overpass_url, data={'data': query})
    return response.json()

def convert_to_porymap(osm_data):
    """Konverter OSM-data til Porymap-format"""
    # Implementering...
    pass
```

---

## 6. Grafikk-pipeline

### 6.1 Sprite-utvikling

#### Overworld Sprites
- **Størrelse:** 16x16 pixels (1 tile) eller 16x32 pixels (2 tiles)
- **Format:** PNG indexed
- **Palett:** 16 farger
- **Animasjon:** 3-4 frames per retning

#### Pokémon Sprites
- **Front sprite:** 64x64 pixels
- **Back sprite:** 64x64 pixels
- **Icon:** 32x32 pixels
- **Format:** PNG indexed
- **Palett:** 16 farger

#### Konvertering
```bash
# Konverter PNG til GBA-format
tools/gbagfx/gbagfx assets/graphics/sprites/olaf.png \
    -o build/sprites/olaf.4bpp \
    -palette assets/graphics/sprites/olaf.pal
```

### 6.2 Grafikk-organisering

```
assets/graphics/
├── tilesets/
│   ├── primary/
│   └── secondary/
├── sprites/
│   ├── overworld/
│   │   ├── npcs/
│   │   │   ├── olaf.png
│   │   │   └── olaf.pal
│   │   └── player/
│   ├── pokemon/
│   │   ├── front/
│   │   ├── back/
│   │   └── icons/
│   └── trainers/
└── ui/
    ├── textbox.png
    ├── menu.png
    └── battle_interface.png
```

---

## 7. Data-strukturer

### 7.1 Vennesla Locations

```json
{
  "locations": [
    {
      "id": "LOC_VENNESLAVEGEN_276",
      "name": "Venneslavegen 276",
      "type": "house",
      "coordinates": {
        "lat": 58.2794,
        "lon": 7.9669
      },
      "map_id": "MAP_VENNESLAVEGEN_276",
      "description": "Spillerens hjem, et typisk norsk enebolig.",
      "npcs": ["Olaf", "Mom"],
      "items": ["POTION"],
      "connections": ["LOC_VENNESLA_BY"]
    }
  ]
}
```

### 7.2 NPC Data

```json
{
  "npcs": [
    {
      "id": "NPC_OLAF",
      "name": "Olaf",
      "age": 60,
      "sprite": "OBJ_EVENT_GFX_OLAF",
      "personality": "friendly_mentor",
      "locations": [
        {
          "map": "MAP_VENNESLAVEGEN_276",
          "x": 10,
          "y": 8,
          "script": "VenneslavegOlaf_EventScript"
        }
      ],
      "dialog": {
        "first_meeting": "Hei Preben! Så bra å se deg ute i frisk luft!",
        "default": "Hvordan går det med Pokémon-treningen?",
        "after_gym1": "Gratulerer med gym-seieren!"
      }
    }
  ]
}
```

### 7.3 Encounter Tables

```json
{
  "encounters": [
    {
      "map": "MAP_ROUTE_1_VENNESLA",
      "type": "grass",
      "rate": 20,
      "slots": [
        {"species": "SPECIES_PIDGEY", "min_level": 2, "max_level": 4, "chance": 50},
        {"species": "SPECIES_RATTATA", "min_level": 2, "max_level": 4, "chance": 30},
        {"species": "SPECIES_ZIGZAGOON", "min_level": 3, "max_level": 5, "chance": 15},
        {"species": "SPECIES_TAILLOW", "min_level": 3, "max_level": 5, "chance": 5}
      ]
    }
  ]
}
```

---

## 8. Testing

### 8.1 Emulator-testing

**Primær emulator:** mGBA

```bash
# Test ROM
mgba pokemon-qbone.gba

# Med debugger
mgba-qt -g pokemon-qbone.gba
```

### 8.2 Automatisert testing

```python
# tests/test_maps.py
import pytest
from tools.mapjson import parse_map

def test_venneslavegen_276_exists():
    map_data = parse_map("data/maps/venneslavegen_276/map.json")
    assert map_data["id"] == "MAP_VENNESLAVEGEN_276"

def test_olaf_npc_present():
    map_data = parse_map("data/maps/venneslavegen_276/map.json")
    npcs = [obj for obj in map_data["object_events"] 
            if obj["graphics_id"] == "OBJ_EVENT_GFX_OLAF"]
    assert len(npcs) == 1
```

### 8.3 Testplan

| Test-type | Verktøy | Frekvens |
|-----------|---------|----------|
| Kompilering | Make | Hver commit |
| Emulator-test | mGBA | Daglig |
| Kart-validering | Python scripts | Per kart |
| Sprite-test | Visual inspection | Per sprite |
| Gameplay-test | Manual testing | Ukentlig |
| Performance | mGBA profiler | Månedlig |

---

## 9. Versjonskontroll

### 9.1 Git-strategi

**Branching-modell:** Git Flow

```
main (production)
├── develop (integration)
│   ├── feature/vennesla-map
│   ├── feature/olaf-npc
│   └── feature/gym-system
└── hotfix/critical-bug
```

### 9.2 Commit-konvensjoner

```
<type>(<scope>): <subject>

<body>

<footer>
```

**Typer:**
- `feat`: Ny feature
- `fix`: Bug-fix
- `docs`: Dokumentasjon
- `style`: Formatering
- `refactor`: Kode-refaktorering
- `test`: Testing
- `chore`: Vedlikehold

**Eksempel:**
```
feat(maps): Add Venneslavegen 276 starter house

- Created house interior layout
- Added Olaf NPC with dialog
- Implemented first tutorial sequence

Closes #12
```

### 9.3 .gitignore

```gitignore
# Build artifacts
*.o
*.elf
*.map
*.gba
build/

# IDE
.vscode/
.idea/
*.swp

# OS
.DS_Store
Thumbs.db

# Temp files
*.tmp
*.bak
*~
```

---

## 10. Performance-optimalisering

### 10.1 Kompileringsoptimalisering

```makefile
# Optimalisering-flags
CFLAGS := -O2 -mthumb -mthumb-interwork \
          -fomit-frame-pointer \
          -ffunction-sections \
          -fdata-sections

LDFLAGS := -Wl,--gc-sections
```

### 10.2 ROM-størrelse

**Mål:** < 16 MB (standard GBA ROM-størrelse)

**Strategier:**
- Komprimering av grafikk
- Effektiv data-strukturering
- Fjerne ubrukt kode

### 10.3 Runtime-performance

**Mål:** 60 FPS konstant

**Profileringsverktøy:**
- mGBA performance monitor
- Custom timing-kode

---

## 11. Sikkerhet og Backup

### 11.1 Versjonskontroll

- **GitHub:** Primær remote repository
- **Backup:** Ukentlig backup til ekstern disk
- **Releases:** Tagged releases for hver milestone

### 11.2 Asset-backup

```bash
# Backup-script
#!/bin/bash
DATE=$(date +%Y%m%d)
tar -czf backups/assets-$DATE.tar.gz assets/
```

---

## 12. Fremtidig Utvidelse

### 12.1 Planlagte Features

- **Multiplayer:** Link cable-emulering
- **Post-game:** Battle Frontier
- **DLC-områder:** Utvidelser til nye områder

### 12.2 Teknisk Gjeld

- Refaktorering av legacy-kode
- Forbedret dokumentasjon
- Automatiserte tester

---

## 13. Referanser

### 13.1 Dokumentasjon

- [pokeemerald decomp](https://github.com/pret/pokeemerald)
- [Porymap dokumentasjon](https://github.com/huderlem/porymap)
- [DevkitARM](https://devkitpro.org/)
- [GBA Programming](https://www.coranac.com/tonc/text/)

### 13.2 Community

- [PokéCommunity](https://www.pokecommunity.com/)
- [ROM Hacking Discord](https://discord.gg/romhacking)

---

*Dette dokumentet oppdateres etter hvert som tekniske beslutninger tas.*

**Siste oppdatering:** 4. november 2025
