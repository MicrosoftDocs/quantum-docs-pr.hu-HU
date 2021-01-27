---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: 9384e5dafd4b5b7d44cb348c9537ebc2c621466d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839595"
---
# <a name="isnotzero-function"></a><span data-ttu-id="bad63-102">IsNotZero függvény</span><span class="sxs-lookup"><span data-stu-id="bad63-102">IsNotZero function</span></span>

<span data-ttu-id="bad63-103">Névtér: [Microsoft. Quantum. kémia](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="bad63-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="bad63-104">Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="bad63-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="bad63-105">Ellenőrzi, hogy egy `Double` szám nem körülbelül nulla-e.</span><span class="sxs-lookup"><span data-stu-id="bad63-105">Checks whether a `Double` number is not approximately zero.</span></span>

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="bad63-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="bad63-106">Input</span></span>

### <a name="number--double"></a><span data-ttu-id="bad63-107">szám: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="bad63-107">number : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="bad63-108">Ellenőrizendő szám</span><span class="sxs-lookup"><span data-stu-id="bad63-108">Number to be checked</span></span>



## <a name="output--bool"></a><span data-ttu-id="bad63-109">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="bad63-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="bad63-110">Igaz értéket ad vissza `number` , ha a értéke nagyobb, mint `1e-15` .</span><span class="sxs-lookup"><span data-stu-id="bad63-110">Returns true if `number` has an absolute value greater than `1e-15`.</span></span>