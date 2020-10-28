---
title: A Quantum Development Kit kibocsátási megjegyzései
description: Ismerje meg a Microsoft Quantum Development Kit előzetes verziójának legújabb frissítéseit.
author: bradben
ms.author: v-benbra
ms.date: 8/30/2020
ms.topic: article
uid: microsoft.quantum.relnotes
no-loc:
- Q#
- $$v
ms.openlocfilehash: fae603a81f8edc23ab8dc14277c5e3c4699f2cee
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691688"
---
# <a name="microsoft-quantum-development-kit-release-notes"></a>A Microsoft Quantum Development Kit kibocsátási megjegyzései

Ez a cikk információkat tartalmaz a Quantum Development Kit egyes verzióiról.

A telepítési utasításokat lásd a [telepítési útmutatóban](xref:microsoft.quantum.install).

A frissítésre vonatkozó utasításokat lásd a [frissítési útmutatóban](xref:microsoft.quantum.update).

## <a name="version-01320102604"></a>0.13.20102604 verziója

*Kiadás dátuma: október 27., 2020*

A verzió a következőket tartalmazza:

- Az erőforrás-becslés mostantól egyidejűleg elérhető mélységi és szélességi becsléseket bocsát ki a qubit száma mellett. Részletekért lásd [itt](xref:microsoft.quantum.machines.resources-estimator#metrics-reported) .

Tekintse meg a [kódtárak](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+closed%3A2020-09-25..2020-10-22), [fordítóprogramok](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+closed%3A2020-09-25..2020-10-22), [futtatókörnyezetek](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+closed%3A2020-09-25..2020-10-22), [minták](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+closed%3A2020-09-25..2020-10-22), [I Q# ](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+closed%3A2020-09-25..2020-10-22) és [kataek](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+closed%3A2020-09-25..2020-10-22)teljes listáját.

## <a name="version-01220100504"></a>0.12.20100504 verziója

*Kiadás dátuma: október 5., 2020*

Ez a kiadás a jegyzetfüzetek terhelését érintő hibát javít Q# (lásd: [iqsharp # 331](https://github.com/microsoft/iqsharp/pull/331)).

## <a name="version-01220092803"></a>0.12.20092803 verziója

*Kiadás dátuma: szeptember 29., 2020*

A verzió a következőket tartalmazza:

- A [Quantum Intermediate reprezentációk (QIR-EK)](https://github.com/microsoft/qsharp-language/tree/main/Specifications/QIR#quantum-intermediate-representation-qir) bejelentése és vázlatos meghatározása a különböző előtér-és háttérrendszer-formátumokban. Lásd még: [blogbejegyzés](https://devblogs.microsoft.com/qsharp/introducing-quantum-intermediate-representation-qir) a QIR-on.
- A teljes [ Q# dokumentációt](https://github.com/microsoft/qsharp-language/tree/main/Specifications/Language#q-language)is tartalmazó új [ Q# nyelvi](https://github.com/microsoft/qsharp-language) tárház elindítása.
- A nagy mennyiségű qubits érintő programok QuantumSimulator teljesítménybeli fejlesztései: a Gate Fusion-döntések jobb alkalmazása; továbbfejlesztett párhuzamos Linux rendszeren; a Gate-végrehajtás intelligens ütemezése hozzáadva; hibajavítások.
- Az IntelliSense-funkciók mostantól a Q# Visual Studióban és a Visual Studio Code-ban is támogatottak a Project fájl nélkül.
- Különböző Q# /Python-együttműködési funkciók és hibajavítások, beleértve a NumPy-adattípusok jobb támogatását.
- A Microsoft. Quantum. Arrays névtér fejlesztése (lásd: [Microsoft/QuantumLibraries # 313](https://github.com/microsoft/QuantumLibraries/issues/313)).
- Egy új, csak két qubits használó [ismételt ismétléses minta](https://github.com/microsoft/Quantum/tree/main/samples/algorithms/repeat-until-success) lett hozzáadva.

A legutóbbi kiadás óta a nyílt forráskódú adattárakban található alapértelmezett ág átnevezve lett a következőre: `main` .

Tekintse meg a [kódtárak](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+closed%3A2020-08-24..2020-09-24), [fordítóprogramok](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+closed%3A2020-08-24..2020-09-24), [futtatókörnyezetek](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+closed%3A2020-08-24..2020-09-24), [minták](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+closed%3A2020-08-24..2020-09-24), [I Q# ](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+closed%3A2020-08-24..2020-09-24) és [kataek](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+closed%3A2020-08-24..2020-09-24)teljes listáját.

## <a name="version-01220082513"></a>0.12.20082513 verziója

*Kiadás dátuma: augusztus 25., 2020*

A verzió a következőket tartalmazza:

- Új [Microsoft. Quantum. Random névtér](xref:Microsoft.Quantum.Random), amely megkönnyíti a véletlenszerű értékek mintavételezését a Q# programokon belülről. ([QuantumLibraries # 311](https://github.com/microsoft/QuantumLibraries/pull/311), [qsharp-Runtime # 328](https://github.com/microsoft/qsharp-runtime/pull/328))
- Javította a [Microsoft. Quantum. Diagnostics névteret](xref:Microsoft.Quantum.Diagnostics) új [ `DumpOperation` művelettel](xref:Microsoft.Quantum.Diagnostics.DumpOperation), valamint új műveleteket a qubit-kiosztási és az Oracle-hívások korlátozásához. ([QuantumLibraries # 302](https://github.com/microsoft/QuantumLibraries/pull/302))
- Új [ `%project` Magic-parancs](xref:microsoft.quantum.iqsharp.magic-ref.project) a Q# Pythonban és az [ `qsharp.projects` API](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects) -ban, hogy támogassa az Q# aktuális munkaterület-mappán kívüli projektekre való hivatkozásokat. A szolgáltatás jelenlegi korlátaihoz lásd: [iqsharp # 277](https://github.com/microsoft/iqsharp/issues/277) . 
- Támogatja a fájlok automatikus betöltését `.csproj` az I Q# /Python gazdagépek számára, amely lehetővé teszi, hogy a külső projekt vagy csomag hivatkozásait inicializálási időben lehessen betölteni. További részletekért tekintse meg a [ Q# Python és a Jupyter notebookok](xref:microsoft.quantum.guide.host-programs) használatát ismertető útmutatót.
- Hozzáadott ErrorCorrection. szindróma minta.
- A SimpleIsing-hez hangolt kapcsolást adott hozzá.
- Frissített HiddenShift minta.
- Példa a sudoku megoldására a a a a a a a a a a a a a a a a a a
- Általános hibajavítások.

Tekintse meg a [kódtárak](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [fordítóprogramok](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [futtatókörnyezetek](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [minták](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed), [I Q# ](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) és [kataek](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed)teljes listáját.  

## <a name="version-01220072031"></a>0.12.20072031 verziója

*Kiadás dátuma: július 21., 2020*

A verzió a következőket tartalmazza:

- A jegyzetfüzetekben megnyitott névterek Q# mostantól elérhetők az összes jövőbeli cella futtatásakor. Ez lehetővé teszi például, hogy a névtereket egyszer kell megnyitni a jegyzetfüzet tetején lévő cellában, ahelyett, hogy a megfelelő névtereket meg kellene nyitnia az egyes kódok celláiban. Az új `%lsopen` Magic parancs megjeleníti a jelenleg megnyitott névterek listáját.

Tekintse meg a [kódtárak](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [fordítóprogramok](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [futtatókörnyezetek](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [minták](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed), [I Q# ](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) és [kataek](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed)teljes listáját.  

## <a name="version-01220070124"></a>0.12.20070124 verziója

*Kiadás dátuma: július 2., 2020*

A verzió a következőket tartalmazza:

- Új `qdk-chem` eszköz az örökölt elektronikus struktúra problémák szerializálási formátumának (például: FCIDUMP) a [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) való átalakításához
- Új függvények és műveletek a [`Microsoft.Quantum.Synthesis`](xref:Microsoft.Quantum.Synthesis) névtérben az átalakítási és a deösszetételes-alapú szintézisi algoritmusok segítségével, hogy koherens módon alkalmazzák a klasszikus Oracle-ket.
- Q#Mostantól a `%simulate` , a `%estimate` és más Magic parancsok argumentumait is engedélyezi. További részletekért tekintse meg a [ `%simulate` Magic parancs referenciáját](xref:microsoft.quantum.iqsharp.magic-ref.simulate) .
- Új fázis megjelenítési beállításai az I-ben Q# . További részletekért tekintse meg a [ `%config` Magic parancs referenciáját](xref:microsoft.quantum.iqsharp.magic-ref.config) .
- Én Q# és a `qsharp` Python-csomag mostantól Conda-csomagokon ([qsharp](https://anaconda.org/quantum-engineering/qsharp) és [iqsharp](https://anaconda.org/quantum-engineering/iqsharp)) keresztül érhető el a Q# Jupyter és a Python funkcióinak Conda-környezetbe való helyi telepítésének egyszerűsítése érdekében. További részletekért tekintse meg a [ Q# Jupyter-jegyzetfüzeteket](xref:microsoft.quantum.install.jupyter) és [ Q# a Python](xref:microsoft.quantum.install.python) telepítési útmutatóit.
- A szimulátor használatakor a qubits már nem kell a (z) | 0 ⟩ állapotban lennie a kiadáskor, de automatikusan alaphelyzetbe állítható, ha a felszabadítás előtt azonnal megmérjük őket.
- A frissítések megkönnyítik Q# &, hogy a felhasználók a különböző QDK-verziókkal rendelkező függvénytár-csomagokat használják fel
- Elavult névtér eltávolítva `Microsoft.Quantum.Primitive.*`
- Áthelyezett műveletek:
  - `Microsoft.Quantum.Intrinsic.Assert` most `Microsoft.Quantum.Diagnostics.AssertMeasurement`
  - `Microsoft.Quantum.Intrinsic.AssertProb` most `Microsoft.Quantum.Diagnostics.AssertMeasurementProbability`
- Hibajavítások 

Tekintse meg a [kódtárak](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [fordítóprogramok](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [futtatókörnyezetek](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [minták](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed), [I Q# ](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) és [kataek](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed)teljes listáját.  

## <a name="version-0112006403"></a>0\.11.2006.403-as verzió

*Kiadási dátum: 2020. június 4.*

Ez a kiadás javít egy hibát, amely hatással van a projektek fordítására Q# .

## <a name="version-0112006207"></a>0\.11.2006.207-es verzió

*Kiadási dátum: 2020. június 3.*

A verzió a következőket tartalmazza:

- Q# a jegyzetfüzetek és a Python-gazdagépek programjai többé nem lesznek sikertelenek, ha Q# belépési pont van jelen
- A [Szabványos kódtár](xref:microsoft.quantum.libraries.standard.intro) frissítései a hozzáférés-módosítók használatához
- A fordító mostantól lehetővé teszi a beépített átírási lépések között az átírási lépések beépülő moduljának használatát
- Számos elavult függvény és művelet el lett távolítva az [API-alapelvek](xref:microsoft.quantum.contributing.api-design) dokumentumban ismertetett ütemezés szerint. Q# a 0.11.2004.2825 verzióban figyelmeztetés nélkül épülő programok és kódtárak továbbra is módosítva lesznek.

Tekintse meg a [kódtárak](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [fordítóprogramok](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [futtatókörnyezetek](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [minták](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed), [I Q# ](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) és [kataek](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed)teljes listáját.  

> [!NOTE]
> Ez a verzió a projektek fordítását érintő hibát tartalmaz Q# . Azt javasoljuk, hogy frissítsen újabb kiadásra.

## <a name="version-01120042825"></a>0\.11.2004.2825-ös verzió

*Kiadási dátum: 2020. április 30.*

A verzió a következőket tartalmazza:

- Új támogatás az Q# alkalmazásokhoz, amelyek már nem igényelnek C#-vagy Python-gazdagépet. További információ az alkalmazások használatáról Q# : [itt](xref:microsoft.quantum.install.standalone).
- Frissült a kvantum-véletlenszámgenerátor rövid útmutatója, hogy a továbbiakban ne legyen szükség C#- vagy Python-gazdafájlra. A frissített [rövid útmutató](xref:microsoft.quantum.quickstarts.qrng) itt tekinthető meg.
- Teljesítménybeli tökéletesítések a Q# Docker-rendszerképekhez

> [!NOTE]
> Q# az új [`@EntryPoint()`](xref:Microsoft.Quantum.Core.EntryPoint) attribútumot használó alkalmazások jelenleg nem hívhatók meg Python-vagy .net-gazdagép-programokból.
> További információkat a [Python](xref:microsoft.quantum.install.python) és a [.NET közötti együttműködést](xref:microsoft.quantum.install.cs) bemutató útmutatókban talál.

## <a name="version-01120033107"></a>0\.11.2003.3107-es verzió

*Kiadási dátum: 2020. március 31.*

Ez a kiadás jelentős hibajavításokat tartalmaz a 0.11.2003.2506-os verzióhoz.

## <a name="version-01120032506"></a>0\.11.2003.2506-os verzió

*Kiadási dátum: 2020. március 26.*

A verzió a következőket tartalmazza:

- Új támogatás a hozzáférés-módosítóhoz a alkalmazásban – Q# További információ: [fájl-struktúrák](xref:microsoft.quantum.guide.filestructure)
- A .NET Core SDK 3.1-es verziójára frissítve

A [kódtárak](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [fordítók](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [futtatókörnyezetek](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [minták](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) és [Katák ](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) lezárt lekéréses kérelmeinek teljes listáját itt tekintheti meg.  

## <a name="version-01020022610"></a>0\.10.2002.2610-es verzió

*Kiadási dátum: 2020. február 27.*

A verzió a következőket tartalmazza:

- Új Kvantum gépi tanulási kódtár – további információért látogasson el a [QML-dokumentációk oldalára](xref:microsoft.quantum.machine-learning.concepts.intro)
- Hibajavítások Q# , ami akár 10 20x teljesítménybeli növekedést eredményezett a NuGet-csomagok betöltésekor

A [kódtárak](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [fordítók](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [futtatókörnyezetek](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [minták](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) és [Katák ](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) lezárt lekéréses kérelmeinek teljes listáját itt tekintheti meg.  

## <a name="version-01020012831"></a>0\.10.2001.2831-es verzió

*Kiadási dátum: 2020. január 29.*

A verzió a következőket tartalmazza:

- Új Microsoft.Quantum.SDK NuGet-csomag, amely lecseréli a Microsoft.Quantum. Development.Kit NuGet-csomagot új projektek létrehozásakor. A Microsoft.Quantum.Development.Kit NuGet-csomag továbbra is támogatott a meglévő projektek esetében. 
- Az Q# új Microsoft. Quantum. SDK NuGet csomag által engedélyezett fordítóprogram-bővítmények támogatása további információért lásd a githubon, a [fordítóprogram-bővítmények mintáján](https://github.com/microsoft/qsharp-compiler/tree/main/examples/CompilerExtensions) és a [ Q# fejlesztői blogon](https://devblogs.microsoft.com/qsharp/extending-the-q-compiler/) található [dokumentációt](https://github.com/microsoft/qsharp-compiler/tree/main/src/QuantumSdk#extending-the-q-compiler).
- Mostantól támogatott a .NET Core 3.1 – erősen ajánlott a 3.1.100-s verzió telepítése, mert a korábbi .NET Core SDK-verziókkal való fejlesztés hibákat eredményezhet.
- A Microsoft.Quantum.QsCompiler.Experimental alatt új fordítóprogram-transzformációk érhetők el
- Új funkciók a kimeneti állapot vektorok számára HTML formátumbanQ#
- Mostantól támogatott az EstimateFrequencyA a Microsoft.Quantum.Characterization névtérben a Hadamard-művelet és a SWAP tesztek esetében
- A AmplitudeAmplification-névtér mostantól Q# stílus-útmutatót használ

A [kódtárak](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [fordítók](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [futtatókörnyezetek](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [minták](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) és [Katák ](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) lezárt lekéréses kérelmeinek teljes listáját itt tekintheti meg.  

## <a name="version-01019120501"></a>0\.10.1912.0501-es verzió

*Kiadási dátum: 2019. december 5.*

A verzió a következőket tartalmazza:

- Új tesztelési attribútum az Q# egység teszteléséhez, lásd [itt](xref:Microsoft.Quantum.Diagnostics.Test) a frissített API-dokumentációt, [here](xref:microsoft.quantum.guide.testingdebugging) valamint a & hibakeresési útmutatójának frissített tesztelési útmutatóját
- A verem nyomkövetésének hozzáadása a Q# program futási hibája esetén
- Töréspontok támogatása a Visual Studio Code-ban az [OmniSharp C# Visual Studio Code-bővítmény](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) frissítése révén

A [kódtárak](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [fordítók](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [futtatókörnyezetek](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [minták](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) és [Katák ](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) lezárt lekéréses kérelmeinek teljes listáját itt tekintheti meg.  

## <a name="version-01019111607"></a>0\.10.1911.1607-es verzió

*Kiadási dátum: 2019. november 17.*

A verzió a következőket tartalmazza:

- Teljesítményjavítás a [Quantum Katas](https://github.com/Microsoft/QuantumKatas) és a Jupyter Notebook-jegyzetfüzetek esetében

A [kódtárak](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [fordítók](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [futtatókörnyezetek](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [minták](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) és [Katák ](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) lezárt lekéréses kérelmeinek teljes listáját itt tekintheti meg.  


## <a name="version-0101911307"></a>0\.10.1911.307-es verzió

*Kiadási dátum: 2019. november 1.*

A verzió a következőket tartalmazza:

- A Visual Studio Code & Visual Studio Extensions frissítése a nyelvi kiszolgáló önálló végrehajtható fájlként való üzembe helyezéséhez, a .NET Core SDK verziótól való függőség megszüntetéséhez  
- Migrálás a .NET Core 3.0-ba
- A Microsoft.Quantum.Simulation.Core.IOperationFactory kompatibilitástörő változása az új `Fail` metódus bevezetésével. Ez csak a SimulatorBase-en nem túllépő egyéni szimulátorokra van hatással. További részletekért [tekintse meg a lekéréses kérelmet a GitHubon](https://github.com/microsoft/qsharp-runtime/pull/59).
- Az elavult attribútumok új támogatása

A [kódtárak](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [fordítók](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [futtatókörnyezetek](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [minták](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) és [Katák ](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) lezárt lekéréses kérelmeinek teljes listáját itt tekintheti meg.  

## <a name="version-0919093002"></a>0\.9.1909.3002-es verzió

*Kiadási dátum: 2019. szeptember 30.*

A verzió a következőket tartalmazza:

- Q#A kód befejezésének új támogatása a Visual studio 2019-ben (16,3 & újabb verziók) & Visual Studio Code-ban
- Új [Quantum Kata](https://github.com/Microsoft/QuantumKatas) a kvantumhozzáadókhoz

A [kódtárak](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [fordítók](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [futtatókörnyezetek](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [minták](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) és [Katák ](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) lezárt lekéréses kérelmeinek teljes listáját itt tekintheti meg.  

## <a name="version-09-packagereference-0919082902"></a>0\.9-es verzió ( *PackageReference 0.9.1908.2902* )

*Kiadási dátum: 2019. augusztus 29.*

A verzió a következőket tartalmazza:

- A következőhöz tartozó [ragozott utasítások](xref:microsoft.quantum.guide.operationsfunctions#conjugations) új támogatása: Q#
- Új kódműveletek a fordítóban, például: csere, dokumentáció hozzáadása és a tömbelemek egyszerű frissítése
- Új telepítési sablon és új projektparancsok a Visual Studio Code-bővítményhez
- Az ApplyIf kombinátor új változatai, például a [Microsoft.Quantum.Canon.ApplyIfOne](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- További Jupyter Notebooksra konvertált [Quantum Katák](https://github.com/Microsoft/QuantumKatas)
- A Visual Studio-bővítményhez most már Visual Studio 2019 szükséges

A [kódtárak](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [fordítók](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [futtatókörnyezetek](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [minták](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) és [Katák ](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) lezárt lekéréses kérelmeinek teljes listáját itt tekintheti meg.  

A módosítások és a meglévő programok frissítésére vonatkozó utasítások összefoglalását itt olvashatja.  További információ ezekről a változásokról a [ Q# fejlesztői blogon](https://devblogs.microsoft.com/qsharp).

## <a name="version-08-packagereference-0819071701"></a>0\.8-as verzió ( *PackageReference 0.8.1907.1701* )

*Kiadási dátum: 2019. július 12.*

A verzió a következőket tartalmazza:

- Új indexelési helyeket a szeletelőtömbökhöz. További információért [lásd a nyelvi referenciát](xref:microsoft.quantum.guide.expressions#array-slices).
- A [Microsoft Container Registryban](https://github.com/microsoft/ContainerRegistry)tárolt Docker-k [ Q# További információt az I adattárban](https://github.com/microsoft/iqsharp/blob/main/README.md) talál.
- A [nyomkövetés-szimulátor](xref:microsoft.quantum.machines.qc-trace-simulator.intro) kompatibilitástörő változása, a konfigurációs beállítások frissítése, névváltozások; a frissített nevek a [.NET API-tallózóban](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulatorconfiguration) találhatók.

A [kódtárak](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) és a [minták](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) lezárt lekéréses kérelmeinek teljes listáját itt tekintheti meg.  

## <a name="version-07-packagereference-0719053109"></a>0\.7-es verzió ( *PackageReference 0.7.1905.3109* )

*Kiadási dátum: 2019. május 31.*

A verzió a következőket tartalmazza:
- Hozzáadás a Q# nyelvhez, 
- a kémiai kódtár frissítései, 
- új numerikus kódtár.

A [kódtárak](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) és a [minták](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) lezárt lekéréses kérelmeinek teljes listáját itt tekintheti meg.  

A módosítások és a meglévő programok frissítésére vonatkozó utasítások összefoglalását itt olvashatja.  További információ ezekről a változásokról a [ Q# fejlesztői blogon](https://devblogs.microsoft.com/qsharp).

### <a name="no-locq-language-syntax"></a>Q# nyelvi szintaxis
Ez a kiadás új Q# nyelvi szintaxist helyez el:
* Elnevezett elemek hozzáadása a [felhasználó által meghatározott típusokhoz](xref:microsoft.quantum.guide.types#user-defined-types).  
* A felhasználó által meghatározott típusú konstruktorok most már függvényként használhatók.
* A [másolás és frissítéshez](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions), valamint az [alkalmazás és újrafelhasználás](xref:microsoft.quantum.guide.variables#rebinding-of-mutable-symbols) új támogatása a felhasználó által meghatározott típusokban.
* A [sikerességig ismétlődő](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop) ciklusok javítási blokkja már opcionális.
* A while ciklusok használata már támogatott a függvényekben (a műveletekben nem).

### <a name="library"></a>Kódtár 

Ez a kiadás egy új numerikus kódtárat is tartalmaz: Tudjon meg többet az [új numerikus kódtár használatáról](xref:microsoft.quantum.numerics.usage), és próbálja ki az [új mintákat](https://github.com/microsoft/quantum/tree/main/Numerics).  [102. lekéréses kérelem](https://github.com/Microsoft/QuantumLibraries/pull/102).  

Ez a kiadás újrarendszerezi, kibővíti és frissíti a kémiai kódtárat:
* Javítja az összetevők modularitását, a bővíthetőséget, és az általános kódtisztítást.  [58. lekéréses kérelem](https://github.com/microsoft/QuantumLibraries/pull/58).
* Támogatást nyújt a [többreferenciás hullámfüggvényekhez](xref:microsoft.quantum.chemistry.concepts.multireference) – mind a ritka többreferenciás hullámfüggvényekhez, mind pedig az egységes kötésű fürthöz.  [110. lekéréses kérelem](https://github.com/Microsoft/QuantumLibraries/pull/110).
* (Köszönjük!) [1QBit](https://1qbit.com)-közreműködő ([@valentinS4t1qbit](https://github.com/ValentinS4t1qbit)): Energiaértékelés variációs kísérletező feltevés segítségével. [120. lekéréses kérelem](https://github.com/Microsoft/QuantumLibraries/pull/120).
* A [Broombridge-séma](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) frissítése az új [0.2-es verzióra](xref:microsoft.quantum.libraries.chemistry.schema.spec_v_0_2), egységes kötésű fürtspecifikáció hozzáadásával. [65. probléma](https://github.com/microsoft/QuantumLibraries/issues/65).
* Python-együttműködés hozzáadása a kémiai kódtárbeli függvényekhez. Próbálja ki ezt a [mintát](https://github.com/microsoft/Quantum/tree/main/Chemistry/PythonIntegration). [53. probléma](https://github.com/microsoft/QuantumLibraries/issues/53) [110. lekéréses kérelem](https://github.com/Microsoft/QuantumLibraries/pull/110).

## <a name="version-061905"></a>0\.6.1905-ös verzió

*Kiadási dátum: 2019. május 3.*

A verzió a következőket tartalmazza:
- módosítja a Q# nyelvet, 
- a Quantum Development Kit kódtárainak átszervezését, 
- új mintákat és 
- javításokat.  Több, [kódtárakra](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) és [mintákra vonatkozó](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) lekéréses kérelmet lezárt.  

A módosítások és a meglévő programok frissítésére vonatkozó utasítások összefoglalását itt olvashatja.  A változásokról a devblogs.microsoft.com/qsharp címen olvashat bővebben.

### <a name="no-locq-language-syntax"></a>Q# nyelvi szintaxis
Ez a kiadás új Q# nyelvi szintaxist helyez el:
* [Rövidített mód hozzáadása a kvantumműveletek](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations) (vezérlés és mellékletek) specializációinak `+` operátorokkal történő kifejezésére.  A régi szintaxis elavult.  A régi szintaxisok egyikét használó programok (például az `: adjoint`) továbbra is működni fognak, de egy fordítási idővel kapcsolatos figyelmeztetés jön létre.  
* [Másolásra és frissítésre](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) szolgáló új `w/` operátor, amely egy meglévő tömb módosításaként fejezi ki egy tömb létrehozását.
* Gyakori [alkalmazási és frissítési utasítások](xref:microsoft.quantum.guide.variables#rebinding-of-mutable-symbols) hozzáadása, például `+=`, `w/=`.
* Új lehetőség az [open utasításokban](xref:microsoft.quantum.guide.filestructure#open-directives) használt névterek rövid nevének megadására.

Ebben a kiadásban a tömbelemek már nem adhatók meg a set utasítások bal oldalán.  Ennek az az oka, hogy az a szintaxis azt sugallja, hogy a tömbök módosíthatók, pedig a művelet eredménye valójában mindig egy új, módosított tömb létrehozása volt.  Ehelyett fordítói hiba jön létre azzal a javaslattal, hogy az új `w/` másolási és frissítési operátort használja ugyanazon eredmény eléréséhez.  

### <a name="library-restructuring"></a>A kódtár átrendezése
Ez a kiadás átrendezi a kódtárakat annak érdekében, hogy következetesen növekedhessenek:
* A Microsoft.Quantum.Primitive névtér nevét Microsoft.Quantum.Intrinsic értékre módosítja.  Ezeket a műveleteket a célgép implementálja.  A Microsoft.Quantum.Primitive névtér elavult.  A futtatókörnyezeti figyelmeztetés jelzi, amikor a programok elavult neveket használó műveleteket és függvényeket hívnak meg.

* Átnevezi a Microsoft.Quantum.Canon csomagot Microsoft.Quantum.Standard névre.  Ez a csomag a legtöbb programhoz közös névtereket tartalmaz Q# .  Az érintett műveletek közé tartoznak az alábbiak:  
    - Microsoft.Quantum.Canon a gyakori műveletekhez
    - Microsoft.Quantum.Arithmetic az általános célú aritmetikai műveletekhez
    - Microsoft.Quantum.Preparation a qubitek állapotának előkészítésére használt műveletekhez
    - Microsoft.Quantum.Simulation a szimulációs funkciókhoz

Ezzel a módosítással azok a programokban, amelyek egyetlen, a Microsoft.Quatum.Canon névtérhez tartozó open utasítás szerepel, felépítési hibák jelentkezhetnek, ha a program a másik három új névtérre áthelyezett műveletekre hivatkozik.  A probléma megoldásának egyszerű módja a három új névtér további open utasításainak hozzáadása.  

* Több névtér elavult, mivel a belső műveletek más névterekre kerültek át. Az ezeket a névtereket használó programok továbbra is működni fognak, a fordítási idővel kapcsolatos figyelmeztetés pedig megnevezi azt a névteret, ahol a művelet meg van határozva.  

* A Microsoft.Quantum.Arithmetic névtér normalizálva lett a felhasználó által meghatározott <xref:Microsoft.Quantum.Arithmetic.LittleEndian> típus használatára. Használja a [BigEndianAsLittleEndian](xref:Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian) függvényt a növekvő bájtsorrendűvé történő átalakításhoz.  

* Számos callables (functions és Operations) neve módosítva lett, hogy megfeleljen a [ Q# stílus útmutatójának](xref:microsoft.quantum.contributing.style).  A régi meghívható nevek elavultak.  A régi meghívható neveket használó programok továbbra is működnek, de megjelenítenek egy fordítási idővel kapcsolatos figyelmeztetést. 

### <a name="new-samples"></a>Új minták

Felvettünk egy [mintát az Q# F # illesztőprogram használatával](https://github.com/Microsoft/Quantum/pull/164).  

**Köszönjük** a http://github.com/Microsoft/Quantum címen található nyíltforráskód-bázis következő közreműködőjének. Ezek a hozzájárulások jelentősen felveszik a kód gazdag mintáit Q# :

* Mathias Soeken ([@msoeken](https://github.com/msoeken)): Oracle-függvények szintézise. [135. lekéréses kérelem](https://github.com/Microsoft/Quantum/pull/135).

### <a name="migrating-existing-projects-to-061905"></a>Meglévő projektek migrálása a 0.6.1905-ös verzióra.

Tekintse meg a [telepítési útmutatót](xref:microsoft.quantum.install) a QDK frissítéséhez.
  
Ha meglévő Q# projektjei a Quantum Development Kit 0,5-es verziójával rendelkeznek, a következő lépésekkel telepítheti át ezeket a projekteket a legújabb verzióra.

1. A projekteket sorrendben kell frissíteni.  Ha több projektet tartalmazó megoldással rendelkezik, a hivatkozás sorrendjében frissítse az egyes projekteket.
2. A parancssorból futtassa a parancsot `dotnet clean` az összes meglévő bináris és köztes fájl eltávolításához.
3. Egy szövegszerkesztőben szerkessze a. csproj fájlt, és módosítsa minden Microsoft.Quantum `PackageReference` verzióját a 0.6.1904-es verzióra, és módosítsa a Microsoft.Quantum.Canon csomagnevet Microsoft.Quantum.Standard értékre, például:

    ```xml
    <PackageReference Include="Microsoft.Quantum.Standard" Version="0.6.1905.301" />
    <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.6.1905.301" />
    ```
4. Futtassa a következő parancsot a parancssorból: `dotnet msbuild`  
5. A parancs futtatása után előfordulhat, hogy a fent felsorolt módosítások miatt továbbra is manuálisan kell megoldania a hibákat.  Sok esetben ezeket a hibákat az IntelliSense is megjeleníti a Visual Studióban vagy a Visual Studio Code-ban.
    - Nyissa meg a projekt gyökérmappáját vagy az azt tartalmazó megoldást a Visual Studio 2019-ben vagy a Visual Studio Code-ban.
    - Miután megnyitotta a. QS fájlt a szerkesztőben, látnia kell a Q# nyelvi bővítmény kimenetét a kimeneti ablakban.
    - Miután a projekt sikeresen betöltődött (ez a kimeneti ablakban látható), nyissa meg az egyes fájlokat, és manuálisan hárítsa el az összes fennmaradó problémát.

> [!NOTE]
> * A 0.6-os kiadásban a Quantum Development Kithez mellékelt nyelvi kiszolgáló csak egy munkaterületet támogat.
> * Ha a Visual Studio Code-ban szeretne használni egy projektet, nyissa meg a gyökérmappát, amely tartalmazza a magát a projektet és az összes hivatkozott projektet.   
> * Ahhoz, hogy a Visual Studióban használhasson egy megoldást, a megoldásban foglalt összes projektnek a megoldás mappájában vagy valamelyik almappájában kell lennie.  
> * A 0.6-os és újabb verzióba migrált projektek és a régebbi csomagverziókat használó projektek közötti hivatkozások **nem** támogatottak.

## <a name="version-051904"></a>0\.5.1904-es verzió

*Kiadási dátum: 2019. április 15.*

A verzió hibajavításokat tartalmaz.


## <a name="version-051903"></a>0\.5.1903-as verzió

*Kiadási dátum: 2019. március 27.*

A verzió a következőket tartalmazza:

- Támogatást nyújt a Jupyter Notebookhoz, amely nagyszerű lehetőséget nyújt a megismerésére Q# .  [Nézze meg az új Jupyter Notebook-mintákat, amelyekből megtudhatja, hogyan írhat saját jegyzetfüzeteket](xref:microsoft.quantum.install). 

- Egész szám hozzáadására használható aritmetikai műveletet ad hozzá a Quantum Canon-kódtárhoz.  Ez a Jupyter-notebook [ismerteti az egész számok új összeadóinak használatát](https://github.com/microsoft/Quantum/blob/main/samples/arithmetic/AdderExample.ipynb).

- A közösség által jelentett DumpRegister probléma hibajavítása ([148.](https://github.com/Microsoft/Quantum/issues/148)).

- Új visszatérési képesség a [using utasításokból](xref:microsoft.quantum.guide.qubits#allocating-qubits).

- Átalakított [útmutató az első lépésekhez](xref:microsoft.quantum.install).


## <a name="version-051902"></a>0\.5.1902-es verzió

*Kiadási dátum: 2019. február 27.*

A verzió a következőket tartalmazza:

- Támogatást nyújt a platformfüggetlen Python-gazdagéphez.  A `qsharp` Python-csomaggal könnyedén szimulálhatja a Q# műveleteket és a függvényeket a Pythonon belülről. A [Python-együttműködésről](xref:microsoft.quantum.install) itt talál további információt. 

- A Visual Studio és a Visual Studio Code már támogatja a szimbólumok (pl. függvények és műveletek) átnevezését.

- A Visual Studio-bővítmény már telepíthető a Visual Studio 2019-hez.

## <a name="version-041901"></a>0\.4.1901-es verzió

*Kiadási dátum: 2019. január 30.*

A verzió a következőket tartalmazza:

- támogatja a BigInt nevű új egyszerű típust, amely egy tetszőleges méretű előjeles egész számot jelöl.  A [BigInt típusról](xref:microsoft.quantum.guide.types) itt talál további információt.
- hozzáadja a Toffoli nevű új, különleges, gyors szimulátort ad hozzá, amely nagy számú qubittel képes X-, CNEM- és több elem által vezérelt X kvantumműveleteket szimulálni.  A [Toffoli-szimulátorról](xref:microsoft.quantum.machines.toffoli-simulator) itt talál további információt.
- egy egyszerű erőforrás-kalkulátort ad hozzá, amely a művelet adott példányának a kvantum-számítógépen való futtatásához szükséges erőforrásokat becsüli Q# meg.  Az [erőforrásbecslőről](xref:microsoft.quantum.machines.resources-estimator) itt talál további információt.


## <a name="version-0318112802"></a>0\.3.1811.2802-es verzió

*Kiadási dátum: 2018. november 28.*

Annak ellenére, hogy a VS Code-bővítményünk nem használta, megjelölték és eltávolították a piactérről az `event-stream` NPM-csomaghoz kapcsolódó [bővítmények végleges törlése](https://code.visualstudio.com/blogs/2018/11/26/event-stream) során. Ez a verzió eltávolítja az összes olyan futtatókörnyezeti függőséget, amely miatt a bővítmény riasztásokat válthatna ki.

Ha korábban már telepítette a bővítményt, akkor újra telepítenie kell. Ehhez keresse fel a Visual Studio piacterét, és kattintson a Telepítés gombra a [Visual Studio Code-hoz készült Microsoft Quantum Development Kit](vscode:extension/quantum.quantum-devkit-vscode) oldalán. Elnézését kérjük a kellemetlenségért.


## <a name="version-0318111511"></a>0\.3.1811.1511-es verzió

*Kiadási dátum: 2018. november 20.*

Ez a kiadás kijavít egy olyan hibát, amely miatt néhány felhasználónak nem sikerült betöltenie a Visual Studio-bővítményt.

## <a name="version-031811203"></a>0\.3.1811.203-as verzió

*Kiadási dátum: 2018. november 2.*

Ez a kiadás hibajavításokat tartalmaz, többek között a következőeket:

* A(z) `DumpMachine` meghívása bizonyos helyzetekben megváltoztathatta a szimulátor állapotát.
* Eltávolítottuk a fordítási figyelmeztetéseket, amelyek a projektek a .NET Core 2.1.403-asnál korábbi verzióinak használatával történő létrehozásakor jelentek meg.
* Átláthatóbbá tettük a dokumentációt, különös tekintettel a VS Code-ban vagy Visual Studióban az egérrel való rámutatáskor megjelenő elemleírásokra.

## <a name="version-0318102508"></a>0\.3.1810.2508-as verzió

*Kiadási dátum: 2018. október 29.*

Ez a kiadás új nyelvi funkciókat és továbbfejlesztett fejlesztői élményt nyújt:

* Ez a kiadás tartalmaz egy nyelvi kiszolgálót Q# , valamint a Visual Studio és a Visual Studio Code ügyfél-integrációját. Ezzel elérhetővé válnak az IntelliSense új funkciói, valamint a valós idejű gépelési visszajelzés a hibák és figyelmeztetések hullámvonalas aláhúzása révén. 
* A frissítés általánosságban véve nagy mértékben javítja a diagnosztikai üzeneteket, egyszerűen elérhetővé teszi a diagnosztikákat és pontosan meghatározza azok tartományait, valamint az egérrel való rámutatással további részletek jelenít meg.
* A Q# nyelv olyan módon lett kiterjesztve, amely egységesíti a fejlesztők számára a gyakori műveleteket, valamint a nyelvi funkciók új fejlesztéseit a nagy teljesítményű expressz kvantum-számításokhoz.  Ebben a kiadásban a nyelvnek van néhány feltört változása Q# .   

Ez a kiadás egy új kvantumkémiai kódtárat is tartalmaz:

* A kémiai kódtár új Hamilton-szimulációs funkciókat tartalmaz, beleértve a következőket:
    - Tetszőleges páros sorrend Trotter–Suzuki-integrátorokkal a nagyobb szimulációs pontosságért.
    - Kvantumbites szimulációs módszer kémiaspecifikus optimalizálással a $T$-kapu összetettségének csökkentéséhez.
* Az új, Broombridge-sémának nevezett nyílt forráskódú séma (a név egy [nevezetességére](https://en.wikipedia.org/wiki/Broom_Bridge) utal, amely a Hamilton-operátorok „születési helyeként” van számon tartva) bevezetése a molekulák ábrázolásának importálására, valamint azok szimulálására.
* Több, a Broombridge-sémával definiált kémiai ábrázolás érhető el.  Ezeket a modelleket a [NWChem](http://www.nwchem-sw.org/), egy nyílt forráskódú, nagy teljesítményű számítási kémiai eszköz hozta létre.
* Az oktatóanyagok és példák bemutatják a kémiai kódtár és a Broombridge-adatmodellek használatának módját a következő alkalmazási területeken:
    - Egyszerű Hamilton-operátorok létrehozása a kémiai kódtár használatával
    - A lítium-hidrid alap és gerjesztett energiáinak vizualizációja fázisbecslés használatával.
    - Erőforrás-becslések végrehajtása kvantumkémiai szimulációkhoz.
    - A Broombridge-séma által ábrázolt molekulák energiaszintjének becslése.
* A dokumentáció ismerteti, hogyan használható a NWChem további kémiai modellek létrehozásához a kvantum-szimulációhoz a használatával Q# .

További információ a [Quantum Development Kit kémiai kódtáráról](xref:microsoft.quantum.chemistry.concepts.intro).

Az új kémiai kódtárral egy új GitHub-adattárba, a [Microsoft/QuantumLibraries](https://github.com/Microsoft/QuantumLibraries) adattárba különítjük el a kódtárakat.  A példák a [Microsoft/Quantum](https://github.com/Microsoft/Quantum) adattárban maradnak.  Örömmel fogadjuk a hozzájárulásokat mindkét adattárhoz!

Ez a kiadás a közösség által jelentett problémákkal kapcsolatos hibajavításokat és funkciókat tartalmaz:

* IntelliSense for Q# ? ([UserVoice](https://quantum.uservoice.com/forums/906943/suggestions/32656918)).
* .qs fájlok ([UserVoice](https://quantum.uservoice.com/forums/906097/suggestions/32593049)).
* Javított hibaüzenet az if utasításokban használt rövidített kapcsos zárójelek esetében ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/34718518)).
* A rekordok dekonstrukciójának támogatása változtatható (újra)kötések esetén ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/35020444)).
* Hiba a megadott BitFlipCode futtatásakor ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546)).
* A H2SimulationGUI időnként nagy csúcsokat jelenít meg ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34668370)).

### <a name="community-contributions"></a>Közösségi hozzájárulások

**Köszönjük** a http://github.com/Microsoft/Quantum címen található nyíltforráskód-bázisunk következő közreműködőinek: Ezek a hozzájárulások jelentősen felveszik a kód gazdag mintáit Q# :

* Rolf Huisman ( [@RolfHuisman](https://github.com/RolfHuisman) ): javította a QASM/ Q# fejlesztők számára nyújtott élményt azáltal, hogy QASM hoz létre a Q# fordítónak. [58. lekéréses kérelem](https://github.com/Microsoft/Quantum/pull/58).

* Andrew Helwer ([@ahelwer](https://github.com/ahelwer)):  Létrehozott egy CHSH-játékot implementáló példát, amely egy nemlokalitással kapcsolatos kvantumjáték.  [84. lekéréses kérelem](https://github.com/Microsoft/Quantum/pull/84).

Köszönjük továbbá Rohit Gupta ([@guptarohit](https://github.com/guptarohit),[PR #90](https://github.com/Microsoft/quantum/pull/90)), Tanaka Takayoshi ([@tanaka-takayoshi](https://github.com/tanaka-takayoshi),[PR #289](https://github.com/MicrosoftDocs/quantum-docs-pr/pull/289)) és Lee James O’Riordan ([@mlxd](https://github.com/mlxd),[PR #96](https://github.com/Microsoft/Quantum/pull/96)) munkáját, amellyel a dokumentáció, a helyesírás és az elírások kijavítása révén jobbá tették a tartalmakat mindannyiunk számára. 

## <a name="version-021809701"></a>0\.2.1809.701-es verzió

*Kiadási dátum: 2018. szeptember 10.*

Ez a kiadás a közösség által jelentett problémákkal kapcsolatos hibajavításokat tartalmaz. A következőket tartalmazza:

* Az eltolási operátor nem használható ([GitHub](https://github.com/Microsoft/Quantum/issues/75)).
* A(z) `DumpMachine` / `DumpRegister` a konzolon való megjelenítéskor hibába ütközik a következőn: `QCTraceSimulator` ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34709680)).
* 0 qubit lefoglalásának engedélyezése ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34768069-allow-allocating-0-qubits)).
* A(z) `AssertQubitState` explicit Complex() hívást igényel ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34713733-assertqubitstate-requires-explicit-complex-call)).
* A(z) `Measure` művelet macOS rendszeren minden esetben a következőt adja vissza: `One` ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546)).

Köszönjük! 

## <a name="version-0218063001"></a>0\.2.1806.3001-es verzió

*Kiadási dátum: 2018. június 30.*

Ez a kiadás csak egy gyors megoldás a [githubon jelentett probléma #48](https://github.com/Microsoft/Quantum/issues/48) (a Q# fordítás meghiúsul, ha a Felhasználónév üres helyet tartalmaz). Kövesse a(z) `0.2.1806.1503` frissítési utasításait a megfelelő új verzió esetében (`0.2.1806.3001-preview`).

## <a name="version-0218061503"></a>0\.2.1806.1503-as verzió

*Kiadási dátum: 2018. június 22.*

Ez a kiadás számos közösségi hozzájárulást tartalmaz, valamint továbbfejlesztett hibakeresési élményt és jobb teljesítményt nyújt.  Ezek a következők:

* Teljesítménybeli javítások a QuantumSimulator célszámítógép kis- és nagyméretű szimulációi esetében.
* Továbbfejlesztett hibakeresési funkciók.
* A közösség által készített hibajavítások, új segédfüggvények, műveletek és új minták.

### <a name="performance-improvements"></a>Teljesítménnyel kapcsolatos fejlesztések

Ez a frissítés jelentős teljesítménybeli javításokat tartalmaz a nagy és kis mennyiségű qubitek szimulálására minden célszámítógépen.  A javulás egyértelműen látható a H<sub>2</sub> szimulációban, amely a Quantum Development Kit egyik standard mintája.

### <a name="improved-debugging-functionality"></a>Továbbfejlesztett hibakeresési funkciók

Ez a frissítés új funkciókkal bővíti a hibakeresést:
* Két új műveletet adtunk hozzá (@"microsoft.quantum.extensions.diagnostics.dumpmachine" és @"microsoft.quantum.extensions.diagnostics.dumpregister"), amelyek hullámfüggvény-információkat adnak a célkvantumgépről egy adott időpontra vonatkozóan.  
* A $\ket{1}$ egyetlen qubiten való mérésének valószínűsége mostantól automatikusan megjelenik a Visual Studióban a QuantumSimulator célgépének hibakeresési ablakában.
* Továbbfejlesztettük a változó tulajdonságok megjelenítését a Visual Studio **Automatikus értékek** és **Helyi változók** hibakeresési ablakaiban. 

További információ a [tesztelésről és hibakeresésről](xref:microsoft.quantum.guide.testingdebugging).

### <a name="community-contributions"></a>Közösségi hozzájárulások

A Q# coder-Közösség egyre nő, és örömmel látjuk, hogy az első felhasználó hozzájárult a könyvtárak és a minták beküldéséhez a nyílt forráskód alapjaként http://github.com/Microsoft/quantum .  **Nagyon szépen köszönjük** a következő közreműködőknek:
* Mathias Soeken ([@msoeken](https://github.com/msoeken)): egy olyan mintát hozott létre, amely egy átalakításon alapuló logikaiszintézis-módszert definiál, amely Toffoli-hálózatokat hoz létre egy adott permutáció megvalósításához. A kód teljes egészében a Q# functions és a műveletekben van írva.  [41. lekéréses kérelem](https://github.com/Microsoft/Quantum/pull/41).
* RolfHuisman ( [@RolfHuisman](https://github.com/RolfHuisman) ): a Microsoft MVP Rolf Huisman egy olyan mintát hozott létre, amely a kód alapján létrehoz egy olyan, korlátozott számú programhoz tartozó QASM-kódot, amely Q# nem rendelkezik klasszikus vezérlési folyamattal és korlátozott kvantum-műveletekkel. [59. lekéréses kérelem](https://github.com/Microsoft/Quantum/pull/59)
* Sarah Kasier ([@crazy4pi314](https://github.com/crazy4pi314)): a kódbázis továbbfejlesztésében nyújtott segítséget egy vezérelt műveletekhez való kódtárfüggvény feltöltésével. [53. lekéréses kérelem](https://github.com/Microsoft/Quantum/pull/53)
* Jessica Lemieux ([@Lemj3111](https://github.com/Lemj3111)): új egységteszteket hozott létre és kijavította a következőt: @"microsoft.quantum.canon.quantumphaseestimation".  [54. lekéréses kérelem](https://github.com/Microsoft/Quantum/pull/54)
* Tama McGlinn ([@TamaHobbit](https://github.com/TamaHobbit)): eltávolította a Teleportálás minta felesleges elemeit a QuantumSimulator-példány elvetésének biztosításával. [20. lekéréses kérelem](https://github.com/Microsoft/Quantum/pull/20)

Továbbá hálás **köszönet** a Microsoft kereskedelmi mérnöki szolgáltatási csapatának szoftvermérnökeinek, akik értékes módosításokat hajtottak végre a dokumentáción a Hackathon során.  Az általuk végrehajtott változtatások nagyban javították az átláthatóságot és a bevezetési élményt mindannyiunk számára:
* Sascha Corti
* Mihaela Curmei
* John Donnelly
* Kirill Logachev
* Jan Pospisil
* Anita Ramanan
* Frances Tibble
* Alessandro Vozza

### <a name="update-existing-projects"></a>Létező projektek frissítése

Ez a kiadás teljes mértékben visszafelé kompatibilis. Egyszerűen frissítse a projektek NuGet-csomagját a(z) `0.2.1806.1503-preview` verzióra, majd hajtson végre **teljes újraépítést** , hogy biztosan újra létrejöjjön minden köztes fájl.

A Visual Studióban kövesse a [csomagok frissítésére](https://docs.microsoft.com/nuget/tools/package-manager-ui#updating-a-package) vonatkozó általános utasításokat.

A projektsablonok parancssorból való frissítéséhez futtassa az alábbi parancsot:
```
dotnet new -i "Microsoft.Quantum.ProjectTemplates::0.2.1806.1503-preview"
```

A parancs futtatása után a(z) `dotnet new <project-type> -lang Q#` használatával létrehozott új projektek automatikusan a Quantum Development Kit jelen verzióját fogják használni.

Egy létező projekt a legújabb verzió használatára való frissítéséhez futtassa az alábbi parancsot a könyvtárból minden projekt esetében:

```
dotnet add package Microsoft.Quantum.Development.Kit -v "0.2.1806.1503-preview"
dotnet add package Microsoft.Quantum.Canon -v "0.2.1806.1503-preview"
```

Ha egy meglévő projekt XUnit-integrációt is használ az egységteszteléshez, akkor egy hasonló parancs használatával az a csomag is frissíthető:
```
dotnet add package Microsoft.Quantum.Xunit -v "0.2.1806.1503-preview"
```

A tesztprojekt által használt XUnit verziójától függően előfordulhat, hogy az XUnitot is frissítenie kell a 2.3.1-es verzióra:
```
dotnet add package xunit -v "2.3.1" 
```

A frissítés után mindenképpen távolítsa el az előző verzió által létrehozott összes ideiglenes fájlt a következő módon:
```
dotnet clean 
```

### <a name="known-issues"></a>Ismert problémák

Nincsenek további ismert problémák.


## <a name="version-0218022202"></a>0\.2.1802.2202-es verzió

*Kiadási dátum: 2018. február 26.*

Ez a kiadás támogatást nyújt a különböző platformokon történő fejlesztéshez, a nyelvi együttműködéshez és a teljesítménybeli továbbfejlesztéshez. Ezek a következők:

- A macOS- és Linux-alapú fejlesztés támogatása. 
- Kompatibilitás a .NET Core-ral, beleértve a Visual Studio Code támogatását minden platformon.
- Teljes nyílt forráskódú licenc a Quantum Development Kit-kódtárakhoz.
- Továbbfejlesztett szimulációs teljesítmény a 20 vagy több qubitet igénylő projektek esetén.
- Együttműködési lehetőség a Python nyelvvel (az előzetes kiadás elérhető Windows rendszeren).

### <a name="net-editions"></a>.NET-kiadások

A .NET platform két különböző kiadásban érhető el: a .NET Framework, amely része a Windows operációs rendszernek, illetve a nyílt forráskódú .NET Core, amely Windows, macOS és Linux rendszereken érhető el.
Ebben a kiadásban a Quantum Development Kit legnagyobb része kódtárakként érhető el a .NET Standardhoz, amelyek a Frameworkben és a Core-ban is elérhető osztályok készlete.
Ezek a kódtárak ezért kompatibilisek mind a .NET Framework, mind a .NET Core legújabb verzióival.

Így a Quantum Development Kit használatával írt projektek lehető legnagyobb szintű hordozhatóságának elősegítése érdekében azt javasoljuk, hogy a Quantum Development Kit használatával írt kódtárprojektek a .NET Standardot, a konzolalkalmazások pedig a .NET Core-t célozzák.
Mivel a Quantum Development Kit korábbi kiadásai csak a .NET Frameworköt támogatták, lehetséges, hogy migrálnia kell a meglévő projektjeit. Ennek részletes leírását az alábbiakban találja.

### <a name="project-migration"></a>Projekt migrálása

A Quantum Development Kit korábbi verzióival létrehozott projektek továbbra is működni fognak, feltéve, hogy nem frissíti az általuk használt NuGet-csomagokat. A meglévő kód új verzióba történő migrálásához hajtsa végre a következő lépéseket:
1. Hozzon létre egy új .NET Core-projektet a megfelelő típusú Q# Project sablon (alkalmazás, könyvtár vagy tesztelési projekt) használatával.
2. Másolja a meglévő .qs és .cs/.fs fájlokat a régi projektből az új projektbe (a Hozzáadás > Meglévő elem lehetőség használatával). Ne másolja át az AssemblyInfo.cs fájlt.
3. Hozza létre és futtassa az új projektet.

Vegye figyelembe, hogy a Microsoft.Quantum.Canon névtérben található RandomWalkPhaseEstimation művelet a [Microsoft/Quantum-NC](https://github.com/microsoft/quantum-nc) adattár Microsoft.Research.Quantum.RandomWalkPhaseEstimation névterébe lett áthelyezve.

### <a name="known-issues"></a>Ismert problémák

- A `--filter` lehetőség, hogy `dotnet test` nem működik megfelelően a-ben írt tesztek esetében Q# .
  Ennek eredményeképpen az egyes egységekhez tartozó tesztek nem futtathatók a Visual Studio Code-ban; azt javasoljuk `dotnet test` , hogy a parancssorból futtassa újra az összes tesztet.

## <a name="version-0118011707"></a>0\.1.1801.1707-es verzió

*Kiadási dátum: 2018. január 18.*

Ez a kiadás a közösség által jelentett problémák javítását tartalmazza. Konkrétabban:

- A szimulátor mostantól a korai, nem AVX-kompatibilis CPU-kkal is működik.
- A regionális decimális beállítások nem okozzák Q# , hogy az elemző sikertelen lesz.
- A `SignD` primitív művelet eredménye mostantól `Double` helyett `Int` értéket ad vissza.


## <a name="version-011712901"></a>0\.1.1712.901-es verzió

*Kiadási dátum: 2017. december 11.*

### <a name="known-issues"></a>Ismert problémák

#### <a name="hardware-and-software-requirements"></a>Hardver- és szoftverkövetelmények

- A Quantum Development Kit részét képező szimulátor futtatásához 64 bites Microsoft Windows használata szükséges.
- A Microsoft a Quantum Development Kit részeként telepített kvantumszimulátora az Advanced Vector Extensions (AVX) bővítményeket használja, és egy AVX-kompatibilis processzor használatát igényli. Az AVX-et a 2011 első negyedévében gyártott (Sandy Bridge) vagy későbbi Intel-processzorok támogatják. Vizsgáljuk a korábbi CPU-k támogatásának lehetőségét is. Az ezzel kapcsolatos részletek bejelentésére a későbbiekben kerülhet sor.

#### <a name="project-creation"></a>Projekt létrehozása

- A használni kívánt megoldás (. SLN) létrehozásakor Q# a megoldásnak a megoldás egyes projektjeinél (. csproj) nagyobbnak kell lennie. Új megoldás létrehozásakor ez úgy biztosítható, ha bejelöli a „Könyvtár létrehozása a megoldásnak” jelölőnégyzetet az „Új projekt” párbeszédpanelen. Ha ezt nem teszi meg, akkor a Quantum Development Kit NuGet-csomagjait manuálisan kell telepíteni.

#### Q#

- Az IntelliSense nem jeleníti meg a kód megfelelő hibáit Q# . Győződjön meg arról, hogy a Visual Studio Hibalista felépítési hibákat jelenít meg a helyes Q# hibák megtekintéséhez. Azt is vegye figyelembe, hogy Q# a hibák addig nem jelennek meg, amíg el nem végzi a létrehozást.
- Ha egy módosítható tömböt használ egy részleges alkalmazásban, az nem várt viselkedést eredményezhet.
- Ha egy nem módosítható tömböt egy módosítható tömbhöz köt (a = b, ahol a „b” egy módosítható tömb), az nem várt viselkedést eredményezhet.
- A profilkészítés, a kódok lefedettsége és más VS beépülő modulok nem mindig számítanak Q# pontosan a soroknak és a blokkoknak.
- A Q# fordító nem érvényesíti az interpolált karakterláncokat. C# fordítási hibák hozhatók létre a változók nevének elírásával, vagy az Q# interpolált karakterláncokban lévő kifejezések használatával.

#### <a name="simulation"></a>Szimuláció

- A kvantumszimulátor az OpenMP használatával párhuzamosítja a szükséges lineáris algebrát. Alapértelmezés szerint az OpenMP az összes rendelkezésre álló hardveres szálat használja, ami azt jelenti, hogy a kis számú qubittel rendelkező programok gyakran lassabban futnak, mert a szükséges koordináció mellett eltörpül a tényleges munka. Ez úgy javítható, ha az OMP_NUM_THREADS környezeti változó értékének egy kisebb számot adunk meg. Nagyon nagy általánosságban nézve 1 szál nagyjából 4 qubithez elég, onnantól pedig qubitenként további 1 szálra van szükség, de ezek a számok nagyban függenek az adott algoritmustól.

#### <a name="debugging"></a>Hibakeresés

- Az F11 (beléptetés) nem működik a Q# kódban.
- A kód kiemelése Q# egy töréspontnál vagy egy lépésenkénti szüneteltetésnél esetenként pontatlan. Ilyenkor a megfelelő sor van kiemelve, de előfordul, hogy a kiemelés a soron belül nem a megfelelő oszlopnál kezdődik és ér véget.

#### <a name="testing"></a>Tesztelés

- A teszteket 64 bites módban kell futtatni. Ha a tesztek meghiúsulnak egy BadImageFormatException kivétel miatt, akkor válassza a Teszt menüben a Teszt beállításai > Alapértelmezett processzorarchitektúra > X64 lehetőséget.
- Bizonyos tesztek futtatása hosszú ideig is eltarthat (a számítógéptől függően akár 5 percig). Ez normális jelenség, mivel némelyik teszt több mint 20 qubitet használ, a legnagyobb közülük jelenleg 23-at.

#### <a name="samples"></a>Példák

- Egyes gépeken előfordulhat, hogy bizonyos kisméretű minták lassan futnak, ha az OMP_NUM_THREADS környezeti változó értéke nem „1”. Lásd még a kibocsátási megjegyzések „Szimuláció” szakaszát.

#### <a name="libraries"></a>Kódtárak

- Az implicit feltételezés az, hogy a különböző argumentumokban egy műveletnek átadott qubitek mind különbözőek. Például az összes kódtárművelet (és az összes szimulátor) azt feltételezi, hogy egy felügyelt NOT felé átadott két qubit különböző. E feltételezés megsértése kiszámíthatatlan, nem várt viselkedéshez vezethet. Ennek tesztelése a kvantumszámítógép nyomkövető szimulátorával lehetséges.
- Előfordulhat, hogy a Microsoft.Quantum.Bind függvény nem minden esetben működik a várt módon.
- A Microsoft.Quantum.Extensions.Math névtérben a SignD függvény Int helyett egy Double értéket ad vissza, annak ellenére, hogy bár a mögöttes System.Math.Sign függvény mindig egész számot ad vissza. Az eredmény biztonságosan összevethető az 1,0, -1,0 és 0,0 értékkel, mivel e dupla értékek mindegyikének van pontos bináris megfelelője.
