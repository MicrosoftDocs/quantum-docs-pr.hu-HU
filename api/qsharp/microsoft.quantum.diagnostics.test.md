---
uid: Microsoft.Quantum.Diagnostics.Test
title: Felhasználó által definiált típus tesztelése
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Test
qsharp.summary: Compiler-recognized attribute used to mark a unit test.
ms.openlocfilehash: 80821cb46d773d84085838d9ee539a8a45c43e61
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201495"
---
# <a name="test-user-defined-type"></a><span data-ttu-id="ef67a-102">Felhasználó által definiált típus tesztelése</span><span class="sxs-lookup"><span data-stu-id="ef67a-102">Test user defined type</span></span>

<span data-ttu-id="ef67a-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="ef67a-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="ef67a-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="ef67a-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="ef67a-105">A fordító által felismert attribútum, amely egy egység tesztének megjelölésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="ef67a-105">Compiler-recognized attribute used to mark a unit test.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Test = (ExecutionTarget : String);
```



## <a name="named-items"></a><span data-ttu-id="ef67a-106">Megnevezett elemek</span><span class="sxs-lookup"><span data-stu-id="ef67a-106">Named Items</span></span>

### <a name="executiontarget--string"></a><span data-ttu-id="ef67a-107">ExecutionTarget: [karakterlánc](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="ef67a-107">ExecutionTarget : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

