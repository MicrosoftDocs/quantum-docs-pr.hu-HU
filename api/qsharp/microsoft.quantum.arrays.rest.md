---
uid: Microsoft.Quantum.Arrays.Rest
title: Rest-függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Rest
qsharp.summary: Creates an array that is equal to an input array except that the first array element is dropped.
ms.openlocfilehash: b6c579df354185a2defb08cd78bce816d8cc5959
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845479"
---
# <a name="rest-function"></a><span data-ttu-id="da894-102">Rest-függvény</span><span class="sxs-lookup"><span data-stu-id="da894-102">Rest function</span></span>

<span data-ttu-id="da894-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="da894-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="da894-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="da894-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="da894-105">Egy olyan tömböt hoz létre, amely egy bemeneti tömbnek felel meg, kivéve, hogy az első tömb elem el lett dobva.</span><span class="sxs-lookup"><span data-stu-id="da894-105">Creates an array that is equal to an input array except that the first array element is dropped.</span></span>

```qsharp
function Rest<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="da894-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="da894-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="da894-107">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="da894-107">array : 'T[]</span></span>

<span data-ttu-id="da894-108">Az a tömb, amelynek az utolsó eleme a kimeneti tömb alkotása.</span><span class="sxs-lookup"><span data-stu-id="da894-108">An array whose second to last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="da894-109">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="da894-109">Output : 'T[]</span></span>

<span data-ttu-id="da894-110">Az elemeket tartalmazó tömb `array[1..Length(array) - 1]` .</span><span class="sxs-lookup"><span data-stu-id="da894-110">An array containing the elements `array[1..Length(array) - 1]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="da894-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="da894-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="da894-112">Nem</span><span class="sxs-lookup"><span data-stu-id="da894-112">'T</span></span>

<span data-ttu-id="da894-113">A tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="da894-113">The type of the array elements.</span></span>