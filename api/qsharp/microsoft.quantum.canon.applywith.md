---
uid: Microsoft.Quantum.Canon.ApplyWith
title: ApplyWith művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWith
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: 7127df047a260b18d75efb092e8e090e2d0b207a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850410"
---
# <a name="applywith-operation"></a><span data-ttu-id="30020-102">ApplyWith művelet</span><span class="sxs-lookup"><span data-stu-id="30020-102">ApplyWith operation</span></span>

<span data-ttu-id="30020-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="30020-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="30020-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="30020-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="30020-105">A két művelet miatt a rendszer az egyiket a másikkal konjugáltként alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="30020-105">Given two operations, applies one as conjugated with the other.</span></span>

```qsharp
operation ApplyWith<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit), target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="30020-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="30020-106">Description</span></span>

<span data-ttu-id="30020-107">A két művelet, illetve a $U $ és a $V $ közötti, az egységes operátorok által leírt módon alkalmazza őket a következő sorrendben: $U ^ {\dagger} V U $.</span><span class="sxs-lookup"><span data-stu-id="30020-107">Given two operations, respectively described by unitary operators $U$ and $V$, applies them in the sequence $U^{\dagger} V U$.</span></span> <span data-ttu-id="30020-108">Ez a művelet megvalósítja a $V $ konjugált $U $-vel való összeláncolását.</span><span class="sxs-lookup"><span data-stu-id="30020-108">That is, this operation implements the unitary operator given by $V$ conjugated with $U$.</span></span>

## <a name="input"></a><span data-ttu-id="30020-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="30020-109">Input</span></span>

### <a name="outeroperation--t--unit--is-adj"></a><span data-ttu-id="30020-110">outerOperation: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="30020-110">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="30020-111">$U $ művelet, amelyet a $V $ konjugátumhoz kell használni.</span><span class="sxs-lookup"><span data-stu-id="30020-111">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="30020-112">Vegye figyelembe, hogy a külső műveletnek $U $ adjointable kell lennie, de nem feltétlenül szükséges.</span><span class="sxs-lookup"><span data-stu-id="30020-112">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit"></a><span data-ttu-id="30020-113">innerOperation: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="30020-113">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="30020-114">Az a művelet, $V $ konjugált.</span><span class="sxs-lookup"><span data-stu-id="30020-114">The operation $V$ being conjugated.</span></span>


### <a name="target--t"></a><span data-ttu-id="30020-115">cél: nem</span><span class="sxs-lookup"><span data-stu-id="30020-115">target : 'T</span></span>

<span data-ttu-id="30020-116">A külső és belső műveletekhez megadott bemenet.</span><span class="sxs-lookup"><span data-stu-id="30020-116">The input to be provided to the outer and inner operations.</span></span>



## <a name="output--unit"></a><span data-ttu-id="30020-117">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="30020-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="30020-118">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="30020-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="30020-119">Nem</span><span class="sxs-lookup"><span data-stu-id="30020-119">'T</span></span>

<span data-ttu-id="30020-120">Az a cél, amelyen az egyes belső és külső műveletek működnek.</span><span class="sxs-lookup"><span data-stu-id="30020-120">The target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="30020-121">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="30020-121">Remarks</span></span>

<span data-ttu-id="30020-122">A külső művelet mindig adjointable, de nem szükséges ahhoz, hogy az összevont művelet ellenőrizhető legyen, és ne legyenek ellenőrizhetők.</span><span class="sxs-lookup"><span data-stu-id="30020-122">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="30020-123">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="30020-123">See Also</span></span>

- [<span data-ttu-id="30020-124">Microsoft. Quantum. Canon. ApplyWithA</span><span class="sxs-lookup"><span data-stu-id="30020-124">Microsoft.Quantum.Canon.ApplyWithA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithA)
- [<span data-ttu-id="30020-125">Microsoft. Quantum. Canon. ApplyWithC</span><span class="sxs-lookup"><span data-stu-id="30020-125">Microsoft.Quantum.Canon.ApplyWithC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithC)
- [<span data-ttu-id="30020-126">Microsoft. Quantum. Canon. ApplyWithCA</span><span class="sxs-lookup"><span data-stu-id="30020-126">Microsoft.Quantum.Canon.ApplyWithCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithCA)