---
uid: Microsoft.Quantum.ErrorCorrection._ExtractLogicalQubitFromSteaneCode
title: _ExtractLogicalQubitFromSteaneCode művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: _ExtractLogicalQubitFromSteaneCode
qsharp.summary: >-
  Syndrome measurement and the inverse of embedding.

  $X$- and $Z$-stabilizers are not treated equally, which is due to the particular choice of the encoding circuit. This asymmetry leads to a different syndrome extraction routine. One could measure the syndrome by measuring multi-qubit Pauli operator directly on the code state, but for the distillation purpose the logical qubit is returned into a single qubit, in course of which the syndrome measurements can be done without further ancillas.
ms.openlocfilehash: fe64343e30a0a3f0d05382e7812d37d5b13133d3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853213"
---
# <a name="_extractlogicalqubitfromsteanecode-operation"></a>_ExtractLogicalQubitFromSteaneCode művelet

Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


A szindrómás mértékét és a beágyazás inverzét.

$X $-és $Z $-stabilizátorokat nem egyformán kezeli a rendszer, ami a kódolási áramkör adott választásának köszönhető.
Ez az aszimmetria egy másik tünetegyüttes-kinyerési rutinhoz vezet.
Az egyik lehetséges, hogy a qubit Pauli-operátort közvetlenül a kód állapotának mérésével mérjük, a qubit azonban a logikai egyetlen qubit kerül vissza, amely során a tünetegyüttes mérése további ancillas nélkül végezhető el.

```qsharp
operation _ExtractLogicalQubitFromSteaneCode (code : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit, Int, Int)
```


## <a name="input"></a>Bevitel

### <a name="code--logicalregister"></a>kód: [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)





## <a name="output--qubitintint"></a>Kimenet: ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))

A logikai qubit és a $X $-szindrómára és $Z $-szindrómára vonatkozó pár egész szám.
A kód azon qubit indexét képviselik, amelyeken egy $X $-vagy $Z $-Error érték a mért szindrómát okozta volna.

## <a name="remarks"></a>Megjegyzések

Vegye figyelembe, hogy ez a művelet nincs megjelölve `internal` , mert az egység-tesztek közvetlenül a művelettől függenek. Jövőbeli fejlesztésként az egységbeli teszteket úgy kell átgondolni, hogy csak a nyilvános callables közvetlenül fussanak.

> [!WARNING]
> Ez a rutin a Steane 7 qubit-kódjának egy adott kódolási áramköréhez van igazítva. Ha a kódolási áramkör módosul, akkor előfordulhat, hogy a szindrómát másképp kell értelmezni.