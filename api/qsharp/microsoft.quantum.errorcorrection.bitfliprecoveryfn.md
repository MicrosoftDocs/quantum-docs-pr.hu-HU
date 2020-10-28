---
uid: Microsoft.Quantum.ErrorCorrection.BitFlipRecoveryFn
title: BitFlipRecoveryFn függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: BitFlipRecoveryFn
qsharp.summary: Function for recovery Pauli operations for given syndrome measurement by table lookup for the ⟦3, 1, 1⟧ bit flip code.
ms.openlocfilehash: dad90475b2506187282825e143b11adc5120f453
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712493"
---
# <a name="bitfliprecoveryfn-function"></a><span data-ttu-id="18d97-102">BitFlipRecoveryFn függvény</span><span class="sxs-lookup"><span data-stu-id="18d97-102">BitFlipRecoveryFn function</span></span>

<span data-ttu-id="18d97-103">Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="18d97-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="18d97-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="18d97-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="18d97-105">Függvény helyreállítási Pauli-műveletekhez az adott szindrómára vonatkozóan a ⟦ 3, 1, 1 ⟧ bit flip Code értékre való táblázatos kereséssel.</span><span class="sxs-lookup"><span data-stu-id="18d97-105">Function for recovery Pauli operations for given syndrome measurement by table lookup for the ⟦3, 1, 1⟧ bit flip code.</span></span>

```qsharp
function BitFlipRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a><span data-ttu-id="18d97-106">Kimenet: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="18d97-106">Output : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="18d97-107">Olyan típusú függvény, `RecoveryFn` amely egy tünetegyüttes-mérést végez, `Result[]` és az `Pauli[]` észlelt hibát javító műveleteket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="18d97-107">Function of type `RecoveryFn` that takes a syndrome measurement `Result[]` and returns the `Pauli[]` operations that corrects the detected error.</span></span>

## <a name="see-also"></a><span data-ttu-id="18d97-108">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="18d97-108">See Also</span></span>

- [<span data-ttu-id="18d97-109">Microsoft. Quantum. ErrorCorrection. RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="18d97-109">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)