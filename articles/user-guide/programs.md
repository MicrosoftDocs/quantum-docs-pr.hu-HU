---
title: 'Q # introdution'
description: 'Gyors bevezetés a Quantum programba a Q-ban #'
author: beheim
ms.author: beheim
ms.date: 11/08/2020
ms.topic: article
uid: microsoft.quantum.guide.programs
ms.openlocfilehash: 975bcda5e0042406b465a83f17f1d2d3f5a1ec4f
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96233979"
---
# <a name="q-quantum-programming-language"></a>Q # Quantum programozási nyelv

Minden, amit tudnia kell a Q # programozási nyelvről, részletesen szerepel a [q # nyelvi útmutatójában](xref:microsoft.quantum.qsharp.index). Mint bármi más, a [nyelvi tervezési folyamat](https://github.com/microsoft/qsharp-language#q-language-and-core-libraries-design) nyílt forráskódú, és szívesen vesszük a hozzájárulásokat.
Ha többet szeretne megtudni az alapjairól és a Q # mögötti motivációról, olvassa el a [Miért van szükségünk q #?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/)című témakört.  
A Q # a Quantum Development Kit (QDK) részeként érhető el egy gyors áttekintéshez, és nézze meg, [Mi a QDK?](xref:microsoft.quantum.overview.q-sharp). 

## <a name="what-is-a-quantum-program"></a>Mi az a Quantum program?

A kvantum-programok a klasszikus alrutinok egy adott készletének tekinthetők meg, amelyek hívásakor a rendszer egy kvantum-rendszerrel való interakcióval végez számítást. a Q #-ban írt programok nem modellezik közvetlenül a kvantum-állapotot, hanem azt, hogy egy klasszikus vezérlő számítógép hogyan kommunikál a qubits.
Ez lehetővé teszi számunkra, hogy teljesen függetlenek legyenek attól, hogy milyen kvantum-állapotot biztosítanak *az egyes* célszámítógépeken, ami különböző értelmezésekkel rendelkezhet a gépen. 

Ennek egyik fontos következménye, hogy a Q # nem tud betekintést adni egy qubit vagy más, a kvantummechanika állapotára, ami garantálja, hogy a Q # program fizikailag végrehajtható a kvantum-számítógépeken.
Ehelyett egy program olyan műveleteket hívhat meg, mint például [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) a klasszikus információk qubit való kinyerése.

A foglalást követően a qubit a műveleteknek és a függvényeknek, más néven *callables* is átadható. Bizonyos értelemben ez azt eredményezi, hogy a Q # program egy qubit tud tenni; A qubit állapotával kapcsolatos közvetlen műveleteket az összes *belső* callables, például [`X`](xref:Microsoft.Quantum.Intrinsic.X) a és-, [`H`](xref:Microsoft.Quantum.Intrinsic.H) azaz a callables határozzák meg, amelyek implementációi nem a Q #-ban vannak definiálva, hanem a célszámítógép által definiált módon. Ezeket a műveleteket ténylegesen csak az adott Q # program futtatásához használt célszámítógép *végzi el.*

Ha például a programot a [teljes állapotú szimulátoron](xref:microsoft.quantum.machines.full-state-simulator)futtatja, a szimulátor a szimulált kvantum-rendszernek megfelelő matematikai műveleteket hajtja végre.
De a jövő irányába szemlélve, amikor a célszámítógép egy valódi kvantum-számítógép, a Q #-ban az ilyen műveletek meghívásával irányítja a kvantum-számítógépet, hogy végrehajtsa a megfelelő *valós* műveleteket a *valós* kvantum-rendszeren (például a pontosan időzített lézeres impulzusok esetében).

A Q # program újrakombinálja ezeket a műveleteket a célszámítógép által meghatározott módon, hogy új, magasabb szintű műveleteket hozzon létre a kvantum-számításokhoz.
Így a Q # megkönnyíti a Quantum és a hibrid kvantum – klasszikus algoritmusok kiépítését, és egyúttal általános megoldást is biztosít a célszámítógép vagy a szimulátor struktúrájára vonatkozóan.

Egy egyszerű példa a következő program, amely egy qubit foglal le a $ \ket {0} $ állapotban, majd Hadamard műveletet alkalmaz `H` rá, és az eredményt az `PauliZ` alapján méri.

```qsharp
@EntryPoint()
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now we measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // we reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, we return the result of the measurement.
        return result;
    }
}
```

A [Quantum katas](https://github.com/microsoft/QuantumKatas#introduction) kiváló bevezetést biztosít a [kvantum-számítástechnikai fogalmakkal](https://github.com/microsoft/QuantumKatas#quantum-computing-concepts-qubits-and-gates) , például a közös kvantum-műveletekkel és a qubits kezelésével kapcsolatban. További példákat is találhat a [belső műveletekben és a függvényekben](xref:microsoft.quantum.libraries.standard.prelude).



