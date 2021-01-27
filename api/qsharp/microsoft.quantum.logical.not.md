---
uid: Microsoft.Quantum.Logical.Not
title: Nem működik
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: bf09cac8d126371df6218b7e92d68a881b732dc8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849075"
---
# <a name="not-function"></a><span data-ttu-id="c02d7-102">Nem működik</span><span class="sxs-lookup"><span data-stu-id="c02d7-102">Not function</span></span>

<span data-ttu-id="c02d7-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="c02d7-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="c02d7-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c02d7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c02d7-105">Egy érték logikai tagadását adja vissza.</span><span class="sxs-lookup"><span data-stu-id="c02d7-105">Returns the Boolean negation of a value.</span></span>

```qsharp
function Not (value : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="c02d7-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c02d7-106">Input</span></span>

### <a name="value--bool"></a><span data-ttu-id="c02d7-107">érték: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c02d7-107">value : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c02d7-108">A megtagadni kívánt érték.</span><span class="sxs-lookup"><span data-stu-id="c02d7-108">The value to be negated.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c02d7-109">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c02d7-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c02d7-110">`true` Ha és csak ha `value` van `false` .</span><span class="sxs-lookup"><span data-stu-id="c02d7-110">`true` if and only if `value` is `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c02d7-111">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="c02d7-111">Remarks</span></span>

<span data-ttu-id="c02d7-112">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="c02d7-112">The following are equivalent:</span></span>

```qsharp
let x = not value;
let x = Not(value);
```