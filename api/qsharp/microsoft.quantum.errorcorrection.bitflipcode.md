---
uid: Microsoft.Quantum.ErrorCorrection.BitFlipCode
title: BitFlipCode függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: BitFlipCode
qsharp.summary: Returns a QECC value representing the ⟦3, 1, 1⟧ bit flip code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 2d0b50bd2467fc01caacbbcb22f98c59a2d13922
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201223"
---
# <a name="bitflipcode-function"></a><span data-ttu-id="ec892-102">BitFlipCode függvény</span><span class="sxs-lookup"><span data-stu-id="ec892-102">BitFlipCode function</span></span>

<span data-ttu-id="ec892-103">Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="ec892-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="ec892-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ec892-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ec892-105">Egy QECC értéket ad vissza, amely a ⟦ 3, 1, 1 ⟧ bit flip Code kódolót és dekódert jelöli a helyi szindrómás mérésével.</span><span class="sxs-lookup"><span data-stu-id="ec892-105">Returns a QECC value representing the ⟦3, 1, 1⟧ bit flip code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function BitFlipCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a><span data-ttu-id="ec892-106">Kimenet: [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span><span class="sxs-lookup"><span data-stu-id="ec892-106">Output : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span></span>

<span data-ttu-id="ec892-107">Egy kvantum-hibajavítási kód végrehajtását adja vissza egy típus megadásával `QECC` .</span><span class="sxs-lookup"><span data-stu-id="ec892-107">Returns an implementation of a quantum error correction code by specifying a `QECC` type.</span></span>