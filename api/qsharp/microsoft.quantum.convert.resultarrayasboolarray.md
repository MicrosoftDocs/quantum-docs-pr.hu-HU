---
uid: Microsoft.Quantum.Convert.ResultArrayAsBoolArray
title: ResultArrayAsBoolArray függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: ResultArrayAsBoolArray
qsharp.summary: Converts a `Result[]` type to a `Bool[]` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.
ms.openlocfilehash: f3af3abd4ee58f495d4ea60ec4f21a2690abec1d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224224"
---
# <a name="resultarrayasboolarray-function"></a><span data-ttu-id="b9175-102">ResultArrayAsBoolArray függvény</span><span class="sxs-lookup"><span data-stu-id="b9175-102">ResultArrayAsBoolArray function</span></span>

<span data-ttu-id="b9175-103">Névtér: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="b9175-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="b9175-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b9175-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b9175-105">Egy típusra konvertál egy típust `Result[]` `Bool[]` , ahol a le `One` van képezve `true` és le `Zero` van képezve `false` .</span><span class="sxs-lookup"><span data-stu-id="b9175-105">Converts a `Result[]` type to a `Bool[]` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.</span></span>

```qsharp
function ResultArrayAsBoolArray (input : Result[]) : Bool[]
```


## <a name="input"></a><span data-ttu-id="b9175-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b9175-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="b9175-107">bemenet: __érvénytelen <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="b9175-107">input : __invalid<Result>__[]</span></span>

<span data-ttu-id="b9175-108">`Result[]` a konvertáláshoz.</span><span class="sxs-lookup"><span data-stu-id="b9175-108">`Result[]` to be converted.</span></span>



## <a name="output--bool"></a><span data-ttu-id="b9175-109">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="b9175-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="b9175-110">`Bool[]`A jelölője `input` .</span><span class="sxs-lookup"><span data-stu-id="b9175-110">A `Bool[]` representing the `input`.</span></span>