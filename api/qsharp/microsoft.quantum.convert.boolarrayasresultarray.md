---
uid: Microsoft.Quantum.Convert.BoolArrayAsResultArray
title: BoolArrayAsResultArray függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsResultArray
qsharp.summary: Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: b30da07272ee1a6c19ae13afa618ba5deb7aaa2d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98834193"
---
# <a name="boolarrayasresultarray-function"></a><span data-ttu-id="4095d-102">BoolArrayAsResultArray függvény</span><span class="sxs-lookup"><span data-stu-id="4095d-102">BoolArrayAsResultArray function</span></span>

<span data-ttu-id="4095d-103">Névtér: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="4095d-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="4095d-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4095d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4095d-105">Egy típusra konvertál egy típust `Bool[]` `Result[]` , ahol a le `true` van képezve `One` és le `false` van képezve `Zero` .</span><span class="sxs-lookup"><span data-stu-id="4095d-105">Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.</span></span>

```qsharp
function BoolArrayAsResultArray (input : Bool[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="4095d-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="4095d-106">Input</span></span>

### <a name="input--bool"></a><span data-ttu-id="4095d-107">bemenet: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="4095d-107">input : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="4095d-108">`Bool[]` a konvertáláshoz.</span><span class="sxs-lookup"><span data-stu-id="4095d-108">`Bool[]` to be converted.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="4095d-109">Kimenet: __érvénytelen <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="4095d-109">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="4095d-110">`Result[]`A jelölője `input` .</span><span class="sxs-lookup"><span data-stu-id="4095d-110">A `Result[]` representing the `input`.</span></span>