---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLEC
title: ReversedOpLEC függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLEC
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: 3a4872be6b81498c26ab9a14134940c5ef8628b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719633"
---
# <a name="reversedoplec-function"></a><span data-ttu-id="ea1cf-102">ReversedOpLEC függvény</span><span class="sxs-lookup"><span data-stu-id="ea1cf-102">ReversedOpLEC function</span></span>

<span data-ttu-id="ea1cf-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ea1cf-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ea1cf-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ea1cf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ea1cf-105">Egy kis endian bemeneti művelet miatt egy új műveletet ad vissza, amely egy nagy endian-bemenetet vesz igénybe.</span><span class="sxs-lookup"><span data-stu-id="ea1cf-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLEC (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="ea1cf-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="ea1cf-106">Input</span></span>

### <a name="op--littleendian--unit-ctl"></a><span data-ttu-id="ea1cf-107">op: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [egység](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="ea1cf-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="ea1cf-108">Az a művelet, amelynek a bemenetét vissza kell fordítani.</span><span class="sxs-lookup"><span data-stu-id="ea1cf-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit-ctl"></a><span data-ttu-id="ea1cf-109">Kimenet: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [egység](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="ea1cf-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="ea1cf-110">Új művelet, amely nagy endian-regisztrációként fogadja el a bemenetét.</span><span class="sxs-lookup"><span data-stu-id="ea1cf-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="ea1cf-111">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="ea1cf-111">See Also</span></span>

- [<span data-ttu-id="ea1cf-112">Microsoft. Quantum. aritmetika. ApplyReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="ea1cf-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC)
- [<span data-ttu-id="ea1cf-113">Microsoft. Quantum. aritmetika. ReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="ea1cf-113">Microsoft.Quantum.Arithmetic.ReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [<span data-ttu-id="ea1cf-114">Microsoft. Quantum. aritmetika. ReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="ea1cf-114">Microsoft.Quantum.Arithmetic.ReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [<span data-ttu-id="ea1cf-115">Microsoft. Quantum. aritmetika. ReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="ea1cf-115">Microsoft.Quantum.Arithmetic.ReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)