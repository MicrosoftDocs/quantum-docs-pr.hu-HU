---
uid: Microsoft.Quantum.Logical.Not
title: Nem működik
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: 3a688aac0178a2f4127496c1009fe7d5ee7ae198
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709861"
---
# <a name="not-function"></a><span data-ttu-id="37687-102">Nem működik</span><span class="sxs-lookup"><span data-stu-id="37687-102">Not function</span></span>

<span data-ttu-id="37687-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="37687-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="37687-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="37687-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="37687-105">Egy érték logikai tagadását adja vissza.</span><span class="sxs-lookup"><span data-stu-id="37687-105">Returns the Boolean negation of a value.</span></span>

```qsharp
function Not (value : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="37687-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="37687-106">Input</span></span>

### <a name="value--bool"></a><span data-ttu-id="37687-107">érték: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="37687-107">value : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="37687-108">A megtagadni kívánt érték.</span><span class="sxs-lookup"><span data-stu-id="37687-108">The value to be negated.</span></span>



## <a name="output--bool"></a><span data-ttu-id="37687-109">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="37687-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="37687-110">`true` Ha és csak ha `value` van `false` .</span><span class="sxs-lookup"><span data-stu-id="37687-110">`true` if and only if `value` is `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="37687-111">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="37687-111">Remarks</span></span>

<span data-ttu-id="37687-112">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="37687-112">The following are equivalent:</span></span>

```Q#
let x = not value;
let x = Not(value);
```