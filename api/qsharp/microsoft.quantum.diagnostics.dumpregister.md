---
uid: Microsoft.Quantum.Diagnostics.DumpRegister
title: DumpRegister függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpRegister
qsharp.summary: Dumps the current target machine's status associated with the given qubits.
ms.openlocfilehash: 9623d6d881f1f0ec048c3a951fe259bdfac84766
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202022"
---
# <a name="dumpregister-function"></a><span data-ttu-id="eb656-102">DumpRegister függvény</span><span class="sxs-lookup"><span data-stu-id="eb656-102">DumpRegister function</span></span>

<span data-ttu-id="eb656-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="eb656-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="eb656-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="eb656-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="eb656-105">A megadott qubits tartozó aktuális célszámítógép állapotának kiírása.</span><span class="sxs-lookup"><span data-stu-id="eb656-105">Dumps the current target machine's status associated with the given qubits.</span></span>

```qsharp
function DumpRegister<'T> (location : 'T, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="eb656-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="eb656-106">Input</span></span>

### <a name="location--t"></a><span data-ttu-id="eb656-107">hely: nem</span><span class="sxs-lookup"><span data-stu-id="eb656-107">location : 'T</span></span>

<span data-ttu-id="eb656-108">Információt nyújt az állapot memóriaképének létrehozásáról.</span><span class="sxs-lookup"><span data-stu-id="eb656-108">Provides information on where to generate the state's dump.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="eb656-109">qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="eb656-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="eb656-110">A jelentést tartalmazó qubits listája.</span><span class="sxs-lookup"><span data-stu-id="eb656-110">The list of qubits to report.</span></span>



## <a name="output--unit"></a><span data-ttu-id="eb656-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eb656-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="eb656-112">Nincsenek.</span><span class="sxs-lookup"><span data-stu-id="eb656-112">None.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="eb656-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="eb656-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="eb656-114">Nem</span><span class="sxs-lookup"><span data-stu-id="eb656-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="eb656-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="eb656-115">Remarks</span></span>

<span data-ttu-id="eb656-116">Ez a módszer lehetővé teszi az adott qubits állapotával kapcsolatos adatok egy fájlba vagy más helyre történő kiírását.</span><span class="sxs-lookup"><span data-stu-id="eb656-116">This method allows you to dump the information associated with the state of the given qubits into a file or some other location.</span></span>
<span data-ttu-id="eb656-117">A ténylegesen létrehozott információk és a szemantikai adatai az `location` egyes célszámítógépeken is jellemzőek.</span><span class="sxs-lookup"><span data-stu-id="eb656-117">The actual information generated and the semantics of `location` are specific to each target machine.</span></span> <span data-ttu-id="eb656-118">Ha azonban üres rekordot ad meg helyként ( `()` ), általában azt jelenti, hogy a kimenetet a-konzolra hozza elő.</span><span class="sxs-lookup"><span data-stu-id="eb656-118">However, providing an empty tuple as a location (`()`) typically means to generate the output to the console.</span></span>

<span data-ttu-id="eb656-119">A Quantum Development Kit részeként elosztott helyi teljes állapotú szimulátor esetében ez a módszer egy karakterláncot vár egy olyan fájl elérési útjával, amelyben a megadott qubits állapotát (azaz a megfelelő alrendszer Wave függvényét) az összetett számok egydimenziós tömbje fogja írni, amelyben az egyes elemek a megfelelő állapot mérésének valószínűségének amplitúdóját jelölik.</span><span class="sxs-lookup"><span data-stu-id="eb656-119">For the local full state simulator distributed as part of the Quantum Development Kit, this method  expects a string with the path to a file in which it will write the state of the given qubits (i.e. the wave function of the corresponding  subsystem) as a one-dimensional array of complex numbers, in which each element represents the amplitudes of the probability of measuring the corresponding state.</span></span>
<span data-ttu-id="eb656-120">Ha a megadott qubits más qubit vannak összefoglalva, és az állapotuk nem különíthető el, akkor csak azt jelenti, hogy a qubits összekeverve vannak.</span><span class="sxs-lookup"><span data-stu-id="eb656-120">If the given qubits are entangled with some other qubit and their state can't be separated, it just reports that the qubits are entangled.</span></span>