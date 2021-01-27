---
uid: Microsoft.Quantum.Convert.ResultAsBool
title: ResultAsBool függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: ResultAsBool
qsharp.summary: Converts a `Result` type to a `Bool` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.
ms.openlocfilehash: 9de7ca64992e0a4d73c1d00218b3eab4ab545a1e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832565"
---
# <a name="resultasbool-function"></a><span data-ttu-id="3ad05-102">ResultAsBool függvény</span><span class="sxs-lookup"><span data-stu-id="3ad05-102">ResultAsBool function</span></span>

<span data-ttu-id="3ad05-103">Névtér: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="3ad05-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="3ad05-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3ad05-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3ad05-105">Egy típusra konvertál egy típust `Result` `Bool` , ahol a le `One` van képezve `true` és le `Zero` van képezve `false` .</span><span class="sxs-lookup"><span data-stu-id="3ad05-105">Converts a `Result` type to a `Bool` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.</span></span>

```qsharp
function ResultAsBool (input : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="3ad05-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="3ad05-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="3ad05-107">bemenet: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="3ad05-107">input : __invalid<Result>__</span></span>

<span data-ttu-id="3ad05-108">`Result` a konvertáláshoz.</span><span class="sxs-lookup"><span data-stu-id="3ad05-108">`Result` to be converted.</span></span>



## <a name="output--bool"></a><span data-ttu-id="3ad05-109">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3ad05-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3ad05-110">`Bool`A jelölője `input` .</span><span class="sxs-lookup"><span data-stu-id="3ad05-110">A `Bool` representing the `input`.</span></span>