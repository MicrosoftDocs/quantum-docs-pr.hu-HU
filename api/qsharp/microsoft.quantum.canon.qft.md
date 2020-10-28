---
uid: Microsoft.Quantum.Canon.QFT
title: QFT művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFT
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: e5b40be6c86647205fe1c764b6b043272296a354
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715656"
---
# <a name="qft-operation"></a><span data-ttu-id="69cd6-102">QFT művelet</span><span class="sxs-lookup"><span data-stu-id="69cd6-102">QFT operation</span></span>

<span data-ttu-id="69cd6-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="69cd6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="69cd6-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="69cd6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="69cd6-105">Végrehajtja a Quantum Fourier-transzformációt egy olyan kvantum-regiszteren, amely egy egész számot tartalmaz a big-endian ábrázolásban.</span><span class="sxs-lookup"><span data-stu-id="69cd6-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.</span></span>

```qsharp
operation QFT (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="69cd6-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="69cd6-106">Input</span></span>

### <a name="qs--bigendian"></a><span data-ttu-id="69cd6-107">QS: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="69cd6-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="69cd6-108">A kvantum-regiszter, amelyre a Quantum Fourier-transzformáció vonatkozik</span><span class="sxs-lookup"><span data-stu-id="69cd6-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="69cd6-109">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="69cd6-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="69cd6-110">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="69cd6-110">Remarks</span></span>

<span data-ttu-id="69cd6-111">A bemenet és a kimenet nagy endian-kódolásban van feltételezve.</span><span class="sxs-lookup"><span data-stu-id="69cd6-111">The input and output are assumed to be in big endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="69cd6-112">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="69cd6-112">See Also</span></span>

- [<span data-ttu-id="69cd6-113">Microsoft. Quantum. Canon. ApplyQuantumFourierTransformBE</span><span class="sxs-lookup"><span data-stu-id="69cd6-113">Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE</span></span>](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)