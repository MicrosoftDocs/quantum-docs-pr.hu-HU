---
uid: Microsoft.Quantum.Canon.ConjugatedBy
title: ConjugatedBy függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedBy
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: 37fbee9a7c11991645933a372f9f12c1fd696b66
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716469"
---
# <a name="conjugatedby-function"></a><span data-ttu-id="792b6-102">ConjugatedBy függvény</span><span class="sxs-lookup"><span data-stu-id="792b6-102">ConjugatedBy function</span></span>

<span data-ttu-id="792b6-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="792b6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="792b6-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="792b6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="792b6-105">Az adott külső és belső műveletek olyan új műveletet adnak vissza, amely a belső műveletet a külső művelettel végzi.</span><span class="sxs-lookup"><span data-stu-id="792b6-105">Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.</span></span>

```qsharp
function ConjugatedBy<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit)) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="792b6-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="792b6-106">Input</span></span>

### <a name="outeroperation--t--unit-adj"></a><span data-ttu-id="792b6-107">outerOperation: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) – Adj</span><span class="sxs-lookup"><span data-stu-id="792b6-107">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="792b6-108">$U $ művelet, amelyet a $V $ konjugátumhoz kell használni.</span><span class="sxs-lookup"><span data-stu-id="792b6-108">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="792b6-109">Vegye figyelembe, hogy a külső műveletnek $U $ adjointable kell lennie, de nem feltétlenül szükséges.</span><span class="sxs-lookup"><span data-stu-id="792b6-109">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit"></a><span data-ttu-id="792b6-110">innerOperation: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="792b6-110">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="792b6-111">Az a művelet, $V $ konjugált.</span><span class="sxs-lookup"><span data-stu-id="792b6-111">The operation $V$ being conjugated.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="792b6-112">Kimenet: nem => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="792b6-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="792b6-113">Egy új művelet, amelynek a műveletét az egységes $U ^ {\dagger} V U $ jelképezi.</span><span class="sxs-lookup"><span data-stu-id="792b6-113">A new operation whose action is represented by the unitary $U^{\dagger} V U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="792b6-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="792b6-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="792b6-115">Nem</span><span class="sxs-lookup"><span data-stu-id="792b6-115">'T</span></span>

<span data-ttu-id="792b6-116">Annak a célnak a típusa, amelyen a belső és a külső műveletek működnek.</span><span class="sxs-lookup"><span data-stu-id="792b6-116">The type of the target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="792b6-117">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="792b6-117">Remarks</span></span>

<span data-ttu-id="792b6-118">A külső művelet mindig adjointable, de nem szükséges ahhoz, hogy az összevont művelet ellenőrizhető legyen, és ne legyenek ellenőrizhetők.</span><span class="sxs-lookup"><span data-stu-id="792b6-118">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="792b6-119">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="792b6-119">See Also</span></span>

- [<span data-ttu-id="792b6-120">Microsoft. Quantum. Canon. ConjugatedByA</span><span class="sxs-lookup"><span data-stu-id="792b6-120">Microsoft.Quantum.Canon.ConjugatedByA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [<span data-ttu-id="792b6-121">Microsoft. Quantum. Canon. ConjugatedByC</span><span class="sxs-lookup"><span data-stu-id="792b6-121">Microsoft.Quantum.Canon.ConjugatedByC</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByC)
- [<span data-ttu-id="792b6-122">Microsoft. Quantum. Canon. ConjugatedByCA</span><span class="sxs-lookup"><span data-stu-id="792b6-122">Microsoft.Quantum.Canon.ConjugatedByCA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [<span data-ttu-id="792b6-123">Microsoft. Quantum. Canon. ApplyWith</span><span class="sxs-lookup"><span data-stu-id="792b6-123">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)