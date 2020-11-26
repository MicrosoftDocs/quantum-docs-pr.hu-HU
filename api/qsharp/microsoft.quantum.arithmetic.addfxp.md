---
uid: Microsoft.Quantum.Arithmetic.AddFxP
title: AddFxP művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddFxP
qsharp.summary: Adds two fixed-point numbers stored in quantum registers.
ms.openlocfilehash: 36a5d585a493f0e6f33f74b1686aaa01cca7ac0b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191040"
---
# <a name="addfxp-operation"></a><span data-ttu-id="5219f-102">AddFxP művelet</span><span class="sxs-lookup"><span data-stu-id="5219f-102">AddFxP operation</span></span>

<span data-ttu-id="5219f-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="5219f-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="5219f-104">Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="5219f-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="5219f-105">Két, a kvantum-regiszterekben tárolt, rögzített ponttal rendelkező számot adja meg.</span><span class="sxs-lookup"><span data-stu-id="5219f-105">Adds two fixed-point numbers stored in quantum registers.</span></span>

```qsharp
operation AddFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="5219f-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="5219f-106">Description</span></span>

<span data-ttu-id="5219f-107">A $ \ket{f_1} $ és a $ \ket{f_2} $ értékben megadott két rögzített pontos regiszter esetében a $ \ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2} $ műveletet hajtja végre.</span><span class="sxs-lookup"><span data-stu-id="5219f-107">Given two fixed-point registers respectively in states $\ket{f_1}$ and $\ket{f_2}$, performs the operation $\ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2}$.</span></span>

## <a name="input"></a><span data-ttu-id="5219f-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="5219f-108">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="5219f-109">FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="5219f-109">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="5219f-110">Első rögzített pont száma</span><span class="sxs-lookup"><span data-stu-id="5219f-110">First fixed-point number</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="5219f-111">FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="5219f-111">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="5219f-112">A rendszer frissíti a második rögzített pont számát, hogy tartalmazza a két bemenet összegét.</span><span class="sxs-lookup"><span data-stu-id="5219f-112">Second fixed-point number, will be updated to contain the sum of the two inputs.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5219f-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5219f-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="5219f-114">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="5219f-114">Remarks</span></span>

<span data-ttu-id="5219f-115">A jelenlegi megvalósításhoz a két rögzített pontból származó számnak azonos ponttal kell rendelkeznie, mint a legkevésbé jelentős, azaz $n _i $ és a $p _i $ értéknek egyenlőnek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="5219f-115">The current implementation requires the two fixed-point numbers to have the same point position counting from the least-significant bit, i.e., $n_i$ and $p_i$ must be equal.</span></span>