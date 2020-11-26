---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC
title: ApplyReversedOpLEC művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpLEC
qsharp.summary: Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.
ms.openlocfilehash: 75b6c0f09c0699b50d9ac1b0274e8074520fc241
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202651"
---
# <a name="applyreversedoplec-operation"></a><span data-ttu-id="fbcbc-102">ApplyReversedOpLEC művelet</span><span class="sxs-lookup"><span data-stu-id="fbcbc-102">ApplyReversedOpLEC operation</span></span>

<span data-ttu-id="fbcbc-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="fbcbc-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="fbcbc-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fbcbc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fbcbc-105">Egy olyan műveletet alkalmaz, amely kis endian-bevitelt tesz lehetővé egy előjel nélküli egész számra a big-endian formátum használatával.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-105">Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.</span></span>

```qsharp
operation ApplyReversedOpLEC (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl), register : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="fbcbc-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="fbcbc-106">Input</span></span>

### <a name="op--littleendian--unit--is-ctl"></a><span data-ttu-id="fbcbc-107">op: a [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="fbcbc-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="fbcbc-108">Egy kis endian-regisztrációt használó művelet.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-108">Operation that acts on a little-endian register.</span></span>


### <a name="register--bigendian"></a><span data-ttu-id="fbcbc-109">Regisztráció: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="fbcbc-109">register : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="fbcbc-110">Egy nagy endian-regisztráció átalakítására.</span><span class="sxs-lookup"><span data-stu-id="fbcbc-110">A big-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fbcbc-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fbcbc-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="fbcbc-112">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="fbcbc-112">See Also</span></span>

- [<span data-ttu-id="fbcbc-113">Microsoft. Quantum. aritmetika. ApplyReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="fbcbc-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [<span data-ttu-id="fbcbc-114">Microsoft. Quantum. aritmetika. ApplyReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="fbcbc-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [<span data-ttu-id="fbcbc-115">Microsoft. Quantum. aritmetika. ApplyReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="fbcbc-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)