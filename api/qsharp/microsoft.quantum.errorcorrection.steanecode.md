---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCode
title: SteaneCode függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCode
qsharp.summary: Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: b981c82acfa82cd58d82666703d4bb95ac5df280
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200475"
---
# <a name="steanecode-function"></a><span data-ttu-id="1bf42-102">SteaneCode függvény</span><span class="sxs-lookup"><span data-stu-id="1bf42-102">SteaneCode function</span></span>

<span data-ttu-id="1bf42-103">Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="1bf42-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="1bf42-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1bf42-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1bf42-105">Egy CSS-értéket ad vissza, amely a ⟦ 7, 1, 3 ⟧ Steane és a dekódert a helyi szindrómás mérésével adja meg.</span><span class="sxs-lookup"><span data-stu-id="1bf42-105">Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function SteaneCode () : Microsoft.Quantum.ErrorCorrection.CSS
```


## <a name="output--css"></a><span data-ttu-id="1bf42-106">Kimenet: [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span><span class="sxs-lookup"><span data-stu-id="1bf42-106">Output : [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span></span>

<span data-ttu-id="1bf42-107">Egy CSS típusú objektum, amely összegyűjti az összes releváns adatot a ⟦ 7, 1, 3 ⟧ Steane kód kódolásának és hibajavításának elvégzéséhez.</span><span class="sxs-lookup"><span data-stu-id="1bf42-107">An object of CSS type which collects all relevant data to perform encoding and error correction for the ⟦7, 1, 3⟧ Steane code.</span></span>

## <a name="remarks"></a><span data-ttu-id="1bf42-108">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="1bf42-108">Remarks</span></span>

<span data-ttu-id="1bf42-109">Ez a kód a következő dokumentumban található:</span><span class="sxs-lookup"><span data-stu-id="1bf42-109">This code was found in the following paper:</span></span>

- <span data-ttu-id="1bf42-110">A.</span><span class="sxs-lookup"><span data-stu-id="1bf42-110">A.</span></span> <span data-ttu-id="1bf42-111">Steane, "több részecske-interferencia és kvantum-hibajavítás", proc.</span><span class="sxs-lookup"><span data-stu-id="1bf42-111">Steane, "Multiple Particle Interference and Quantum Error Correction", Proc.</span></span> <span data-ttu-id="1bf42-112">Roy.</span><span class="sxs-lookup"><span data-stu-id="1bf42-112">Roy.</span></span> <span data-ttu-id="1bf42-113">SoC. Lond.</span><span class="sxs-lookup"><span data-stu-id="1bf42-113">Soc. Lond.</span></span> <span data-ttu-id="1bf42-114">A452 (1996) PP. 2551; https://arxiv.org/abs/quant-ph/9601029.</span><span class="sxs-lookup"><span data-stu-id="1bf42-114">A452 (1996) pp. 2551; https://arxiv.org/abs/quant-ph/9601029.</span></span>