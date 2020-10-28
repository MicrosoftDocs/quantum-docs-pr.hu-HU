---
uid: Microsoft.Quantum.Arithmetic.SquareI
title: SquareI művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareI
qsharp.summary: Computes the square of the integer `xs` into `result`, which must be zero initially.
ms.openlocfilehash: d7334d50f245ba358624e6e2eee94b63d9ed7569
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719537"
---
# <a name="squarei-operation"></a><span data-ttu-id="05c3a-102">SquareI művelet</span><span class="sxs-lookup"><span data-stu-id="05c3a-102">SquareI operation</span></span>

<span data-ttu-id="05c3a-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="05c3a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="05c3a-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="05c3a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="05c3a-105">Kiszámítja az egész szám négyzetét a értékre `xs` `result` , amelynek kezdetben nullának kell lennie.</span><span class="sxs-lookup"><span data-stu-id="05c3a-105">Computes the square of the integer `xs` into `result`, which must be zero initially.</span></span>

```qsharp
operation SquareI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="05c3a-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="05c3a-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="05c3a-107">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="05c3a-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="05c3a-108">$n $ bites számot a négyzetbe (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="05c3a-108">$n$-bit number to square (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="05c3a-109">eredmény: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="05c3a-109">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="05c3a-110">a $2n $-bit result (LittleEndian) értékének kezdetben a következő állapotban kell lennie: $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="05c3a-110">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="05c3a-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="05c3a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="05c3a-112">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="05c3a-112">Remarks</span></span>

<span data-ttu-id="05c3a-113">A a négyzet kiszámításához szabványos eltolási és hozzáadási megközelítést használ.</span><span class="sxs-lookup"><span data-stu-id="05c3a-113">Uses a standard shift-and-add approach to compute the square.</span></span> <span data-ttu-id="05c3a-114">A $n-$1 qubits az egyenes továbbítási megoldáshoz képest menti, amely először az XS-t másolja, mielőtt normál szorzót alkalmazzon, majd visszaveszi a másolási műveletet.</span><span class="sxs-lookup"><span data-stu-id="05c3a-114">Saves $n-1$ qubits compared to the straight-forward solution which first copies out xs before applying a regular multiplier and then undoing the copy operation.</span></span>