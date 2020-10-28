---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBECA
title: ReversedOpBECA függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBECA
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 5617e191260903ac25effc8b922810932b7dc505
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719668"
---
# <a name="reversedopbeca-function"></a><span data-ttu-id="1db7b-102">ReversedOpBECA függvény</span><span class="sxs-lookup"><span data-stu-id="1db7b-102">ReversedOpBECA function</span></span>

<span data-ttu-id="1db7b-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="1db7b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="1db7b-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1db7b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1db7b-105">Olyan művelet miatt, amely nagy endian adatbevitelt igényel, egy új műveletet ad vissza, amely egy kis endian-bemenetet vesz igénybe.</span><span class="sxs-lookup"><span data-stu-id="1db7b-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBECA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj + Ctl)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="1db7b-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="1db7b-106">Input</span></span>

### <a name="op--bigendian--unit-adj--ctl"></a><span data-ttu-id="1db7b-107">op: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [egység](xref:microsoft.quantum.lang-ref.unit) – Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="1db7b-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="1db7b-108">Az a művelet, amelynek a bemenetét vissza kell fordítani.</span><span class="sxs-lookup"><span data-stu-id="1db7b-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit-adj--ctl"></a><span data-ttu-id="1db7b-109">Kimenet: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [egység](xref:microsoft.quantum.lang-ref.unit) , adj + CTL</span><span class="sxs-lookup"><span data-stu-id="1db7b-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="1db7b-110">Új művelet, amely kis endian-regisztrációként fogadja el a bemenetét.</span><span class="sxs-lookup"><span data-stu-id="1db7b-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="1db7b-111">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="1db7b-111">See Also</span></span>

- [<span data-ttu-id="1db7b-112">Microsoft. Quantum. aritmetika. ApplyReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="1db7b-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)
- [<span data-ttu-id="1db7b-113">Microsoft. Quantum. aritmetika. ReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="1db7b-113">Microsoft.Quantum.Arithmetic.ReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [<span data-ttu-id="1db7b-114">Microsoft. Quantum. aritmetika. ReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="1db7b-114">Microsoft.Quantum.Arithmetic.ReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [<span data-ttu-id="1db7b-115">Microsoft. Quantum. aritmetika. ReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="1db7b-115">Microsoft.Quantum.Arithmetic.ReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)