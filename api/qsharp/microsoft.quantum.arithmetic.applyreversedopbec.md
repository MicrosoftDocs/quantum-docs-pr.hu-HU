---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC
title: ApplyReversedOpBEC művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBEC
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: 3a5fef3bb4549433540b2a7b5e94d3cd2d527639
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202770"
---
# <a name="applyreversedopbec-operation"></a><span data-ttu-id="504dd-102">ApplyReversedOpBEC művelet</span><span class="sxs-lookup"><span data-stu-id="504dd-102">ApplyReversedOpBEC operation</span></span>

<span data-ttu-id="504dd-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="504dd-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="504dd-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="504dd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="504dd-105">Egy olyan műveletet alkalmaz, amely nagy endian adatbevitelt tesz lehetővé egy olyan, előjel nélküli egész számra, amely kis endian formátumot használ.</span><span class="sxs-lookup"><span data-stu-id="504dd-105">Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.</span></span>

```qsharp
operation ApplyReversedOpBEC (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="504dd-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="504dd-106">Input</span></span>

### <a name="op--bigendian--unit--is-ctl"></a><span data-ttu-id="504dd-107">op: a [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="504dd-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="504dd-108">Nagy endian-regisztrációt használó művelet.</span><span class="sxs-lookup"><span data-stu-id="504dd-108">Operation that acts on a big-endian register.</span></span>


### <a name="register--littleendian"></a><span data-ttu-id="504dd-109">Regisztráció: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="504dd-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="504dd-110">Egy kis endian-regisztrációt kell átalakítani.</span><span class="sxs-lookup"><span data-stu-id="504dd-110">A little-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="504dd-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="504dd-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="504dd-112">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="504dd-112">See Also</span></span>

- [<span data-ttu-id="504dd-113">Microsoft. Quantum. aritmetika. ApplyReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="504dd-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="504dd-114">Microsoft. Quantum. aritmetika. ApplyReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="504dd-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [<span data-ttu-id="504dd-115">Microsoft. Quantum. aritmetika. ApplyReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="504dd-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)