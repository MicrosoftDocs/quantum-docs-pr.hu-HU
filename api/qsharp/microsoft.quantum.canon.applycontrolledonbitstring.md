---
uid: Microsoft.Quantum.Canon.ApplyControlledOnBitString
title: ApplyControlledOnBitString művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnBitString
qsharp.summary: Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.
ms.openlocfilehash: 7a054511bacff574e6f7e889ace048c78886cf91
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718360"
---
# <a name="applycontrolledonbitstring-operation"></a><span data-ttu-id="59009-102">ApplyControlledOnBitString művelet</span><span class="sxs-lookup"><span data-stu-id="59009-102">ApplyControlledOnBitString operation</span></span>

<span data-ttu-id="59009-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="59009-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="59009-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="59009-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="59009-105">Egy egységes műveletet alkalmaz a cél-tételjegyzéken, amelyet egy adott bit-maszk által meghatározott állapotban kell vezérelni.</span><span class="sxs-lookup"><span data-stu-id="59009-105">Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.</span></span>

```qsharp
operation ApplyControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="59009-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="59009-106">Input</span></span>

### <a name="bits--bool"></a><span data-ttu-id="59009-107">BITS: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="59009-107">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="59009-108">Az adott egységes műveletnek a-on való vezérlésére szolgáló kis sztring.</span><span class="sxs-lookup"><span data-stu-id="59009-108">The bit string to control the given unitary operation on.</span></span>


### <a name="oracle--t--unit-adj--ctl"></a><span data-ttu-id="59009-109">Oracle: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) : Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="59009-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="59009-110">A cél-regisztráción alkalmazandó egységes művelet.</span><span class="sxs-lookup"><span data-stu-id="59009-110">The unitary operation to be applied on the target register.</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="59009-111">controlRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="59009-111">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="59009-112">Egy kvantum-regisztráció, amely a alkalmazást vezérli `oracle` .</span><span class="sxs-lookup"><span data-stu-id="59009-112">A quantum register that controls application of `oracle`.</span></span>


### <a name="targetregister--t"></a><span data-ttu-id="59009-113">targetRegister: nem</span><span class="sxs-lookup"><span data-stu-id="59009-113">targetRegister : 'T</span></span>

<span data-ttu-id="59009-114">A célként megadott regiszter, amelyet bemenetként kell átadni `oracle` .</span><span class="sxs-lookup"><span data-stu-id="59009-114">The target register to be passed to `oracle` as an input.</span></span>



## <a name="output--unit"></a><span data-ttu-id="59009-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="59009-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="59009-116">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="59009-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="59009-117">Nem</span><span class="sxs-lookup"><span data-stu-id="59009-117">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="59009-118">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="59009-118">Remarks</span></span>

<span data-ttu-id="59009-119">A által megadott minta `bits` rövidebb lehet, mint `controlRegister` , amelynél a rendszer figyelmen kívül hagyja a további vezérlési qubits (azaz nem a $ \ket {0} $, sem a $ \ket $ értéket sem {1} ).</span><span class="sxs-lookup"><span data-stu-id="59009-119">The pattern given by `bits` may be shorter than `controlRegister`, in which case additional control qubits are ignored (that is, neither controlled on $\ket{0}$ nor $\ket{1}$).</span></span>
<span data-ttu-id="59009-120">Ha `bits` a értéke hosszabb `controlRegister` , hiba történik.</span><span class="sxs-lookup"><span data-stu-id="59009-120">If `bits` is longer than `controlRegister`, an error is raised.</span></span>

<span data-ttu-id="59009-121">Például az `bits = [0,1,0,0,1]` azt jelenti, hogy az `oracle` csak akkor van alkalmazva, ha a, és csak akkor, ha `controlRegister` a \ket {0} \ket {1} \ket {0} \ket {0} \ket {1} $ állapotban van.</span><span class="sxs-lookup"><span data-stu-id="59009-121">For example, `bits = [0,1,0,0,1]` means that `oracle` is applied if and only if `controlRegister` is in the state $\ket{0}\ket{1}\ket{0}\ket{0}\ket{1}$.</span></span>