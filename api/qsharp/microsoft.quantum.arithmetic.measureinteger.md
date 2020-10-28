---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: MeasureInteger művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: 7cd2d93332eb168c7c2be92a3b910033ca8c10ae
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720965"
---
# <a name="measureinteger-operation"></a><span data-ttu-id="abd6a-102">MeasureInteger művelet</span><span class="sxs-lookup"><span data-stu-id="abd6a-102">MeasureInteger operation</span></span>

<span data-ttu-id="abd6a-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="abd6a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="abd6a-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="abd6a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="abd6a-105">A kvantum-regiszter tartalmát méri, és egy egész számra konvertálja.</span><span class="sxs-lookup"><span data-stu-id="abd6a-105">Measures the content of a quantum register and converts it to an integer.</span></span> <span data-ttu-id="abd6a-106">A mérés a standard számítási alapon történik, azaz a eigenbasis `PauliZ` .</span><span class="sxs-lookup"><span data-stu-id="abd6a-106">The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.</span></span>

```qsharp
operation MeasureInteger (target : Microsoft.Quantum.Arithmetic.LittleEndian) : Int
```


## <a name="input"></a><span data-ttu-id="abd6a-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="abd6a-107">Input</span></span>

### <a name="target--littleendian"></a><span data-ttu-id="abd6a-108">cél: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="abd6a-108">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="abd6a-109">A kis endian kódolású kvantum-regisztráció.</span><span class="sxs-lookup"><span data-stu-id="abd6a-109">A quantum register in the little-endian encoding.</span></span>



## <a name="output--int"></a><span data-ttu-id="abd6a-110">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="abd6a-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="abd6a-111">Előjel nélküli egész szám, amely a mért értéket tartalmazza `target` .</span><span class="sxs-lookup"><span data-stu-id="abd6a-111">An unsigned integer that contains the measured value of `target`.</span></span>

## <a name="remarks"></a><span data-ttu-id="abd6a-112">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="abd6a-112">Remarks</span></span>

<span data-ttu-id="abd6a-113">Ez a művelet visszaállítja a bemeneti regisztrációját a $ \ket{00\cdots 0} $ állapotra, amely alkalmas a célszámítógép visszaengedésére.</span><span class="sxs-lookup"><span data-stu-id="abd6a-113">This operation resets its input register to the $\ket{00\cdots 0}$ state, suitable for releasing back to a target machine.</span></span>

## <a name="see-also"></a><span data-ttu-id="abd6a-114">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="abd6a-114">See Also</span></span>

- [<span data-ttu-id="abd6a-115">Microsoft. Quantum. Canon. MeasureIntegerBE</span><span class="sxs-lookup"><span data-stu-id="abd6a-115">Microsoft.Quantum.Canon.MeasureIntegerBE</span></span>](xref:Microsoft.Quantum.Canon.MeasureIntegerBE)