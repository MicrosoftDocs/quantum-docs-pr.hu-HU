---
uid: Microsoft.Quantum.Convert.ResultArrayAsBoolArray
title: ResultArrayAsBoolArray függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: ResultArrayAsBoolArray
qsharp.summary: Converts a `Result[]` type to a `Bool[]` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.
ms.openlocfilehash: 384531137474562ebc8cc24dcd1ac976dc91ad9d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832591"
---
# <a name="resultarrayasboolarray-function"></a><span data-ttu-id="5d864-102">ResultArrayAsBoolArray függvény</span><span class="sxs-lookup"><span data-stu-id="5d864-102">ResultArrayAsBoolArray function</span></span>

<span data-ttu-id="5d864-103">Névtér: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="5d864-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="5d864-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5d864-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5d864-105">Egy típusra konvertál egy típust `Result[]` `Bool[]` , ahol a le `One` van képezve `true` és le `Zero` van képezve `false` .</span><span class="sxs-lookup"><span data-stu-id="5d864-105">Converts a `Result[]` type to a `Bool[]` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.</span></span>

```qsharp
function ResultArrayAsBoolArray (input : Result[]) : Bool[]
```


## <a name="input"></a><span data-ttu-id="5d864-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="5d864-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="5d864-107">bemenet: __érvénytelen <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="5d864-107">input : __invalid<Result>__[]</span></span>

<span data-ttu-id="5d864-108">`Result[]` a konvertáláshoz.</span><span class="sxs-lookup"><span data-stu-id="5d864-108">`Result[]` to be converted.</span></span>



## <a name="output--bool"></a><span data-ttu-id="5d864-109">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="5d864-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="5d864-110">`Bool[]`A jelölője `input` .</span><span class="sxs-lookup"><span data-stu-id="5d864-110">A `Bool[]` representing the `input`.</span></span>