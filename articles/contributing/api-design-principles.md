---
title: 'Q # API tervezési alapelvek'
description: 'Q # API tervezési alapelvek'
author: cgranade
ms.author: chgranad
ms.date: 3/9/2020
ms.topic: article
uid: microsoft.quantum.contributing.api-design
ms.openlocfilehash: 03c32331f8988181ec6fedcfc207d752b4a880b2
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/10/2020
ms.locfileid: "79024202"
---
# <a name="q-api-design-principles"></a>Q # API tervezési alapelvek

## <a name="introduction"></a>Introduction (Bevezetés)

Nyelvként és platformként a Q # lehetővé teszi a felhasználók számára a kvantum-alkalmazások írását, futtatását, megismerését és megismerését.
Ahhoz, hogy a felhasználók felhatalmazzák a Q # kódtárakat, az API-tervezési alapelveket követve elvégezheti a kialakítást, és segítheti a felhasználható könyvtárak létrehozását a Quantum fejlesztői közösség számára.
Ez a cikk felsorolja ezeket az alapelveket, és példákat mutat be arra, hogyan alkalmazhatja őket a Q # API-k tervezésekor.

> [!TIP]
> Ez egy meglehetősen részletes dokumentum, amely segítséget nyújt a függvénytár-fejlesztés és a részletes függvénytár-hozzájárulások létrehozásához.
> Valószínűleg hasznosnak fogja találni a saját kódtárak megírását a Q #-ban, vagy ha nagyobb funkciókkal járul hozzá a [q # librarys tárházhoz](https://github.com/microsoft/QuantumLibraries).
>
> Ha szeretné megtudni, hogy miként járulhat hozzá általánosabban a Quantum Development Kit-hez, javasoljuk, hogy kezdje a [hozzájárulási útmutatóval](xref:microsoft.quantum.contributing).
> Ha többet szeretne megtudni arról, hogy a Q #-kód formázása miért javasolt, érdemes lehet megtekinteni a [stílusra vonatkozó útmutatót](xref:microsoft.quantum.contributing.style).

## <a name="general-principles"></a>Általános alapelvek

**Kulcs elve:** Tegye elérhetővé a kvantum-alkalmazásokra koncentráló API-kat.

- ✅ **válassza** ki a műveletek és függvények nevét, amelyek az algoritmusok és alkalmazások magas szintű szerkezetét tükrözik.
- ⛔️ **nem** tesz elérhetővé olyan API-kat, amelyek elsősorban az alacsony szintű megvalósítási részletekre összpontosítanak.

**Kulcs elve:** Az API-k tervezésének megkezdése minta-használati esetek használatával biztosíthatja, hogy az API-k könnyen használhatók legyenek.

- ✅ gondoskodjon arról, hogy a nyilvános API-k minden összetevője megfelelő használati esettel rendelkezik, **és nem kell** megterveznie az összes lehetséges felhasználást a Start menüből.
    Másképpen fogalmazva, ne vezessen be nyilvános API-kat abban az esetben, ha azok hasznosak, de győződjön meg arról, hogy az API-k mindegyik része *konkrét* példát mutat be, amelyben hasznos lehet.

  *Példák*
  - @"microsoft.quantum.canon.applytoeachca" felhasználható `ApplyToEachCA(H, _)`ként, hogy a regisztereket egységes, több kvantum-algoritmusban közös feladatként készítse elő. Ugyanezt a műveletet számos más feladathoz is felhasználhatja előkészítési, numerikus és Oracle-alapú algoritmusokban.

- ✅ **az** ötletbörze és a workshop új API-terveivel megvizsgálhatja, hogy azok intuitívek és a javasolt használati eseteknek megfelelőek-e.

  *Példák*
  - Tekintse meg az aktuális Q\# kódot, amelyből megtudhatja, hogy az új API-tervek hogyan egyszerűsíthetik a meglévő implementációkat
  - Tekintse át a javasolt API-terveket az elsődleges célközönségek képviselőivel.

**Kulcs elve:** Tervezzen API-kat az olvasható kódok támogatásához és ösztönzéséhez.

- ✅ **gondoskodjon arról,** hogy a kód a tartományi szakértők és a nem szakértők számára is olvasható legyen.
- ✅ **Helyezze** a fókuszt az egyes műveletek és függvények hatására a magas szintű algoritmuson belül, a dokumentáció segítségével pedig szükség szerint a megvalósítás részleteit.
- ✅ **tegye** a Common [Q\# stílusú útmutatót](xref:microsoft.quantum.contributing.style) , ha van ilyen.

**Kulcs elve:** Az API-k megtervezése stabil és a továbbítási kompatibilitás biztosítása érdekében.

- ✅ **a** régi API-k elavultak, ha a változtatások megszakadnak.

- a **✅ olyan** "alátét" műveleteket és funkciókat biztosít, amelyek lehetővé teszik, hogy a meglévő felhasználói kód megfelelően működjön az elavulás során.

  *Példák*
  - Ha egy `EstimateExpectation` nevű művelet átnevezésével `EstimateAverage`, akkor egy új műveletet kell meg`EstimateExpectation` hívnia, amely új néven meghívja az eredeti műveletet, hogy a meglévő kód továbbra is megfelelően működjön.

- ✅ **használja** a @"microsoft.quantum.core.deprecated" attribútumot az elavultak a felhasználó felé való kommunikációhoz.

- ✅ egy művelet vagy függvény átnevezése **esetén adja meg** az új nevet karakterlánc-bemenetként a `@Deprecated`hoz.

- ⛔️ **ne** távolítsa el a meglévő függvényeket vagy műveleteket, ha az előzetes verziónál legalább hat hónapig elavult időszak van, vagy legalább két év a támogatott kiadásokhoz.

## <a name="functions-and-operations"></a>Függvények és műveletek

**Kulcs elve:** gondoskodjon arról, hogy minden függvény és művelet egyetlen jól meghatározott céllal legyen az API-n belül.

- ⛔️ **nem** tesznek elérhetővé több nem kapcsolódó feladatot végrehajtó függvényeket és műveleteket.

**Kulcs elve:** a lehető legtöbbször felhasználható és a jövőbeli igényeknek megfelelő tervezési funkciókat és műveleteket kell megtervezni.

- ✅ **a** tervezési függvényeket és műveleteket más függvényekkel és műveletekkel is összeállíthatja, mind UGYANABBAN az API-ban, mind a korábban meglévő könyvtárakban.

  *Példák*
  - A @"microsoft.quantum.canon.delay" művelet minimális feltételezéseket biztosít a bemenetével kapcsolatban, így a Q # standard könyvtárban vagy a felhasználók által meghatározott műveletek bármelyike esetében késleltetheti az alkalmazások használatát.
    <!-- TODO: define bad example. -->

- ✅ **csak** a klasszikus logika determinisztikus, mint a függvények helyett.

  *Példák*
  - Egy olyan alrutin, amely a lebegőpontos bemenetének négyzetes beírását is lehetővé teszi, determinisztikus módon, így a felhasználó `Squared : Double -> Double` helyett a művelet `Square : Double => Double`. Ez lehetővé teszi, hogy a alrutin több helyen legyen meghívva (pl.: más funkciókon belül), és hasznos optimalizálási információkat biztosít a fordítónak, amely hatással lehet a teljesítményre és az optimalizálásokra.
  - a `ForEach<'TInput, 'TOutput>('TInput => 'TOutput, 'TInput[]) => 'TOutput[]` és a `Mapped<'TInput, 'TOutput>('TInput -> 'TOutput, 'TInput[]) -> 'TOutput[]` eltérnek a meghatározatlan feltételekkel kapcsolatban tett garanciákban; mindkettő különböző helyzetekben hasznos.
  - A Quantum Operations alkalmazást átalakító API-rutinok gyakran determinisztikus módon hajthatók végre, így például a `CControlled<'T>(op : 'T => Unit) => ((Bool, 'T) => Unit)`is elérhetők.

- ✅ **a** bemeneti típus általánosítása az egyes függvényekhez és műveletekhez ésszerű mértékben, szükség szerint írja be a paramétereket.

  *Példák*
  - a `ApplyToEach` típusa `<'T>(('T => Unit), 'T[]) => Unit` nem a leggyakoribb alkalmazás konkrét típusa, `((Qubit => Unit), Qubit[]) => Unit`.

> [!TIP]
> Fontos, hogy előre jelezze a jövőbeli igényeket, de fontos, hogy konkrét problémák megoldására is szükség van a felhasználók számára.
> Ennek a kulcsfontosságú alapelveknek az alkalmazása ezért mindig alapos megfontolást és kiegyensúlyozást igényel az API-k "csak abban az esetben" való fejlesztése érdekében.

**Legfontosabb elv:** válassza a bemeneti és kimeneti típusok lehetőséget a kiszámítható, valamint a meghívásos művelet céljával kommunikáló függvények és műveletek számára.

- ✅ használja a rekord típusait logikailag csoportosítani a bemeneteket és kimeneteket, amelyek csak akkor jelentősek, ha azokat **együtt kell tekinteni** . Ezekben az esetekben érdemes lehet felhasználó által definiált típust használni.

  *Példák*
  - Előfordulhat, hogy egy másik függvény helyi minimális értékeinek kimenetére szolgáló függvénynek a keresési időközt kell használnia bemenetként, így `LocalMinima(fn : (Double -> Double), (left : Double, right : Double)) : Double` lehet a megfelelő aláírás.
  - A Machine learning-osztályozó a paraméter-átváltási technikával való kiszámításához szükséges műveletnek az áthelyezett és a nem áthelyezett paramétereket is fel kell vennie bemenetként. Ebben az esetben a `(unshifted : Double[], shifted : Double[])`hoz hasonló bemenet is megfelelő lehet.

- ✅ **a** bemeneti és kimeneti rekordok lévő elemek sorrendjét a különböző függvényekben és műveletekben következetesen.

  *Példák*
  - Ha két vagy több olyan függvényt vagy műveletet vizsgál, amelyek mindegyike elforgatási szöget és a célként megadott qubit bemenetként veszi figyelembe, ügyeljen arra, hogy mindegyik bemeneti rekordban azonos sorrendben legyenek rendezve. Ez inkább `ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl` és `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)` `ApplyRotation(target : Qubit, angle : Double) : Unit is Adj + Ctl` és `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)`.

**Legfontosabb elv:** a Q\# nyelvi funkciói, például a részleges alkalmazás használatával jól használható tervezési függvények és műveletek.

- ✅ **DO** megrendelési elemeket a bemeneti rekordok úgy, hogy a leggyakrabban alkalmazott bemenetek először történnek (például:, hogy a részleges alkalmazás a curry-hez hasonlóan működik).

  *Példák*
  - Egy olyan műveleti `ApplyRotation`, amely egy lebegőpontos számot és egy qubit használ, a bemenetek gyakran részlegesen alkalmazhatók a lebegőpontos bemenettel, amely a `Qubit => Unit`típusú adatbevitelt elvárt műveletekkel használható. Így a `operation ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl` aláírása
      a leghatékonyabban együttműködik a részleges alkalmazásokkal.
  - Ez az útmutató általában azt jelenti, hogy az összes klasszikus adatot a bemeneti rekordok összes qubits elé helyezi, de jó ítéletet használ, és megvizsgálja, hogyan hívják meg az API-t a gyakorlatban.

## <a name="user-defined-types"></a>Felhasználó által definiált típusok

**Legfontosabb elv:** felhasználói típusok használata az API-k egyszerűbb és kényelmes használatának megkönnyítéséhez.

- ✅ **olyan** új felhasználó által definiált típusokat vezet be, amelyek hosszú és/vagy bonyolult típusok hasznos rövidítését teszik lehetővé.

  *Példák*
  - Azokban az esetekben, amikor egy három qubit-tömb bemenettel rendelkező Művelettípus általában bemenetként van megadva, vagy kimenetként adja vissza, UDT, például `newtype TimeDependentBlockEncoding = ((Qubit[], Qubit[], Qubit[]) => Unit is Adj + Ctl)`
      hasznos rövidítést tud nyújtani.

- ✅ **az** új, felhasználó által definiált típusok bevezetésével jelezheti, hogy egy adott alaptípust csak nagyon konkrét értelemben kell használni.

  *Példák*
  - Egy olyan műveletet, amelyet kifejezetten olyan műveletként kell értelmezni, amely a klasszikus adatmennyiséget egy kvantum-regiszterbe kódolja, a felhasználó által definiált típusú `newtype InputEncoder = (Apply : (Qubit[] => Unit))`címkével kell rendelkeznie.

- ✅ **olyan** megnevezett elemekkel rendelkező új felhasználó által definiált típusokat vezessen be, amelyek lehetővé teszik a későbbi bővíthetőséget (például: egy olyan eredmény-struktúra, amely további megnevezett elemeket tartalmazhat a jövőben).

  *Példák*
  - Ha egy `TrainModel` művelet nagy számú konfigurációs beállítást tesz elérhetővé, ezeket a beállításokat új `TrainingOptions` UDT, és egy új függvényt biztosít `DefaultTrainingOptions : Unit -> TrainingOptions` lehetővé teszi, hogy a felhasználók felülbírálják a TrainingOptions UDT-értékek meghatározott elnevezett elemeit, miközben továbbra is lehetővé teszik a könyvtár-fejlesztők számára, hogy szükség szerint új UDT-elemeket adjanak hozzá.

- ✅ **DO** elnevezett elemeket deklaráljon az új, felhasználó által definiált típusokhoz, hogy a felhasználók megismerjék a megfelelő rekord dekonstrukcióját.

  *Példák*
  - Ha egy összetett számot jelképez a Polar dekompozícióban, inkább a `newtype ComplexPolar = (Magnitude: Double, Argument: Double)` `newtype ComplexPolar = (Double, Double)`.

**Legfontosabb alapelv:** a felhasználó által definiált típusok használata a kognitív terhelés csökkentése és a felhasználónak nem kell további fogalmakat és nómenklatúrát megtanulnia.

- ⛔️ **ne** vezessen be olyan felhasználó által definiált típusokat, amelyek megkövetelik a felhasználótól, hogy gyakran használják a kicsomagolási operátort (`!`), vagy amelyek általában több szintű kicsomagolást igényelnek. A lehetséges kockázatcsökkentő stratégiák a következők:

  - Amikor egy felhasználó által definiált típust adott meg egyetlen elemmel, érdemes lehet megadnia az adott elem nevét. Például érdemes lehet `newtype Encoder = (Apply : (Qubit[] => Unit is Adj + Ctl))` `newtype Encoder = (Qubit[] => Unit is Adj + Ctl)`.

  - Annak biztosítása, hogy más függvények és műveletek is elfogadják a "becsomagolt" UDT-példányokat közvetlenül.

- ⛔️ **ne** vezessen be olyan új, felhasználó által definiált típusokat, amelyek a beépített típusokat nem biztosítanak további kifejező.

  *Példák*
  - A UDT `newtype QubitRegister = Qubit[]` nem biztosít további kifejező a `Qubit[]`, és így nehezebb a használata, amely nem kielégítő előnyt jelent.
  - A UDT `newtype LittleEndian = Qubit[]` a dokumentumok alapjául szolgáló regisztráció felhasználását és értelmezését, és így további kifejező biztosít az alaptípusa alapján.

- ⛔️ csak akkor vezessen be hozzáférési feladatokat, **Ha nem feltétlenül** szükséges;   Ebben az esetben az elnevezett elemek erősen előnyben részesítettek.

  *Példák*
  - UDT-`newtype Complex = (Double, Double)`bevezetésekor inkább a definíciók módosítását `newtype Complex = (Real : Double, Imag : Double)` a függvények `GetReal : Complex -> Double` és `GetImag : Complex -> Double`bevezetéséhez.

## <a name="namespaces-and-organization"></a>Névterek és szervezet

**Kulcs elve:** válassza ki a kiszámítható és a függvények, a műveletek és a felhasználó által definiált típusok nevét a névtérben.

- ✅ **név** névtereket `Publisher.Product.DomainArea`ként.

  *Példák*
  - A Microsoft a Quantum Development Kit Quantum szimulációs funkciójának részeként közzétett functions, Operations és UDT a `Microsoft.Quantum.Simulation` névtérbe kerül.
  - a `Microsoft.Quantum.Math` a Microsoft által közzétett névteret jelöli a matematikai tartomány területéhez tartozó Quantum Development-készlet részeként.

- a **✅ műveleteket** , függvényeket és felhasználó által definiált típusokat használhat egy olyan névtérben, amely leírja az adott funkciót, még akkor is, ha az adott funkciót a különböző problémás tartományokban használják.

  *Példák*
  - A Microsoft a Quantum Development Kit részeként közzétett állapot-előkészítési API-kat `Microsoft.Quantum.Preparation`ba helyezi.
  - A Microsoft által a Quantum Development Kit részeként közzétett Quantum szimulációs API-k a `Microsoft.Quantum.Simulation`ba kerülnek.

- ✅ **olyan** műveleteket, függvényeket és felhasználó által definiált típusokat, amelyeket csak adott tartományokban használ a segédprogram tartományát jelző névtérbe. Ha szükséges, használjon alnévtereket az egyes tartományalapú névtereken belüli célzott feladatok jelzéséhez.

  *Példák*
  - A Microsoft által közzétett Quantum Machine learning-függvénytár nagyrészt a @"microsoft.quantum.machinelearning" névtérbe kerül, de a @"microsoft.quantum.machinelearning.datasets" névtér a példában szereplő adatkészleteket is megadja.
  - A Microsoft által a Quantum Development Kit részeként közzétett Quantum kémia API-kat `Microsoft.Quantum.Chemistry`ba kell helyezni. A Jordan--Wigner elbomlásának megvalósítására vonatkozó funkciók `Microsoft.Quantum.Chemistry.JordanWigner`ba helyezhetők, így a kvantum-kémia tartományának elsődleges felülete nem vonatkozik a megvalósításokra.

**Kulcs elve:** A névterek és a hozzáférés-módosítók együttes használata szándékos lehet a felhasználók számára elérhető API-felülettel, valamint az API-k megvalósításával és tesztelésével kapcsolatos belső adatok elrejtésével.

- ✅ ha ésszerű, minden olyan funkciót és műveletet helyezzen el, amely ahhoz **szükséges, hogy** az API-t ugyanahhoz a névtérhez adja, mint a megvalósított API-t, de a "Private" vagy a "belső" kulcsszavakkal jelölve jelezze, hogy nem részei a könyvtár nyilvános API-felületének. Használjon aláhúzás (`_`) kezdetű nevet, hogy vizuálisan megkülönböztesse a privát és belső műveleteket és funkciókat a nyilvános callables.

  *Példák*
  - A művelet neve `_Features` egy olyan függvényt jelez, amely egy adott névtérhez és szerelvényhez tartozik, és a `internal` kulcsszónak kell kísérnie.

- ✅ abban a ritka esetben, ha egy adott névtérhez tartozó API-k megvalósításához szükség van a privát funkciók vagy műveletek széles körére, **akkor** azokat egy új névtérbe helyezi, amely megfelel a megvalósított névtérnek, és `.Private`végződik.

- ✅ **az** összes egység tesztjét a test (tesztelés) elemnél a névtérnek megfelelő névtérbe helyezi, `.Tests`.

## <a name="naming-conventions-and-vocabulary"></a>Elnevezési konvenciók és szókincs

**Kulcs elve:** Válassza ki azokat a neveket és terminológiát, amelyek egyértelmű, hozzáférhető és olvashatók különböző célközönségek között, beleértve a kvantum-kezdőket és a szakértőket is.

- ⛔️ **ne** használja a megkülönböztető vagy kizárási azonosító nevét, és az API-dokumentációs megjegyzésekben szereplő terminológiát sem.

- ✅ az API-dokumentációs megjegyzésekkel **megadhatja** a megfelelő kontextust, példákat és referenciákat, különösen a bonyolultabb fogalmakat illetően.

- ⛔️ **ne** használjon feleslegesen ezoterikus azonosítókat, vagy amelyekben jelentős mennyiségű kvantum-algoritmust kell olvasni.

  *Példák*
  - A "amplitúdó-erősítési iteráció" a "a" a "a" a "a".

- ✅ **válassza** ki a műveletek és a függvények nevét, amelyek világosan közlik a meghívottak kívánt hatását, és nem annak megvalósítását. Vegye figyelembe, hogy a megvalósítás lehet

  *Példák*
  - Inkább az "átfedés megbecslése" kifejezést a "Hadamard teszt" értékre, ahogy az utóbbi kommunikál az előző megvalósításával.

- ✅ **az** összes Q\# API-val egységes módon használja a szavakat:

  - **Igék**

    - **Érvényesítés**: Győződjön meg arról, hogy a célszámítógép és a qubits állapotáról feltételezi a feltételezést, valószínűleg a nem fizikai erőforrások használatával. Az ezt a műveletet használó műveleteknek mindig biztonságosan eltávolíthatók, anélkül, hogy ez befolyásolná a kódtárak és a végrehajtható programok működését. Vegye figyelembe, hogy a tényekkel ellentétben az állítások általában külső állapottól függenek, például egy qubit-regisztráció, a végrehajtási környezet vagy így tovább. Mivel a külső állapottól való függőség egyfajta mellékhatás, a kijelentéseket függvények helyett műveleteknek kell kitenni.

    - **Becslés**: egy vagy több valószínűleg ismétlődő mérés használata a mérési eredményekből származó klasszikus mennyiség megbecslése.

      *Példák*
      - @"microsoft.quantum.characterization.estimatefrequency"
      - @"microsoft.quantum.characterization.estimateoverlapbetweenstates"

    - **Előkészítés**: alkalmazzon egy vagy több olyan qubits, amely egy adott kezdeti állapotban indul (általában $ \ket{00\cdots 0} $), így a qubits állapota a kívánt befejezési állapotnak megfelelően alakulhat ki. Általánosságban elmondható, hogy a megadott kiindulási állapotban **kívüli állapotok** nem definiált egységes átalakítást eredményezhetnek, de továbbra is meg kell őrizniük, hogy egy művelet és a adjoint "megszakítása", és a No-op alkalmazása **szükséges** .

      *Példák*
      - @"microsoft.quantum.preparation.preparearbitrarystate"
      - @"microsoft.quantum.preparation.prepareuniformsuperposition"

    - **Mérték**: egy vagy több qubits alkalmazza a kvantum-műveletet vagy a műveletek egy szakaszát, és olvassa ki a klasszikus adatok biztonsági mentését.

      *Példák*
      - @"microsoft.quantum.intrinsic.measure"
      - @"microsoft.quantum.arithmetic.measurefxp"
      - @"microsoft.quantum.arithmetic.measureinteger"

    - **Alkalmazás**: egy vagy több qubits alkalmazza a kvantum-műveletet vagy a műveletek egy szakaszát, így a qubits állapota koherens módon változhat. Ez az ige a legáltalánosabb művelet a Q\#-nómenklatúrában, és **nem** használható, ha egy konkrétabb művelet sokkal közvetlenebb jelentőséggel bír.

  - **Főnevek**:

    - **Tény**: egy olyan logikai feltétel, amely csak a bemenettől függ, és nem a célszámítógép, a környezete vagy a gép qubits állapota alapján. Egy állítással ellentétben a tény csak az adott tényhez megadott *értékekre* érzékeny. Például:

      *Példák*
      - @"microsoft.quantum.diagnostics.equalityfacti": egy Esélyegyenlőségi tényt képvisel két egész szám bemenettel kapcsolatban; vagy a bemenetként megadott egész számok egyenlőek egymással, vagy nem, függetlenül attól, hogy a többi program állapota független-e.

    - **Beállítások:** Olyan UDT, amely több megnevezett elemet tartalmaz, amelyek "választható argumentumként" működhetnek egy függvényhez vagy művelethez. Például:

      *Példák*
      - A @"microsoft.quantum.machinelearning.trainingoptions" UDT tartalmaz elnevezett elemeket a tanulási sebesség, a minibatch mérete és más, a ML-képzéshez konfigurálható paraméterek számára.

  - **Melléknevek**:

    - ⛔️ **új**: ezt a jelzőt **nem** szabad használni, mert így elkerülhető, hogy a használatot számos programozási nyelvben (például: C++, C#, Java, írógéppel, PowerShell) használják.

  - **Alaphelyzetek:** Bizonyos esetekben a függvények és a műveletek neveiben a nevek és a műveletek további egyértelműsítse vagy tisztázására is használhatók az előírások. Ezt a gondos és következetesen kell figyelembe venni.

    - **A következőképpen:** Azt jelzi, hogy a függvény bemenete és kimenete ugyanazokat az adatokat képviseli, de a kimenet az eredeti ábrázolás helyett *X* - **ként** jelöli meg az adatokat. Ez különösen gyakori a Type Conversion functions esetében.

      *Példák*
      - `IntAsDouble(2)` azt jelzi, hogy mind a bemenet (`2`), mind a kimenet (`2.0`) ugyanazokat az információkat képviseli, de a Q\# eltérő adattípusok használatával.

    - **Forrás:** A konzisztencia biztosítása érdekében ez az előírás **nem** használható a Type Conversion functions vagy bármely más, a megfelelőnek **minősülő** eset jelzésére.

    - ⛔️ **a** következőhöz: ezt az előfeltételt **nem** szabad használni, mert így elkerülhető, hogy a használatuk ne legyen több programozási nyelvben.
