---
uid: Microsoft.Quantum.ErrorCorrection.TableLookupRecovery
title: TableLookupRecovery függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: TableLookupRecovery
qsharp.summary: For a given table of Pauli operations on a given register of qubits, this function returns an object of type `RecoveryFn` which contains all information needed to perform a table-lookup decoding with respect to the given array of Pauli operations.
ms.openlocfilehash: c56a9bbb1db72b5ba03ee9976e648a59f651aa16
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712045"
---
# <a name="tablelookuprecovery-function"></a><span data-ttu-id="35c42-102">TableLookupRecovery függvény</span><span class="sxs-lookup"><span data-stu-id="35c42-102">TableLookupRecovery function</span></span>

<span data-ttu-id="35c42-103">Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="35c42-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="35c42-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="35c42-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="35c42-105">Egy adott, a qubits adott nyilvántartásába tartozó művelet esetében ez a függvény egy típusú objektumot ad vissza, `RecoveryFn` amely tartalmazza az összes olyan információt, amely egy táblázatos keresési dekódolás végrehajtásához szükséges a Pauli-műveletek adott tömbje tekintetében.</span><span class="sxs-lookup"><span data-stu-id="35c42-105">For a given table of Pauli operations on a given register of qubits, this function returns an object of type `RecoveryFn` which contains all information needed to perform a table-lookup decoding with respect to the given array of Pauli operations.</span></span>

```qsharp
function TableLookupRecovery (table : Pauli[][]) : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="input"></a><span data-ttu-id="35c42-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="35c42-106">Input</span></span>

### <a name="table--pauli"></a><span data-ttu-id="35c42-107">tábla: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="35c42-107">table : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="35c42-108">Egy adott qubit-regisztrációban működő Pauli-műveletek táblázata</span><span class="sxs-lookup"><span data-stu-id="35c42-108">Table of Pauli operations that operate on a given qubit register</span></span>



## <a name="output--recoveryfn"></a><span data-ttu-id="35c42-109">Kimenet: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="35c42-109">Output : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="35c42-110">Egy típusú objektum `RecoveryFn` , azaz egy `Syndrome -> Pauli[]` adott szindrómához társított Térkép egy megfelelő Pauli-javító művelet.</span><span class="sxs-lookup"><span data-stu-id="35c42-110">An object of type `RecoveryFn`, i.e., a map `Syndrome -> Pauli[]` that associates with a given syndrome array a corresponding Pauli correction operation.</span></span>