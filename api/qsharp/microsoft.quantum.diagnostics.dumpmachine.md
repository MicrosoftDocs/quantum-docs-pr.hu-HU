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
# <a name="dumpmachine-function"></a><span data-ttu-id="dc3a7-102">DumpMachine függvény</span><span class="sxs-lookup"><span data-stu-id="dc3a7-102">DumpMachine function</span></span>

<span data-ttu-id="dc3a7-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="dc3a7-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="dc3a7-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dc3a7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dc3a7-105">Az aktuális célszámítógép állapotának kiírása.</span><span class="sxs-lookup"><span data-stu-id="dc3a7-105">Dumps the current target machine's status.</span></span>

```qsharp
function DumpMachine<'T> (location : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="dc3a7-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="dc3a7-106">Input</span></span>

### <a name="location--t"></a><span data-ttu-id="dc3a7-107">hely: nem</span><span class="sxs-lookup"><span data-stu-id="dc3a7-107">location : 'T</span></span>

<span data-ttu-id="dc3a7-108">Információt nyújt a gép memóriaképének létrehozásáról.</span><span class="sxs-lookup"><span data-stu-id="dc3a7-108">Provides information on where to generate the machine's dump.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dc3a7-109">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dc3a7-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="dc3a7-110">Nincsenek.</span><span class="sxs-lookup"><span data-stu-id="dc3a7-110">None.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="dc3a7-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="dc3a7-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="dc3a7-112">Nem</span><span class="sxs-lookup"><span data-stu-id="dc3a7-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="dc3a7-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="dc3a7-113">Remarks</span></span>

<span data-ttu-id="dc3a7-114">Ez a módszer lehetővé teszi a célszámítógép aktuális állapotával kapcsolatos információk egy fájlba vagy egy másik helyre való kiírását.</span><span class="sxs-lookup"><span data-stu-id="dc3a7-114">This method allows you to dump information about the current status of the target machine into a file or some other location.</span></span>
<span data-ttu-id="dc3a7-115">A ténylegesen létrehozott információk és a szemantikai adatai az `location` egyes célszámítógépeken is jellemzőek.</span><span class="sxs-lookup"><span data-stu-id="dc3a7-115">The actual information generated and the semantics of `location` are specific to each target machine.</span></span> <span data-ttu-id="dc3a7-116">Ha azonban üres rekordot ad meg helyként ( `()` ), vagy csak a paraméter kihagyása `location` általában azt jelenti, hogy a kimenetet a konzolon hozza elő.</span><span class="sxs-lookup"><span data-stu-id="dc3a7-116">However, providing an empty tuple as a location (`()`) or just omitting the `location` parameter typically means to generate the output to the console.</span></span>

<span data-ttu-id="dc3a7-117">A Quantum Development Kit részeként elosztott helyi teljes állapotú szimulátor esetében ez a metódus egy karakterláncot vár egy olyan fájl elérési útjával, amelyben a Wave függvényt összetett számok egydimenziós tömbként fogja írni, amelyben az egyes elemek a megfelelő állapot mérésének valószínűségét jelölik.</span><span class="sxs-lookup"><span data-stu-id="dc3a7-117">For the local full state simulator distributed as part of the Quantum Development Kit, this method  expects a string with the path to a file in which it will write the wave function as a one-dimensional array of complex numbers, in which each element represents the amplitudes of the probability of measuring the corresponding state.</span></span>