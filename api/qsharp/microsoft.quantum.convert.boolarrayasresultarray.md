---
uid: Microsoft.Quantum.Convert.BoolArrayAsResultArray
title: BoolArrayAsResultArray függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsResultArray
qsharp.summary: Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: 50a2bdb4a73ef9d67d3f5532493c142bb7f753cf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713598"
---
# <a name="boolarrayasresultarray-function"></a><span data-ttu-id="e143d-102">BoolArrayAsResultArray függvény</span><span class="sxs-lookup"><span data-stu-id="e143d-102">BoolArrayAsResultArray function</span></span>

<span data-ttu-id="e143d-103">Névtér: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="e143d-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="e143d-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e143d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e143d-105">Egy típusra konvertál egy típust `Bool[]` `Result[]` , ahol a le `true` van képezve `One` és le `false` van képezve `Zero` .</span><span class="sxs-lookup"><span data-stu-id="e143d-105">Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.</span></span>

```qsharp
function BoolArrayAsResultArray (input : Bool[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="e143d-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e143d-106">Input</span></span>

### <a name="input--bool"></a><span data-ttu-id="e143d-107">bemenet: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="e143d-107">input : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="e143d-108">`Bool[]` a konvertáláshoz.</span><span class="sxs-lookup"><span data-stu-id="e143d-108">`Bool[]` to be converted.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="e143d-109">Kimenet: __érvénytelen <Result>__ []</span><span class="sxs-lookup"><span data-stu-id="e143d-109">Output : __invalid<Result>__ []</span></span>

<span data-ttu-id="e143d-110">`Result[]`A jelölője `input` .</span><span class="sxs-lookup"><span data-stu-id="e143d-110">A `Result[]` representing the `input`.</span></span>