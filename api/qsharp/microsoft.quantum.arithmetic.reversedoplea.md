---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLEA
title: ReversedOpLEA függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLEA
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: b0fcf1c735bb19308a381307e64314d9d961e5da
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846424"
---
# <a name="reversedoplea-function"></a><span data-ttu-id="3f3e0-102">ReversedOpLEA függvény</span><span class="sxs-lookup"><span data-stu-id="3f3e0-102">ReversedOpLEA function</span></span>

<span data-ttu-id="3f3e0-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="3f3e0-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="3f3e0-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3f3e0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3f3e0-105">Egy kis endian bemeneti művelet miatt egy új műveletet ad vissza, amely egy nagy endian-bemenetet vesz igénybe.</span><span class="sxs-lookup"><span data-stu-id="3f3e0-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLEA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="3f3e0-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="3f3e0-106">Input</span></span>

### <a name="op--littleendian--unit--is-adj"></a><span data-ttu-id="3f3e0-107">op: az [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3f3e0-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="3f3e0-108">Az a művelet, amelynek a bemenetét vissza kell fordítani.</span><span class="sxs-lookup"><span data-stu-id="3f3e0-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit--is-adj"></a><span data-ttu-id="3f3e0-109">Kimenet: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3f3e0-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="3f3e0-110">Új művelet, amely nagy endian-regisztrációként fogadja el a bemenetét.</span><span class="sxs-lookup"><span data-stu-id="3f3e0-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="3f3e0-111">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="3f3e0-111">See Also</span></span>

- [<span data-ttu-id="3f3e0-112">Microsoft. Quantum. aritmetika. ApplyReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="3f3e0-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [<span data-ttu-id="3f3e0-113">Microsoft. Quantum. aritmetika. ReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="3f3e0-113">Microsoft.Quantum.Arithmetic.ReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [<span data-ttu-id="3f3e0-114">Microsoft. Quantum. aritmetika. ReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="3f3e0-114">Microsoft.Quantum.Arithmetic.ReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)
- [<span data-ttu-id="3f3e0-115">Microsoft. Quantum. aritmetika. ReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="3f3e0-115">Microsoft.Quantum.Arithmetic.ReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)