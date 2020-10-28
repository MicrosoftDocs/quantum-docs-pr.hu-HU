---
uid: Microsoft.Quantum.Diagnostics.Test
title: Felhasználó által definiált típus tesztelése
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Test
qsharp.summary: Compiler-recognized attribute used to mark a unit test.
ms.openlocfilehash: 8030f6378ac0cb393c7ed2b9e636a7561e8943a4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712646"
---
# <a name="test-user-defined-type"></a><span data-ttu-id="f7423-102">Felhasználó által definiált típus tesztelése</span><span class="sxs-lookup"><span data-stu-id="f7423-102">Test user defined type</span></span>

<span data-ttu-id="f7423-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="f7423-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="f7423-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f7423-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f7423-105">A fordító által felismert attribútum, amely egy egység tesztének megjelölésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="f7423-105">Compiler-recognized attribute used to mark a unit test.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Test = (ExecutionTarget : String);
```



## <a name="named-items"></a><span data-ttu-id="f7423-106">Megnevezett elemek</span><span class="sxs-lookup"><span data-stu-id="f7423-106">Named Items</span></span>

### <a name="executiontarget--string"></a><span data-ttu-id="f7423-107">ExecutionTarget: [karakterlánc](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="f7423-107">ExecutionTarget : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

