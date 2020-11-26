---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA
title: ApplyReversedOpBECA művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBECA
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: 5c761fb8e1042a25cd2e88f1b33e597c7d9287f9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202719"
---
# <a name="applyreversedopbeca-operation"></a><span data-ttu-id="52f78-102">ApplyReversedOpBECA művelet</span><span class="sxs-lookup"><span data-stu-id="52f78-102">ApplyReversedOpBECA operation</span></span>

<span data-ttu-id="52f78-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="52f78-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="52f78-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="52f78-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="52f78-105">Egy olyan műveletet alkalmaz, amely nagy endian adatbevitelt tesz lehetővé egy olyan, előjel nélküli egész számra, amely kis endian formátumot használ.</span><span class="sxs-lookup"><span data-stu-id="52f78-105">Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.</span></span>

```qsharp
operation ApplyReversedOpBECA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl + Adj), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="52f78-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="52f78-106">Input</span></span>

### <a name="op--bigendian--unit--is-adj--ctl"></a><span data-ttu-id="52f78-107">op: az [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="52f78-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="52f78-108">Nagy endian-regisztrációt használó művelet.</span><span class="sxs-lookup"><span data-stu-id="52f78-108">Operation that acts on a big-endian register.</span></span>


### <a name="register--littleendian"></a><span data-ttu-id="52f78-109">Regisztráció: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="52f78-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="52f78-110">Egy kis endian-regisztrációt kell átalakítani.</span><span class="sxs-lookup"><span data-stu-id="52f78-110">A little-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="52f78-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="52f78-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="52f78-112">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="52f78-112">See Also</span></span>

- [<span data-ttu-id="52f78-113">Microsoft. Quantum. aritmetika. ApplyReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="52f78-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="52f78-114">Microsoft. Quantum. aritmetika. ApplyReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="52f78-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [<span data-ttu-id="52f78-115">Microsoft. Quantum. aritmetika. ApplyReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="52f78-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)