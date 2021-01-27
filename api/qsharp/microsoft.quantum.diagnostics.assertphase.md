---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: AssertPhase művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: 59fa0f2f68b4de271b972aef776ee5097fd5c201
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830083"
---
# <a name="assertphase-operation"></a>AssertPhase művelet

Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Azt állítja be, hogy az egyenlő prioritású állapot fázisában a várt érték szerepel.

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a>Leírás

Ez a művelet azt állítja be, hogy a $ \frac{e ^ {i t}} {\sqrt {2} } (e ^ {i\phi} \ ket {0} + e ^ {-i\phi} \ ket) $t $ értékű Quantum állapot $ \phi $ {1} értéke a várt értékkel rendelkezik.

## <a name="input"></a>Bevitel

### <a name="expected--double"></a>várt érték: [Double](xref:microsoft.quantum.lang-ref.double)

A várt érték: $ \phi \in (-\pi, \pi] $.


### <a name="qubit--qubit"></a>qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

A várt állapotot tároló qubit.


### <a name="tolerance--double"></a>tolerancia: [dupla](xref:microsoft.quantum.lang-ref.double)

A tényleges és a várt érték közötti különbség abszolút tűréshatára.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Példa

A következő érvényesítés sikeres: `qubit` állapot $ \ket{\psi} = e ^ {i 0.5} \ SQRT {1/2} \ ket {0} + e ^ {i 0.5} \ SQRT {1/2} \ ket {1} $;

- `AssertPhase(0.0,qubit,10e-10);`

`qubit` állapotban van $ \ket{\psi} = e ^ {i 0.5} \ SQRT {1/2} \ ket {0} + e ^ {-i 0.5} \ SQRT {1/2} \ ket {1} $;

- `AssertPhase(0.5,qubit,10e-10);`

`qubit` állapotban van $ \ket{\psi} = e ^ {-i 2.2} \ SQRT {1/2} \ ket {0} + e ^ {i 0.2} \ SQRT {1/2} \ ket {1} $;

- `AssertPhase(-1.2,qubit,10e-10);`