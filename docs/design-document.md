# Pokémon Qbone - Pokéliga Edition: Designdokument

**Versjon:** 1.0  
**Dato:** 4. november 2025  
**Forfatter:** Robstad Interactive Solutions (R-I&S)  
**Status:** Living Document - Under kontinuerlig utvikling

---

## 1. Overordnet Visjon

### 1.1 Konsept

Pokémon Qbone - Pokéliga Edition er et ROM-hack basert på Pokémon FireRed/Emerald som transplanterer den klassiske Pokémon-opplevelsen til den virkelige geografien i Vennesla, Norge. Spillet kombinerer nostalgisk gameplay med lokal identitet, historiske referanser og humoristiske elementer.

### 1.2 Målgruppe

- **Primær:** Pokémon-fans fra Vennesla-området (15-35 år)
- **Sekundær:** ROM-hacking entusiaster
- **Tertiær:** Norske Pokémon-spillere generelt

### 1.3 Kjerneverdier

1. **Autentisitet** - Tro mot virkelig geografi og lokale referanser
2. **Nostalgi** - Ekte Gen 3 Pokémon-følelse
3. **Humor** - Lekent og underholdende uten å være respektløst
4. **Kvalitet** - Profesjonell utførelse og polert gameplay

---

## 2. Spillverden

### 2.1 Geografisk Grunnlag

Spillverdenen er basert på faktisk geografi fra Vennesla kommune og omkringliggende områder.

#### Hovedområder

| Område | Virkelig Lokasjon | Spillfunksjon | Nivå |
|--------|-------------------|---------------|------|
| **Vennesla By** | Vennesla sentrum | Startby, PokéCenter, Gym #1 | 1-10 |
| **Venneslavegen** | Venneslavegen 276 | Spillerens hjem, startpunkt | 1-5 |
| **Hunsfoss** | Hunsfoss industriområde | Industriby, Gym #2 | 10-20 |
| **Øvrebø** | Øvrebø | Landlig område, gårder | 15-25 |
| **Grovane** | Grovane skog | Skogsområde, ville Pokémon | 20-30 |
| **Otra** | Otra elv | Vannrute, fiske-spot | 25-35 |
| **Kilefjorden** | Kilefjorden | Kystområde, surfing | 30-40 |
| **Kristiansand** | Kristiansand by | Storby, Pokémon League | 40-50 |

### 2.2 Startlokasjon: Venneslavegen 276

**Beskrivelse:** Et typisk norsk enebolig-hjem med moderne fasiliteter.

#### Interiør Layout

**Første etasje:**
- Entré
- Stue med TV (fungerer som PC)
- Kjøkken
- Trapp til andre etasje

**Andre etasje:**
- Spillerens rom (startpunkt)
- Foreldres soverom
- Bad

#### Eksteriør

- Hage med gress (første wilde Pokémon-encounter)
- Innkjørsel
- Postkasse
- Gate mot Venneslavegen

### 2.3 Vennesla By (Startby)

**Funksjoner:**
- PokéCenter (gratis healing)
- PokéMart (grunnleggende items)
- Gym #1 (Normal-type)
- Olaf's hus (tutorial NPC)
- Bibliotek (lore og tips)
- Bussholdeplass (fast travel senere)

---

## 3. Karakterer

### 3.1 Hovedkarakter: Preben

**Alder:** 14 år  
**Hjemby:** Vennesla  
**Bakgrunn:** En vanlig ungdom fra Vennesla som drømmer om å bli Pokémon-mester

**Utseende:**
- Moderne norsk ungdom
- Vinterjakke (norsk klima)
- Ryggsekk
- Sprite-design: Tilpasset Gen 3-stil

**Personlighet:**
- Nysgjerrig og eventyrlysten
- Respektfull overfor naturen
- Litt naiv, men lærer underveis

### 3.2 Viktige NPCs

#### Olaf (Første NPC)

**Rolle:** Nabo, mentor, guide  
**Alder:** ~60 år  
**Personlighet:** Vennlig, erfaren, litt eksentrisk

**Funksjon:**
- Introduserer spilleren til Pokémon-verden
- Gir første tutorial
- Recurring character gjennom spillet
- Gir tips og råd

**Dialog-eksempel:**
```
"Hei Preben! Så bra å se deg ute i frisk luft!
Har du hørt om Pokémon? Fantastiske skapninger
som lever i harmoni med naturen her i Vennesla.
Kom, jeg skal vise deg noe spennende!"
```

#### Professor Bjørk (Pokémon Professor)

**Rolle:** Lokal Pokémon-forsker  
**Lokasjon:** Forskningslaboratorium i Vennesla sentrum  
**Spesialitet:** Norske Pokémon-variasjoner og økologi

**Funksjon:**
- Gir spilleren første Pokémon
- Gir Pokédex
- Forskningsoppdrag gjennom spillet

#### Rival: Magnus

**Rolle:** Barndomsvenn og rival  
**Personlighet:** Konkurranselysten men vennlig  
**Pokémon:** Starter med motsatt type av spilleren

**Kamper:**
1. Første kamp: Rett etter første Pokémon (nivå 5)
2. Andre kamp: Ved Hunsfoss (nivå 15)
3. Tredje kamp: Før Gym #4 (nivå 28)
4. Finale: Før Elite Four (nivå 55)

### 3.3 Gym Leaders

#### Gym #1: Vennesla - Normal-type
**Leader:** Kari  
**Tema:** Allsidighet og grunnleggende strategi  
**Badge:** Vennesla-merket  
**Team:** Rattata (Lv.8), Meowth (Lv.10)

#### Gym #2: Hunsfoss - Steel-type
**Leader:** Bjørn  
**Tema:** Industri og styrke  
**Badge:** Stål-merket  
**Team:** Magnemite (Lv.16), Aron (Lv.18)

*(Flere gyms under planlegging)*

---

## 4. Gameplay

### 4.1 Starter Pokémon

Spilleren velger mellom tre starter Pokémon hos Professor Bjørk:

1. **Treecko** (Grass) - God for nybegynnere
2. **Torchic** (Fire) - Balansert
3. **Mudkip** (Water) - Offensiv

**Rationale:** Bruker standard Gen 3 starters for kompatibilitet, men kan senere legge til regionale varianter.

### 4.2 Pokémon Encounters

#### Venneslavegen-området (Rute 1)
- Pidgey (50%)
- Rattata (30%)
- Zigzagoon (15%)
- Taillow (5%)

#### Grovane Skog
- Wurmple (30%)
- Poochyena (25%)
- Seedot (20%)
- Shroomish (15%)
- Slakoth (10%)

*(Komplette encounter-tabeller under utvikling)*

### 4.3 Pokéliga-System

**Konsept:** Et lokalt turneringssystem parallelt med Gym-systemet.

**Struktur:**
- Månedlige turneringer i Vennesla By
- Rangering basert på seire
- Spesielle premier og Pokémon
- Storyline-integrasjon

**Turneringstyper:**
- Single Battle
- Double Battle
- Rotation Battle (senere)

### 4.4 Spesielle Features

#### Norsk Vær-system
- Realistisk norsk klima (mye regn!)
- Sesongvariasjoner
- Påvirker Pokémon-spawns

#### Lokale Events
- 17. mai-feiring (spesiell event)
- Julemarked (vinter-event)
- Sommerfestival (sommer-event)

#### Dialekt-variasjoner
- NPCs snakker med lokal dialekt
- Autentiske uttrykk og vendinger
- Bokmål som hovedspråk med dialektinnslag

---

## 5. Storyline

### 5.1 Akt 1: Begynnelsen (Nivå 1-15)

**Startpunkt:** Preben våkner i sitt rom på Venneslavegen 276.

**Hovedhendelser:**
1. Møter Olaf utenfor huset
2. Introduksjon til Pokémon-konseptet
3. Besøk til Professor Bjørk
4. Får første Pokémon og Pokédex
5. Første rival-kamp mot Magnus
6. Utforsker Vennesla By
7. Første Gym-kamp mot Kari

**Mål:** Etablere spillverden og grunnleggende mekanikk.

### 5.2 Akt 2: Utforskning (Nivå 15-30)

**Fokus:** Utforske Vennesla-området og omkringliggende byer.

**Hovedhendelser:**
1. Reise til Hunsfoss
2. Møte med Team Kaos (antagonister)
3. Gym #2-4
4. Introduksjon til Pokéliga-systemet
5. Første større storyline-konflikt

**Mål:** Utvide spillverden og introdusere antagonister.

### 5.3 Akt 3: Konflikt (Nivå 30-45)

**Fokus:** Team Kaos' planer truer Vennesla-området.

**Hovedhendelser:**
1. Team Kaos' base oppdages
2. Legendary Pokémon-subplot
3. Gym #5-7
4. Allianser med andre trenere
5. Klimaks-kamp mot Team Kaos

**Mål:** Hovedkonflikt og dramatisk høydepunkt.

### 5.4 Akt 4: Mesterskapet (Nivå 45-60)

**Fokus:** Reise til Pokémon League og bli mester.

**Hovedhendelser:**
1. Gym #8
2. Victory Road
3. Elite Four
4. Champion-kamp
5. Post-game innhold

**Mål:** Klassisk Pokémon-avslutning med lokalt twist.

---

## 6. Antagonister

### 6.1 Team Kaos

**Konsept:** En organisasjon som vil utnytte Pokémon for profitt.

**Leder:** Direktør Svendsen  
**Mål:** Industrialisere Pokémon-fangst for eksport  
**Tema:** Grådighet vs. naturvern

**Grunts:**
- Uniform: Svarte dresser med Team Kaos-logo
- Pokémon: Poison og Dark-types
- Personlighet: Kyniske, men ikke onde

**Storyline-rolle:**
- Første møte: Hunsfoss (Akt 2)
- Hovedkonflikt: Akt 3
- Oppløsning: Slutten av Akt 3

---

## 7. Teknisk Design

### 7.1 Base ROM

**Valg:** Pokémon FireRed (USA)  
**Rationale:**
- Stabil decomp-base
- God dokumentasjon
- Stort community
- Kompatibel med moderne verktøy

### 7.2 Kartdesign-prinsipper

1. **Autentisitet:** Basert på virkelig geografi
2. **Gameplay-flow:** Logisk progresjon
3. **Utforskning:** Belønner nysgjerrighet
4. **Tilgjengelighet:** Tydelig navigasjon

### 7.3 Sprite-stil

**Retningslinjer:**
- Gen 3-kompatibel stil
- 64x64 pixels for overworld sprites
- 16-fargers palett
- Norsk estetikk (klær, bygninger)

### 7.4 Lyddesign

**Musikk:**
- Remixes av klassiske Pokémon-temaer
- Norsk folkemusikk-inspirasjon for spesielle områder
- Dynamisk musikk basert på lokasjon

**Lydeffekter:**
- Standard Gen 3-effekter
- Egne effekter for spesielle events

---

## 8. Fremdriftsplan

### Fase 1: Fundamentering (Måned 1-2)
- ✅ Prosjektstruktur
- ✅ Dokumentasjon
- ⏳ Decomp-integrasjon
- ⏳ Build-system

### Fase 2: Prototype (Måned 3-4)
- ⏳ Første kart (Venneslavegen 276)
- ⏳ Første NPCs
- ⏳ Grunnleggende gameplay
- ⏳ Testing

### Fase 3: Innholdsutvikling (Måned 5-8)
- ⏳ Alle hovedkart
- ⏳ Alle NPCs og dialog
- ⏳ Storyline-implementering
- ⏳ Pokéliga-system

### Fase 4: Polering (Måned 9-10)
- ⏳ Bug-fixing
- ⏳ Balansering
- ⏳ Grafisk polering
- ⏳ Lydimplementering

### Fase 5: Release (Måned 11-12)
- ⏳ Beta-testing
- ⏳ Final bug-fixes
- ⏳ Dokumentasjon
- ⏳ Offentlig release

---

## 9. Referanser og Inspirasjon

### Pokémon ROM-hacks
- Pokémon Crystal Clear
- Pokémon Gaia
- Pokémon Unbound

### Lokale Referanser
- Vennesla kommunes historie
- Lokal geografi og landemerker
- Kulturelle tradisjoner

### Tekniske Ressurser
- pokeemerald decomp-dokumentasjon
- PokéCommunity ROM-hacking forum
- Porymap-dokumentasjon

---

## 10. Vedlegg

### 10.1 Ordliste

- **Decomp:** Decompilation - rekonstruert kildekode
- **ROM-hack:** Modifisert versjon av original spill
- **Tileset:** Sett med grafikk-tiles for kart
- **Sprite:** Grafikk for karakterer og Pokémon
- **NPC:** Non-Player Character

### 10.2 Kontaktinformasjon

**Prosjektleder:** Preben Robstad  
**Organisasjon:** Robstad Interactive Solutions (R-I&S)  
**GitHub:** github.com/prebenR93/pokemon-qbone-pokeligaen

---

*Dette dokumentet oppdateres kontinuerlig etter hvert som prosjektet utvikler seg.*

**Siste oppdatering:** 4. november 2025
