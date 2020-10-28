---
uid: Microsoft.Quantum.Convert.BoolAsResult
title: BoolAsResult függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolAsResult
qsharp.summary: Converts a `Bool` type to a `Result` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: eea6c062afdbb3172e63261e52a82e2576c14011
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713585"
---
# <a name="boolasresult-function"></a><span data-ttu-id="43f78-102">BoolAsResult függvény</span><span class="sxs-lookup"><span data-stu-id="43f78-102">BoolAsResult function</span></span>

<span data-ttu-id="43f78-103">Névtér: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="43f78-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="43f78-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="43f78-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="43f78-105">Egy típusra konvertál egy típust `Bool` `Result` , ahol a le `true` van képezve `One` és le `false` van képezve `Zero` .</span><span class="sxs-lookup"><span data-stu-id="43f78-105">Converts a `Bool` type to a `Result` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.</span></span>

```qsharp
function BoolAsResult (input : Bool) : Result
```


## <a name="input"></a><span data-ttu-id="43f78-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="43f78-106">Input</span></span>

### <a name="input--bool"></a><span data-ttu-id="43f78-107">bemenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="43f78-107">input : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="43f78-108">`Bool` a konvertáláshoz.</span><span class="sxs-lookup"><span data-stu-id="43f78-108">`Bool` to be converted.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="43f78-109">Kimenet: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="43f78-109">Output : __invalid<Result>__</span></span>

<span data-ttu-id="43f78-110">`Result`A jelölője `input` .</span><span class="sxs-lookup"><span data-stu-id="43f78-110">A `Result` representing the `input`.</span></span>