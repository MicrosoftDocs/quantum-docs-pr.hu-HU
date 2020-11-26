---
uid: Microsoft.Quantum.Targeting.RequiresCapability
title: RequiresCapability-felhasználó által definiált típus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Targeting
qsharp.name: RequiresCapability
qsharp.summary: Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.
ms.openlocfilehash: 0d9e4eb294b3ce91058c204d5dba37ea29b4ac28
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231007"
---
# <a name="requirescapability-user-defined-type"></a><span data-ttu-id="b5709-102">RequiresCapability-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="b5709-102">RequiresCapability user defined type</span></span>

<span data-ttu-id="b5709-103">Névtér: [Microsoft. Quantum. Targeting](xref:Microsoft.Quantum.Targeting)</span><span class="sxs-lookup"><span data-stu-id="b5709-103">Namespace: [Microsoft.Quantum.Targeting](xref:Microsoft.Quantum.Targeting)</span></span>

<span data-ttu-id="b5709-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="b5709-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="b5709-105">Fordító által felismert attribútum, amely egy meghívót jelöl meg a szükséges futtatókörnyezeti képességekkel.</span><span class="sxs-lookup"><span data-stu-id="b5709-105">Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype RequiresCapability = (Level : String, Reason : String);
```



## <a name="named-items"></a><span data-ttu-id="b5709-106">Megnevezett elemek</span><span class="sxs-lookup"><span data-stu-id="b5709-106">Named Items</span></span>

### <a name="level--string"></a><span data-ttu-id="b5709-107">Szint: [sztring](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="b5709-107">Level : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="b5709-108">A meghíváshoz szükséges futásidejű képességi szint neve.</span><span class="sxs-lookup"><span data-stu-id="b5709-108">The name of the runtime capability level required by the callable.</span></span>
### <a name="reason--string"></a><span data-ttu-id="b5709-109">Ok: [karakterlánc](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="b5709-109">Reason : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="b5709-110">Annak leírása, hogy a hívó miért igényli ezt a futásidejű képességet.</span><span class="sxs-lookup"><span data-stu-id="b5709-110">A description of why the callable requires this runtime capability.</span></span>

## <a name="remarks"></a><span data-ttu-id="b5709-111">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="b5709-111">Remarks</span></span>

<span data-ttu-id="b5709-112">Ezt az attribútumot a fordító automatikusan hozzáadja a callables, kivéve, ha az attribútum egy példánya már létezik a meghívóhoz.</span><span class="sxs-lookup"><span data-stu-id="b5709-112">This attribute is automatically added to callables by the compiler, unless an instance of this attribute already exists on the callable.</span></span> <span data-ttu-id="b5709-113">Nem használható, kivéve olyan ritka esetekben, amikor a fordító nem következteti ki a szükséges képességet.</span><span class="sxs-lookup"><span data-stu-id="b5709-113">It should not be used except in rare cases where the compiler does not infer the required capability correctly.</span></span>

<span data-ttu-id="b5709-114">Az alábbi lista a képességek szintjének neveinek listáját mutatja be a kapacitás növelése vagy a csökkenő korlátozások érdekében:</span><span class="sxs-lookup"><span data-stu-id="b5709-114">Below is the list of capability level names, in order of increasing capabilities or decreasing restrictions:</span></span>

## `"BasicQuantumFunctionality"`

<span data-ttu-id="b5709-115">A mérési eredmények nem hasonlíthatók össze az egyenlőséghez.</span><span class="sxs-lookup"><span data-stu-id="b5709-115">Measurement results cannot be compared for equality.</span></span>

## `"BasicMeasurementFeedback"`

<span data-ttu-id="b5709-116">A mérési eredmények összehasonlítható a műveletekben szereplő if-utasítás feltételes kifejezésekben szereplő egyenlőséggel.</span><span class="sxs-lookup"><span data-stu-id="b5709-116">Measurement results can be compared for equality only in if-statement conditional expressions in operations.</span></span> <span data-ttu-id="b5709-117">Egy Eredménytől függő if-utasítás blokkban nem szerepelhetnek a blokkon kívül deklarált, változtatható változókhoz tartozó set utasítások, vagy a Return utasítások.</span><span class="sxs-lookup"><span data-stu-id="b5709-117">The block of an if-statement that depends on a result cannot contain set statements for mutable variables declared outside the block, or return statements.</span></span>

## `"FullComputation"`

<span data-ttu-id="b5709-118">Nincs futásidejű korlátozás.</span><span class="sxs-lookup"><span data-stu-id="b5709-118">No runtime restrictions.</span></span> <span data-ttu-id="b5709-119">Bármely Q # program végrehajtható.</span><span class="sxs-lookup"><span data-stu-id="b5709-119">Any Q# program can be executed.</span></span>