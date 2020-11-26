---
uid: Microsoft.Quantum.Logical.Not
title: Nem működik
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: f2db43f4a2ce83d8cad1d60aa8c481a33b0c7d44
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197449"
---
# <a name="not-function"></a><span data-ttu-id="569c5-102">Nem működik</span><span class="sxs-lookup"><span data-stu-id="569c5-102">Not function</span></span>

<span data-ttu-id="569c5-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="569c5-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="569c5-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="569c5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="569c5-105">Egy érték logikai tagadását adja vissza.</span><span class="sxs-lookup"><span data-stu-id="569c5-105">Returns the Boolean negation of a value.</span></span>

```qsharp
function Not (value : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="569c5-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="569c5-106">Input</span></span>

### <a name="value--bool"></a><span data-ttu-id="569c5-107">érték: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="569c5-107">value : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="569c5-108">A megtagadni kívánt érték.</span><span class="sxs-lookup"><span data-stu-id="569c5-108">The value to be negated.</span></span>



## <a name="output--bool"></a><span data-ttu-id="569c5-109">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="569c5-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="569c5-110">`true` Ha és csak ha `value` van `false` .</span><span class="sxs-lookup"><span data-stu-id="569c5-110">`true` if and only if `value` is `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="569c5-111">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="569c5-111">Remarks</span></span>

<span data-ttu-id="569c5-112">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="569c5-112">The following are equivalent:</span></span>

```Q#
let x = not value;
let x = Not(value);
```