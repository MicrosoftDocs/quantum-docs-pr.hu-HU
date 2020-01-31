---
title: Quantum Computing Szószedet | Microsoft Docs
description: Quantum kifejezések szószedete
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.glossary
ms.openlocfilehash: 5c7f2c4a572f6194ee846f056016a25b8c5303a2
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820759"
---
# <a name="quantum-computing-glossary"></a>Quantum Computing – Szószedet

|Időtartam|Meghatározás|
|-------------|----------|
|Adjoint|A művelet összetett konjugált átültetése. Az egységes operátort megvalósító műveletek esetében a adjoint a művelet inverze.|
|Használata hívható|A műveletek és a függvények együttesen *callables*néven ismertek.|
|Standard|A Q #-ban definiált műveletek és függvények az előjátékban definiált logikára épülnek. A standard szintű függvénytár-implementáció agnosztikus a célszámítógépek tekintetében.|
|Clifford-csoport|A Bloch gömb octants elfoglaló műveletek összessége. Ezek többek között a következők: `X`, `Y`, `Z`, `H` és `S`|
|Ellenőrzött|Olyan Quantum művelet, amely egy vagy több qubits használ a cél művelethez.|
|Dirac jelölése|A kvantum állapotának rövidített ábrázolása. További részletekért tekintse meg a [Dirac jelölési](xref:microsoft.quantum.concepts.dirac) szakaszt.|
|Eigenvalues és Eigenvectors|A részletekért tekintse meg a [speciális mátrix szakaszt](xref:microsoft.quantum.concepts.matrix-advanced) .|
|EPR pár|Más néven [harangos állapot](https://en.wikipedia.org/wiki/Bell_state)|
|Evolution|Az állapot időbeli változása. Tekintse meg a <xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials> című szakaszt egy példát. |
|Függvény|Tisztán klasszikus rutinok a Q # nyelven|
| <a id="global-phase"></a>Globális fázis | Két olyan állapot, amely azonos egy összetett $e szám többszörösével (^ {i\phi} $), a rendszer azt jelzi, hogy egy globális fázisban különböznek egymástól. A helyi fázisokkal ellentétben a globális fázisok nem figyelhetők meg semmilyen méréssel. További részletekért lásd a [Pauli-mérések](xref:microsoft.quantum.concepts.pauli) című témakört. |
|Mérés|Klasszikus bit beszerzése egy qubit (vagy qubits). További részletekért tekintse meg a [Qubit fogalmakat](xref:microsoft.quantum.concepts.qubit) ismertető szakaszt.|
|Változtatható|Egy változó, amelynek az értéke a létrehozása után módosítható.|
|Névtér|A kapcsolódó nevek (jellemzően műveletek, függvények és típusok) gyűjteményének címkéje. A névtér például [`Microsoft.Quantum.Preparation`](xref:microsoft.quantum.preparation) a szabványos könyvtárban definiált összes szimbólumot, amely a kezdeti állapotok előkészítését segíti elő.|
|Művelet|A Quantum végrehajtás alapegysége a Q #-ban. Nagyjából egyenértékű a C, C++ vagy Python függvényeivel, illetve a C# vagy Java statikus metódusaival.|
|Kezelő alkalmazás|Quantum művelet végrehajtása. Ez általában egy egységes mátrixot alkalmaz az aktuális állapot vektorára. További részletekért lásd [a kvantum-fogalmak bevezetését](xref:microsoft.quantum.concepts.intro) ismertető témakört.|
|Oracle|Egy olyan alrutin, amely Adatfüggő adatokat biztosít a kvantum-algoritmusnak futásidőben. A cél az, hogy a kimenetek a helyükön lévő bemeneteknek megfelelő kimenetet adjanak.   |
|Részleges alkalmazás|Függvény vagy művelet hívása az összes szükséges paraméter nélkül. A egy új meghívót ad vissza, amely csak a hiányzó paramétereket igényli a jövőbeli alkalmazásokban.|
|Pauli-operátorok|A `X`, `Y` és `Z` Quantum Gates.|
|Prelúdium|Az egyes célszámítógépek által meghatározott primitív és klasszikus műveletek és függvények összessége, nem pedig a Q # szintjén.|
|Quantum Circuit|A kvantum-számítógép programjának ábrázolása. További részletekért tekintse meg a <xref:microsoft.quantum.concepts.circuits> szakaszt.|
|Kvantum állapota|A rendszer qubits ábrázolása. Ez általában egy összetett oszlop vektora. További információ: <xref:microsoft.quantum.concepts.vectors>. |
|Qubit|A Quantum Storage egysége. További részletekért tekintse meg a <xref:microsoft.quantum.concepts.qubit> szakaszt.|
|Ismétlés a sikerig|A probabilistically által sikeresnek bizonyuló kvantum-algoritmus. Hiba esetén a rutin újra próbálkozik, amíg a művelet sikertelen lesz (vagy elérte a korlátot). |
|Célszámítógép|Fordítási cél, amely egy absztrakt kvantum-programot csökkenti a hardver vagy a szimuláció irányába. Ez általában számos célra, például a kapu cseréjére, a hibajavítások kódolására, a geometriai elrendezésre és egyebekre vonatkozó újraírásokat tartalmaz.|
|Rekord|Vesszővel tagolt típusok csoportosítva zárójelen keresztül. |
|Felhasználó által definiált típus|Beépített vagy korábban definiált típusok gyűjteménye, amelyek egyetlen egységként is szerepelhetnek.|

