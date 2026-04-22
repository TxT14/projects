---
name: tldr
description: Vat tekst, documenten of webpagina's razendsnel samen met het /tldr commando. Gebruik deze skill altijd wanneer de gebruiker /tldr typt, vraagt om een samenvatting, iets wil "tldr-en", of zegt "kort samenvatten", "wat staat hier in", "geef me de essentie" — ook zonder het /tldr commando. Ondersteunt geplakte tekst, geüploade bestanden (PDF, Word) en weblinks.
---

# /tldr Skill

Vat content razendsnel samen in het Nederlands, tenzij de gebruiker iets anders aangeeft.

## Wanneer triggeren

- Gebruiker typt `/tldr` (met of zonder content erachter)
- Gebruiker vraagt om een samenvatting, de kern, de essentie
- Gebruiker zegt "wat staat hier?", "kort samenvatten", "geef me de highlights"

## Inputvormen

### 1. Tekst geplakt in de chat
Gebruik de tekst direct. Geen extra stappen nodig.

### 2. Geüpload bestand (PDF of Word)
- Lees eerst `/mnt/skills/public/file-reading/SKILL.md` om de juiste leesmethode te bepalen
- Extraheer de tekst en vat samen

### 3. Webpagina (link)
- Gebruik de browser/navigate tool om de pagina te openen
- Gebruik `get_page_text` om de inhoud te lezen
- Vat de inhoud samen (negeer navigatie, advertenties, footers)

## Outputformaat

Geen menu, geen vragen — gewoon direct samenvatten.

- **Standaard:** 3 tot 6 zinnen in vloeiend Nederlands
- **"kort"** in het bericht → 1 à 2 zinnen
- **"lang"** in het bericht → uitgebreidere samenvatting, 8-10 zinnen
- **"engels" / "english"** in het bericht → output in het Engels

## Opmaak

Gebruik altijd deze structuur:

```
**TL;DR**
[samenvatting hier]
```

Houd het scherp, concreet en to-the-point. Geen wollige taal. Geen herhaling. Geen onnodige intro's zoals "Dit artikel gaat over...".

## Voorbeelden

**Input:** `/tldr [lange tekst over klimaatverandering]`
**Output:**
> **TL;DR**
> - CO₂-uitstoot stijgt nog steeds wereldwijd
> - Zeespiegel stijgt sneller dan verwacht
> - Overheden missen klimaatdoelen uit Parijs-akkoord
> - Hernieuwbare energie groeit, maar niet snel genoeg

**Input:** `/tldr 1 zin [artikel]`
**Output:**
> **TL;DR**
> De aarde warmt sneller op dan verwacht en overheden doen te weinig.

## Taal

- Standaard via het keuzemenu
- Kan ook direct meegegeven worden: "in het Engels", "English please", `/tldr en`