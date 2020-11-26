---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: MeasureInteger művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: e3ff06e5cbb2ef8a63e4ad12308b382347c90fc3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222643"
---
# <a name="measureinteger-operation"></a><span data-ttu-id="90f08-102">MeasureInteger művelet</span><span class="sxs-lookup"><span data-stu-id="90f08-102">MeasureInteger operation</span></span>

<span data-ttu-id="90f08-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="90f08-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="90f08-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="90f08-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="90f08-105">A kvantum-regiszter tartalmát méri, és egy egész számra konvertálja.</span><span class="sxs-lookup"><span data-stu-id="90f08-105">Measures the content of a quantum register and converts it to an integer.</span></span> <span data-ttu-id="90f08-106">A mérés a standard számítási alapon történik, azaz a eigenbasis `PauliZ` .</span><span class="sxs-lookup"><span data-stu-id="90f08-106">The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.</span></span>

```qsharp
operation MeasureInteger (target : Microsoft.Quantum.Arithmetic.LittleEndian) : Int
```


## <a name="input"></a><span data-ttu-id="90f08-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="90f08-107">Input</span></span>

### <a name="target--littleendian"></a><span data-ttu-id="90f08-108">cél: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="90f08-108">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="90f08-109">A kis endian kódolású kvantum-regisztráció.</span><span class="sxs-lookup"><span data-stu-id="90f08-109">A quantum register in the little-endian encoding.</span></span>



## <a name="output--int"></a><span data-ttu-id="90f08-110">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="90f08-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="90f08-111">Előjel nélküli egész szám, amely a mért értéket tartalmazza `target` .</span><span class="sxs-lookup"><span data-stu-id="90f08-111">An unsigned integer that contains the measured value of `target`.</span></span>

## <a name="remarks"></a><span data-ttu-id="90f08-112">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="90f08-112">Remarks</span></span>

<span data-ttu-id="90f08-113">Ez a művelet visszaállítja a bemeneti regisztrációját a $ \ket{00\cdots 0} $ állapotra, amely alkalmas a célszámítógép visszaengedésére.</span><span class="sxs-lookup"><span data-stu-id="90f08-113">This operation resets its input register to the $\ket{00\cdots 0}$ state, suitable for releasing back to a target machine.</span></span>

## <a name="see-also"></a><span data-ttu-id="90f08-114">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="90f08-114">See Also</span></span>

- [<span data-ttu-id="90f08-115">Microsoft. Quantum. Canon. MeasureIntegerBE</span><span class="sxs-lookup"><span data-stu-id="90f08-115">Microsoft.Quantum.Canon.MeasureIntegerBE</span></span>](xref:Microsoft.Quantum.Canon.MeasureIntegerBE)