---
uid: Microsoft.Quantum.Targeting.RequiresCapability
title: RequiresCapability-felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Targeting
qsharp.name: RequiresCapability
qsharp.summary: Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.
ms.openlocfilehash: 63b1952d402f1bcb81a8f9d0afc3cdf7aa7e5ed8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725138"
---
# <a name="requirescapability-user-defined-type"></a><span data-ttu-id="05f09-102">RequiresCapability-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="05f09-102">RequiresCapability user defined type</span></span>

<span data-ttu-id="05f09-103">Névtér: [Microsoft. Quantum. Targeting](xref:Microsoft.Quantum.Targeting)</span><span class="sxs-lookup"><span data-stu-id="05f09-103">Namespace: [Microsoft.Quantum.Targeting](xref:Microsoft.Quantum.Targeting)</span></span>

<span data-ttu-id="05f09-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="05f09-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="05f09-105">Fordító által felismert attribútum, amely egy meghívót jelöl meg a szükséges futtatókörnyezeti képességekkel.</span><span class="sxs-lookup"><span data-stu-id="05f09-105">Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype RequiresCapability = (Level : String, Reason : String);
```



## <a name="named-items"></a><span data-ttu-id="05f09-106">Megnevezett elemek</span><span class="sxs-lookup"><span data-stu-id="05f09-106">Named Items</span></span>

### <a name="level--string"></a><span data-ttu-id="05f09-107">Szint: [sztring](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="05f09-107">Level : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="05f09-108">A meghíváshoz szükséges futásidejű képességi szint neve.</span><span class="sxs-lookup"><span data-stu-id="05f09-108">The name of the runtime capability level required by the callable.</span></span>
### <a name="reason--string"></a><span data-ttu-id="05f09-109">Ok: [karakterlánc](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="05f09-109">Reason : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="05f09-110">Annak leírása, hogy a hívó miért igényli ezt a futásidejű képességet.</span><span class="sxs-lookup"><span data-stu-id="05f09-110">A description of why the callable requires this runtime capability.</span></span>

## <a name="remarks"></a><span data-ttu-id="05f09-111">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="05f09-111">Remarks</span></span>

<span data-ttu-id="05f09-112">Ezt az attribútumot a fordító automatikusan hozzáadja a callables, kivéve, ha az attribútum egy példánya már létezik a meghívóhoz.</span><span class="sxs-lookup"><span data-stu-id="05f09-112">This attribute is automatically added to callables by the compiler, unless an instance of this attribute already exists on the callable.</span></span> <span data-ttu-id="05f09-113">Nem használható, kivéve olyan ritka esetekben, amikor a fordító nem következteti ki a szükséges képességet.</span><span class="sxs-lookup"><span data-stu-id="05f09-113">It should not be used except in rare cases where the compiler does not infer the required capability correctly.</span></span>

<span data-ttu-id="05f09-114">Az alábbi lista a képességek szintjének neveinek listáját mutatja be a kapacitás növelése vagy a csökkenő korlátozások érdekében:</span><span class="sxs-lookup"><span data-stu-id="05f09-114">Below is the list of capability level names, in order of increasing capabilities or decreasing restrictions:</span></span>

## `"BasicQuantumFunctionality"`

<span data-ttu-id="05f09-115">A mérési eredmények nem hasonlíthatók össze az egyenlőséghez.</span><span class="sxs-lookup"><span data-stu-id="05f09-115">Measurement results cannot be compared for equality.</span></span>

## `"BasicMeasurementFeedback"`

<span data-ttu-id="05f09-116">A mérési eredmények összehasonlítható a műveletekben szereplő if-utasítás feltételes kifejezésekben szereplő egyenlőséggel.</span><span class="sxs-lookup"><span data-stu-id="05f09-116">Measurement results can be compared for equality only in if-statement conditional expressions in operations.</span></span> <span data-ttu-id="05f09-117">Egy Eredménytől függő if-utasítás blokkban nem szerepelhetnek a blokkon kívül deklarált, változtatható változókhoz tartozó set utasítások, vagy a Return utasítások.</span><span class="sxs-lookup"><span data-stu-id="05f09-117">The block of an if-statement that depends on a result cannot contain set statements for mutable variables declared outside the block, or return statements.</span></span>

## `"FullComputation"`

<span data-ttu-id="05f09-118">Nincs futásidejű korlátozás.</span><span class="sxs-lookup"><span data-stu-id="05f09-118">No runtime restrictions.</span></span> <span data-ttu-id="05f09-119">Bármely Q # program végrehajtható.</span><span class="sxs-lookup"><span data-stu-id="05f09-119">Any Q# program can be executed.</span></span>