---
uid: Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance
title: AssertQubitIsInStateWithinTolerance művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitIsInStateWithinTolerance
qsharp.summary: >-
  Asserts that a qubit in the expected state.

  `expected` represents a complex vector, $\ket{\psi} = \begin{bmatrix}a & b\end{bmatrix}^{\mathrm{T}}$. The first element of the tuples representing each of $a$, $b$ is the real part of the complex number, while the second one is the imaginary part. The last argument defines the tolerance with which assertion is made.
ms.openlocfilehash: b40c5c4f731190c8c0d00d33718680e5448bf767
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829780"
---
# <a name="assertqubitisinstatewithintolerance-operation"></a>AssertQubitIsInStateWithinTolerance művelet

Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Azt állítja be, hogy a qubit a várt állapotú.

`expected` összetett vektort jelöl: $ \ket{\psi} = \begin{bmatrix}a & b\end {bmatrix} ^ {\mathrm{T}} $.
A $a $, $b $ értéket képviselő rekordok első eleme a komplex szám valódi része, míg a második a képzeletbeli rész.
Az utolsó argumentum meghatározza azt a tűréshatárt, amellyel az érvényesítés történik.

```qsharp
operation AssertQubitIsInStateWithinTolerance (expected : (Microsoft.Quantum.Math.Complex, Microsoft.Quantum.Math.Complex), register : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a>Bevitel

### <a name="expected--complexcomplex"></a>várt: ([összetett](xref:Microsoft.Quantum.Math.Complex),[összetett](xref:Microsoft.Quantum.Math.Complex))

A várt összetett amplitúdók a $ \ket {0} $ és a $ \ket $ értéknél {1} .


### <a name="register--qubit"></a>Regisztráció: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Az a Qubit, amelynek az állapotát érvényesíteni kell. Vegye figyelembe, hogy ez a qubit feltételezhető, hogy elkülöníthető a többi lefoglalt qubits, és nincs összekeverve.


### <a name="tolerance--double"></a>tolerancia: [dupla](xref:microsoft.quantum.lang-ref.double)

Az adalékanyag tűréshatára, amellyel a tényleges amplitúdók eltérhetnek a várttól.
Részletekért lásd az alábbi megjegyzéseket.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Példa

```qsharp
using (qubits = Qubit[2]) {
    // Both qubits are initialized as |0〉: a=(1 + 0*i), b=(0 + 0*i)
    AssertQubitIsInStateWithinTolerance((Complex(1., 0.), Complex(0., 0.)), qubits[0], 1e-5);
    AssertQubitIsInStateWithinTolerance((Complex(1., 0.), Complex(0., 0.)), qubits[1], 1e-5);
    Y(qubits[1]);
    // Y |0〉 = i |1〉: a=(0 + 0*i), b=(0 + 1*i)
    AssertQubitIsInStateWithinTolerance((Complex(0., 0.), Complex(0., 1.)), qubits[1], 1e-5);
}
```

## <a name="remarks"></a>Megjegyzések

A következő Mathematica-kód segítségével ellenőrizheti a mi, MX, My, MZ kifejezéseket:

```mathematica
{Id, X, Y, Z} = Table[PauliMatrix[k], {k, 0, 3}];
st = {{ reA + I imA }, { reB + I imB} };
M = st . ConjugateTranspose[st];
mx = Tr[M.X] // ComplexExpand;
my = Tr[M.Y] // ComplexExpand;
mz = Tr[M.Z] // ComplexExpand;
mi = Tr[M.Id] // ComplexExpand;
2 m == Id mi + X mx + Z mz + Y my // ComplexExpand // Simplify
```

A tolerancia a $L \_ {\infty} $ távolság a 3 dimenziós valós vektor között (x ₂, x ₃, x ₄) a $ \langle\psi | \psi\rangle = x \_ 1 I + x \_ 2 x + x \_ 3 Y + x \_ 4 Z $ és a Real Vector (y ₂, y ₃, y ₄) által meghatározott ρ = Y ₁ I + y ₂ x + y ₃ Y + y ₄ Z, ahol a ρ a regiszter állapotának megfelelő sűrűségi mátrix.
Ez csak abban az esetben igaz, ha a TR (ρ) és a TR (| ψ ⟩ ⟨ ψ |) mindkettő 1 (például x ₁ = 1/2, y ₁ = 1/2).
Ha ez nem így van, a függvény azt állítja be, hogy az l ∞ távolság (x ₂-x ₁, x ₃-x ₁, x ₄-x ₁, x ₄ + x ₁) és (y ₂-y ₁, y ₃-y ₁, y ₄-y ₁, y ₄ + y ₁) értéke kisebb, mint a tolerancia paraméter.