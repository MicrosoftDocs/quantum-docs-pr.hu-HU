---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: GetQubitsAvailableToBorrow művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow. This includes unused qubits; that is, this includes the qubits returned by `GetQubitsAvailableToUse`.
ms.openlocfilehash: cb56ce4aefd7a03c0f0827b8d34688ef17988f56
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712590"
---
# <a name="getqubitsavailabletoborrow-operation"></a><span data-ttu-id="b3770-102">GetQubitsAvailableToBorrow művelet</span><span class="sxs-lookup"><span data-stu-id="b3770-102">GetQubitsAvailableToBorrow operation</span></span>

<span data-ttu-id="b3770-103">Névtér: [Microsoft. Quantum. environment](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="b3770-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="b3770-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b3770-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b3770-105">A jelenleg elérhető qubits számát adja vissza.</span><span class="sxs-lookup"><span data-stu-id="b3770-105">Returns the number of qubits currently available to borrow.</span></span>
<span data-ttu-id="b3770-106">Ez magában foglalja a nem használt qubits; Ez magában foglalja a által visszaadott qubits `GetQubitsAvailableToUse` .</span><span class="sxs-lookup"><span data-stu-id="b3770-106">This includes unused qubits; that is, this includes the qubits returned by `GetQubitsAvailableToUse`.</span></span>

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a><span data-ttu-id="b3770-107">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b3770-107">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b3770-108">Egy utasításban lefoglalt qubits száma `borrowing` .</span><span class="sxs-lookup"><span data-stu-id="b3770-108">The number of qubits that could be allocated in a `borrowing` statement.</span></span>
<span data-ttu-id="b3770-109">Ha a használt célszámítógép nem adja meg ezeket az adatokat, akkor a `-1` rendszer visszaadja.</span><span class="sxs-lookup"><span data-stu-id="b3770-109">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="b3770-110">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="b3770-110">See Also</span></span>

- [<span data-ttu-id="b3770-111">Microsoft. Quantum. environment. GetQubitsAvailableToUse</span><span class="sxs-lookup"><span data-stu-id="b3770-111">Microsoft.Quantum.Environment.GetQubitsAvailableToUse</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)