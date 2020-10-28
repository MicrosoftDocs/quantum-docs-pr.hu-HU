---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBEA
title: ReversedOpBEA függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBEA
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: b2418911e71c0b98e1a78247b2ae066887d89cd8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719693"
---
# <a name="reversedopbea-function"></a><span data-ttu-id="d1235-102">ReversedOpBEA függvény</span><span class="sxs-lookup"><span data-stu-id="d1235-102">ReversedOpBEA function</span></span>

<span data-ttu-id="d1235-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d1235-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d1235-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d1235-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d1235-105">Olyan művelet miatt, amely nagy endian adatbevitelt igényel, egy új műveletet ad vissza, amely egy kis endian-bemenetet vesz igénybe.</span><span class="sxs-lookup"><span data-stu-id="d1235-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBEA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="d1235-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="d1235-106">Input</span></span>

### <a name="op--bigendian--unit-adj"></a><span data-ttu-id="d1235-107">op: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [egység](xref:microsoft.quantum.lang-ref.unit) – Adj</span><span class="sxs-lookup"><span data-stu-id="d1235-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="d1235-108">Az a művelet, amelynek a bemenetét vissza kell fordítani.</span><span class="sxs-lookup"><span data-stu-id="d1235-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit-adj"></a><span data-ttu-id="d1235-109">Kimenet: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [egység](xref:microsoft.quantum.lang-ref.unit) – Adj</span><span class="sxs-lookup"><span data-stu-id="d1235-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="d1235-110">Új művelet, amely kis endian-regisztrációként fogadja el a bemenetét.</span><span class="sxs-lookup"><span data-stu-id="d1235-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="d1235-111">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="d1235-111">See Also</span></span>

- [<span data-ttu-id="d1235-112">Microsoft. Quantum. aritmetika. ApplyReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="d1235-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [<span data-ttu-id="d1235-113">Microsoft. Quantum. aritmetika. ReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="d1235-113">Microsoft.Quantum.Arithmetic.ReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [<span data-ttu-id="d1235-114">Microsoft. Quantum. aritmetika. ReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="d1235-114">Microsoft.Quantum.Arithmetic.ReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)
- [<span data-ttu-id="d1235-115">Microsoft. Quantum. aritmetika. ReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="d1235-115">Microsoft.Quantum.Arithmetic.ReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)