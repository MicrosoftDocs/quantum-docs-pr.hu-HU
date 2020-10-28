---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX
title: SteaneCodeRecoveryX függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeRecoveryX
qsharp.summary: Decoder for the X-part of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 0f6b987ca23bd9ff2076080d60f1ca756b36848e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712129"
---
# <a name="steanecoderecoveryx-function"></a><span data-ttu-id="93468-102">SteaneCodeRecoveryX függvény</span><span class="sxs-lookup"><span data-stu-id="93468-102">SteaneCodeRecoveryX function</span></span>

<span data-ttu-id="93468-103">Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="93468-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="93468-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="93468-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="93468-105">A ⟦ 7, 1, 3 ⟧ Steane kvantum-kód stabilizátor csoportjába tartozó X-részhez tartozó dekóder.</span><span class="sxs-lookup"><span data-stu-id="93468-105">Decoder for the X-part of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
function SteaneCodeRecoveryX (syndrome : Microsoft.Quantum.ErrorCorrection.Syndrome) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="93468-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="93468-106">Input</span></span>

### <a name="syndrome--syndrome"></a><span data-ttu-id="93468-107">szindróma: [szindróma](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span><span class="sxs-lookup"><span data-stu-id="93468-107">syndrome : [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span></span>

<span data-ttu-id="93468-108">A stabilizátor X-részének mérésével kapott tünetegyüttes-tömb.</span><span class="sxs-lookup"><span data-stu-id="93468-108">A syndrome array obtained from measuring the X-part of the stabilizer.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="93468-109">Kimenet: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="93468-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="93468-110">Egy olyan Pauli-műveletből álló tömb, amely a kódolt kvantum-rendszerre alkalmazva kijavította a megfelelő hibát `syndrome` .</span><span class="sxs-lookup"><span data-stu-id="93468-110">An array of Pauli operations which, when applied to the encoded quantum system corrects the error corresponding to `syndrome`.</span></span>

## <a name="remarks"></a><span data-ttu-id="93468-111">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="93468-111">Remarks</span></span>

<span data-ttu-id="93468-112">A kiválasztott dekóder a ⟦ 7, 1, 3 ⟧ Steane kód CSS Code tulajdonságát használja, azaz az X hibákat és a Z hibákat külön-külön kijavította.</span><span class="sxs-lookup"><span data-stu-id="93468-112">The chosen decoder uses the CSS code property of the ⟦7, 1, 3⟧ Steane code, i.e., it corrects X errors and Z errors separately.</span></span> <span data-ttu-id="93468-113">A kód egy tulajdonsága az, hogy az alkalmazni kívánt X, vagy Z érték az X, a z szindróma 3 bites kódolása, ha egész számnak számít.</span><span class="sxs-lookup"><span data-stu-id="93468-113">A property of the code is that the location of the X, respectively, Z correction to be applied is the 3-bit encoding of the X, respectively, Z syndrome when considered an integer.</span></span>

## <a name="references"></a><span data-ttu-id="93468-114">Referencia</span><span class="sxs-lookup"><span data-stu-id="93468-114">References</span></span>

- <span data-ttu-id="93468-115">D.</span><span class="sxs-lookup"><span data-stu-id="93468-115">D.</span></span> <span data-ttu-id="93468-116">Gottesman, "stabilizátor-kódok és kvantum-hibák javítása" Ph.D. tézis, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span><span class="sxs-lookup"><span data-stu-id="93468-116">Gottesman, "Stabilizer Codes and Quantum Error Correction," Ph.D. Thesis, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span></span>

## <a name="see-also"></a><span data-ttu-id="93468-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="93468-117">See Also</span></span>

- [<span data-ttu-id="93468-118">Microsoft. Quantum. ErrorCorrection. SteaneCodeRecoveryX</span><span class="sxs-lookup"><span data-stu-id="93468-118">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX)
- [<span data-ttu-id="93468-119">Microsoft. Quantum. ErrorCorrection. SteaneCodeRecoveryFns</span><span class="sxs-lookup"><span data-stu-id="93468-119">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns)