---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: FormattedFailure függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: 6b1202c8897d67e3089a88a0855c8008b3a8c2ba
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98828280"
---
# <a name="formattedfailure-function"></a><span data-ttu-id="d0575-102">FormattedFailure függvény</span><span class="sxs-lookup"><span data-stu-id="d0575-102">FormattedFailure function</span></span>

<span data-ttu-id="d0575-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="d0575-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="d0575-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d0575-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d0575-105">Az értelmes hibaüzenetek sikertelen végrehajtásához használt belső függvény.</span><span class="sxs-lookup"><span data-stu-id="d0575-105">Internal function used to fail with meaningful error messages.</span></span>

```qsharp
function FormattedFailure<'T> (actual : 'T, expected : 'T, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="d0575-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="d0575-106">Input</span></span>

### <a name="actual--t"></a><span data-ttu-id="d0575-107">tényleges: nem</span><span class="sxs-lookup"><span data-stu-id="d0575-107">actual : 'T</span></span>




### <a name="expected--t"></a><span data-ttu-id="d0575-108">várt érték: 'T</span><span class="sxs-lookup"><span data-stu-id="d0575-108">expected : 'T</span></span>




### <a name="message--string"></a><span data-ttu-id="d0575-109">üzenet: [karakterlánc](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="d0575-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>





## <a name="output--unit"></a><span data-ttu-id="d0575-110">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d0575-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d0575-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="d0575-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d0575-112">Nem</span><span class="sxs-lookup"><span data-stu-id="d0575-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="d0575-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="d0575-113">Remarks</span></span>

<span data-ttu-id="d0575-114">Ez a függvény a szimulációs futtatókörnyezetek által emulált, így lehetővé téve a formázott ellentmondások továbbítását.</span><span class="sxs-lookup"><span data-stu-id="d0575-114">This function is intended to be emulated by simulation runtimes, so as to allow forwarding formatted contradictions.</span></span>