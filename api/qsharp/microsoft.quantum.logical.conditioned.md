---
uid: Microsoft.Quantum.Logical.Conditioned
title: Feltételes függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: ea3b8eba960acceb6540978c6fccd9f796b0f67d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817285"
---
# <a name="conditioned-function"></a><span data-ttu-id="86aa7-102">Feltételes függvény</span><span class="sxs-lookup"><span data-stu-id="86aa7-102">Conditioned function</span></span>

<span data-ttu-id="86aa7-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="86aa7-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="86aa7-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="86aa7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="86aa7-105">Egy logikai feltétel értékétől függően két érték egyikét adja vissza.</span><span class="sxs-lookup"><span data-stu-id="86aa7-105">Returns one of two values, depending on the value of a Boolean condition.</span></span>

```qsharp
function Conditioned<'T> (condition : Bool, ifTrue : 'T, ifFalse : 'T) : 'T
```


## <a name="input"></a><span data-ttu-id="86aa7-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="86aa7-106">Input</span></span>

### <a name="condition--bool"></a><span data-ttu-id="86aa7-107">feltétel: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="86aa7-107">condition : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="86aa7-108">A visszaadott bemenet szabályozására szolgáló feltétel.</span><span class="sxs-lookup"><span data-stu-id="86aa7-108">A condition used to control which input is returned.</span></span>


### <a name="iftrue--t"></a><span data-ttu-id="86aa7-109">ifTrue: nem</span><span class="sxs-lookup"><span data-stu-id="86aa7-109">ifTrue : 'T</span></span>

<span data-ttu-id="86aa7-110">Az értékeként visszaadott érték `condition` `true` .</span><span class="sxs-lookup"><span data-stu-id="86aa7-110">The value to be returned when `condition` is `true`.</span></span>


### <a name="iffalse--t"></a><span data-ttu-id="86aa7-111">ifFalse: nem</span><span class="sxs-lookup"><span data-stu-id="86aa7-111">ifFalse : 'T</span></span>

<span data-ttu-id="86aa7-112">Az értékeként visszaadott érték `condition` `false` .</span><span class="sxs-lookup"><span data-stu-id="86aa7-112">The value to be returned when `condition` is `false`.</span></span>



## <a name="output--t"></a><span data-ttu-id="86aa7-113">Kimenet: nem</span><span class="sxs-lookup"><span data-stu-id="86aa7-113">Output : 'T</span></span>

<span data-ttu-id="86aa7-114">`ifTrue` Ha `condition` van `true` , és `ifFalse` egyéb módon.</span><span class="sxs-lookup"><span data-stu-id="86aa7-114">`ifTrue` if `condition` is `true`, and `ifFalse` otherwise.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="86aa7-115">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="86aa7-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="86aa7-116">Nem</span><span class="sxs-lookup"><span data-stu-id="86aa7-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="86aa7-117">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="86aa7-117">Remarks</span></span>

<span data-ttu-id="86aa7-118">Az `?|` operátortól eltérően ez a függvény nem rövidzárlat, így mindkét bemenet teljes mértékben ki van értékelve.</span><span class="sxs-lookup"><span data-stu-id="86aa7-118">Unlike the `?|` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="86aa7-119">Akár rövid összekapcsolási viselkedés, a következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="86aa7-119">Up to short-circuiting behavior, the following are equivalent:</span></span>

```qsharp
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```