---
uid: Microsoft.Quantum.Canon.ApplyControlledOnInt
title: ApplyControlledOnInt művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnInt
qsharp.summary: Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: c8ea76946143967de4b6ac65986a1c4407ecb633
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718349"
---
# <a name="applycontrolledonint-operation"></a><span data-ttu-id="0bdcd-102">ApplyControlledOnInt művelet</span><span class="sxs-lookup"><span data-stu-id="0bdcd-102">ApplyControlledOnInt operation</span></span>

<span data-ttu-id="0bdcd-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0bdcd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0bdcd-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0bdcd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0bdcd-105">Egy egységes műveletet alkalmaz a cél-tételjegyzéken, ha a vezérlő regisztrálása állapot egy megadott pozitív egész számnak felel meg.</span><span class="sxs-lookup"><span data-stu-id="0bdcd-105">Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
operation ApplyControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="0bdcd-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="0bdcd-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="0bdcd-107">numberState: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0bdcd-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0bdcd-108">Nem negatív egész szám, amelyen a műveletet `oracle` ellenőrizni kell.</span><span class="sxs-lookup"><span data-stu-id="0bdcd-108">A nonnegative integer on which the operation `oracle` should be controlled.</span></span>


### <a name="oracle--t--unit-adj--ctl"></a><span data-ttu-id="0bdcd-109">Oracle: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) : Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="0bdcd-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="0bdcd-110">Egy szabályozható, egységes művelet.</span><span class="sxs-lookup"><span data-stu-id="0bdcd-110">A unitary operation to be controlled.</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="0bdcd-111">controlRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0bdcd-111">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0bdcd-112">Egy kvantum-regisztráció, amely a alkalmazást vezérli `oracle` .</span><span class="sxs-lookup"><span data-stu-id="0bdcd-112">A quantum register that controls application of `oracle`.</span></span>


### <a name="targetregister--t"></a><span data-ttu-id="0bdcd-113">targetRegister: nem</span><span class="sxs-lookup"><span data-stu-id="0bdcd-113">targetRegister : 'T</span></span>

<span data-ttu-id="0bdcd-114">Egy regisztráció, amelyre alkalmazni kell `oracle` .</span><span class="sxs-lookup"><span data-stu-id="0bdcd-114">A register on which to apply `oracle`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0bdcd-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0bdcd-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0bdcd-116">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="0bdcd-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0bdcd-117">Nem</span><span class="sxs-lookup"><span data-stu-id="0bdcd-117">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="0bdcd-118">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="0bdcd-118">Remarks</span></span>

<span data-ttu-id="0bdcd-119">A értéke `numberState` kis endian kódolással értelmezhető.</span><span class="sxs-lookup"><span data-stu-id="0bdcd-119">The value of `numberState` is interpreted using a little-endian encoding.</span></span>

<span data-ttu-id="0bdcd-120">`numberState` legfeljebb 2 ^ \texttt{Length kell lennie (controlRegister)} – $1.</span><span class="sxs-lookup"><span data-stu-id="0bdcd-120">`numberState` must be at most $2^\texttt{Length(controlRegister)} - 1$.</span></span>
<span data-ttu-id="0bdcd-121">Például az `numberState = 537` azt jelenti, hogy az `oracle` csak akkor van alkalmazva, ha a és csak `controlRegister` a $ \ket $ állapotban van {537} .</span><span class="sxs-lookup"><span data-stu-id="0bdcd-121">For example, `numberState = 537` means that `oracle` is applied if and only if `controlRegister` is in the state $\ket{537}$.</span></span>