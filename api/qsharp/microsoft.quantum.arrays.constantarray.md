---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: a3ad8a18856888a0ca6f9dd691242156b0c044d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846223"
---
# <a name="constantarray-function"></a><span data-ttu-id="e47b8-102">ConstantArray függvény</span><span class="sxs-lookup"><span data-stu-id="e47b8-102">ConstantArray function</span></span>

<span data-ttu-id="e47b8-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e47b8-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e47b8-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e47b8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e47b8-105">Egy adott hosszúságú tömböt hoz létre a megadott értékkel egyenlő összes elemmel.</span><span class="sxs-lookup"><span data-stu-id="e47b8-105">Creates an array of given length with all elements equal to given value.</span></span>

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a><span data-ttu-id="e47b8-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e47b8-106">Input</span></span>

### <a name="length--int"></a><span data-ttu-id="e47b8-107">Hossz: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e47b8-107">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e47b8-108">Az új tömb hossza.</span><span class="sxs-lookup"><span data-stu-id="e47b8-108">Length of the new array.</span></span>


### <a name="value--t"></a><span data-ttu-id="e47b8-109">érték: nem</span><span class="sxs-lookup"><span data-stu-id="e47b8-109">value : 'T</span></span>

<span data-ttu-id="e47b8-110">Az új tömb egyes elemeinek értéke.</span><span class="sxs-lookup"><span data-stu-id="e47b8-110">The value of each element of the new array.</span></span>



## <a name="output--t"></a><span data-ttu-id="e47b8-111">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="e47b8-111">Output : 'T[]</span></span>

<span data-ttu-id="e47b8-112">Egy új hosszúságú tömb `length` , amely minden elemnél `value` .</span><span class="sxs-lookup"><span data-stu-id="e47b8-112">A new array of length `length`, such that every element is `value`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e47b8-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="e47b8-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e47b8-114">Nem</span><span class="sxs-lookup"><span data-stu-id="e47b8-114">'T</span></span>



## <a name="example"></a><span data-ttu-id="e47b8-115">Példa</span><span class="sxs-lookup"><span data-stu-id="e47b8-115">Example</span></span>

<span data-ttu-id="e47b8-116">A következő kód három logikai értékből álló tömböt hoz létre, amelyek mindegyike egyenlő `true` :</span><span class="sxs-lookup"><span data-stu-id="e47b8-116">The following code creates an array of 3 Boolean values, each equal to `true`:</span></span>

```qsharp
let array = ConstantArray(3, true);
```