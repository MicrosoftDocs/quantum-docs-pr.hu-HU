---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA
title: ApplyReversedOpLEA művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpLEA
qsharp.summary: Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.
ms.openlocfilehash: d5bc1b38500c449b58f8dafd640627b8e933e902
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202736"
---
# <a name="applyreversedoplea-operation"></a><span data-ttu-id="8a8ee-102">ApplyReversedOpLEA művelet</span><span class="sxs-lookup"><span data-stu-id="8a8ee-102">ApplyReversedOpLEA operation</span></span>

<span data-ttu-id="8a8ee-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="8a8ee-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="8a8ee-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8a8ee-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8a8ee-105">Egy olyan műveletet alkalmaz, amely kis endian-bevitelt tesz lehetővé egy előjel nélküli egész számra a big-endian formátum használatával.</span><span class="sxs-lookup"><span data-stu-id="8a8ee-105">Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.</span></span>

```qsharp
operation ApplyReversedOpLEA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj), register : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="8a8ee-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="8a8ee-106">Input</span></span>

### <a name="op--littleendian--unit--is-adj"></a><span data-ttu-id="8a8ee-107">op: az [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8a8ee-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="8a8ee-108">Egy kis endian-regisztrációt használó művelet.</span><span class="sxs-lookup"><span data-stu-id="8a8ee-108">Operation that acts on a little-endian register.</span></span>


### <a name="register--bigendian"></a><span data-ttu-id="8a8ee-109">Regisztráció: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="8a8ee-109">register : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="8a8ee-110">Egy nagy endian-regisztráció átalakítására.</span><span class="sxs-lookup"><span data-stu-id="8a8ee-110">A big-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8a8ee-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8a8ee-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="8a8ee-112">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="8a8ee-112">See Also</span></span>

- [<span data-ttu-id="8a8ee-113">Microsoft. Quantum. aritmetika. ApplyReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="8a8ee-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [<span data-ttu-id="8a8ee-114">Microsoft. Quantum. aritmetika. ApplyReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="8a8ee-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC)
- [<span data-ttu-id="8a8ee-115">Microsoft. Quantum. aritmetika. ApplyReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="8a8ee-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)