---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: GetQubitsAvailableToBorrow művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow.
ms.openlocfilehash: f2294fadb9c10d800b7a743fbfe0810f36f18516
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853249"
---
# <a name="getqubitsavailabletoborrow-operation"></a><span data-ttu-id="9d02e-102">GetQubitsAvailableToBorrow művelet</span><span class="sxs-lookup"><span data-stu-id="9d02e-102">GetQubitsAvailableToBorrow operation</span></span>

<span data-ttu-id="9d02e-103">Névtér: [Microsoft. Quantum. environment](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="9d02e-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="9d02e-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="9d02e-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="9d02e-105">A jelenleg elérhető qubits számát adja vissza.</span><span class="sxs-lookup"><span data-stu-id="9d02e-105">Returns the number of qubits currently available to borrow.</span></span>

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a><span data-ttu-id="9d02e-106">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9d02e-106">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9d02e-107">A kölcsönzött qubits száma, és nem lesz lefoglalva egy utasítás részeként `borrowing` .</span><span class="sxs-lookup"><span data-stu-id="9d02e-107">The number of qubits that could be borrowed and won't be allocated as part of a `borrowing` statement.</span></span>
<span data-ttu-id="9d02e-108">Ha a használt célszámítógép nem adja meg ezeket az adatokat, akkor a `-1` rendszer visszaadja.</span><span class="sxs-lookup"><span data-stu-id="9d02e-108">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="9d02e-109">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="9d02e-109">See Also</span></span>

- [<span data-ttu-id="9d02e-110">Microsoft. Quantum. environment. GetQubitsAvailableToUse</span><span class="sxs-lookup"><span data-stu-id="9d02e-110">Microsoft.Quantum.Environment.GetQubitsAvailableToUse</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)