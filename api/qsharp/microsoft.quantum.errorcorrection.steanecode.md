---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCode
title: SteaneCode függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCode
qsharp.summary: Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: ea36320fff1f0c24426e2fcead976ef051d6699f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712184"
---
# <a name="steanecode-function"></a><span data-ttu-id="c95a8-102">SteaneCode függvény</span><span class="sxs-lookup"><span data-stu-id="c95a8-102">SteaneCode function</span></span>

<span data-ttu-id="c95a8-103">Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="c95a8-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="c95a8-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c95a8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c95a8-105">Egy CSS-értéket ad vissza, amely a ⟦ 7, 1, 3 ⟧ Steane és a dekódert a helyi szindrómás mérésével adja meg.</span><span class="sxs-lookup"><span data-stu-id="c95a8-105">Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function SteaneCode () : Microsoft.Quantum.ErrorCorrection.CSS
```


## <a name="output--css"></a><span data-ttu-id="c95a8-106">Kimenet: [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span><span class="sxs-lookup"><span data-stu-id="c95a8-106">Output : [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span></span>

<span data-ttu-id="c95a8-107">Egy CSS típusú objektum, amely összegyűjti az összes releváns adatot a ⟦ 7, 1, 3 ⟧ Steane kód kódolásának és hibajavításának elvégzéséhez.</span><span class="sxs-lookup"><span data-stu-id="c95a8-107">An object of CSS type which collects all relevant data to perform encoding and error correction for the ⟦7, 1, 3⟧ Steane code.</span></span>

## <a name="remarks"></a><span data-ttu-id="c95a8-108">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="c95a8-108">Remarks</span></span>

<span data-ttu-id="c95a8-109">Ez a kód a következő dokumentumban található:</span><span class="sxs-lookup"><span data-stu-id="c95a8-109">This code was found in the following paper:</span></span>

- <span data-ttu-id="c95a8-110">A.</span><span class="sxs-lookup"><span data-stu-id="c95a8-110">A.</span></span> <span data-ttu-id="c95a8-111">Steane, "több részecske-interferencia és kvantum-hibajavítás", proc.</span><span class="sxs-lookup"><span data-stu-id="c95a8-111">Steane, "Multiple Particle Interference and Quantum Error Correction", Proc.</span></span> <span data-ttu-id="c95a8-112">Roy.</span><span class="sxs-lookup"><span data-stu-id="c95a8-112">Roy.</span></span> <span data-ttu-id="c95a8-113">SoC. Lond.</span><span class="sxs-lookup"><span data-stu-id="c95a8-113">Soc. Lond.</span></span> <span data-ttu-id="c95a8-114">A452 (1996) PP. 2551; https://arxiv.org/abs/quant-ph/9601029.</span><span class="sxs-lookup"><span data-stu-id="c95a8-114">A452 (1996) pp. 2551; https://arxiv.org/abs/quant-ph/9601029.</span></span>