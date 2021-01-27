---
uid: Microsoft.Quantum.Canon.NoOp
title: NoOp művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: NoOp
qsharp.summary: Performs the identity operation (no-op) on an argument.
ms.openlocfilehash: 45f3c8c9d4bae8ac8f7f60c4e4f8ead5d92e7c00
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852394"
---
# <a name="noop-operation"></a><span data-ttu-id="b1946-102">NoOp művelet</span><span class="sxs-lookup"><span data-stu-id="b1946-102">NoOp operation</span></span>

<span data-ttu-id="b1946-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b1946-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b1946-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="b1946-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="b1946-105">Végrehajtja az Identity műveletet (No-op) egy argumentumon.</span><span class="sxs-lookup"><span data-stu-id="b1946-105">Performs the identity operation (no-op) on an argument.</span></span>

```qsharp
operation NoOp<'T> (input : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="b1946-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="b1946-106">Description</span></span>

<span data-ttu-id="b1946-107">A művelet bármilyen típusú értéket igénybe vesz, és semmit sem tesz hozzá.</span><span class="sxs-lookup"><span data-stu-id="b1946-107">This operation takes a value of any type and does nothing to it.</span></span>
<span data-ttu-id="b1946-108">Ez akkor lehet hasznos, ha egy Művelettípus bemenete várható, de nem kell végrehajtania a műveletet.</span><span class="sxs-lookup"><span data-stu-id="b1946-108">This can be useful whenever an input of an operation type is expected, but no action should be taken.</span></span>
<span data-ttu-id="b1946-109">Ha például egy adott hibajavítási szindróma azt jelzi, hogy a hiba nem történt meg, `NoOp<Qubit[]>` a megfelelő helyreállítási eljárás lehet.</span><span class="sxs-lookup"><span data-stu-id="b1946-109">For instance, if a particular error correction syndrome indicates that no error has occurred, `NoOp<Qubit[]>` may be the correct recovery procedure.</span></span>
<span data-ttu-id="b1946-110">Hasonlóképpen, ha egy művelet egy állapot-előkészítési eljárást vár bemenetként, `NoOp<Qubit[]>` felkészítheti a $ \ket{0 \cdots 0} $ állapotot.</span><span class="sxs-lookup"><span data-stu-id="b1946-110">Similarly, if an operation expects a state preparation procedure as input, `NoOp<Qubit[]>` can be used to prepare the state $\ket{0 \cdots 0}$.</span></span>

## <a name="input"></a><span data-ttu-id="b1946-111">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b1946-111">Input</span></span>

### <a name="input--t"></a><span data-ttu-id="b1946-112">bemenet: nem</span><span class="sxs-lookup"><span data-stu-id="b1946-112">input : 'T</span></span>

<span data-ttu-id="b1946-113">A figyelmen kívül hagyott érték.</span><span class="sxs-lookup"><span data-stu-id="b1946-113">A value to be ignored.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b1946-114">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b1946-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b1946-115">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="b1946-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b1946-116">Nem</span><span class="sxs-lookup"><span data-stu-id="b1946-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="b1946-117">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="b1946-117">Remarks</span></span>

<span data-ttu-id="b1946-118">Szinte minden esetben explicit módon meg kell adni a type paramétert `NoOp` .</span><span class="sxs-lookup"><span data-stu-id="b1946-118">In almost all cases, the type parameter for `NoOp` needs to be specified explicitly.</span></span> <span data-ttu-id="b1946-119">A például megegyezik a következővel: `NoOp<Qubit>` <xref:microsoft.quantum.intrinsic.i> .</span><span class="sxs-lookup"><span data-stu-id="b1946-119">For instance, `NoOp<Qubit>` is identical to <xref:microsoft.quantum.intrinsic.i>.</span></span>

## <a name="see-also"></a><span data-ttu-id="b1946-120">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="b1946-120">See Also</span></span>

- [<span data-ttu-id="b1946-121">Microsoft. Quantum. belső. I</span><span class="sxs-lookup"><span data-stu-id="b1946-121">Microsoft.Quantum.Intrinsic.I</span></span>](xref:Microsoft.Quantum.Intrinsic.I)