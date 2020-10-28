---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLEA
title: ReversedOpLEA függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLEA
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: eabeb8e068ef32cf6717efd6e818271a667b39b2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719644"
---
# <a name="reversedoplea-function"></a><span data-ttu-id="ed7e6-102">ReversedOpLEA függvény</span><span class="sxs-lookup"><span data-stu-id="ed7e6-102">ReversedOpLEA function</span></span>

<span data-ttu-id="ed7e6-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ed7e6-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ed7e6-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ed7e6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ed7e6-105">Egy kis endian bemeneti művelet miatt egy új műveletet ad vissza, amely egy nagy endian-bemenetet vesz igénybe.</span><span class="sxs-lookup"><span data-stu-id="ed7e6-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLEA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="ed7e6-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="ed7e6-106">Input</span></span>

### <a name="op--littleendian--unit-adj"></a><span data-ttu-id="ed7e6-107">op: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [egység](xref:microsoft.quantum.lang-ref.unit) – Adj</span><span class="sxs-lookup"><span data-stu-id="ed7e6-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="ed7e6-108">Az a művelet, amelynek a bemenetét vissza kell fordítani.</span><span class="sxs-lookup"><span data-stu-id="ed7e6-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit-adj"></a><span data-ttu-id="ed7e6-109">Kimenet: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [egység](xref:microsoft.quantum.lang-ref.unit) – Adj</span><span class="sxs-lookup"><span data-stu-id="ed7e6-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="ed7e6-110">Új művelet, amely nagy endian-regisztrációként fogadja el a bemenetét.</span><span class="sxs-lookup"><span data-stu-id="ed7e6-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="ed7e6-111">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="ed7e6-111">See Also</span></span>

- [<span data-ttu-id="ed7e6-112">Microsoft. Quantum. aritmetika. ApplyReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="ed7e6-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [<span data-ttu-id="ed7e6-113">Microsoft. Quantum. aritmetika. ReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="ed7e6-113">Microsoft.Quantum.Arithmetic.ReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [<span data-ttu-id="ed7e6-114">Microsoft. Quantum. aritmetika. ReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="ed7e6-114">Microsoft.Quantum.Arithmetic.ReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)
- [<span data-ttu-id="ed7e6-115">Microsoft. Quantum. aritmetika. ReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="ed7e6-115">Microsoft.Quantum.Arithmetic.ReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)