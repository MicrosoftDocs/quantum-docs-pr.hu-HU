---
uid: Microsoft.Quantum.Arithmetic.AddFxP
title: AddFxP művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddFxP
qsharp.summary: Adds two fixed-point numbers stored in quantum registers.
ms.openlocfilehash: cf1f1379b7e1c32aefb0fccb55f4d13c95c78d8f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721697"
---
# <a name="addfxp-operation"></a><span data-ttu-id="6631d-102">AddFxP művelet</span><span class="sxs-lookup"><span data-stu-id="6631d-102">AddFxP operation</span></span>

<span data-ttu-id="6631d-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="6631d-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="6631d-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6631d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6631d-105">Két, a kvantum-regiszterekben tárolt, rögzített ponttal rendelkező számot adja meg.</span><span class="sxs-lookup"><span data-stu-id="6631d-105">Adds two fixed-point numbers stored in quantum registers.</span></span>

```qsharp
operation AddFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="description"></a><span data-ttu-id="6631d-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="6631d-106">Description</span></span>

<span data-ttu-id="6631d-107">A $ \ket{f_1} $ és a $ \ket{f_2} $ értékben megadott két rögzített pontos regiszter esetében a $ \ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2} $ műveletet hajtja végre.</span><span class="sxs-lookup"><span data-stu-id="6631d-107">Given two fixed-point registers respectively in states $\ket{f_1}$ and $\ket{f_2}$, performs the operation $\ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2}$.</span></span>

## <a name="input"></a><span data-ttu-id="6631d-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="6631d-108">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="6631d-109">FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="6631d-109">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="6631d-110">Első rögzített pont száma</span><span class="sxs-lookup"><span data-stu-id="6631d-110">First fixed-point number</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="6631d-111">FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="6631d-111">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="6631d-112">A rendszer frissíti a második rögzített pont számát, hogy tartalmazza a két bemenet összegét.</span><span class="sxs-lookup"><span data-stu-id="6631d-112">Second fixed-point number, will be updated to contain the sum of the two inputs.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6631d-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6631d-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="6631d-114">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="6631d-114">Remarks</span></span>

<span data-ttu-id="6631d-115">A jelenlegi megvalósításhoz a két rögzített pontból származó számnak azonos ponttal kell rendelkeznie, mint a legkevésbé jelentős, azaz $n _i $ és a $p _i $ értéknek egyenlőnek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="6631d-115">The current implementation requires the two fixed-point numbers to have the same point position counting from the least-significant bit, i.e., $n_i$ and $p_i$ must be equal.</span></span>