---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA
title: ApplyReversedOpLECA művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpLECA
qsharp.summary: Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.
ms.openlocfilehash: c0bc04efe55792f5e177266c27552fb0546707e0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202583"
---
# <a name="applyreversedopleca-operation"></a><span data-ttu-id="bafeb-102">ApplyReversedOpLECA művelet</span><span class="sxs-lookup"><span data-stu-id="bafeb-102">ApplyReversedOpLECA operation</span></span>

<span data-ttu-id="bafeb-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="bafeb-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="bafeb-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bafeb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bafeb-105">Egy olyan műveletet alkalmaz, amely kis endian-bevitelt tesz lehetővé egy előjel nélküli egész számra a big-endian formátum használatával.</span><span class="sxs-lookup"><span data-stu-id="bafeb-105">Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.</span></span>

```qsharp
operation ApplyReversedOpLECA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl + Adj), register : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="bafeb-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="bafeb-106">Input</span></span>

### <a name="op--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="bafeb-107">op: az [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="bafeb-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="bafeb-108">Egy kis endian-regisztrációt használó művelet.</span><span class="sxs-lookup"><span data-stu-id="bafeb-108">Operation that acts on a little-endian register.</span></span>


### <a name="register--bigendian"></a><span data-ttu-id="bafeb-109">Regisztráció: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="bafeb-109">register : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="bafeb-110">Egy nagy endian-regisztráció átalakítására.</span><span class="sxs-lookup"><span data-stu-id="bafeb-110">A big-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bafeb-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bafeb-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="bafeb-112">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="bafeb-112">See Also</span></span>

- [<span data-ttu-id="bafeb-113">Microsoft. Quantum. aritmetika. ApplyReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="bafeb-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [<span data-ttu-id="bafeb-114">Microsoft. Quantum. aritmetika. ApplyReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="bafeb-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [<span data-ttu-id="bafeb-115">Microsoft. Quantum. aritmetika. ApplyReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="bafeb-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC)