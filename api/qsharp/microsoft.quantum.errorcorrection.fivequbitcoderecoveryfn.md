---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeRecoveryFn
title: FiveQubitCodeRecoveryFn függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeRecoveryFn
qsharp.summary: Returns function that maps error syndrome measurements to the appropriate error-correcting Pauli operators by table lookup for the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 94b6c12f31b0e6367151d0ebb225cff5f82915e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853129"
---
# <a name="fivequbitcoderecoveryfn-function"></a><span data-ttu-id="7440f-102">FiveQubitCodeRecoveryFn függvény</span><span class="sxs-lookup"><span data-stu-id="7440f-102">FiveQubitCodeRecoveryFn function</span></span>

<span data-ttu-id="7440f-103">Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="7440f-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="7440f-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7440f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7440f-105">Azt a függvényt adja vissza, amely leképezi a hiba-szindrómát a megfelelő hiba kijavítani a Pauli-operátorok számára az 5, 1, 3 ⟧ kvantum-kód ⟦.</span><span class="sxs-lookup"><span data-stu-id="7440f-105">Returns function that maps error syndrome measurements to the appropriate error-correcting Pauli operators by table lookup for the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
function FiveQubitCodeRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a><span data-ttu-id="7440f-106">Kimenet: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="7440f-106">Output : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="7440f-107">Olyan típusú függvény, `RecoveryFn` amely egy tünetegyüttes-mérést végez `Result[]` , és az `Pauli[]` észlelt hibát javító operátorokat adja vissza.</span><span class="sxs-lookup"><span data-stu-id="7440f-107">Function of type `RecoveryFn` that takes a syndrome measurement `Result[]` and returns the `Pauli[]` operators that corrects the detected error.</span></span>

## <a name="remarks"></a><span data-ttu-id="7440f-108">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="7440f-108">Remarks</span></span>

<span data-ttu-id="7440f-109">Az $1 $ súlyozású összes hiba megismétlésével összesen $3 \ alkalommal 5 = 15 $ lehetséges, nem triviális tünetegyüttest kapunk.</span><span class="sxs-lookup"><span data-stu-id="7440f-109">By iterating over all errors of weight $1$, we obtain a total of $3\times 5=15$ possible non-trivial syndromes.</span></span>
<span data-ttu-id="7440f-110">Az identitással együtt a rendszer felépíti a hibát tartalmazó táblázatot és a megfelelő szindrómát.</span><span class="sxs-lookup"><span data-stu-id="7440f-110">Together with the identity, a table of error and corresponding syndrome is built up.</span></span> <span data-ttu-id="7440f-111">Az 5 qubit-kód esetében ezt a táblázatot a következő adja meg: $X \_ 1: (0, 0, 0, 1); X \_ 2: (1, 0, 0, 0); X \_ 3: (1, 1, 0, 0); X \_ 4: (0, 1, 1, 0); X \_ 5: (0, 0, 1, 1) $, $Z \_ 1: (1, 0, 1, 0); Z \_ 2: (0, 1, 0, 1); Z \_ 3: (0, 0, 1, 0); Z \_ 4: (1, 0, 0, 1); Z \_ 5: (0, 1, 0, 0) $ $Y _i $ beszerzésével, a $X _i $ és a $Z $ szindrómák hozzáadásával.</span><span class="sxs-lookup"><span data-stu-id="7440f-111">For the 5 qubit code this table is given by: $X\_1: (0,0,0,1); X\_2: (1,0,0,0); X\_3: (1,1,0,0); X\_4: (0,1,1,0); X\_5: (0,0,1,1)$, $Z\_1: (1,0,1,0); Z\_2: (0,1,0,1); Z\_3: (0,0,1,0); Z\_4: (1,0,0,1); Z\_5: (0,1,0,0)$ with $Y_i$ obtained by adding the $X_i$ and $Z_i$ syndromes.</span></span> <span data-ttu-id="7440f-112">Vegye figyelembe, hogy a tábla keresésének helyreállítását úgy adja meg, hogy a bitvectors egész számmá (kis endian használatával) konvertálja.</span><span class="sxs-lookup"><span data-stu-id="7440f-112">Note that the ordering in the table lookup recovery is given by converting the bitvectors to integers (using little endian).</span></span>

## <a name="see-also"></a><span data-ttu-id="7440f-113">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="7440f-113">See Also</span></span>

- [<span data-ttu-id="7440f-114">Microsoft. Quantum. ErrorCorrection. RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="7440f-114">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)