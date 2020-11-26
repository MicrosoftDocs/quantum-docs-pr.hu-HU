---
uid: Microsoft.Quantum.Chemistry.HTerm
title: HTerm-felhasználó által definiált típus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTerm
qsharp.summary: Format of data passed from C# to Q# to represent a term of the Hamiltonian. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 504d55dc57ce92c12e6f016e9afcedfd59664aa1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204130"
---
# <a name="hterm-user-defined-type"></a><span data-ttu-id="24425-102">HTerm-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="24425-102">HTerm user defined type</span></span>

<span data-ttu-id="24425-103">Névtér: [Microsoft. Quantum. kémia](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="24425-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="24425-104">Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="24425-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="24425-105">A C# és a Q # között átadott adatok formátuma, amely a Hamilton kifejezését jelöli.</span><span class="sxs-lookup"><span data-stu-id="24425-105">Format of data passed from C# to Q# to represent a term of the Hamiltonian.</span></span>
<span data-ttu-id="24425-106">A megjelenített adatmennyiség jelentését az azt fogadó algoritmus határozza meg.</span><span class="sxs-lookup"><span data-stu-id="24425-106">The meaning of the data represented is determined by the algorithm that receives it.</span></span>

```qsharp

newtype HTerm = (Int[], Double[]);
```

