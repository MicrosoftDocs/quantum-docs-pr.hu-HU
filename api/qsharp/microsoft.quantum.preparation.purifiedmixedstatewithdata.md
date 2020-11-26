---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateWithData
title: PurifiedMixedStateWithData függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateWithData
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed\rstate, entangled with a register representing a given collection of data.\rA \"purified mixed state with data\" refers to a state of the form Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |\U0001D465ᵢ⟩ |garbageᵢ⟩,\rwhere each \U0001D465ᵢ is a bitstring encoding additional data associated with the register |\U0001D456⟩.\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: c89ee8f5df58e5d6b154b67d2b39db208bc8a215
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229953"
---
# <a name="purifiedmixedstatewithdata-function"></a>PurifiedMixedStateWithData függvény

Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy olyan műveletet ad vissza, amely egy adott kevert állapot megtisztítását készíti elő, amely egy adott adatgyűjteményt jelképező regiszterrel van összekeverve.
A "tisztított kevert állapot az adatmennyiséggel" kifejezés az űrlap Σi √ PI | i ⟩ | XI ⟩ | garbagei ⟩, ahol minden XI egy bitstring-kódolással kapcsolatos további, a regisztrációhoz | i ⟩.

További vitát a következő témakörben talál: https://arxiv.org/pdf/1805.03662.pdf?page=15 .

```qsharp
function PurifiedMixedStateWithData (targetError : Double, coefficients : (Double, Bool[])[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a>Leírás

A Quantum ROM technikáját használja egy adott sűrűségű mátrix ábrázolására, amely állapot-előkészítési műveletként visszaküldi azt.

Különösen a $N $ együtthatók $ \ alpha_j $, valamint az _egyes együtthatókkal társított $ \vec{x} j $ bitstring. Ez a függvény egy olyan műveletet ad vissza, amely a Quantum ROM technikát használja a közelítés előkészítéséhez $ $ \begin{align} \tilde\rho = \sum_{j = 0} ^ {N-1} p_j \ket{j}\bra{j} \otimes \ket{\vec{x} _j} \bra{\vec{x}_j} \end{align} $ $ of the Mixed State $ $ \begin{align} \rho = \sum_{j = 0} ^ {N-1} \ frac {| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} \otimes \ket{\vec{x} _j} \bra{\vec{x} _j}, \end{align} $ $, ahol minden egyes $p _j $ az adott együtthatóra való közelítés $ \ alpha_j $, például $ $ \begin{align} \left | p_j – \frac{| \ alpha_j |} {\ sum_k | \ alpha_k |} \Le \frac{\epsilon}{N} \end{align} $ $ minden $j $-hoz.

Ha átadott egy index-regisztrációt és egy, a szemetet qubits tartalmazó regisztert, amely kezdetben a $ \ket {0} \ket{00\cdots 0} állapotban van, a visszaadott művelet előkészíti mindkét regisztrációt a $ \tilde \rho $, $ $ \begin{align} \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j} \ket{\vec{x} _j} \ket{\text{garbage} _j}, \end{align} $ $ értékre, amely a szemét-regisztráció alaphelyzetbe állítása és felszabadítása előtt a kívánt előkészítést a $ \epsilon $ értékre állítja be.

## <a name="input"></a>Bevitel

### <a name="targeterror--double"></a>targetError: [dupla](xref:microsoft.quantum.lang-ref.double)

A célként megadott hiba $ \epsilon $.


### <a name="coefficients--doublebool"></a>együtthatók: ([Double](xref:microsoft.quantum.lang-ref.double),[bool](xref:microsoft.quantum.lang-ref.bool)[]) []

$N $ együtthatók tömbje, amely az egyes együtthatókkal társított bitstring $ \vec{x} _j $-t határozza meg.
A $-\ alpha_j $ negatív számot a rendszer pozitív $ | \ alpha_j | $ értékűre fogja kezelni.



## <a name="output--mixedstatepreparation"></a>Kimenet: [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)

Egy művelet, amely a $ \tilde \rho $-t előkészíti a közös indexre és a szemét-regisztrációra.

## <a name="remarks"></a>Megjegyzések

Az ehhez a művelethez megadott együtthatók az 1 normát követően normalizálva vannak, így az együtthatók mindig az érvényes kategorikus valószínűségi eloszlás leírásának tekintendők.

## <a name="references"></a>Hivatkozások

- Elektronikus spektrumok kódolása a kvantum-áramkörökben a lineáris T komplexitás Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, fahamvas McClean, Alexandru Paleer, Austin Fowler, Hartmut neven https://arxiv.org/abs/1805.03662

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. előkészítés. PurifiedMixedState](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)