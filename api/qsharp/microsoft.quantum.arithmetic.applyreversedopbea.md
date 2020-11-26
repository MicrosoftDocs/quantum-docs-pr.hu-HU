---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA
title: ApplyReversedOpBEA művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBEA
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: 17d05e0914eead28ff0e04b858b003659d37ab7f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202821"
---
# <a name="applyreversedopbea-operation"></a><span data-ttu-id="3c056-102">ApplyReversedOpBEA művelet</span><span class="sxs-lookup"><span data-stu-id="3c056-102">ApplyReversedOpBEA operation</span></span>

<span data-ttu-id="3c056-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="3c056-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="3c056-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3c056-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3c056-105">Egy olyan műveletet alkalmaz, amely nagy endian adatbevitelt tesz lehetővé egy olyan, előjel nélküli egész számra, amely kis endian formátumot használ.</span><span class="sxs-lookup"><span data-stu-id="3c056-105">Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.</span></span>

```qsharp
operation ApplyReversedOpBEA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="3c056-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="3c056-106">Input</span></span>

### <a name="op--bigendian--unit--is-adj"></a><span data-ttu-id="3c056-107">op: az [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3c056-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="3c056-108">Nagy endian-regisztrációt használó művelet.</span><span class="sxs-lookup"><span data-stu-id="3c056-108">Operation that acts on a big-endian register.</span></span>


### <a name="register--littleendian"></a><span data-ttu-id="3c056-109">Regisztráció: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3c056-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="3c056-110">Egy kis endian-regisztrációt kell átalakítani.</span><span class="sxs-lookup"><span data-stu-id="3c056-110">A little-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3c056-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3c056-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="3c056-112">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="3c056-112">See Also</span></span>

- [<span data-ttu-id="3c056-113">Microsoft. Quantum. aritmetika. ApplyReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="3c056-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="3c056-114">Microsoft. Quantum. aritmetika. ApplyReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="3c056-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)
- [<span data-ttu-id="3c056-115">Microsoft. Quantum. aritmetika. ApplyReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="3c056-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)