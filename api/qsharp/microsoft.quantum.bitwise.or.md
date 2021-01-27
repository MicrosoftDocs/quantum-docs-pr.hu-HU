---
uid: Microsoft.Quantum.Bitwise.Or
title: Vagy függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: Or
qsharp.summary: Returns the bitwise OR of two integers. This performs the same computation as the built-in `|||` operator.
ms.openlocfilehash: 811e7cf64424e8302c5745c4c71d76de50ab8c08
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845267"
---
# <a name="or-function"></a><span data-ttu-id="03d71-102">Vagy függvény</span><span class="sxs-lookup"><span data-stu-id="03d71-102">Or function</span></span>

<span data-ttu-id="03d71-103">Névtér: [Microsoft. Quantum. bitenkénti](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="03d71-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="03d71-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="03d71-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="03d71-105">A bitenkénti vagy két egész számot ad vissza.</span><span class="sxs-lookup"><span data-stu-id="03d71-105">Returns the bitwise OR of two integers.</span></span>
<span data-ttu-id="03d71-106">Ez ugyanazokat a számításokat hajtja végre, mint a beépített `|||` operátor.</span><span class="sxs-lookup"><span data-stu-id="03d71-106">This performs the same computation as the built-in `|||` operator.</span></span>

```qsharp
function Or (a : Int, b : Int) : Int
```


## <a name="input"></a><span data-ttu-id="03d71-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="03d71-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="03d71-108">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="03d71-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="b--int"></a><span data-ttu-id="03d71-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="03d71-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="03d71-110">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="03d71-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="example"></a><span data-ttu-id="03d71-111">Példa</span><span class="sxs-lookup"><span data-stu-id="03d71-111">Example</span></span>

```qsharp
let a = 248;      //                 11111000₂
let b = 63;       //                 00111111₂
let x = Or(a, b); // x : Int = 255 = 11111111₂.
```

## <a name="remarks"></a><span data-ttu-id="03d71-112">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="03d71-112">Remarks</span></span>

<span data-ttu-id="03d71-113">Lásd: [C# | ](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/or-operator) További részletekért lásd a kezelőt.</span><span class="sxs-lookup"><span data-stu-id="03d71-113">See the [C# | Operator](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/or-operator) for more details.</span></span>