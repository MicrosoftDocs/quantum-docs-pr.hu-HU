---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: GetQubitsAvailableToUse művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: 2ed8c3789331a15b351769be960d06f6364d8047
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827798"
---
# <a name="getqubitsavailabletouse-operation"></a><span data-ttu-id="c2b39-102">GetQubitsAvailableToUse művelet</span><span class="sxs-lookup"><span data-stu-id="c2b39-102">GetQubitsAvailableToUse operation</span></span>

<span data-ttu-id="c2b39-103">Névtér: [Microsoft. Quantum. environment](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="c2b39-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="c2b39-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="c2b39-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="c2b39-105">A jelenleg használható qubits számát adja vissza.</span><span class="sxs-lookup"><span data-stu-id="c2b39-105">Returns the number of qubits currently available to use.</span></span>

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a><span data-ttu-id="c2b39-106">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c2b39-106">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c2b39-107">Egy utasításban lefoglalt qubits száma `using` .</span><span class="sxs-lookup"><span data-stu-id="c2b39-107">The number of qubits that could be allocated in a `using` statement.</span></span>
<span data-ttu-id="c2b39-108">Ha a használt célszámítógép nem adja meg ezeket az adatokat, akkor a `-1` rendszer visszaadja.</span><span class="sxs-lookup"><span data-stu-id="c2b39-108">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="c2b39-109">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="c2b39-109">See Also</span></span>

- [<span data-ttu-id="c2b39-110">Microsoft. Quantum. environment. GetQubitsAvailableToBorrow</span><span class="sxs-lookup"><span data-stu-id="c2b39-110">Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)