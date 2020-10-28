---
uid: Microsoft.Quantum.Canon.MultiplexerBruteForceFromGenerator
title: MultiplexerBruteForceFromGenerator függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexerBruteForceFromGenerator
qsharp.summary: >-
  Returns a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: ad388bd34a778a7d774cd2a5118399b3db45267d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715895"
---
# <a name="multiplexerbruteforcefromgenerator-function"></a>MultiplexerBruteForceFromGenerator függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag [](https://nuget.org/packages/)


Egy szorzásra vezérelt, egységes műveletet ad vissza, $U $, amely egy egységes $V _j $ értéket alkalmaz, ha n-qubit számú \ket{j} $.

$U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.

```qsharp
function MultiplexerBruteForceFromGenerator (unitaryGenerator : (Int, (Int -> (Qubit[] => Unit is Adj + Ctl)))) : ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a>Bevitel

### <a name="unitarygenerator--intint---qubit--unit-adj--ctl"></a>unitaryGenerator: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) : Adj + CTL)

Egy rekord, amelyben az első elem `Int` a unitaries $N $, a második elem `(Int -> ('T => () is Adj + Ctl))` pedig egy függvény, amely egy egész $j $ értéket vesz igénybe $ [0, N-1] $ értékben, és az egységes művelet $V _j $ értéket adja eredményül.



## <a name="output--littleendianqubit--unit-adj--ctl"></a>Kimenet: ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [egység](xref:microsoft.quantum.lang-ref.unit) Adj + CTL

Egy szorzásra vezérelt, egységes művelet $U $, amely a által ismertetett unitaries alkalmazza `unitaryGenerator` .

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. MultiplexerBruteForceFromGenerator](xref:Microsoft.Quantum.Canon.MultiplexerBruteForceFromGenerator)