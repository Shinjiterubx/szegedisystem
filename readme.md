# Szegedisystem – Portfólió oldal dokumentáció

## Mi ez?

Egy egyoldalas (single-page), retro-futurisztikus **portfólió weboldal** Szegedi Tamás full-stack fejlesztő számára. A látványvilág fő eleme egy egyedi, canvas alapú **ASCII-stílusú 3D városrenderelő**, ami a háttérben egy animált, éjszakai, "cyberpunk" hangulatú várost jelenít meg — épületekkel, autó- és vonatforgalommal, csillagokkal, hullócsillagokkal, sőt egy opcionális Scarface-easter egg léghajóval is.

A tartalom öt szekcióra tagolódik: `Rólam`, `Projektek`, `Stack`, `Kapcsolat`, plusz egy hero (nyitó) szekció.

## Fő funkciók

- **Egyedi 3D → ASCII renderer**: saját írású, könyvtár nélküli canvas motor, ami 3D koordinátákat vetít karakteres "pixelekre" (nincs Three.js vagy más grafikus lib, minden vanilla JS-ben, mátrix-transzformációkkal és saját kamera-rendszerrel).
- **Boot-képernyő animáció**: BIOS-szerű indítóképernyő gépelős szöveggel, ami csak az első látogatáskor fut le (session storage alapú).
- **Kétnyelvű (HU/EN) felület**: teljes i18n megoldás `data-i18n` attribútumokkal, `localStorage`-ben mentett nyelvi preferenciával.
- **Scroll-vezérelt kamera**: a görgetési pozíció alapján a 3D kamera különböző "kulcspontok" (KEYS) között interpolál a városban.
- **Interaktív easter egg**: kapcsolható "Scarface reference" gomb, ami egy repülő léghajót jelenít meg forgó neon szöveggel ("THE WORLD IS YOURS").
- **Reszponzív, akadálymentességi alapokkal**: `prefers-reduced-motion` támogatás (statikus render mozgás helyett), fókusz-stílusok, szemantikus HTML.
- **CRT/scanline vizuális effekt** és üveg-panel (glassmorphism) design a tartalmi blokkokon.

## Használt technológiák

| Terület | Technológia |
|---|---|
| Struktúra | Natív HTML5 |
| Stílus | Natív CSS3 (CSS custom properties, `backdrop-filter`, `clamp()`, media query-k) |
| Logika / animáció | Vanilla JavaScript (ES6+, IIFE modul, `requestAnimationFrame`) |
| Grafika | Canvas 2D API — saját 3D→2D projekciós és ASCII-shading motor |
| Betűtípusok | Google Fonts: `VT323` (kijelző/cím), `IBM Plex Mono` (törzsszöveg) |
| Perzisztencia | `localStorage` (nyelv, easter egg állapot), `sessionStorage` (boot animáció egyszeri lefutása) |
| Egyéb | `IntersectionObserver` (panel-megjelenési animációk), saját pszeudo-random generátor (mulberry32) determinisztikus városgeneráláshoz |

Külső keretrendszer vagy build-eszköz **nincs** — az oldal egyetlen, önmagában futtatható `.html` fájl, külső függőség csak a Google Fonts betöltés.

## Készítés

A oldal kódja **Claude Fable 5**-tel készült.
