---
uid: Microsoft.Quantum.Arithmetic.PhaseLittleEndian
title: PhaseLittleEndian-felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PhaseLittleEndian
qsharp.summary: >-
  Little-endian unsigned integers in QFT basis.

  For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.
ms.openlocfilehash: f1f792d62004a2765d4e63870f5a41a4377b0d34
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719729"
---
# <a name="phaselittleendian-user-defined-type"></a><span data-ttu-id="81d3b-102">PhaseLittleEndian-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="81d3b-102">PhaseLittleEndian user defined type</span></span>

<span data-ttu-id="81d3b-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="81d3b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="81d3b-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="81d3b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="81d3b-105">Kis endian előjel nélküli egész számok QFT alapján.</span><span class="sxs-lookup"><span data-stu-id="81d3b-105">Little-endian unsigned integers in QFT basis.</span></span>

<span data-ttu-id="81d3b-106">Ha például a $ \ket{x} $ a $x $ egész szám kis endian kódolása számítási alapon, akkor a $ \operatorname{QFTLE} \ket{x} $ a QFT-alapú $x $ kódolású.</span><span class="sxs-lookup"><span data-stu-id="81d3b-106">For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.</span></span>

```qsharp

newtype PhaseLittleEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="81d3b-107">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="81d3b-107">Remarks</span></span>

<span data-ttu-id="81d3b-108">`PhaseLittleEndian` `PhaseLE` A dokumentációnak megfelelően rövidítjük.</span><span class="sxs-lookup"><span data-stu-id="81d3b-108">We abbreviate `PhaseLittleEndian` as `PhaseLE` in the documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="81d3b-109">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="81d3b-109">See Also</span></span>

- [<span data-ttu-id="81d3b-110">Microsoft. Quantum. Canon. QFT</span><span class="sxs-lookup"><span data-stu-id="81d3b-110">Microsoft.Quantum.Canon.QFT</span></span>](xref:Microsoft.Quantum.Canon.QFT)
- [<span data-ttu-id="81d3b-111">Microsoft. Quantum. Canon. QFTLE</span><span class="sxs-lookup"><span data-stu-id="81d3b-111">Microsoft.Quantum.Canon.QFTLE</span></span>](xref:Microsoft.Quantum.Canon.QFTLE)