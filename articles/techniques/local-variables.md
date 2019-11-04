---
title: 'Q # technikák – helyi változók | Microsoft Docs'
description: 'Q # technikák – helyi változók'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4f5eff1ee8482fa5e5fee9dff421efab93fc0c5a
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183284"
---
# <a name="local-variables"></a>Helyi változók #

A Q # bármelyik típusának értéke hozzárendelhető egy változóhoz egy műveleten vagy függvényen belül az `let` kulcsszó használatával.
Például:

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

Ez a Pauli-operátorok egy adott tömbjét rendeli hozzá egy `measurementOperator`nevű változóhoz.

> [!TIP]
> Ne feledje, hogy nem kell explicit módon megadnia az új változó típusát, mivel a `let` utasítás jobb oldalán lévő kifejezés nem egyértelmű, és a típust a fordító következteti ki. 

A Q # változói nem *változtathatók*meg, ami azt jelenti, hogy ha egy változót ily módon definiáltak, akkor már nem módosítható semmilyen módon.
Ez számos hasznos optimalizálást tesz lehetővé, beleértve a változók `Adjoint` változatának átrendezésére szolgáló klasszikus logika optimalizálását.

A `let` kötés használatával meghatározott változók egy adott hatókörön belül helyiek, például egy művelet törzse vagy egy `for` hurok tartalma.


## <a name="mutability"></a>Változékonyság ##

A `let`-vel való változó létrehozásának alternatívájaként a `mutable` kulcsszó egy speciális, módosítható változót hoz létre, amely újra köthető az `set` kulcsszó használatával.

```qsharp
operation RandomInts(maxInt : Int, nrSamples : Int) : Int[] {
    mutable samples = new Int[0];
    for (i in 1 .. nrSamples) {
        set samples += [RandomInt(maxInt)];
    }
    return samples;
}
```

A Q # összes típusa, beleértve a tömböket, az érték szemantikai követése. Különösen nem lehetséges a tömb elemeinek frissítése. Egy meglévő tömb módosításához a másolási és frissítési mechanizmust is ugyanúgy kell kihasználnia, mint a rekordokban F#. A [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays)által biztosított tömbökhöz tartozó függvénytár-eszközök használatával például egyszerűen definiálhat egy olyan függvényt, amely Paulis tömböt ad vissza, ahol a Pauli at index `i` a megadott értéket és az összes többi bejegyzést az identitás: 

```qsharp
function EmbedPauli (pauli : Pauli, i : Int, n : Int) : Pauli[] {
    
    let arr = ConstantArray(n, PauliI); // creates an array of filled with PauliI
    return arr w/ i <- pauli; // constructs a new array based on arr except that entry i is set to pauli
}
```

A Q # utasítások és kifejezések megvitatásakor további tudnivalókat fogunk kidolgozni a tömbök használatáról. 

A Q # változékonyság egy olyan fogalom, amely típus vagy érték helyett *szimbólumra* vonatkozik. Pontosabban nem rendelkezik a típusrendszer, implicit módon vagy explicit módon, valamint attól, hogy a kötés módosítható-e (ahogy azt a `mutable` kulcsszó jelezte) vagy a nem változtatható (ahogyan az `let`) nem változtatja meg a kötött változó (k) típusát. Ez fontos módszert kínál a változékonyság elkülönítésére a speciális funkciókon és műveleteken belül.
Különösen annak ellenére, hogy egy változtatható változót használó művelethez adjoint specializáció nem hozható létre automatikusan, az automatikus generálás jól működik a változékonyság-t használó függvényt meghívó művelethez.
Ezért célszerű olyan függvényeket és műveleteket készíteni, amelyek a lehető legrövidebb és kompakt változékonyság használják, így a kvantum-program többi része megváltoztathatatlan változók használatával is írható.


## <a name="deconstruction"></a>Dekonstrukció ##

Egyetlen változó hozzárendelésén kívül a `let` és `mutable` kulcsszavakat – vagy valójában bármilyen más kötési összeállítást is – lehetővé teszi egy [rekord típusú](xref:microsoft.quantum.language.type-model#tuple-types)tartalom kicsomagolását.
Az űrlap kiosztása a rekord elemeinek *kiépítése* .
Ha például egy rekordban egy Hamilton egy kifejezést modellezünk, akkor a dekonstrukcióval elérheti azokat a különböző adattípusokat, amelyekre az adott időszak alatt szimulálni kell:

```qsharp
// Represents H = 3.1 X_0 Z_1.
let (_, (paulis, idxQubits)) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // paulis and idxQubits are both immutable variables
mutable ((c1, c2), _) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // c1 and c2 are both mutable variables
```


