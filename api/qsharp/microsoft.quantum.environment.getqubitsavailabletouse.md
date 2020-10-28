---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: GetQubitsAvailableToUse művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: 25d43d369193fc7453fd5ce9c50769c438a69afb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712577"
---
# <a name="getqubitsavailabletouse-operation"></a><span data-ttu-id="aec80-102">GetQubitsAvailableToUse művelet</span><span class="sxs-lookup"><span data-stu-id="aec80-102">GetQubitsAvailableToUse operation</span></span>

<span data-ttu-id="aec80-103">Névtér: [Microsoft. Quantum. environment](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="aec80-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="aec80-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="aec80-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="aec80-105">A jelenleg használható qubits számát adja vissza.</span><span class="sxs-lookup"><span data-stu-id="aec80-105">Returns the number of qubits currently available to use.</span></span>

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a><span data-ttu-id="aec80-106">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="aec80-106">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="aec80-107">Egy utasításban lefoglalt qubits száma `using` .</span><span class="sxs-lookup"><span data-stu-id="aec80-107">The number of qubits that could be allocated in a `using` statement.</span></span>
<span data-ttu-id="aec80-108">Ha a használt célszámítógép nem adja meg ezeket az adatokat, akkor a `-1` rendszer visszaadja.</span><span class="sxs-lookup"><span data-stu-id="aec80-108">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="aec80-109">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="aec80-109">See Also</span></span>

- [<span data-ttu-id="aec80-110">Microsoft. Quantum. environment. GetQubitsAvailableToBorrow</span><span class="sxs-lookup"><span data-stu-id="aec80-110">Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)