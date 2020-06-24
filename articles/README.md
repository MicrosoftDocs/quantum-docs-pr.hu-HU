# <a name="articles"></a>Cikkek

Ebben a könyvtárban megtalálja a Quantum Development Kit dokumentációjának cikkeit. Ez a könyvtár a következőket tartalmazza:

- **Cikkek könyvtárai**: tartalmazza a dokumentáció egyes szakaszainak cikkeit. Ezekben a címtárakban a következő tartalmak találhatók:
  
  - Minden könyvtár tartalmaz egy `toc.yml` fájlt, amely megjeleníti a könyvtár tartalmát a fő tartalomjegyzékben (TOC).
  - Markdown cikkek, amelyek tartalmazzák a dokumentációt. A cikkeknek követniük kell a [Microsoft docs közreműködői útmutató](https://docs.microsoft.com/en-us/contribute/)útmutatásait.
  - Cikkek alkönyvtárai. Ezeknek az alkönyvtáraknak is tartalmazniuk kell a saját `toc.yml` fájljaikat.

> :p encil: Bár lehetséges, hogy a `*.md` fájlokat közvetlenül a szülő fájlban tekinti át `TOC.yml` , hogy a megrendelt dolgok megmaradjanak, csak az `toc.yml` aktuális címtárból.

- Tartalomjegyzék- ** `TOC.yml` fájl**: ebben a FÁJLBAN a webhely tartalomjegyzékének szakaszai szerepelnek az `toc.yml` egyes szakaszok könyvtárának fő fájljára mutató hivatkozással együtt.
- **`index.yml`** YAML a dokumentáció kezdőlapjának konfigurációjával.
- **`\media`**: A dokumentációban használt összes rendszerkép tárolására szolgáló könyvtár. Tartalmaz egy `\media\src` alkönyvtárat, amely a lemezképek forrásfájljait tárolja.
- **Licencfájl**: jogi licenceket tartalmazó fájlok
- **Technikai fájlok**: makrókat és metaadatokat tartalmazó fájlok.

## <a name="guidelines"></a>Irányelvek

Néhány általános útmutató a címtár a közreműködők szervezetével kapcsolatban:

- Minden címtárnak vagy alkönyvtárnak tartalmaznia kell a saját `toc.yml` fájlját, amelyben az azonos szintű cikkek, illetve a `toc.yml` hozzá tartozó alárendelt könyvtárak fájljai vannak.
- A tárház könyvtárainak Szervezetének a lehető legpontosabbnak kell lennie a dokumentációs webhely tartalomjegyzékének szervezete számára.
- Az összes lemezképet a cikkek mappában kell tárolni, `articles\media` és nem.
- A cikkek címeinek, a TARTALOMJEGYZÉKben szereplő névnek és a metaadatok *UID* azonosítójának a lehető legpontosabbnak kell lennie, és egyértelműen a Markdown-dokumentum H1-fejlécét jelöli.

## <a name="adding-images"></a>Képek hozzáadása

A képek sötét módban való megjelenítéséhez a fóliákat el kell kerülni.
- A `*.jpg` fájlok esetében semmit nem kell tennie, mivel a fájlformátum nem támogatja az átlátszó elemeket.
- A `*.png` fájlok esetében fehér hátteret kell hozzáadnia, vagy az alfa-csatorna értékét 100-ra kell módosítania. Ezt a Windowsban a legegyszerűbben úgy teheti meg, ha megnyitja a fájlt a Paintben és a mentésben, felülírja az eredeti fájlt.
- A `*.svg` fájlokhoz hozzá kell adnia egy fehér téglalapot a legalacsonyabb rétegben. Ezt az Inkscape használatával teheti meg:
  - Nyissa meg az `*.svg` fájlt.
  - Válassza ki a négyzet-készítő eszközt, és rajzoljon egy fehér téglalapot az eredeti ábra fölé.
  - Kattintson a sötét nyílra, vagy nyomja le az F1 billentyűt, és válassza ki az "objektumok kiválasztása és átalakítása" eszközt.
  - A négyszög kijelölése után kattintson az "alsó kijelölés az aljáig" elemre.
  - Állítsa be a téglalapot az egérrel vagy a nyílbillentyűk használatával.
