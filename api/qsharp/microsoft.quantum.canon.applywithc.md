---
uid: Microsoft.Quantum.Canon.ApplyWithC
title: ApplyWithC művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithC
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: 8de1ddf0bf176853b33926be7647bc5d1d35095d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716902"
---
# <a name="applywithc-operation"></a><span data-ttu-id="ad3e5-102">ApplyWithC művelet</span><span class="sxs-lookup"><span data-stu-id="ad3e5-102">ApplyWithC operation</span></span>

<span data-ttu-id="ad3e5-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ad3e5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ad3e5-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ad3e5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ad3e5-105">A két művelet miatt a rendszer az egyiket a másikkal konjugáltként alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="ad3e5-105">Given two operations, applies one as conjugated with the other.</span></span>

```qsharp
operation ApplyWithC<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Ctl), target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="ad3e5-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="ad3e5-106">Description</span></span>

<span data-ttu-id="ad3e5-107">A két művelet, illetve a $U $ és a $V $ közötti, az egységes operátorok által leírt módon alkalmazza őket a következő sorrendben: $U ^ {\dagger} V U $.</span><span class="sxs-lookup"><span data-stu-id="ad3e5-107">Given two operations, respectively described by unitary operators $U$ and $V$, applies them in the sequence $U^{\dagger} V U$.</span></span> <span data-ttu-id="ad3e5-108">Ez a művelet megvalósítja a $V $ konjugált $U $-vel való összeláncolását.</span><span class="sxs-lookup"><span data-stu-id="ad3e5-108">That is, this operation implements the unitary operator given by $V$ conjugated with $U$.</span></span>

## <a name="input"></a><span data-ttu-id="ad3e5-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="ad3e5-109">Input</span></span>

### <a name="outeroperation--t--unit-adj"></a><span data-ttu-id="ad3e5-110">outerOperation: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) – Adj</span><span class="sxs-lookup"><span data-stu-id="ad3e5-110">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="ad3e5-111">$U $ művelet, amelyet a $V $ konjugátumhoz kell használni.</span><span class="sxs-lookup"><span data-stu-id="ad3e5-111">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="ad3e5-112">Vegye figyelembe, hogy a külső műveletnek $U $ adjointable kell lennie, de nem feltétlenül szükséges.</span><span class="sxs-lookup"><span data-stu-id="ad3e5-112">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit-ctl"></a><span data-ttu-id="ad3e5-113">innerOperation: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="ad3e5-113">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="ad3e5-114">Az a művelet, $V $ konjugált.</span><span class="sxs-lookup"><span data-stu-id="ad3e5-114">The operation $V$ being conjugated.</span></span>


### <a name="target--t"></a><span data-ttu-id="ad3e5-115">cél: nem</span><span class="sxs-lookup"><span data-stu-id="ad3e5-115">target : 'T</span></span>

<span data-ttu-id="ad3e5-116">A külső és belső műveletekhez megadott bemenet.</span><span class="sxs-lookup"><span data-stu-id="ad3e5-116">The input to be provided to the outer and inner operations.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ad3e5-117">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ad3e5-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ad3e5-118">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="ad3e5-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ad3e5-119">Nem</span><span class="sxs-lookup"><span data-stu-id="ad3e5-119">'T</span></span>

<span data-ttu-id="ad3e5-120">Az a cél, amelyen az egyes belső és külső műveletek működnek.</span><span class="sxs-lookup"><span data-stu-id="ad3e5-120">The target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="ad3e5-121">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="ad3e5-121">Remarks</span></span>

<span data-ttu-id="ad3e5-122">A külső művelet mindig adjointable, de nem szükséges ahhoz, hogy az összevont művelet ellenőrizhető legyen, és ne legyenek ellenőrizhetők.</span><span class="sxs-lookup"><span data-stu-id="ad3e5-122">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="ad3e5-123">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="ad3e5-123">See Also</span></span>

- [<span data-ttu-id="ad3e5-124">Microsoft. Quantum. Canon. ApplyWith</span><span class="sxs-lookup"><span data-stu-id="ad3e5-124">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)
- [<span data-ttu-id="ad3e5-125">Microsoft. Quantum. Canon. ApplyWithA</span><span class="sxs-lookup"><span data-stu-id="ad3e5-125">Microsoft.Quantum.Canon.ApplyWithA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithA)
- [<span data-ttu-id="ad3e5-126">Microsoft. Quantum. Canon. ApplyWithCA</span><span class="sxs-lookup"><span data-stu-id="ad3e5-126">Microsoft.Quantum.Canon.ApplyWithCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithCA)