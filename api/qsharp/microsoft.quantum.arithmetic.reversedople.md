---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLE
title: ReversedOpLE függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLE
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: 6ebc4e97cb6d515e99e85922d03ca246b56084ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719645"
---
# <a name="reversedople-function"></a><span data-ttu-id="0d686-102">ReversedOpLE függvény</span><span class="sxs-lookup"><span data-stu-id="0d686-102">ReversedOpLE function</span></span>

<span data-ttu-id="0d686-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="0d686-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="0d686-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0d686-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0d686-105">Egy kis endian bemeneti művelet miatt egy új műveletet ad vissza, amely egy nagy endian-bemenetet vesz igénybe.</span><span class="sxs-lookup"><span data-stu-id="0d686-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLE (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit)
```


## <a name="input"></a><span data-ttu-id="0d686-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="0d686-106">Input</span></span>

### <a name="op--littleendian--unit"></a><span data-ttu-id="0d686-107">op: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0d686-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="0d686-108">Az a művelet, amelynek a bemenetét vissza kell fordítani.</span><span class="sxs-lookup"><span data-stu-id="0d686-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit"></a><span data-ttu-id="0d686-109">Kimenet: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0d686-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="0d686-110">Új művelet, amely nagy endian-regisztrációként fogadja el a bemenetét.</span><span class="sxs-lookup"><span data-stu-id="0d686-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="0d686-111">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="0d686-111">See Also</span></span>

- [<span data-ttu-id="0d686-112">Microsoft. Quantum. aritmetika. ApplyReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="0d686-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [<span data-ttu-id="0d686-113">Microsoft. Quantum. aritmetika. ReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="0d686-113">Microsoft.Quantum.Arithmetic.ReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [<span data-ttu-id="0d686-114">Microsoft. Quantum. aritmetika. ReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="0d686-114">Microsoft.Quantum.Arithmetic.ReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)
- [<span data-ttu-id="0d686-115">Microsoft. Quantum. aritmetika. ReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="0d686-115">Microsoft.Quantum.Arithmetic.ReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)