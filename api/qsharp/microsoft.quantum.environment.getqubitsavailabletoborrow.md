---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: GetQubitsAvailableToBorrow művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow.
ms.openlocfilehash: 30b97c2b6e1353f008d085c3bae6160763557c67
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201461"
---
# <a name="getqubitsavailabletoborrow-operation"></a><span data-ttu-id="07c46-102">GetQubitsAvailableToBorrow művelet</span><span class="sxs-lookup"><span data-stu-id="07c46-102">GetQubitsAvailableToBorrow operation</span></span>

<span data-ttu-id="07c46-103">Névtér: [Microsoft. Quantum. environment](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="07c46-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="07c46-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="07c46-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="07c46-105">A jelenleg elérhető qubits számát adja vissza.</span><span class="sxs-lookup"><span data-stu-id="07c46-105">Returns the number of qubits currently available to borrow.</span></span>

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a><span data-ttu-id="07c46-106">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="07c46-106">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="07c46-107">A kölcsönzött qubits száma, és nem lesz lefoglalva egy utasítás részeként `borrowing` .</span><span class="sxs-lookup"><span data-stu-id="07c46-107">The number of qubits that could be borrowed and won't be allocated as part of a `borrowing` statement.</span></span>
<span data-ttu-id="07c46-108">Ha a használt célszámítógép nem adja meg ezeket az adatokat, akkor a `-1` rendszer visszaadja.</span><span class="sxs-lookup"><span data-stu-id="07c46-108">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="07c46-109">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="07c46-109">See Also</span></span>

- [<span data-ttu-id="07c46-110">Microsoft. Quantum. environment. GetQubitsAvailableToUse</span><span class="sxs-lookup"><span data-stu-id="07c46-110">Microsoft.Quantum.Environment.GetQubitsAvailableToUse</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)