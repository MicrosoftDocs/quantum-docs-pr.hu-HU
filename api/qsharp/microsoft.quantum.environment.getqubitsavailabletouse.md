---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: GetQubitsAvailableToUse művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: ce461b03a08b4c83b9de142c957ce5c590fe9659
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201410"
---
# <a name="getqubitsavailabletouse-operation"></a><span data-ttu-id="fb164-102">GetQubitsAvailableToUse művelet</span><span class="sxs-lookup"><span data-stu-id="fb164-102">GetQubitsAvailableToUse operation</span></span>

<span data-ttu-id="fb164-103">Névtér: [Microsoft. Quantum. environment](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="fb164-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="fb164-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="fb164-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="fb164-105">A jelenleg használható qubits számát adja vissza.</span><span class="sxs-lookup"><span data-stu-id="fb164-105">Returns the number of qubits currently available to use.</span></span>

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a><span data-ttu-id="fb164-106">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fb164-106">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fb164-107">Egy utasításban lefoglalt qubits száma `using` .</span><span class="sxs-lookup"><span data-stu-id="fb164-107">The number of qubits that could be allocated in a `using` statement.</span></span>
<span data-ttu-id="fb164-108">Ha a használt célszámítógép nem adja meg ezeket az adatokat, akkor a `-1` rendszer visszaadja.</span><span class="sxs-lookup"><span data-stu-id="fb164-108">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="fb164-109">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="fb164-109">See Also</span></span>

- [<span data-ttu-id="fb164-110">Microsoft. Quantum. environment. GetQubitsAvailableToBorrow</span><span class="sxs-lookup"><span data-stu-id="fb164-110">Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)