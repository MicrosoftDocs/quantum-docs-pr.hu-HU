---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCode
title: FiveQubitCode függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCode
qsharp.summary: Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 7509de880b1e3ea8964b61e4b3f034ce20b2f202
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712339"
---
# <a name="fivequbitcode-function"></a><span data-ttu-id="da3fc-102">FiveQubitCode függvény</span><span class="sxs-lookup"><span data-stu-id="da3fc-102">FiveQubitCode function</span></span>

<span data-ttu-id="da3fc-103">Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="da3fc-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="da3fc-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="da3fc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="da3fc-105">Egy QECC értéket ad vissza, amely a ⟦ 5, 1, 3 ⟧ és a dekódert, valamint a helyi szindrómás mérését jelöli.</span><span class="sxs-lookup"><span data-stu-id="da3fc-105">Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function FiveQubitCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a><span data-ttu-id="da3fc-106">Kimenet: [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span><span class="sxs-lookup"><span data-stu-id="da3fc-106">Output : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span></span>

<span data-ttu-id="da3fc-107">Egy kvantum-hibajavítási kód végrehajtását adja vissza egy típus megadásával `QECC` .</span><span class="sxs-lookup"><span data-stu-id="da3fc-107">Returns an implementation of a quantum error correction code by specifying a `QECC` type.</span></span>

## <a name="remarks"></a><span data-ttu-id="da3fc-108">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="da3fc-108">Remarks</span></span>

<span data-ttu-id="da3fc-109">A kód a következő két dokumentumtól függetlenül található:</span><span class="sxs-lookup"><span data-stu-id="da3fc-109">This code was found independently in the following two papers:</span></span>

- <span data-ttu-id="da3fc-110">C.</span><span class="sxs-lookup"><span data-stu-id="da3fc-110">C.</span></span> <span data-ttu-id="da3fc-111">H.</span><span class="sxs-lookup"><span data-stu-id="da3fc-111">H.</span></span> <span data-ttu-id="da3fc-112">Bennett, D. alvincenzo, J. A.</span><span class="sxs-lookup"><span data-stu-id="da3fc-112">Bennett, D. DiVincenzo, J. A.</span></span> <span data-ttu-id="da3fc-113">Smolin és W. K.</span><span class="sxs-lookup"><span data-stu-id="da3fc-113">Smolin and W. K.</span></span> <span data-ttu-id="da3fc-114">Wootters, "vegyes állapotú felakadás és kvantum-hibajavítás," leltár. Rev. A, 54 (1996) PP. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 és</span><span class="sxs-lookup"><span data-stu-id="da3fc-114">Wootters, "Mixed state entanglement and quantum error correction," Phys. Rev. A, 54 (1996) pp. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 and</span></span>
- <span data-ttu-id="da3fc-115">R.</span><span class="sxs-lookup"><span data-stu-id="da3fc-115">R.</span></span> <span data-ttu-id="da3fc-116">Leva, C. Miquel, J. P.</span><span class="sxs-lookup"><span data-stu-id="da3fc-116">Laflamme, C. Miquel, J. P.</span></span> <span data-ttu-id="da3fc-117">Paz és W. H</span><span class="sxs-lookup"><span data-stu-id="da3fc-117">Paz and W. H.</span></span> <span data-ttu-id="da3fc-118">Zurek, "tökéletes kvantum-hibajavítási kód", "leltár. Rev. lett.</span><span class="sxs-lookup"><span data-stu-id="da3fc-118">Zurek, "Perfect quantum error correction code," Phys. Rev. Lett.</span></span> <span data-ttu-id="da3fc-119">77 (1996) PP. 198-201; https://arxiv.org/abs/quant-ph/9602019</span><span class="sxs-lookup"><span data-stu-id="da3fc-119">77 (1996) pp. 198-201; https://arxiv.org/abs/quant-ph/9602019</span></span>