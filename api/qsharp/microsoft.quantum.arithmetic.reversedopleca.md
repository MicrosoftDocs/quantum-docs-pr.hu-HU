---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLECA
title: ReversedOpLECA függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLECA
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: b5413e43ad50ba7252705ef53b21e63650dbb2a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719620"
---
# <a name="reversedopleca-function"></a><span data-ttu-id="c62a7-102">ReversedOpLECA függvény</span><span class="sxs-lookup"><span data-stu-id="c62a7-102">ReversedOpLECA function</span></span>

<span data-ttu-id="c62a7-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c62a7-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c62a7-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c62a7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c62a7-105">Egy kis endian bemeneti művelet miatt egy új műveletet ad vissza, amely egy nagy endian-bemenetet vesz igénybe.</span><span class="sxs-lookup"><span data-stu-id="c62a7-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLECA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="c62a7-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c62a7-106">Input</span></span>

### <a name="op--littleendian--unit-adj--ctl"></a><span data-ttu-id="c62a7-107">op: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [egység](xref:microsoft.quantum.lang-ref.unit) – Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="c62a7-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="c62a7-108">Az a művelet, amelynek a bemenetét vissza kell fordítani.</span><span class="sxs-lookup"><span data-stu-id="c62a7-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit-adj--ctl"></a><span data-ttu-id="c62a7-109">Kimenet: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [egység](xref:microsoft.quantum.lang-ref.unit) , adj + CTL</span><span class="sxs-lookup"><span data-stu-id="c62a7-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="c62a7-110">Új művelet, amely nagy endian-regisztrációként fogadja el a bemenetét.</span><span class="sxs-lookup"><span data-stu-id="c62a7-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="c62a7-111">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="c62a7-111">See Also</span></span>

- [<span data-ttu-id="c62a7-112">Microsoft. Quantum. aritmetika. ApplyReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="c62a7-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)
- [<span data-ttu-id="c62a7-113">Microsoft. Quantum. aritmetika. ReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="c62a7-113">Microsoft.Quantum.Arithmetic.ReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [<span data-ttu-id="c62a7-114">Microsoft. Quantum. aritmetika. ReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="c62a7-114">Microsoft.Quantum.Arithmetic.ReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [<span data-ttu-id="c62a7-115">Microsoft. Quantum. aritmetika. ReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="c62a7-115">Microsoft.Quantum.Arithmetic.ReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)