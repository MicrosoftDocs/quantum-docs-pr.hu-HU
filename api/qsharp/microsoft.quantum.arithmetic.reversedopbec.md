---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBEC
title: ReversedOpBEC függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBEC
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 5e9aa6e6dfef74bca004170cf2b1cd91aa13f0b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719680"
---
# <a name="reversedopbec-function"></a><span data-ttu-id="7d8cf-102">ReversedOpBEC függvény</span><span class="sxs-lookup"><span data-stu-id="7d8cf-102">ReversedOpBEC function</span></span>

<span data-ttu-id="7d8cf-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="7d8cf-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="7d8cf-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7d8cf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7d8cf-105">Olyan művelet miatt, amely nagy endian adatbevitelt igényel, egy új műveletet ad vissza, amely egy kis endian-bemenetet vesz igénybe.</span><span class="sxs-lookup"><span data-stu-id="7d8cf-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBEC (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="7d8cf-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="7d8cf-106">Input</span></span>

### <a name="op--bigendian--unit-ctl"></a><span data-ttu-id="7d8cf-107">op: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [egység](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="7d8cf-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="7d8cf-108">Az a művelet, amelynek a bemenetét vissza kell fordítani.</span><span class="sxs-lookup"><span data-stu-id="7d8cf-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit-ctl"></a><span data-ttu-id="7d8cf-109">Kimenet: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [egység](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="7d8cf-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="7d8cf-110">Új művelet, amely kis endian-regisztrációként fogadja el a bemenetét.</span><span class="sxs-lookup"><span data-stu-id="7d8cf-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="7d8cf-111">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="7d8cf-111">See Also</span></span>

- [<span data-ttu-id="7d8cf-112">Microsoft. Quantum. aritmetika. ApplyReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="7d8cf-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)
- [<span data-ttu-id="7d8cf-113">Microsoft. Quantum. aritmetika. ReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="7d8cf-113">Microsoft.Quantum.Arithmetic.ReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [<span data-ttu-id="7d8cf-114">Microsoft. Quantum. aritmetika. ReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="7d8cf-114">Microsoft.Quantum.Arithmetic.ReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [<span data-ttu-id="7d8cf-115">Microsoft. Quantum. aritmetika. ReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="7d8cf-115">Microsoft.Quantum.Arithmetic.ReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)