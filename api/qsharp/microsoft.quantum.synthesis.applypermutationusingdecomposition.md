---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition
title: ApplyPermutationUsingDecomposition művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecomposition
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: 40b51807da155c57c3fa8d740eff28ceef0a0ffc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725320"
---
# <a name="applypermutationusingdecomposition-operation"></a>ApplyPermutationUsingDecomposition művelet

Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)

Csomag [](https://nuget.org/packages/)


A Permutes az amplitúdókat a dekompozíciós-alapú szintézis használatával, a kvantum-állapotban kell megadni.

```qsharp
operation ApplyPermutationUsingDecomposition (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>Leírás

Ez az eljárás megvalósítja a dekompozíciós alapú szintézis megközelítését.  A bemenet egy \pi $ több mint $2 ^ n $ Elements $ \{ 0, \dots, 2 ^ n-1 \} $, amely egy $n $-változó megfordítható logikai függvényt jelöl.
A iteratív algoritmus a következő lépéseket hajtja végre az egyes változók $i $-indexek esetében:

1. A számítási $ ((\ pi_l, \ pi_r), \pi ') $ úgy, hogy a $ \ pi_l $ és a $ \ pi_r $ lemezképek ne változtassák meg a BITS-elemeket a $i $ és a $ \pi ' $ értéknél nem változtatnak a bit $i $ értékkel az elemekben.
2. Állítsa be a $ \pi \leftarrow \pi ' $ értéket, és származtatja az igazság táblákat a $ \ pi_l $ és a $ \ pi_r $ érték alapján a nem rögzített elemek alapján.

Miután alkalmazza ezeket a lépéseket az összes változó indexre, a fennmaradó permutáció $ \pi $ lesz az identitás, és az összegyűjtött igazság táblák és indexek alapján az egyik @"microsoft.quantum.intrinsic.x" a művelettel az igazság-tábla által vezérelt műveletekkel is alkalmazható @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" .

A változó sorrend értéke $0, \dots, n-$1.  A műveletben megadhat egyéni változó sorrendet @"microsoft.quantum.synthesis.applypermutationusingdecompositionwithvariableorder" .

## <a name="input"></a>Bevitel

### <a name="perm--int"></a>dauer: [int](xref:microsoft.quantum.lang-ref.int)[]

A 0-tól kezdődően 2 ^ n $ elemből álló permutáció.


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$N $ qubits listája, amelyre a permutáció vonatkozik.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Referencia

- [*Alexis de Vos* , *Yvan van Rentergem* , ADV. in Math. of comm. 2 (2), 2008, PP. 183--200](http://www.aimsciences.org/article/doi/10.3934/amc.2008.2.183)
- [*Mathias Soeken* , *Laura Tóthné* , *Gerhard W. Dueck* , *Rolf Drechsler* , szimbolikus számítások lapja 73 (2016), PP. 1--26](https://www.sciencedirect.com/science/article/pii/S0747717115000188?via%3Dihub)

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. szintézis. ApplyPermutationUsingDecompositionWithVariableOrder](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder)
- [Microsoft. Quantum. szintézis. ApplyPermutationUsingTransformation](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)