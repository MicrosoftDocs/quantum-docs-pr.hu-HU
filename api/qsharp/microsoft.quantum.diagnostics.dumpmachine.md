---
uid: Microsoft.Quantum.Diagnostics.DumpMachine
title: DumpMachine függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpMachine
qsharp.summary: Dumps the current target machine's status.
ms.openlocfilehash: c85cf6764bdc913a71448c525318f45743bf1df0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712871"
---
# <a name="dumpmachine-function"></a>DumpMachine függvény

Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Csomag [](https://nuget.org/packages/)


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