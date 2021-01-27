---
title: Q# API-tervezési alapelvek
description: Q# API-tervezési alapelvek
author: cgranade
ms.author: chgranad
ms.date: 3/9/2020
ms.topic: contributor-guide
uid: microsoft.quantum.contributing.api-design
no-loc:
- Q#
- $$v
ms.openlocfilehash: 452b32141dc660acbe8ef28530f1430e5acff9aa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856699"
---
# <a name="no-locq-api-design-principles"></a>Q# API-tervezési alapelvek

## <a name="introduction"></a>Bevezetés

Nyelvként és platformként Q# lehetővé teszi a felhasználók számára a kvantum-alkalmazások írását, futtatását, megismerését és megismerését.
Ahhoz, hogy a felhasználók megtervezzék a Q# kódtárakat, az API-tervezési alapelveket követve elvégezheti a kialakítást, és segítheti a felhasználható könyvtárak létrehozását a Quantum fejlesztői közösség számára.
Ez a cikk felsorolja ezeket az alapelveket, és példákat mutat be arra, hogyan alkalmazhatja őket az API-k tervezésekor Q# .

> [!TIP]
> Ez egy meglehetősen részletes dokumentum, amely segítséget nyújt a függvénytár-fejlesztés és a részletes függvénytár-hozzájárulások létrehozásához.
> Valószínűleg hasznosnak találja a saját kódtárainak írásakor Q# , vagy ha nagyobb funkciókkal járul hozzá a [ Q# kódtárak tárházához](https://github.com/microsoft/QuantumLibraries).
>
> Ha szeretné megtudni, hogy miként járulhat hozzá általánosabban a Quantum Development Kit-hez, javasoljuk, hogy kezdje a [hozzájárulási útmutatóval](xref:microsoft.quantum.contributing).
> Ha többet szeretne megtudni a kód formázásának javasolt módjáról, érdemes lehet megtekinteni Q# a [stílusra vonatkozó útmutatót](xref:microsoft.quantum.contributing.style).

## <a name="general-principles"></a>Általános alapelvek

**Kulcs elve:** Tegye elérhetővé a kvantum-alkalmazásokra koncentráló API-kat.

- ✅**Válassza ki a műveletek és** függvények nevét, amelyek az algoritmusok és alkalmazások magas szintű szerkezetét tükrözik.
- ⛔️ **nem** tesz elérhetővé olyan API-kat, amelyek elsősorban az alacsony szintű megvalósítási részletekre összpontosítanak.

**Kulcs elve:** Az API-k tervezésének megkezdése minta-használati esetek használatával biztosíthatja, hogy az API-k könnyen használhatók legyenek.

- ✅**Győződjön meg** arról, hogy a nyilvános API-k minden összetevőjének van megfelelő használati esete, és nem kell megterveznie az összes lehetséges felhasználást a Start menüből.
    Másképpen fogalmazva, ne vezessen be nyilvános API-kat abban az esetben, ha azok hasznosak, de győződjön meg arról, hogy az API-k mindegyik része *konkrét* példát mutat be, amelyben hasznos lehet.

  *Példák:*
  - @"microsoft.quantum.canon.applytoeachca" felhasználható úgy, `ApplyToEachCA(H, _)` hogy a regisztereket egységes, a számos kvantum-algoritmusban közös feladatként készítse elő. Ugyanezt a műveletet számos más feladathoz is felhasználhatja előkészítési, numerikus és Oracle-alapú algoritmusokban.

- ✅A **brainstorming és** a workshop új API-ját úgy tervezze meg, hogy azok intuitívek legyenek, és megfeleljenek a javasolt használati eseteknek.

  *Példák:*
  - Vizsgálja \# meg az aktuális Q-kódot, hogy megtudja, hogyan egyszerűsíthető az új API-k és a meglévő implementációk tisztázása.
  - Tekintse át a javasolt API-terveket az elsődleges célközönségek képviselőivel.

**Kulcs elve:** Tervezzen API-kat az olvasható kódok támogatásához és ösztönzéséhez.

- ✅**Győződjön meg** arról, hogy a kód a tartományi szakértők és a nem szakértők számára is olvasható.
- ✅**Helyezze a** fókuszt az egyes műveletek és függvények hatására a magas szintű algoritmuson belül, a dokumentáció segítségével pedig szükség szerint illessze be a megvalósítás részleteit.
- ✅Ha alkalmazható **, kövesse a** közös [Q- \# stílus útmutatóját](xref:microsoft.quantum.contributing.style) .

**Kulcs elve:** Az API-k megtervezése stabil és a továbbítási kompatibilitás biztosítása érdekében.

- ✅A régi API- **k elavultak** legyenek, ha a változtatások megszakadnak.

- ✅**Olyan "** alátét" műveleteket és függvényeket adjon meg, amelyek lehetővé teszik, hogy a meglévő felhasználói kód megfelelően működjön az elavulás során.

  *Példák:*
  - Egy nevű művelet átnevezése során `EstimateExpectation`   `EstimateAverage` egy új műveletet kell meghívnia,   `EstimateExpectation` amely új néven hívja meg az eredeti műveletet, hogy a meglévő kód továbbra is megfelelően működjön.

- ✅**Használja az** @"microsoft.quantum.core.deprecated" attribútumot az elavultak a felhasználóval való kommunikációhoz.

- ✅ Egy művelet vagy függvény átnevezése **esetén adja meg** az új nevet karakterlánc-bemenetként `@Deprecated` .

- ⛔️ **ne** távolítsa el a meglévő függvényeket vagy műveleteket, ha az előzetes verziónál legalább hat hónapig elavult időszak van, vagy legalább két év a támogatott kiadásokhoz.

## <a name="functions-and-operations"></a>Függvények és műveletek

**Kulcs elve:** gondoskodjon arról, hogy minden függvény és művelet egyetlen jól meghatározott céllal legyen az API-n belül.

- ⛔️ **nem** tesznek elérhetővé több nem kapcsolódó feladatot végrehajtó függvényeket és műveleteket.

**Kulcs elve:** a lehető legtöbbször felhasználható és a jövőbeli igényeknek megfelelő tervezési funkciókat és műveleteket kell megtervezni.

- ✅A **tervezési függvények** és műveletek a más függvényekkel és műveletekkel is összehozhatók, mind UGYANABBAN az API-ban, mind a korábban meglévő könyvtárakban.

  *Példák:*
  - A @"microsoft.quantum.canon.delay" művelet minimális feltételezéseket biztosít a bemenetével kapcsolatban, így felhasználhatja bármelyik művelet alkalmazásait a Q# szabványos könyvtárban vagy a felhasználók által megadott módon.
    <!-- TODO: define bad example. -->

- ✅A művelet helyett kizárólag klasszikus logikai determinisztikus **teheti** elérhetővé.

  *Példák:*
  - Egy olyan alrutin, amely a lebegőpontos bemenetének négyzetes beírását is lehetővé teszi, determinisztikus módon, így nem műveletként kell a felhasználó számára elérhetőnek lennie `Squared : Double -> Double` `Square : Double => Double` . Ez lehetővé teszi, hogy a alrutin több helyen legyen meghívva (pl.: más funkciókon belül), és hasznos optimalizálási információkat biztosít a fordítónak, amely hatással lehet a teljesítményre és az optimalizálásokra.
  - `ForEach<'TInput, 'TOutput>('TInput => 'TOutput, 'TInput[]) => 'TOutput[]` és `Mapped<'TInput, 'TOutput>('TInput -> 'TOutput, 'TInput[]) -> 'TOutput[]` különbözik a megkötések tekintetében nyújtott garanciákkal; mindkettő különböző helyzetekben hasznos.
  - A Quantum Operations alkalmazást átalakító API-rutinok gyakran determinisztikus módon hajthatók végre, így olyan függvényként is elérhetők, mint a   `CControlled<'T>(op : 'T => Unit) => ((Bool, 'T) => Unit)` .

- ✅ Az egyes függvényekhez és műveletekhez az adott típus paramétereit igény szerint adja meg, és használja a bemeneti típust.

  *Példák:*
  - `ApplyToEach` a típusa `<'T>(('T => Unit), 'T[]) => Unit` nem a leggyakrabban használt alkalmazás típusa, hanem az adott típus `((Qubit => Unit), Qubit[]) => Unit` .

> [!TIP]
> Fontos, hogy előre jelezze a jövőbeli igényeket, de fontos, hogy konkrét problémák megoldására is szükség van a felhasználók számára.
> Ennek a kulcsfontosságú alapelveknek az alkalmazása ezért mindig alapos megfontolást és kiegyensúlyozást igényel az API-k "csak abban az esetben" való fejlesztése érdekében.

**Legfontosabb elv:** válassza a bemeneti és kimeneti típusok lehetőséget a kiszámítható, valamint a meghívásos művelet céljával kommunikáló függvények és műveletek számára.

- ✅ A rekord típusú típusokkal logikailag csoportosíthatja azokat a bemeneteket és kimeneteket, amelyek csak akkor jelentősek, ha azokat együtt tekintik. Ezekben az esetekben érdemes lehet felhasználó által definiált típust használni.

  *Példák:*
  - Előfordulhat, hogy egy másik függvény helyi minimális értékeinek kimenetére szolgáló függvénynek egy keresési időközt kell megadnia bemenetként, ami lehet `LocalMinima(fn : (Double -> Double), (left : Double, right : Double)) : Double` megfelelő aláírás.
  - A Machine learning-osztályozó a paraméter-átváltási technikával való kiszámításához szükséges műveletnek az áthelyezett és a nem áthelyezett paramétereket is fel kell vennie bemenetként. Ebben az esetben a `(unshifted : Double[], shifted : Double[])` megfelelőhöz hasonló bemenetnek kell lennie.

- ✅A bemeneti és kimeneti rekordok lévő **elemek sorrendje** konzisztens legyen a különböző függvények és műveletek között.

  *Példák:*
  - Ha két vagy több olyan függvényt vagy műveletet vizsgál, amelyek mindegyike elforgatási szöget és a célként megadott qubit bemenetként veszi figyelembe, ügyeljen arra, hogy mindegyik bemeneti rekordban azonos sorrendben legyenek rendezve. Ez inkább a és `ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl` `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)` a `ApplyRotation(target : Qubit, angle : Double) : Unit is Adj + Ctl` és a `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)` .

**Legfontosabb alapelv:** a Q \# nyelvi funkciókkal, például a részleges alkalmazásokkal jól használható tervezési függvények és műveletek.

- ✅A bemeneti rekordok **megrendelje** az elemeket úgy, hogy a leggyakrabban alkalmazott bemenetek először (pl.:, hogy a részleges alkalmazás a curry-hez hasonlóan működik).

  *Példák:*
  - Egy `ApplyRotation` lebegőpontos számot és egy qubit tartalmazó műveletet gyakran csak részben lehet a lebegőpontos bemenettel együtt alkalmazni, hogy először a típus bemenetét elvárt műveletekkel használják `Qubit => Unit` . Így a `operation ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl`
      a leghatékonyabban együttműködik a részleges alkalmazásokkal.
  - Ez az útmutató általában azt jelenti, hogy az összes klasszikus adatot a bemeneti rekordok összes qubits elé helyezi, de jó ítéletet használ, és megvizsgálja, hogyan hívják meg az API-t a gyakorlatban.

## <a name="user-defined-types"></a>User-Defined típusok

**Legfontosabb elv:** felhasználói típusok használata az API-k egyszerűbb és kényelmes használatának megkönnyítéséhez.

- ✅Az új, felhasználó által definiált típusok **bevezetésével** hasznos rövidítéseket biztosíthat a hosszú és/vagy bonyolult típusok számára.

  *Példák:*
  - Azokban az esetekben, amikor egy három qubit tömb bemenettel rendelkező Művelettípus általában bemenetként van megadva vagy kimenetként van visszaadva, egy UDT, például `newtype TimeDependentBlockEncoding = ((Qubit[], Qubit[], Qubit[]) => Unit is Adj + Ctl)`
      hasznos rövidítést tud nyújtani.

- ✅Az új, felhasználó által definiált **típusok bevezetése azt** jelzi, hogy egy adott alaptípust csak nagyon konkrét értelemben kell használni.

  *Példák:*
  - Egy olyan műveletet, amelyet kifejezetten olyan műveletként kell értelmezni, amely a klasszikus adatmennyiséget egy kvantum-regiszterbe kódolja, célszerű lehet egy felhasználó által definiált típussal megjelölni `newtype InputEncoder = (Apply : (Qubit[] => Unit))` .

- ✅Új, felhasználó által definiált típusokat **vezessen** be olyan névvel ellátott elemekkel, amelyek lehetővé teszik a későbbi bővíthetőséget (például: egy olyan eredmény-struktúra, amely további megnevezett elemeket tartalmazhat a jövőben).

  *Példák:*
  - Ha egy művelet `TrainModel` nagy számú konfigurációs beállítást tesz elérhetővé, ezeket a beállításokat új UDT teszik közzé,   `TrainingOptions` és egy új függvényt biztosítanak, amely   `DefaultTrainingOptions : Unit -> TrainingOptions` lehetővé teszi a felhasználók számára, hogy a TrainingOptions UDT értékeiben felülbírálják a meghatározott megnevezett elemeket, miközben továbbra is lehetővé teszik a könyvtár-fejlesztők számára, hogy szükség szerint

- ✅Megnevezett **elemek deklarálása** új, felhasználó által definiált típusokhoz, amelyekkel a felhasználóknak ismerniük kell a megfelelő rekord dekonstrukcióját.

  *Példák:*
  - Ha egy összetett számot képvisel a Polar dekompozícióban, inkább a következőhöz:   `newtype ComplexPolar = (Magnitude: Double, Argument: Double)`   `newtype ComplexPolar = (Double, Double)` .

**Legfontosabb alapelv:** a felhasználó által definiált típusok használata a kognitív terhelés csökkentése és a felhasználónak nem kell további fogalmakat és nómenklatúrát megtanulnia.

- ⛔️ **ne** vezessen be olyan felhasználó által definiált típusokat, amelyek megkövetelik a felhasználótól, hogy a kicsomagolási operátor () gyakori használatát igényli `!` , vagy amelyekhez gyakran több szintű kicsomagolásra van szükség. A lehetséges kockázatcsökkentő stratégiák a következők:

  - Amikor egy felhasználó által definiált típust adott meg egyetlen elemmel, érdemes lehet megadnia az adott elem nevét. Vegyük például a következőt `newtype Encoder = (Apply : (Qubit[] => Unit is Adj + Ctl))` : `newtype Encoder = (Qubit[] => Unit is Adj + Ctl)` .

  - Annak biztosítása, hogy más függvények és műveletek is elfogadják a "becsomagolt" UDT-példányokat közvetlenül.

- ⛔️ **ne** vezessen be olyan új, felhasználó által definiált típusokat, amelyek a beépített típusokat nem biztosítanak további kifejező.

  *Példák:*
  - A UDT `newtype QubitRegister = Qubit[]` nem biztosít további kifejező `Qubit[]` , és így nehezebben használható, és nem vehető igénybe.
  - A UDT `newtype LittleEndian = Qubit[]` dokumentálja, hogy az alapul szolgáló regisztert hogyan kell használni és értelmezni, így további kifejező biztosít az alaptípusa alapján.

- ⛔️ csak akkor vezessen be hozzáférési feladatokat, **Ha nem feltétlenül** szükséges;   Ebben az esetben az elnevezett elemek erősen előnyben részesítettek.

  *Példák:*
  - A UDT bevezetéséhez `newtype Complex = (Double, Double)` inkább a definíciók módosítását kell módosítania a   `newtype Complex = (Real : Double, Imag : Double)` függvények és a funkciók bevezetéséhez `GetReal : Complex -> Double`   `GetImag : Complex -> Double` .

## <a name="namespaces-and-organization"></a>Névterek és szervezet

**Kulcs elve:** válassza ki a kiszámítható és a függvények, a műveletek és a felhasználó által definiált típusok nevét a névtérben.

- ✅**Nevezze el** a névtereket `Publisher.Product.DomainArea` .

  *Példák:*
  - A Microsoft a Quantum Development Kit Quantum szimulációs funkciójának részeként közzétett functions, Operations és UDT a   `Microsoft.Quantum.Simulation` névtérbe kerül.
  - `Microsoft.Quantum.Math` a Microsoft által közzétett, a matematikai tartomány területéhez tartozó Quantum Development-készlet részeként közzétett névteret jelöli.

- ✅Az adott funkciókhoz használt műveletekkel, függvényekkel és felhasználó által definiált típusokkal olyan névteret **használhat,** amely leírja ezt a funkciót, még akkor is, ha az adott funkciót a különböző problémás tartományok között használják.

  *Példák:*
  - A Microsoft által a Quantum Development Kit részeként közzétett állapot-előkészítési API-k bekerülnek a szolgáltatásba   `Microsoft.Quantum.Preparation` .
  - A Microsoft által a Quantum Development Kit részeként közzétett Quantum szimulációs API-k bekerülnek a szolgáltatásba   `Microsoft.Quantum.Simulation` .

- ✅ A műveleteket, a függvényeket és a felhasználó által definiált típusokat csak meghatározott tartományokon belül, a segédprogram tartományát jelző névterekben használja. Ha szükséges, használjon alnévtereket az egyes tartományalapú névtereken belüli célzott feladatok jelzéséhez.

  *Példák:*
  - A Microsoft által közzétett Quantum Machine learning-függvénytár nagyrészt a @"microsoft.quantum.machinelearning" névtérbe kerül, de a névtér a példában szereplő adatkészleteket is megadja @"microsoft.quantum.machinelearning.datasets"   .
  - A Microsoft által a Quantum Development Kit részeként közzétett Quantum kémia API-kat be kell helyezni `Microsoft.Quantum.Chemistry` . A Jordan--Wigner-bomlás megvalósítására vonatkozó funkciók a következő helyen helyezhetők el `Microsoft.Quantum.Chemistry.JordanWigner` , így a kvantum-kémia tartomány elsődleges felülete nem vonatkozik a megvalósításokra.

**Kulcs elve:** A névterek és a hozzáférés-módosítók együttes használata szándékos lehet a felhasználók számára elérhető API-felülettel, valamint az API-k megvalósításával és tesztelésével kapcsolatos belső adatok elrejtésével.

- ✅ Ha ésszerű, minden olyan funkciót és műveletet helyezzen el, amely ahhoz **szükséges, hogy** az API-t ugyanahhoz a névtérhez adja, mint a megvalósított API-t, de a "Private" vagy a "belső" kulcsszavakkal van megjelölve, hogy azok nem részei a könyvtár nyilvános API-felületének. Az aláhúzás () karakterrel kezdődő nevet használva `_` vizuálisan megkülönböztetheti a privát és belső műveleteket és funkciókat a nyilvános callables.

  *Példák:*
  - A művelet neve `_Features` olyan függvényt jelöl, amely egy adott névtérhez és szerelvényhez tartozik, és a kulcsszónak kell kísérnie `internal` .

- ✅ Abban a ritka esetben, ha egy adott névtérhez tartozó API-k megvalósításához szükség van egy kiterjedt privát funkcióra vagy műveletre, **akkor** azokat egy új névtérbe helyezi, amely megfelel a megvalósított névtérnek, és a-ben végződik `.Private` .

- ✅Az összes egység tesztet olyan névterekben **Helyezze el** , amelyek megfelelnek a névtérnek a tesztelés és a Befejezés szakaszban `.Tests` .

## <a name="naming-conventions-and-vocabulary"></a>Elnevezési konvenciók és szókincs

**Kulcs elve:** Válassza ki azokat a neveket és terminológiát, amelyek egyértelmű, hozzáférhető és olvashatók különböző célközönségek között, beleértve a kvantum-kezdőket és a szakértőket is.

- ⛔️ **ne** használja a megkülönböztető vagy kizárási azonosító nevét, és az API-dokumentációs megjegyzésekben szereplő terminológiát sem.

- ✅**Az API** -dokumentációs megjegyzések használatával biztosíthatja a megfelelő kontextust, példákat és referenciákat, különösen a bonyolultabb fogalmakat illetően.

- ⛔️ **ne** használjon feleslegesen ezoterikus azonosítókat, vagy amelyekben jelentős mennyiségű kvantum-algoritmust kell olvasni.

  *Példák:*
  - A "amplitúdó-erősítési iteráció" a "a" a "a" a "a".

- ✅**Válassza ki** a műveletek és a függvények nevét, amelyek világosan közlik a meghívottak kívánt hatását, és nem annak megvalósítását. Vegye figyelembe, hogy a megvalósítást az API- [dokumentációs megjegyzésekben](xref:microsoft.quantum.qsharp.comments#documentation-comments)kell dokumentálni.

  *Példák:*
  - Inkább az "átfedés megbecslése" kifejezést a "Hadamard teszt" értékre, ahogy az utóbbi kommunikál az előző megvalósításával.

- ✅**Az összes** Q API-val egységes módon használja a szavakat \# :

  - **Igék**

    - **Érvényesítés**: Győződjön meg arról, hogy a célszámítógép és a qubits állapotáról feltételezi a feltételezést, valószínűleg a nem fizikai erőforrások használatával. Az ezt a műveletet használó műveleteknek mindig biztonságosan eltávolíthatók, anélkül, hogy ez befolyásolná a kódtárak és a végrehajtható programok működését. Fontos megjegyezni, hogy a tényekkel ellentétben a kijelentések általában külső állapottól függenek, például egy qubit-regiszter, a futtatási környezet vagy így tovább. Mivel a külső állapottól való függőség egyfajta mellékhatás, a kijelentéseket függvények helyett műveleteknek kell kitenni.

    - **Becslés**: egy vagy több valószínűleg ismétlődő mérés használata a mérési eredményekből származó klasszikus mennyiség megbecslése.

      *Példák:*
      - @"microsoft.quantum.characterization.estimatefrequency"
      - @"microsoft.quantum.characterization.estimateoverlapbetweenstates"

    - **Előkészítés**: alkalmazzon egy vagy több olyan qubits, amely egy adott kezdeti állapotban indul (általában $ \ket{00\cdots 0} $), így a qubits állapota a kívánt befejezési állapotnak megfelelően alakulhat ki. Általánosságban elmondható, hogy a megadott kiindulási állapotban **kívüli állapotok** nem definiált egységes átalakítást eredményezhetnek, de továbbra is meg kell őrizniük, hogy egy művelet és a adjoint "megszakítása", és a No-op alkalmazása **szükséges** .

      *Példák:*
      - @"microsoft.quantum.preparation.preparearbitrarystate"
      - @"microsoft.quantum.preparation.prepareuniformsuperposition"

    - **Mérték**: egy vagy több qubits alkalmazza a kvantum-műveletet vagy a műveletek egy szakaszát, és olvassa ki a klasszikus adatok biztonsági mentését.

      *Példák:*
      - @"Microsoft.Quantum.Intrinsic.Measure"
      - @"microsoft.quantum.arithmetic.measurefxp"
      - @"microsoft.quantum.arithmetic.measureinteger"

    - **Alkalmazás**: egy vagy több qubits alkalmazza a kvantum-műveletet vagy a műveletek egy szakaszát, így a qubits állapota koherens módon változhat. Ez az ige a legáltalánosabb művelet a Q- \# nómenklatúrában, és **nem** használható, ha egy konkrétabb művelet közvetlen jelentőséggel bír.

  - **Főnevek**:

    - **Tény**: egy olyan logikai feltétel, amely csak a bemenettől függ, és nem a célszámítógép, a környezete vagy a gép qubits állapota alapján. Egy állítással ellentétben a tény csak az adott tényhez megadott *értékekre* érzékeny. Például:

      *Példák:*
      - @"microsoft.quantum.diagnostics.equalityfacti": egy Esélyegyenlőségi tényt képvisel két egész számból álló bemenettel kapcsolatban; vagy a bemenetként megadott egész számok egyenlőek egymással, vagy nem, függetlenül attól, hogy a többi program állapota független-e.

    - **Beállítások:** Olyan UDT, amely több megnevezett elemet tartalmaz, amelyek "választható argumentumként" működhetnek egy függvényhez vagy művelethez. Például:

      *Példák:*
      - A @"microsoft.quantum.machinelearning.trainingoptions" UDT tartalmazza a tanulási sebesség, a minibatch-méret és más, a ml-képzéshez konfigurálható paraméterek elnevezett elemeit.

  - **Melléknevek**:

    - ⛔️ **új**: ezt a jelzőt **nem** szabad használni, mert így elkerülhető, hogy a használatot számos programozási nyelvben (pl.: C++, C#, Java, írógéppel, PowerShell) használják.

  - **Alaphelyzetek:** Bizonyos esetekben a függvények és a műveletek neveiben a nevek és a műveletek további egyértelműsítse vagy tisztázására is használhatók az előírások. Ezt a gondos és következetesen kell figyelembe venni.

    - **A következőképpen:** Azt jelzi, hogy a függvény bemenete és kimenete ugyanazokat az adatokat képviseli, de a kimenet az eredeti ábrázolás helyett *X* - **ként** jelöli meg az adatokat. Ez különösen gyakori a Type Conversion functions esetében.

      *Példák:*
      - `IntAsDouble(2)` azt jelzi, hogy mind a bemenet ( `2` ), mind a kimenet ( `2.0` ) ugyanazt az információt jeleníti meg, de különböző Q \# adattípusokat használ.

    - **Forrás:** A konzisztencia biztosítása érdekében ez az előírás   **nem** használható a Type Conversion functions vagy bármely más, a megfelelőnek **minősülő** eset jelzésére.

    - ⛔️ **a** következőhöz: ezt az előfeltételt **nem** szabad használni, mert így elkerülhető, hogy a használatuk ne legyen több programozási nyelvben.
