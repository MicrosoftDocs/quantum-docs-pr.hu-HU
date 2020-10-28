---
uid: Microsoft.Quantum.ErrorCorrection.CSS
title: CSS-felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: CSS
qsharp.summary: Represents a Calderbank–Shor–Steane (CSS) code as defined by its encoder, decoder, and its syndrome measurement procedures for `X` and `Z` errors, respectively.
ms.openlocfilehash: c5227c771ec2c7c81d05a28681745af641eebeaf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712492"
---
# <a name="css-user-defined-type"></a><span data-ttu-id="cc657-102">CSS-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="cc657-102">CSS user defined type</span></span>

<span data-ttu-id="cc657-103">Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="cc657-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="cc657-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cc657-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cc657-105">Egy Calderbank – rövid – Steane (CSS) kódot jelöl, amelyet a kódoló, a dekóder és a szindrómás-mérési eljárások határoznak meg, illetve `X` `Z` hibák esetén.</span><span class="sxs-lookup"><span data-stu-id="cc657-105">Represents a Calderbank–Shor–Steane (CSS) code as defined by its encoder, decoder, and its syndrome measurement procedures for `X` and `Z` errors, respectively.</span></span>

```qsharp

newtype CSS = (Microsoft.Quantum.ErrorCorrection.EncodeOp, Microsoft.Quantum.ErrorCorrection.DecodeOp, Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp, Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp);
```

