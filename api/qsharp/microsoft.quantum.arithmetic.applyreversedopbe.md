---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBE
title: ApplyReversedOpBE művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBE
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: 6db1fcb7437d97b1e56c64165d1be523ed2df07a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202855"
---
# <a name="applyreversedopbe-operation"></a><span data-ttu-id="6ba23-102">ApplyReversedOpBE művelet</span><span class="sxs-lookup"><span data-stu-id="6ba23-102">ApplyReversedOpBE operation</span></span>

<span data-ttu-id="6ba23-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="6ba23-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="6ba23-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6ba23-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6ba23-105">Egy olyan műveletet alkalmaz, amely nagy endian adatbevitelt tesz lehetővé egy olyan, előjel nélküli egész számra, amely kis endian formátumot használ.</span><span class="sxs-lookup"><span data-stu-id="6ba23-105">Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.</span></span>

```qsharp
operation ApplyReversedOpBE (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="6ba23-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="6ba23-106">Input</span></span>

### <a name="op--bigendian--unit"></a><span data-ttu-id="6ba23-107">op: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6ba23-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="6ba23-108">Nagy endian-regisztrációt használó művelet.</span><span class="sxs-lookup"><span data-stu-id="6ba23-108">Operation that acts on a big-endian register.</span></span>


### <a name="register--littleendian"></a><span data-ttu-id="6ba23-109">Regisztráció: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="6ba23-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="6ba23-110">Egy kis endian-regisztrációt kell átalakítani.</span><span class="sxs-lookup"><span data-stu-id="6ba23-110">A little-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6ba23-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6ba23-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="6ba23-112">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="6ba23-112">See Also</span></span>

- [<span data-ttu-id="6ba23-113">Microsoft. Quantum. aritmetika. ApplyReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="6ba23-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [<span data-ttu-id="6ba23-114">Microsoft. Quantum. aritmetika. ApplyReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="6ba23-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)
- [<span data-ttu-id="6ba23-115">Microsoft. Quantum. aritmetika. ApplyReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="6ba23-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)