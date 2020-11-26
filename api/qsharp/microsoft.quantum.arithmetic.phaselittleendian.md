---
uid: Microsoft.Quantum.Arithmetic.PhaseLittleEndian
title: PhaseLittleEndian-felhasználó által definiált típus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PhaseLittleEndian
qsharp.summary: >-
  Little-endian unsigned integers in QFT basis.

  For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.
ms.openlocfilehash: 45b824a74d664df0d5707264a3c616fb27c477b3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222422"
---
# <a name="phaselittleendian-user-defined-type"></a><span data-ttu-id="6de95-102">PhaseLittleEndian-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="6de95-102">PhaseLittleEndian user defined type</span></span>

<span data-ttu-id="6de95-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="6de95-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="6de95-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6de95-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6de95-105">Kis endian előjel nélküli egész számok QFT alapján.</span><span class="sxs-lookup"><span data-stu-id="6de95-105">Little-endian unsigned integers in QFT basis.</span></span>

<span data-ttu-id="6de95-106">Ha például a $ \ket{x} $ a $x $ egész szám kis endian kódolása számítási alapon, akkor a $ \operatorname{QFTLE} \ket{x} $ a QFT-alapú $x $ kódolású.</span><span class="sxs-lookup"><span data-stu-id="6de95-106">For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.</span></span>

```qsharp

newtype PhaseLittleEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="6de95-107">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="6de95-107">Remarks</span></span>

<span data-ttu-id="6de95-108">`PhaseLittleEndian` `PhaseLE` A dokumentációnak megfelelően rövidítjük.</span><span class="sxs-lookup"><span data-stu-id="6de95-108">We abbreviate `PhaseLittleEndian` as `PhaseLE` in the documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="6de95-109">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="6de95-109">See Also</span></span>

- [<span data-ttu-id="6de95-110">Microsoft. Quantum. Canon. QFT</span><span class="sxs-lookup"><span data-stu-id="6de95-110">Microsoft.Quantum.Canon.QFT</span></span>](xref:Microsoft.Quantum.Canon.QFT)
- [<span data-ttu-id="6de95-111">Microsoft. Quantum. Canon. QFTLE</span><span class="sxs-lookup"><span data-stu-id="6de95-111">Microsoft.Quantum.Canon.QFTLE</span></span>](xref:Microsoft.Quantum.Canon.QFTLE)