---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE
title: ApplyQuantumFourierTransformBE művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransformBE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: d15310298dc138bdffb612895bbf20ca1371db6f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717785"
---
# <a name="applyquantumfouriertransformbe-operation"></a><span data-ttu-id="76d53-102">ApplyQuantumFourierTransformBE művelet</span><span class="sxs-lookup"><span data-stu-id="76d53-102">ApplyQuantumFourierTransformBE operation</span></span>

<span data-ttu-id="76d53-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="76d53-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="76d53-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="76d53-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="76d53-105">Végrehajtja a Quantum Fourier-transzformációt egy olyan kvantum-regiszteren, amely egy egész számot tartalmaz a big-endian ábrázolásban.</span><span class="sxs-lookup"><span data-stu-id="76d53-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.</span></span>

```qsharp
operation ApplyQuantumFourierTransformBE (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="76d53-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="76d53-106">Input</span></span>

### <a name="qs--bigendian"></a><span data-ttu-id="76d53-107">QS: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="76d53-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="76d53-108">A kvantum-regiszter, amelyre a Quantum Fourier-transzformáció vonatkozik</span><span class="sxs-lookup"><span data-stu-id="76d53-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="76d53-109">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="76d53-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="76d53-110">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="76d53-110">Remarks</span></span>

<span data-ttu-id="76d53-111">A bemenet és a kimenet nagy endian-kódolásban van feltételezve.</span><span class="sxs-lookup"><span data-stu-id="76d53-111">The input and output are assumed to be in big endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="76d53-112">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="76d53-112">See Also</span></span>

- [<span data-ttu-id="76d53-113">Microsoft. Quantum. Canon. ApproximateQFT</span><span class="sxs-lookup"><span data-stu-id="76d53-113">Microsoft.Quantum.Canon.ApproximateQFT</span></span>](xref:Microsoft.Quantum.Canon.ApproximateQFT)
- [<span data-ttu-id="76d53-114">Microsoft. Quantum. Canon. QFTLE</span><span class="sxs-lookup"><span data-stu-id="76d53-114">Microsoft.Quantum.Canon.QFTLE</span></span>](xref:Microsoft.Quantum.Canon.QFTLE)