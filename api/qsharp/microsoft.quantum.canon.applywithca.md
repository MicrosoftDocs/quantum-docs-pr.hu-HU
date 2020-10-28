---
uid: Microsoft.Quantum.Canon.ApplyWithCA
title: ApplyWithCA művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithCA
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: abc62791416e78c1b2937a226327b71da8b8e288
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716888"
---
# <a name="applywithca-operation"></a><span data-ttu-id="46302-102">ApplyWithCA művelet</span><span class="sxs-lookup"><span data-stu-id="46302-102">ApplyWithCA operation</span></span>

<span data-ttu-id="46302-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="46302-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="46302-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="46302-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="46302-105">A két művelet miatt a rendszer az egyiket a másikkal konjugáltként alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="46302-105">Given two operations, applies one as conjugated with the other.</span></span>

```qsharp
operation ApplyWithCA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj + Ctl), target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="46302-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="46302-106">Description</span></span>

<span data-ttu-id="46302-107">A két művelet, illetve a $U $ és a $V $ közötti, az egységes operátorok által leírt módon alkalmazza őket a következő sorrendben: $U ^ {\dagger} V U $.</span><span class="sxs-lookup"><span data-stu-id="46302-107">Given two operations, respectively described by unitary operators $U$ and $V$, applies them in the sequence $U^{\dagger} V U$.</span></span> <span data-ttu-id="46302-108">Ez a művelet megvalósítja a $V $ konjugált $U $-vel való összeláncolását.</span><span class="sxs-lookup"><span data-stu-id="46302-108">That is, this operation implements the unitary operator given by $V$ conjugated with $U$.</span></span>

## <a name="input"></a><span data-ttu-id="46302-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="46302-109">Input</span></span>

### <a name="outeroperation--t--unit-adj"></a><span data-ttu-id="46302-110">outerOperation: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) – Adj</span><span class="sxs-lookup"><span data-stu-id="46302-110">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="46302-111">$U $ művelet, amelyet a $V $ konjugátumhoz kell használni.</span><span class="sxs-lookup"><span data-stu-id="46302-111">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="46302-112">Vegye figyelembe, hogy a külső műveletnek $U $ adjointable kell lennie, de nem feltétlenül szükséges.</span><span class="sxs-lookup"><span data-stu-id="46302-112">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit-adj--ctl"></a><span data-ttu-id="46302-113">innerOperation: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) , adj + CTL</span><span class="sxs-lookup"><span data-stu-id="46302-113">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="46302-114">Az a művelet, $V $ konjugált.</span><span class="sxs-lookup"><span data-stu-id="46302-114">The operation $V$ being conjugated.</span></span>


### <a name="target--t"></a><span data-ttu-id="46302-115">cél: nem</span><span class="sxs-lookup"><span data-stu-id="46302-115">target : 'T</span></span>

<span data-ttu-id="46302-116">A külső és belső műveletekhez megadott bemenet.</span><span class="sxs-lookup"><span data-stu-id="46302-116">The input to be provided to the outer and inner operations.</span></span>



## <a name="output--unit"></a><span data-ttu-id="46302-117">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="46302-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="46302-118">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="46302-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="46302-119">Nem</span><span class="sxs-lookup"><span data-stu-id="46302-119">'T</span></span>

<span data-ttu-id="46302-120">Az a cél, amelyen az egyes belső és külső műveletek működnek.</span><span class="sxs-lookup"><span data-stu-id="46302-120">The target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="46302-121">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="46302-121">Remarks</span></span>

<span data-ttu-id="46302-122">A külső művelet mindig adjointable, de nem szükséges ahhoz, hogy az összevont művelet ellenőrizhető legyen, és ne legyenek ellenőrizhetők.</span><span class="sxs-lookup"><span data-stu-id="46302-122">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="46302-123">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="46302-123">See Also</span></span>

- [<span data-ttu-id="46302-124">Microsoft. Quantum. Canon. ApplyWith</span><span class="sxs-lookup"><span data-stu-id="46302-124">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)
- [<span data-ttu-id="46302-125">Microsoft. Quantum. Canon. ApplyWithA</span><span class="sxs-lookup"><span data-stu-id="46302-125">Microsoft.Quantum.Canon.ApplyWithA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithA)
- [<span data-ttu-id="46302-126">Microsoft. Quantum. Canon. ApplyWithC</span><span class="sxs-lookup"><span data-stu-id="46302-126">Microsoft.Quantum.Canon.ApplyWithC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithC)