---
uid: Microsoft.Quantum.Core.Deprecated
title: Elavult felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: Deprecated
qsharp.summary: Compiler-recognized attribute used to mark a type or callable as deprecated.
ms.openlocfilehash: b1fcae9647b2a655d25773386ecffa826515516e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713276"
---
# <a name="deprecated-user-defined-type"></a><span data-ttu-id="92a17-102">Elavult felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="92a17-102">Deprecated user defined type</span></span>

<span data-ttu-id="92a17-103">Névtér: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="92a17-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="92a17-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="92a17-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="92a17-105">Fordító által felismert attribútum, amely a típus vagy a meghívható elavultként való megjelölésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="92a17-105">Compiler-recognized attribute used to mark a type or callable as deprecated.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a><span data-ttu-id="92a17-106">Megnevezett elemek</span><span class="sxs-lookup"><span data-stu-id="92a17-106">Named Items</span></span>

### <a name="newname--string"></a><span data-ttu-id="92a17-107">NewName: [karakterlánc](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="92a17-107">NewName : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="92a17-108">A típus teljes neve vagy hívható a használatra.</span><span class="sxs-lookup"><span data-stu-id="92a17-108">The full name of the type or callable to use instead.</span></span>
<span data-ttu-id="92a17-109">Az üres karakterláncra van beállítva, ha a típus vagy a meghívható a helyettesítés nélkül elavult.</span><span class="sxs-lookup"><span data-stu-id="92a17-109">Is set to the empty String if a type or callable has been deprecated without substitution.</span></span>