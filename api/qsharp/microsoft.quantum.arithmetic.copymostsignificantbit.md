---
uid: Microsoft.Quantum.Arithmetic.CopyMostSignificantBit
title: CopyMostSignificantBit művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CopyMostSignificantBit
qsharp.summary: Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.
ms.openlocfilehash: 02119103fa7b5776f0e1681535115e0773a34c4c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721216"
---
# <a name="copymostsignificantbit-operation"></a><span data-ttu-id="19fa2-102">CopyMostSignificantBit művelet</span><span class="sxs-lookup"><span data-stu-id="19fa2-102">CopyMostSignificantBit operation</span></span>

<span data-ttu-id="19fa2-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="19fa2-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="19fa2-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="19fa2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="19fa2-105">Egy olyan qubit-regiszter legjelentősebb részét másolja, amely `from` előjel nélküli egész számot jelképez a qubit `target` .</span><span class="sxs-lookup"><span data-stu-id="19fa2-105">Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.</span></span>

```qsharp
operation CopyMostSignificantBit (from : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="19fa2-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="19fa2-106">Input</span></span>

### <a name="from--littleendian"></a><span data-ttu-id="19fa2-107">Forrás: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="19fa2-107">from : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="19fa2-108">Az előjel nélküli egész szám, amelyből a legmagasabb bit át lett másolva.</span><span class="sxs-lookup"><span data-stu-id="19fa2-108">The unsigned integer from which the highest bit is copied from.</span></span>
<span data-ttu-id="19fa2-109">az egész szám kódolása kis endian formátumban történik.</span><span class="sxs-lookup"><span data-stu-id="19fa2-109">the integer is encoded in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="19fa2-110">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="19fa2-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="19fa2-111">Az a qubit, amelyben a legmagasabb bit másolása zajlik.</span><span class="sxs-lookup"><span data-stu-id="19fa2-111">The qubit in which the highest bit is being copied.</span></span> <span data-ttu-id="19fa2-112">A bit kódolás számítási alapon történik.</span><span class="sxs-lookup"><span data-stu-id="19fa2-112">The bit encoding is in computational basis.</span></span>



## <a name="output--unit"></a><span data-ttu-id="19fa2-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="19fa2-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="19fa2-114">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="19fa2-114">See Also</span></span>

- [<span data-ttu-id="19fa2-115">Microsoft. Quantum. aritmetika. LittleEndian</span><span class="sxs-lookup"><span data-stu-id="19fa2-115">Microsoft.Quantum.Arithmetic.LittleEndian</span></span>](xref:Microsoft.Quantum.Arithmetic.LittleEndian)