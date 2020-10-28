---
uid: Microsoft.Quantum.Canon.NoOp
title: NoOp művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: NoOp
qsharp.summary: Performs the identity operation (no-op) on an argument.
ms.openlocfilehash: 987e39577c3b736418234431ed7a915ae461f763
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715755"
---
# <a name="noop-operation"></a><span data-ttu-id="38489-102">NoOp művelet</span><span class="sxs-lookup"><span data-stu-id="38489-102">NoOp operation</span></span>

<span data-ttu-id="38489-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="38489-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="38489-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="38489-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="38489-105">Végrehajtja az Identity műveletet (No-op) egy argumentumon.</span><span class="sxs-lookup"><span data-stu-id="38489-105">Performs the identity operation (no-op) on an argument.</span></span>

```qsharp
operation NoOp<'T> (input : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="38489-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="38489-106">Description</span></span>

<span data-ttu-id="38489-107">A művelet bármilyen típusú értéket igénybe vesz, és semmit sem tesz hozzá.</span><span class="sxs-lookup"><span data-stu-id="38489-107">This operation takes a value of any type and does nothing to it.</span></span>
<span data-ttu-id="38489-108">Ez akkor lehet hasznos, ha egy Művelettípus bemenete várható, de nem kell végrehajtania a műveletet.</span><span class="sxs-lookup"><span data-stu-id="38489-108">This can be useful whenever an input of an operation type is expected, but no action should be taken.</span></span>
<span data-ttu-id="38489-109">Ha például egy adott hibajavítási szindróma azt jelzi, hogy a hiba nem történt meg, `NoOp<Qubit[]>` a megfelelő helyreállítási eljárás lehet.</span><span class="sxs-lookup"><span data-stu-id="38489-109">For instance, if a particular error correction syndrome indicates that no error has occurred, `NoOp<Qubit[]>` may be the correct recovery procedure.</span></span>
<span data-ttu-id="38489-110">Hasonlóképpen, ha egy művelet egy állapot-előkészítési eljárást vár bemenetként, `NoOp<Qubit[]>` felkészítheti a $ \ket{0 \cdots 0} $ állapotot.</span><span class="sxs-lookup"><span data-stu-id="38489-110">Similarly, if an operation expects a state preparation procedure as input, `NoOp<Qubit[]>` can be used to prepare the state $\ket{0 \cdots 0}$.</span></span>

## <a name="input"></a><span data-ttu-id="38489-111">Bevitel</span><span class="sxs-lookup"><span data-stu-id="38489-111">Input</span></span>

### <a name="input--t"></a><span data-ttu-id="38489-112">bemenet: nem</span><span class="sxs-lookup"><span data-stu-id="38489-112">input : 'T</span></span>

<span data-ttu-id="38489-113">A figyelmen kívül hagyott érték.</span><span class="sxs-lookup"><span data-stu-id="38489-113">A value to be ignored.</span></span>



## <a name="output--unit"></a><span data-ttu-id="38489-114">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="38489-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="38489-115">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="38489-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="38489-116">Nem</span><span class="sxs-lookup"><span data-stu-id="38489-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="38489-117">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="38489-117">Remarks</span></span>

<span data-ttu-id="38489-118">Szinte minden esetben explicit módon meg kell adni a type paramétert `NoOp` .</span><span class="sxs-lookup"><span data-stu-id="38489-118">In almost all cases, the type parameter for `NoOp` needs to be specified explicitly.</span></span> <span data-ttu-id="38489-119">A például megegyezik a következővel: `NoOp<Qubit>` <xref:microsoft.quantum.intrinsic.i> .</span><span class="sxs-lookup"><span data-stu-id="38489-119">For instance, `NoOp<Qubit>` is identical to <xref:microsoft.quantum.intrinsic.i>.</span></span>

## <a name="see-also"></a><span data-ttu-id="38489-120">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="38489-120">See Also</span></span>

- [<span data-ttu-id="38489-121">Microsoft. Quantum. belső. I</span><span class="sxs-lookup"><span data-stu-id="38489-121">Microsoft.Quantum.Intrinsic.I</span></span>](xref:Microsoft.Quantum.Intrinsic.I)