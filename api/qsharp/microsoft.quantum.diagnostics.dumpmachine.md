---
uid: Microsoft.Quantum.Diagnostics.DumpMachine
title: DumpMachine függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpMachine
qsharp.summary: Dumps the current target machine's status.
ms.openlocfilehash: 579300d4efb9e22cb671fbb4bce0a6f72dd0e2ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853420"
---
# <a name="dumpmachine-function"></a>DumpMachine függvény

Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Az aktuális célszámítógép állapotának kiírása.

```qsharp
function DumpMachine<'T> (location : 'T) : Unit
```


## <a name="input"></a>Bevitel

### <a name="location--t"></a>hely: nem

Információt nyújt a gép memóriaképének létrehozásáról.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

Nincsenek.

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem



## <a name="remarks"></a>Megjegyzések

Ez a módszer lehetővé teszi a célszámítógép aktuális állapotával kapcsolatos információk egy fájlba vagy egy másik helyre való kiírását.
A ténylegesen létrehozott információk és a szemantikai adatai az `location` egyes célszámítógépeken is jellemzőek. Ha azonban üres rekordot ad meg helyként ( `()` ), vagy csak a paraméter kihagyása `location` általában azt jelenti, hogy a kimenetet a konzolon hozza elő.

A Quantum Development Kit részeként elosztott helyi teljes állapotú szimulátor esetében ez a metódus egy karakterláncot vár egy olyan fájl elérési útjával, amelyben a Wave függvényt összetett számok egydimenziós tömbként fogja írni, amelyben az egyes elemek a megfelelő állapot mérésének valószínűségét jelölik.