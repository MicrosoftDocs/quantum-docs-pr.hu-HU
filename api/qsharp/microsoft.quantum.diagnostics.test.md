---
uid: Microsoft.Quantum.Diagnostics.Test
title: Felhasználó által definiált típus tesztelése
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Test
qsharp.summary: Compiler-recognized attribute used to mark a unit test.
ms.openlocfilehash: 2f1b521c4ef2bf8e672ca4fe7a5f380d744300b7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853255"
---
# <a name="test-user-defined-type"></a><span data-ttu-id="f6a8e-102">Felhasználó által definiált típus tesztelése</span><span class="sxs-lookup"><span data-stu-id="f6a8e-102">Test user defined type</span></span>

<span data-ttu-id="f6a8e-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="f6a8e-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="f6a8e-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="f6a8e-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="f6a8e-105">A fordító által felismert attribútum, amely egy egység tesztének megjelölésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="f6a8e-105">Compiler-recognized attribute used to mark a unit test.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Test = (ExecutionTarget : String);
```



## <a name="named-items"></a><span data-ttu-id="f6a8e-106">Megnevezett elemek</span><span class="sxs-lookup"><span data-stu-id="f6a8e-106">Named Items</span></span>

### <a name="executiontarget--string"></a><span data-ttu-id="f6a8e-107">ExecutionTarget: [karakterlánc](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="f6a8e-107">ExecutionTarget : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

