---
uid: Microsoft.Quantum.Diagnostics.DumpRegister
title: DumpRegister függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpRegister
qsharp.summary: Dumps the current target machine's status associated with the given qubits.
ms.openlocfilehash: 835c7a9edb22b4be630ebfc04587c12b3ff668b2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829232"
---
# <a name="dumpregister-function"></a>DumpRegister függvény

Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


A megadott qubits tartozó aktuális célszámítógép állapotának kiírása.

```qsharp
function DumpRegister<'T> (location : 'T, qubits : Qubit[]) : Unit
```


## <a name="input"></a>Bevitel

### <a name="location--t"></a>hely: nem

Információt nyújt az állapot memóriaképének létrehozásáról.


### <a name="qubits--qubit"></a>qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

A jelentést tartalmazó qubits listája.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

Nincsenek.

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem



## <a name="remarks"></a>Megjegyzések

Ez a módszer lehetővé teszi az adott qubits állapotával kapcsolatos adatok egy fájlba vagy más helyre történő kiírását.
A ténylegesen létrehozott információk és a szemantikai adatai az `location` egyes célszámítógépeken is jellemzőek. Ha azonban üres rekordot ad meg helyként ( `()` ), általában azt jelenti, hogy a kimenetet a-konzolra hozza elő.

A Quantum Development Kit részeként elosztott helyi teljes állapotú szimulátor esetében ez a módszer egy karakterláncot vár egy olyan fájl elérési útjával, amelyben a megadott qubits állapotát (azaz a megfelelő alrendszer Wave függvényét) az összetett számok egydimenziós tömbje fogja írni, amelyben az egyes elemek a megfelelő állapot mérésének valószínűségének amplitúdóját jelölik.
Ha a megadott qubits más qubit vannak összefoglalva, és az állapotuk nem különíthető el, akkor csak azt jelenti, hogy a qubits összekeverve vannak.