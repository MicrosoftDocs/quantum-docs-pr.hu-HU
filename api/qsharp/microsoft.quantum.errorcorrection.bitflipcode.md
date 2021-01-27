---
uid: Microsoft.Quantum.ErrorCorrection.BitFlipCode
title: BitFlipCode függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: BitFlipCode
qsharp.summary: Returns a QECC value representing the ⟦3, 1, 1⟧ bit flip code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 0a5a028f85b80575b754b93a797a1460d21bb552
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853195"
---
# <a name="bitflipcode-function"></a><span data-ttu-id="01ca5-102">BitFlipCode függvény</span><span class="sxs-lookup"><span data-stu-id="01ca5-102">BitFlipCode function</span></span>

<span data-ttu-id="01ca5-103">Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="01ca5-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="01ca5-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="01ca5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="01ca5-105">Egy QECC értéket ad vissza, amely a ⟦ 3, 1, 1 ⟧ bit flip Code kódolót és dekódert jelöli a helyi szindrómás mérésével.</span><span class="sxs-lookup"><span data-stu-id="01ca5-105">Returns a QECC value representing the ⟦3, 1, 1⟧ bit flip code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function BitFlipCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a><span data-ttu-id="01ca5-106">Kimenet: [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span><span class="sxs-lookup"><span data-stu-id="01ca5-106">Output : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span></span>

<span data-ttu-id="01ca5-107">Egy kvantum-hibajavítási kód végrehajtását adja vissza egy típus megadásával `QECC` .</span><span class="sxs-lookup"><span data-stu-id="01ca5-107">Returns an implementation of a quantum error correction code by specifying a `QECC` type.</span></span>