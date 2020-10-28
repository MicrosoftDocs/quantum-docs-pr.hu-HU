---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBE
title: ReversedOpBE függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBE
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 170f63e60e6c26dbdd33af02c6a3387a1b3dbc44
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719704"
---
# <a name="reversedopbe-function"></a><span data-ttu-id="a6f20-102">ReversedOpBE függvény</span><span class="sxs-lookup"><span data-stu-id="a6f20-102">ReversedOpBE function</span></span>

<span data-ttu-id="a6f20-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a6f20-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a6f20-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a6f20-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a6f20-105">Olyan művelet miatt, amely nagy endian adatbevitelt igényel, egy új műveletet ad vissza, amely egy kis endian-bemenetet vesz igénybe.</span><span class="sxs-lookup"><span data-stu-id="a6f20-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBE (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit)
```


## <a name="input"></a><span data-ttu-id="a6f20-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="a6f20-106">Input</span></span>

### <a name="op--bigendian--unit"></a><span data-ttu-id="a6f20-107">op: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a6f20-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="a6f20-108">Az a művelet, amelynek a bemenetét vissza kell fordítani.</span><span class="sxs-lookup"><span data-stu-id="a6f20-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit"></a><span data-ttu-id="a6f20-109">Kimenet: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a6f20-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="a6f20-110">Új művelet, amely kis endian-regisztrációként fogadja el a bemenetét.</span><span class="sxs-lookup"><span data-stu-id="a6f20-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="a6f20-111">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="a6f20-111">See Also</span></span>

- [<span data-ttu-id="a6f20-112">Microsoft. Quantum. aritmetika. ApplyReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="a6f20-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="a6f20-113">Microsoft. Quantum. aritmetika. ReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="a6f20-113">Microsoft.Quantum.Arithmetic.ReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [<span data-ttu-id="a6f20-114">Microsoft. Quantum. aritmetika. ReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="a6f20-114">Microsoft.Quantum.Arithmetic.ReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)
- [<span data-ttu-id="a6f20-115">Microsoft. Quantum. aritmetika. ReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="a6f20-115">Microsoft.Quantum.Arithmetic.ReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)