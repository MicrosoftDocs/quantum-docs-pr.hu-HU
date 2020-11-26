---
uid: Microsoft.Quantum.ErrorCorrection.TableLookupRecovery
title: TableLookupRecovery függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: TableLookupRecovery
qsharp.summary: For a given table of Pauli operations on a given register of qubits, this function returns an object of type `RecoveryFn` which contains all information needed to perform a table-lookup decoding with respect to the given array of Pauli operations.
ms.openlocfilehash: e4136add99ab7fb6904d7cac3c7f3e5076cc3176
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213667"
---
# <a name="tablelookuprecovery-function"></a>TableLookupRecovery függvény

Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy adott, a qubits adott nyilvántartásába tartozó művelet esetében ez a függvény egy típusú objektumot ad vissza, `RecoveryFn` amely tartalmazza az összes olyan információt, amely egy táblázatos keresési dekódolás végrehajtásához szükséges a Pauli-műveletek adott tömbje tekintetében.

```qsharp
function TableLookupRecovery (table : Pauli[][]) : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="input"></a>Bevitel

### <a name="table--pauli"></a>tábla: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Egy adott qubit-regisztrációban működő Pauli-műveletek táblázata



## <a name="output--recoveryfn"></a>Kimenet: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

Egy típusú objektum `RecoveryFn` , azaz egy `Syndrome -> Pauli[]` adott szindrómához társított Térkép egy megfelelő Pauli-javító művelet.