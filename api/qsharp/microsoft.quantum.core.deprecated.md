---
uid: Microsoft.Quantum.Core.Deprecated
title: Elavult felhasználó által definiált típus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: Deprecated
qsharp.summary: Compiler-recognized attribute used to mark a type or callable as deprecated.
ms.openlocfilehash: 122cbc113a68cec107558d68a6fb145cf6bbd9db
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224088"
---
# <a name="deprecated-user-defined-type"></a><span data-ttu-id="9ccd9-102">Elavult felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="9ccd9-102">Deprecated user defined type</span></span>

<span data-ttu-id="9ccd9-103">Névtér: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="9ccd9-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="9ccd9-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="9ccd9-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="9ccd9-105">Fordító által felismert attribútum, amely a típus vagy a meghívható elavultként való megjelölésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="9ccd9-105">Compiler-recognized attribute used to mark a type or callable as deprecated.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a><span data-ttu-id="9ccd9-106">Megnevezett elemek</span><span class="sxs-lookup"><span data-stu-id="9ccd9-106">Named Items</span></span>

### <a name="newname--string"></a><span data-ttu-id="9ccd9-107">NewName: [karakterlánc](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="9ccd9-107">NewName : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="9ccd9-108">A típus teljes neve vagy hívható a használatra.</span><span class="sxs-lookup"><span data-stu-id="9ccd9-108">The full name of the type or callable to use instead.</span></span>
<span data-ttu-id="9ccd9-109">Az üres karakterláncra van beállítva, ha a típus vagy a meghívható a helyettesítés nélkül elavult.</span><span class="sxs-lookup"><span data-stu-id="9ccd9-109">Is set to the empty String if a type or callable has been deprecated without substitution.</span></span>