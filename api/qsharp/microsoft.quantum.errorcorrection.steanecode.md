---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCode
title: SteaneCode függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCode
qsharp.summary: Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: af3f3ef5088b898bd827ebca00fdc7fcb992f2a1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853059"
---
# <a name="steanecode-function"></a><span data-ttu-id="bf704-102">SteaneCode függvény</span><span class="sxs-lookup"><span data-stu-id="bf704-102">SteaneCode function</span></span>

<span data-ttu-id="bf704-103">Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="bf704-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="bf704-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bf704-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bf704-105">Egy CSS-értéket ad vissza, amely a ⟦ 7, 1, 3 ⟧ Steane és a dekódert a helyi szindrómás mérésével adja meg.</span><span class="sxs-lookup"><span data-stu-id="bf704-105">Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function SteaneCode () : Microsoft.Quantum.ErrorCorrection.CSS
```


## <a name="output--css"></a><span data-ttu-id="bf704-106">Kimenet: [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span><span class="sxs-lookup"><span data-stu-id="bf704-106">Output : [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span></span>

<span data-ttu-id="bf704-107">Egy CSS típusú objektum, amely összegyűjti az összes releváns adatot a ⟦ 7, 1, 3 ⟧ Steane kód kódolásának és hibajavításának elvégzéséhez.</span><span class="sxs-lookup"><span data-stu-id="bf704-107">An object of CSS type which collects all relevant data to perform encoding and error correction for the ⟦7, 1, 3⟧ Steane code.</span></span>

## <a name="remarks"></a><span data-ttu-id="bf704-108">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="bf704-108">Remarks</span></span>

<span data-ttu-id="bf704-109">Ez a kód a következő dokumentumban található:</span><span class="sxs-lookup"><span data-stu-id="bf704-109">This code was found in the following paper:</span></span>

- <span data-ttu-id="bf704-110">A.</span><span class="sxs-lookup"><span data-stu-id="bf704-110">A.</span></span> <span data-ttu-id="bf704-111">Steane, "több részecske-interferencia és kvantum-hibajavítás", proc.</span><span class="sxs-lookup"><span data-stu-id="bf704-111">Steane, "Multiple Particle Interference and Quantum Error Correction", Proc.</span></span> <span data-ttu-id="bf704-112">Roy.</span><span class="sxs-lookup"><span data-stu-id="bf704-112">Roy.</span></span> <span data-ttu-id="bf704-113">SoC. Lond.</span><span class="sxs-lookup"><span data-stu-id="bf704-113">Soc. Lond.</span></span> <span data-ttu-id="bf704-114">A452 (1996) PP. 2551; https://arxiv.org/abs/quant-ph/9601029.</span><span class="sxs-lookup"><span data-stu-id="bf704-114">A452 (1996) pp. 2551; https://arxiv.org/abs/quant-ph/9601029.</span></span>