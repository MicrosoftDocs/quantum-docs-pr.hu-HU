---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: FormattedFailure függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: 0d7fb01ddf23cd6d79f722c8f6b691afa74a8885
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712675"
---
# <a name="formattedfailure-function"></a><span data-ttu-id="b3a2c-102">FormattedFailure függvény</span><span class="sxs-lookup"><span data-stu-id="b3a2c-102">FormattedFailure function</span></span>

<span data-ttu-id="b3a2c-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="b3a2c-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="b3a2c-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b3a2c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b3a2c-105">Az értelmes hibaüzenetek sikertelen végrehajtásához használt belső függvény.</span><span class="sxs-lookup"><span data-stu-id="b3a2c-105">Internal function used to fail with meaningful error messages.</span></span>

```qsharp
function FormattedFailure<'T> (actual : 'T, expected : 'T, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="b3a2c-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b3a2c-106">Input</span></span>

### <a name="actual--t"></a><span data-ttu-id="b3a2c-107">tényleges: nem</span><span class="sxs-lookup"><span data-stu-id="b3a2c-107">actual : 'T</span></span>




### <a name="expected--t"></a><span data-ttu-id="b3a2c-108">várt érték: 'T</span><span class="sxs-lookup"><span data-stu-id="b3a2c-108">expected : 'T</span></span>




### <a name="message--string"></a><span data-ttu-id="b3a2c-109">üzenet: [karakterlánc](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="b3a2c-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>





## <a name="output--unit"></a><span data-ttu-id="b3a2c-110">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b3a2c-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b3a2c-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="b3a2c-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b3a2c-112">Nem</span><span class="sxs-lookup"><span data-stu-id="b3a2c-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="b3a2c-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="b3a2c-113">Remarks</span></span>

<span data-ttu-id="b3a2c-114">Ez a függvény a szimulációs futtatókörnyezetek által emulált, így lehetővé téve a formázott ellentmondások továbbítását.</span><span class="sxs-lookup"><span data-stu-id="b3a2c-114">This function is intended to be emulated by simulation runtimes, so as to allow forwarding formatted contradictions.</span></span>