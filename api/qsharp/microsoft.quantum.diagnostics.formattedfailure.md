---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: FormattedFailure függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: da809c04059d4fd0f0ec92412a3094f5b582fd91
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201699"
---
# <a name="formattedfailure-function"></a><span data-ttu-id="71004-102">FormattedFailure függvény</span><span class="sxs-lookup"><span data-stu-id="71004-102">FormattedFailure function</span></span>

<span data-ttu-id="71004-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="71004-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="71004-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="71004-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="71004-105">Az értelmes hibaüzenetek sikertelen végrehajtásához használt belső függvény.</span><span class="sxs-lookup"><span data-stu-id="71004-105">Internal function used to fail with meaningful error messages.</span></span>

```qsharp
function FormattedFailure<'T> (actual : 'T, expected : 'T, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="71004-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="71004-106">Input</span></span>

### <a name="actual--t"></a><span data-ttu-id="71004-107">tényleges: nem</span><span class="sxs-lookup"><span data-stu-id="71004-107">actual : 'T</span></span>




### <a name="expected--t"></a><span data-ttu-id="71004-108">várt érték: 'T</span><span class="sxs-lookup"><span data-stu-id="71004-108">expected : 'T</span></span>




### <a name="message--string"></a><span data-ttu-id="71004-109">üzenet: [karakterlánc](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="71004-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>





## <a name="output--unit"></a><span data-ttu-id="71004-110">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="71004-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="71004-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="71004-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="71004-112">Nem</span><span class="sxs-lookup"><span data-stu-id="71004-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="71004-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="71004-113">Remarks</span></span>

<span data-ttu-id="71004-114">Ez a függvény a szimulációs futtatókörnyezetek által emulált, így lehetővé téve a formázott ellentmondások továbbítását.</span><span class="sxs-lookup"><span data-stu-id="71004-114">This function is intended to be emulated by simulation runtimes, so as to allow forwarding formatted contradictions.</span></span>