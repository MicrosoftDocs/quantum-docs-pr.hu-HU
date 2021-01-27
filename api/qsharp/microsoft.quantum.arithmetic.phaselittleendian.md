---
uid: Microsoft.Quantum.Arithmetic.PhaseLittleEndian
title: PhaseLittleEndian-felhasználó által definiált típus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PhaseLittleEndian
qsharp.summary: >-
  Little-endian unsigned integers in QFT basis.

  For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.
ms.openlocfilehash: 59df1db31090f875ccd261fe6cc43995ba57b963
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843003"
---
# <a name="phaselittleendian-user-defined-type"></a><span data-ttu-id="6afc4-102">PhaseLittleEndian-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="6afc4-102">PhaseLittleEndian user defined type</span></span>

<span data-ttu-id="6afc4-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="6afc4-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="6afc4-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6afc4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6afc4-105">Kis endian előjel nélküli egész számok QFT alapján.</span><span class="sxs-lookup"><span data-stu-id="6afc4-105">Little-endian unsigned integers in QFT basis.</span></span>

<span data-ttu-id="6afc4-106">Ha például a $ \ket{x} $ a $x $ egész szám kis endian kódolása számítási alapon, akkor a $ \operatorname{QFTLE} \ket{x} $ a QFT-alapú $x $ kódolású.</span><span class="sxs-lookup"><span data-stu-id="6afc4-106">For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.</span></span>

```qsharp

newtype PhaseLittleEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="6afc4-107">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="6afc4-107">Remarks</span></span>

<span data-ttu-id="6afc4-108">`PhaseLittleEndian` `PhaseLE` A dokumentációnak megfelelően rövidítjük.</span><span class="sxs-lookup"><span data-stu-id="6afc4-108">We abbreviate `PhaseLittleEndian` as `PhaseLE` in the documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="6afc4-109">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="6afc4-109">See Also</span></span>

- [<span data-ttu-id="6afc4-110">Microsoft. Quantum. Canon. QFT</span><span class="sxs-lookup"><span data-stu-id="6afc4-110">Microsoft.Quantum.Canon.QFT</span></span>](xref:Microsoft.Quantum.Canon.QFT)
- [<span data-ttu-id="6afc4-111">Microsoft. Quantum. Canon. QFTLE</span><span class="sxs-lookup"><span data-stu-id="6afc4-111">Microsoft.Quantum.Canon.QFTLE</span></span>](xref:Microsoft.Quantum.Canon.QFTLE)