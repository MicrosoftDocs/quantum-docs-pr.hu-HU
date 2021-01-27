---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation
title: ApplyPermutationUsingTransformation művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingTransformation
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using transformation-based synthesis.
ms.openlocfilehash: 79913bec44514d477b7ee0668b43396b297b9ab8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858999"
---
# <a name="applypermutationusingtransformation-operation"></a>ApplyPermutationUsingTransformation művelet

Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


A Permutes az átalakítási alapú szintézis használatával egy olyan kvantum-állapotot adott meg, amely egy permutációt használ.

```qsharp
operation ApplyPermutationUsingTransformation (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Leírás

Ez az eljárás megvalósítja az egyirányú átalakításon alapuló szintézis megközelítését.  A bemenet egy \pi $ több mint $2 ^ n $ Elements $ \{ 0, \dots, 2 ^ n-1 \} $, amely egy $n $-változó visszafordítható logikai függvényt jelöl.
Az algoritmus a következő lépésekkel hajtja végre a iteratív:

1. Keresse meg a legkisebb $x $ értéket, amely $x \ne \pi (x) = y $.
2. Több vezérelt Toffoli-művelet, amelyek a kimenetekre vonatkoznak, a $ \pi (x) = x $ értéket, és nem változtatja meg a $ \pi (x) $ értéket az összes $x "< x $

## <a name="input"></a>Bevitel

### <a name="perm--int"></a>dauer: [int](xref:microsoft.quantum.lang-ref.int)[]

A 0-tól kezdődően 2 ^ n $ elemből álló permutáció.


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$N $ qubits listája, amelyre a permutáció vonatkozik.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Példa

Művelet szintetizálása `SWAP` :

```qsharp
using (qubits = Qubit[2]) {
  ApplyPermutationUsingTransformation([0, 2, 1, 3], LittleEndian(qubits));
}
```

## <a name="references"></a>Hivatkozások

- [*D. Michael Miller*, *Dmitrij Maslov*, *Gerhard W. Dueck*, proc. DAC 2003, IEEE, PP. 318-323, 2003](https://doi.org/10.1145/775832.775915)
- [*Mathias Soeken*, *Gerhard W. Dueck*, *D. Michael Miller*, proc. RC 2016, Springer, PP. 307-321, 2016](https://doi.org/10.1007/978-3-319-40578-0_22)

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. szintézis. ApplyPermutationUsingDecomposition](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)