---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCode
title: FiveQubitCode függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCode
qsharp.summary: Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 3b45af29897735905f7fe52340e2a8e425bd8cbe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200883"
---
# <a name="fivequbitcode-function"></a><span data-ttu-id="23876-102">FiveQubitCode függvény</span><span class="sxs-lookup"><span data-stu-id="23876-102">FiveQubitCode function</span></span>

<span data-ttu-id="23876-103">Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="23876-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="23876-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="23876-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="23876-105">Egy QECC értéket ad vissza, amely a ⟦ 5, 1, 3 ⟧ és a dekódert, valamint a helyi szindrómás mérését jelöli.</span><span class="sxs-lookup"><span data-stu-id="23876-105">Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function FiveQubitCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a><span data-ttu-id="23876-106">Kimenet: [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span><span class="sxs-lookup"><span data-stu-id="23876-106">Output : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span></span>

<span data-ttu-id="23876-107">Egy kvantum-hibajavítási kód végrehajtását adja vissza egy típus megadásával `QECC` .</span><span class="sxs-lookup"><span data-stu-id="23876-107">Returns an implementation of a quantum error correction code by specifying a `QECC` type.</span></span>

## <a name="remarks"></a><span data-ttu-id="23876-108">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="23876-108">Remarks</span></span>

<span data-ttu-id="23876-109">A kód a következő két dokumentumtól függetlenül található:</span><span class="sxs-lookup"><span data-stu-id="23876-109">This code was found independently in the following two papers:</span></span>

- <span data-ttu-id="23876-110">C.</span><span class="sxs-lookup"><span data-stu-id="23876-110">C.</span></span> <span data-ttu-id="23876-111">H.</span><span class="sxs-lookup"><span data-stu-id="23876-111">H.</span></span> <span data-ttu-id="23876-112">Bennett, D. alvincenzo, J. A.</span><span class="sxs-lookup"><span data-stu-id="23876-112">Bennett, D. DiVincenzo, J. A.</span></span> <span data-ttu-id="23876-113">Smolin és W. K.</span><span class="sxs-lookup"><span data-stu-id="23876-113">Smolin and W. K.</span></span> <span data-ttu-id="23876-114">Wootters, "vegyes állapotú felakadás és kvantum-hibajavítás," leltár. Rev. A, 54 (1996) PP. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 és</span><span class="sxs-lookup"><span data-stu-id="23876-114">Wootters, "Mixed state entanglement and quantum error correction," Phys. Rev. A, 54 (1996) pp. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 and</span></span>
- <span data-ttu-id="23876-115">R.</span><span class="sxs-lookup"><span data-stu-id="23876-115">R.</span></span> <span data-ttu-id="23876-116">Leva, C. Miquel, J. P.</span><span class="sxs-lookup"><span data-stu-id="23876-116">Laflamme, C. Miquel, J. P.</span></span> <span data-ttu-id="23876-117">Paz és W. H</span><span class="sxs-lookup"><span data-stu-id="23876-117">Paz and W. H.</span></span> <span data-ttu-id="23876-118">Zurek, "tökéletes kvantum-hibajavítási kód", "leltár. Rev. lett.</span><span class="sxs-lookup"><span data-stu-id="23876-118">Zurek, "Perfect quantum error correction code," Phys. Rev. Lett.</span></span> <span data-ttu-id="23876-119">77 (1996) PP. 198-201; https://arxiv.org/abs/quant-ph/9602019</span><span class="sxs-lookup"><span data-stu-id="23876-119">77 (1996) pp. 198-201; https://arxiv.org/abs/quant-ph/9602019</span></span>