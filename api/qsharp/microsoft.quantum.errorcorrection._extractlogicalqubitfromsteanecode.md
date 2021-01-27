---
uid: Microsoft.Quantum.ErrorCorrection._ExtractLogicalQubitFromSteaneCode
title: _ExtractLogicalQubitFromSteaneCode művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: _ExtractLogicalQubitFromSteaneCode
qsharp.summary: >-
  Syndrome measurement and the inverse of embedding.

  $X$- and $Z$-stabilizers are not treated equally, which is due to the particular choice of the encoding circuit. This asymmetry leads to a different syndrome extraction routine. One could measure the syndrome by measuring multi-qubit Pauli operator directly on the code state, but for the distillation purpose the logical qubit is returned into a single qubit, in course of which the syndrome measurements can be done without further ancillas.
ms.openlocfilehash: fe64343e30a0a3f0d05382e7812d37d5b13133d3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853213"
---
# <a name="_extractlogicalqubitfromsteanecode-operation"></a><span data-ttu-id="df599-102">_ExtractLogicalQubitFromSteaneCode művelet</span><span class="sxs-lookup"><span data-stu-id="df599-102">_ExtractLogicalQubitFromSteaneCode operation</span></span>

<span data-ttu-id="df599-103">Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="df599-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="df599-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="df599-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="df599-105">A szindrómás mértékét és a beágyazás inverzét.</span><span class="sxs-lookup"><span data-stu-id="df599-105">Syndrome measurement and the inverse of embedding.</span></span>

<span data-ttu-id="df599-106">$X $-és $Z $-stabilizátorokat nem egyformán kezeli a rendszer, ami a kódolási áramkör adott választásának köszönhető.</span><span class="sxs-lookup"><span data-stu-id="df599-106">$X$- and $Z$-stabilizers are not treated equally, which is due to the particular choice of the encoding circuit.</span></span>
<span data-ttu-id="df599-107">Ez az aszimmetria egy másik tünetegyüttes-kinyerési rutinhoz vezet.</span><span class="sxs-lookup"><span data-stu-id="df599-107">This asymmetry leads to a different syndrome extraction routine.</span></span>
<span data-ttu-id="df599-108">Az egyik lehetséges, hogy a qubit Pauli-operátort közvetlenül a kód állapotának mérésével mérjük, a qubit azonban a logikai egyetlen qubit kerül vissza, amely során a tünetegyüttes mérése további ancillas nélkül végezhető el.</span><span class="sxs-lookup"><span data-stu-id="df599-108">One could measure the syndrome by measuring multi-qubit Pauli operator directly on the code state, but for the distillation purpose the logical qubit is returned into a single qubit, in course of which the syndrome measurements can be done without further ancillas.</span></span>

```qsharp
operation _ExtractLogicalQubitFromSteaneCode (code : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit, Int, Int)
```


## <a name="input"></a><span data-ttu-id="df599-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="df599-109">Input</span></span>

### <a name="code--logicalregister"></a><span data-ttu-id="df599-110">kód: [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="df599-110">code : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>





## <a name="output--qubitintint"></a><span data-ttu-id="df599-111">Kimenet: ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))</span><span class="sxs-lookup"><span data-stu-id="df599-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>

<span data-ttu-id="df599-112">A logikai qubit és a $X $-szindrómára és $Z $-szindrómára vonatkozó pár egész szám.</span><span class="sxs-lookup"><span data-stu-id="df599-112">The logical qubit and a pair of integers for $X$-syndrome and $Z$-syndrome.</span></span>
<span data-ttu-id="df599-113">A kód azon qubit indexét képviselik, amelyeken egy $X $-vagy $Z $-Error érték a mért szindrómát okozta volna.</span><span class="sxs-lookup"><span data-stu-id="df599-113">They represent the index of the code qubit on which a single $X$- or $Z$-error would have caused the measured syndrome.</span></span>

## <a name="remarks"></a><span data-ttu-id="df599-114">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="df599-114">Remarks</span></span>

<span data-ttu-id="df599-115">Vegye figyelembe, hogy ez a művelet nincs megjelölve `internal` , mert az egység-tesztek közvetlenül a művelettől függenek.</span><span class="sxs-lookup"><span data-stu-id="df599-115">Note that this operation is not marked as `internal`, as unit tests directly depend on this operation.</span></span> <span data-ttu-id="df599-116">Jövőbeli fejlesztésként az egységbeli teszteket úgy kell átgondolni, hogy csak a nyilvános callables közvetlenül fussanak.</span><span class="sxs-lookup"><span data-stu-id="df599-116">As a future improvement, unit tests should be refactored to depend only on public callables directly.</span></span>

> [!WARNING]
> <span data-ttu-id="df599-117">Ez a rutin a Steane 7 qubit-kódjának egy adott kódolási áramköréhez van igazítva. Ha a kódolási áramkör módosul, akkor előfordulhat, hogy a szindrómát másképp kell értelmezni.</span><span class="sxs-lookup"><span data-stu-id="df599-117">This routine is tailored to a particular encoding circuit for Steane's 7 qubit code; if the encoding circuit is modified then the syndrome outcome might have to be interpreted differently.</span></span>