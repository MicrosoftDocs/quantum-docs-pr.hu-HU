---
title: Mi az a Q# programozási nyelv és a QDK?
description: Ismerje meg a Microsoft Quantum Development Kitet, a Q# programozási nyelvet, valamint a kvantumprogramok létrehozásának módját.
author: bradben
ms.author: v-benbra
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.q-sharp
no-loc:
- Q#
- $$v
ms.openlocfilehash: 21adfcc1c5321d87665adb39a3c838bbda0b8861
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834567"
---
# <a name="what-are-the-no-locq-programming-language-and-qdk"></a>Mi az a Q# programozási nyelv és a QDK?

A Q# a Microsoft nyílt forráskódú programozási nyelve, amely kvantumalgoritmusok fejlesztésére és futtatására szolgál. Ez a Quantum Development Kit (QDK) része, amelyben [Q#-kódtárak](xref:microsoft.quantum.libraries), [kvantumszimulátorok](xref:microsoft.quantum.machines), [más programozási környezetekhez használható bővítmények](xref:microsoft.quantum.install) és [API-dokumentáció](xref:microsoft.quantum.apiref-intro) található. A standard Q#-kódtár mellett a QDK kémiai, gépi tanulási és numerikus kódtárakat is tartalmaz.

Programozási nyelvként a Q# a Python, a C# és az F# ismerős elemeit használja, és támogatja a programok hurkokkal, ha-akkor típusú utasításokkal és gyakori adattípusokkal való írásának alapszintű eljárási modelljeit. Új, kvantumspecifikus adatszerkezeteket és műveleteket is bevezet.

## <a name="what-can-i-do-with-the-qdk"></a>Mire használhatom a QDK-t?

A QDK a Q# nyelvhez készült teljes körű fejlesztői készlet, amelyet általános eszközökkel és nyelvekkel használhat különböző környezetekben futtatható kvantumalkalmazások fejlesztéséhez. A Q#-programok konzolalkalmazásként futtathatók a Jupyter-notebookokon keresztül, illetve Python- vagy .NET-gazdaprogramokat is használhatnak.

### <a name="develop-in-common-tools-and-environments"></a>Fejlesztés általános eszközökben és környezetekben

A kvantumfejlesztés integrálható a [Visual Studióval, a Visual Studio Code-dal](xref:microsoft.quantum.install.standalone) és a [Jupyter-notebookokkal](xref:microsoft.quantum.install.jupyter). A beépített API-kkal [Python](xref:microsoft.quantum.install.python)- és [.NET](xref:microsoft.quantum.install.cs)-gazdanyelvekkel párosíthatja a programjait.

### <a name="try-quantum-operations-and-domain-specific-libraries"></a>Kvantumműveletek és tartományspecifikus kódtárak kipróbálása

Kvantumalgoritmusokat írhat és tesztelhet a szuperpozíció, az összefonódás és más kvantumműveletek megismerése érdekében. A Q#-kódtárakkal összetett kvantumműveleteket futtathat anélkül, hogy alacsony szintű műveletsorozatokat kellene írnia.

### <a name="run-programs-in-simulators"></a>Programok futtatása szimulátorokban

A kvantumprogramokat egy teljes körű kvantumszimulátoron vagy egy korlátozott hatókörű Toffoli-szimulátoron futtathatja, illetve különböző erőforrásbecslőkben tesztelheti Q#-kódját. 

## <a name="where-can-i-learn-more"></a>Hol találhatok további információkat?

|||
| ---- | ---- |
| **Még nem ismerem a kvantum-számítástechnikát** | A [Fő fogalmak](xref:microsoft.quantum.overview.understanding) című szakaszban áttekintheti a kvantumfizika és a kvantum-számítástechnika alapjait.|
| **Részletesebben meg szeretném ismerni a Q# nyelvet** | [A Q# használati útmutatójában](xref:microsoft.quantum.guide) megismerheti a típusokat, a kifejezéseket, a változókat és a kvantumprogramok struktúráját.|
| **Csak el szeretnék kezdeni kvantumprogramokat írni** | A [Gyorsútmutatókban](xref:microsoft.quantum.install) beállíthatja a Q#-környezetet, és megkezdheti a kvantumprogramok írását.|

## <a name="how-does-no-locq-work"></a>Hogyan működik a Q#?

A Q#-programok különálló alkalmazásba fordíthatók, de egy Python vagy .NET nyelven írt gazdaprogram által is meghívhatók.

A program létrehozásakor és futtatásakor létrejön a kvantumszimulátor egy példánya, amely megkapja a Q#-kódot. A szimulátor a Q#-kóddal hoz létre qubiteket (kvantumrészecskék szimulációit), és átalakításokat alkalmaz az állapotuk módosításához. A rendszer ezután visszaadja a programnak a kvantumműveletek eredményeit.  

A Q#-kód a szimulátoron belüli elkülönítése biztosítja, hogy az algoritmusok kövessék a kvantumfizika törvényeit, és megfelelően fussanak a kvantumszámítógépeken.

![Qsharp-kódfolyamat](~/media/qsharp-code-flow.png)

## <a name="how-do-i-use-the-qdk"></a>Hogyan működik a QDK?

A helyi számítógépre telepíthető és onnan futtatható minden, amire szüksége lehet a Q#-programok írásához és futtatásához, beleértve a Q#-fordítót, a Q#-kódtárakat és a kvantumszimulátorokat. Előbb-utóbb távolról is futtathatja majd a Q#-programokat egy valódi kvantumszámítógépen, de addig is a QDK által biztosított kvantumszimulátorok pontos és megbízható eredményeket nyújtanak.

- A [Q#-alkalmazások](xref:microsoft.quantum.install.standalone) fejlesztésével teheti meg leggyorsabban az első lépéseket.

- Futtasson önálló [Jupyter-notebookokat az IQ#-pal](xref:microsoft.quantum.install.jupyter), amely a Q#-programok fordítására, szimulálására és megjelenítésére szolgáló Jupyter-bővítmény.

- Ha ismeri a [Python](xref:microsoft.quantum.install.python) nyelvet, a kezdéshez használhatja gazda programozási platformként. A Pythont nem csak a fejlesztők használják széles körben, hanem a tudósok, kutatók és tanárok is.

- Ha már van tapasztalata a [C#, F# vagy VB.NET](xref:microsoft.quantum.install.cs) nyelvekkel, és ismeri a Visual Studio fejlesztési környezetet, csak néhány bővítményt kell adnia a Visual Studióhoz, hogy előkészítse a Q# nyelvhez.  

## <a name="summary"></a>Összefoglalás

A Q# egy nyílt forráskódú programozási nyelv, amely kvantumprogramok fejlesztésére és futtatására szolgál. Olyan kódtárakat tartalmaz, amelyekkel összetett kvantumműveleteket hozhat létre, és olyan kvantumszimulátorokat, amelyekkel pontosan futtathatja és tesztelheti a programokat. A Q#-programok futtathatók önálló alkalmazásként, de meghívhatók egy Python- vagy .NET-gazdaprogramból is, az írásuk, futtatásuk és tesztelésük pedig elvégezhető a helyi számítógépről is.

## <a name="next-steps"></a>Következő lépések

[A kvantum-számítástechnika lineáris algebrája](xref:microsoft.quantum.overview.algebra)
