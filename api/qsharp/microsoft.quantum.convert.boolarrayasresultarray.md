---
uid: Microsoft.Quantum.Convert.BoolArrayAsResultArray
title: BoolArrayAsResultArray függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsResultArray
qsharp.summary: Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: 388fb67ba33810fc813fb646577bfa7f4a2b51ae
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224462"
---
# <a name="boolarrayasresultarray-function"></a><span data-ttu-id="3537e-102">BoolArrayAsResultArray függvény</span><span class="sxs-lookup"><span data-stu-id="3537e-102">BoolArrayAsResultArray function</span></span>

<span data-ttu-id="3537e-103">Névtér: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="3537e-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="3537e-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3537e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3537e-105">Egy típusra konvertál egy típust `Bool[]` `Result[]` , ahol a le `true` van képezve `One` és le `false` van képezve `Zero` .</span><span class="sxs-lookup"><span data-stu-id="3537e-105">Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.</span></span>

```qsharp
function BoolArrayAsResultArray (input : Bool[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="3537e-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="3537e-106">Input</span></span>

### <a name="input--bool"></a><span data-ttu-id="3537e-107">bemenet: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="3537e-107">input : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="3537e-108">`Bool[]` a konvertáláshoz.</span><span class="sxs-lookup"><span data-stu-id="3537e-108">`Bool[]` to be converted.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="3537e-109">Kimenet: __érvénytelen <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="3537e-109">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="3537e-110">`Result[]`A jelölője `input` .</span><span class="sxs-lookup"><span data-stu-id="3537e-110">A `Result[]` representing the `input`.</span></span>