---
uid: Microsoft.Quantum.Preparation.PurifiedMixedState
title: PurifiedMixedState függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedState
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed state.\rA \"purified mixed state\" refers to states of the form |ψ⟩ = Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |garbageᵢ⟩ specified by a vector of\rcoefficients {\U0001D45Dᵢ}. States of this form can be reduced to mixed states ρ ≔ \U0001D45Dᵢ |\U0001D456⟩⟨\U0001D456| by tracing over the \"garbage\"\rregister (that is, a mixed state that is diagonal in the computational basis).\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: 594a1d9fa674e457ab88072ade4198283b677af6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854306"
---
# <a name="purifiedmixedstate-function"></a>PurifiedMixedState függvény

Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy olyan műveletet ad vissza, amely egy adott kevert állapot tisztítását készíti elő.
A "tisztított kevert állapot" kifejezés a következő űrlap állapotára hivatkozik: | ψ ⟩ = Σi √ PI | i ⟩ | garbagei ⟩ által meghatározott együtthatók vektora {PI}. Az űrlap állapotait vegyes állapotokra lehet csökkenteni, ρ ≔ PI | i ⟩ ⟨ i | a "Garbage" regiszter (azaz a számítási alapon átlós, kevert állapot) alapján történő nyomkövetéssel.

További vitát a következő témakörben talál: https://arxiv.org/pdf/1805.03662.pdf?page=15 .

```qsharp
function PurifiedMixedState (targetError : Double, coefficients : Double[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a>Leírás

A Quantum ROM technikáját használja egy adott sűrűségű mátrix ábrázolására, amely állapot-előkészítési műveletként visszaküldi azt.

Különösen, ha a $N $ együtthatós $ \ alpha_j $ értéket adta meg, ez a függvény egy olyan műveletet ad vissza, amely a Quantum ROM-technikát használja a közelítés előkészítéséhez $ $ \begin{align} \tilde\rho = \ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} \end{align} $ $ vegyes állapotú $ $ \begin{align} \rho = \ sum_ {j = 0} ^ {N-1} \ frac {| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j}, \end{align} $ $, ahol minden egyes $p _j $ az adott együtthatóra való közelítés $ \ alpha_j $, például $ $ \begin{align} \left | p_j – \frac{| \ alpha_j |} {\ sum_k | \ alpha_k |} \Le \frac{\epsilon}{N} \end{align} $ $ minden $j $-hoz.

Ha átadott egy index-regisztrációt és egy, a szemetet qubits tartalmazó regisztert, amely kezdetben a $ \ket {0} \ket{00\cdots 0} állapotban van, a visszaadott művelet előkészíti mindkét regisztrációt a $ \tilde \rho $, $ $ \begin{align} \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j}\ket{\text{garbage} _j}, \end{align} $ $ értékre, amely a szemét-regisztráció alaphelyzetbe állítása és felszabadítása előtt a kívánt előkészítést a \epsilon $ értékre állítja be.

## <a name="input"></a>Bevitel

### <a name="targeterror--double"></a>targetError: [dupla](xref:microsoft.quantum.lang-ref.double)

A célként megadott hiba $ \epsilon $.


### <a name="coefficients--double"></a>együtthatók: [Double](xref:microsoft.quantum.lang-ref.double)[]

$N $ együtthatók tömbje, amely meghatározza az alapul szolgáló állapotok valószínűségét.
A $-\ alpha_j $ negatív számot a rendszer pozitív $ | \ alpha_j | $ értékűre fogja kezelni.



## <a name="output--mixedstatepreparation"></a>Kimenet: [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)

Egy művelet, amely a $ \tilde \rho $-t előkészíti a közös indexre és a szemét-regisztrációra.

## <a name="example"></a>Példa

A következő kódrészlet felkészíti a $3 $-qubit állapotot $ \rho = \ sum_ {j = 0} ^ {4} \frac{| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} $, ahol $ \vec\alpha = (1.0, 2,0, 3,0, 4,0, 5,0) $, és a célként megadott hiba a következő {-3} : $10 ^ $:

```qsharp
let coefficients = [1.0, 2.0, 3.0, 4.0, 5.0];
let targetError = 1e-3;
let purifiedState = PurifiedMixedState(targetError, coefficients);
using (indexRegister = Qubit[purifiedState::Requirements::NIndexQubits]) {
    using (garbageRegister = Qubit[purifiedState::Requirements::NGarbageQubits]) {
        purifiedState::Prepare(LittleEndian(indexRegister), new Qubit[0], garbageRegister);
    }
}
```

## <a name="remarks"></a>Megjegyzések

Az ehhez a művelethez megadott együtthatók az 1 normát követően normalizálva vannak, így az együtthatók mindig az érvényes kategorikus valószínűségi eloszlás leírásának tekintendők.

## <a name="references"></a>Hivatkozások

- Elektronikus spektrumok kódolása a kvantum-áramkörökben a lineáris T komplexitás Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, fahamvas McClean, Alexandru Paleer, Austin Fowler, Hartmut neven https://arxiv.org/abs/1805.03662

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. előkészítés. PurifiedMixedStateWithData](xref:Microsoft.Quantum.Preparation.PurifiedMixedStateWithData)