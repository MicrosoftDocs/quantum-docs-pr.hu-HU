---
title: Jordánia – Wigner-képviselet
description: Ismerkedjen meg a Jordan-Wigner képviselettel, amely az Hamilton-operátorokat a kvantum-számítógépeken könnyebben megvalósítható, egységes mátrixokra képezi le.
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.jordanwigner
ms.openlocfilehash: 17cb473c6d33e3356d5da886f47985c3828d4d1f
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275096"
---
# <a name="jordan-wigner-representation"></a>Jordánia – Wigner-képviselet

Míg a második kvantálási Hamiltonians a $a ^ \dagger $ (létrehozás) és a $a $ (megsemmisítés) szempontjából jól reprezentálva vannak, ezek a műveletek nem alapvető műveletek a kvantum-számítógépeken.
Ennek eredményeképpen, ha azt szeretnénk, hogy egy kvantum-számítógépen Implementáljuk azokat, az operátorokat a kvantum-számítógépeken megvalósítható, egységes mátrixokhoz kell rendelni.
A Jordan – Wigner ábrázolás egy ilyen térképet biztosít.
Azonban mások, például a Bravyi – Kitaev képviselet is létezik, és saját relatív előnyökkel és hátrányokkal rendelkeznek.
A Jordan-Wigner ábrázolás legfőbb előnye az egyszerűsége.

A Jordan-Wigner ábrázolása egyenesen a származtatás felé.
Ne felejtse el, hogy a $ \ket {0} _j $ állapot azt jelenti, hogy a spin orbitális $j $ üres, és a $ \ket {1} _j $ érték azt jelenti, hogy foglalt.
Ez azt jelenti, hogy a qubits természetes módon képes tárolni egy adott spin-orbitális megszállását.
Ezután $a ^ \ dagger_j \ket {0} _j = \ket {1} _j $ és $a ^ \ dagger_j \ket {1} _j = $0.
Könnyen ellenőrizhető, hogy \begin{align}-e a következő: ^ \ dagger_j &= \begin{bmatrix}0 & 0 \\ \ 1 &0 \end{bmatrix} = \frac{X_j-iY_j} {2} , \nonumber \\ \\ a_j &= \begin{bmatrix}0 & 1 \\ \ 0 &0 \end{bmatrix} = \frac{X_j + iY_j} {2} , \end{align}, ahol $X _j $ és $Y _j $ a Qubit $X $-on működő Pauli-$Y $ és-$j $ operátorok.

>[!NOTE]
> A Q # a $ \ket {0} $ állapot a $Z $ operátor + 1 eigenstate jelöli. A \ket $ fizika egyes területein {0} az alacsony energiájú terepi állapot, így az $Z $ operátor-1 eigenstate. Ezért előfordulhat, hogy egyes képletek eltérhetnek a népszerű irodalomtól.

A kémia könyvtárában a $ \ket $ értéket használjuk a nem {0} foglalt spin-Orbit jelölésére.
Ez azt mutatja, hogy egyetlen spin-orbitális esetében könnyen ábrázolható a létrehozási és a megsemmisítési operátor a kvantum-számítógépek által értelmezhető, egységes mátrixok tekintetében.
Vegye figyelembe, hogy míg a $X $ és a $Y $ egységes $a ^ \dagger $ és $a $ nem.
Később látni fogjuk, hogy ez nem jelent kihívást a szimulációhoz.

Egy olyan probléma, amely továbbra is az, hogy a fenti szerkezet egyetlen spin-pályára működik, a két vagy több spin-pályával rendelkező rendszerek esetében sikertelen.
Mivel a Fermions antisymmetic, tudjuk, hogy $a ^ \ dagger_j a ^ \ dagger_k =-a ^ \ dagger_k a ^ \ dagger_j $ értéket minden $j $ és $k $ esetén.
Azonban $ $ \left (\frac{X_j-iY_j} {2} \right) \left (\frac{X_k-iY_k} {2} \right) = \left (\frac{X_k-iY_k} {2} \right) \left (\frac{X_j-iY_j} {2} \right).
$ $ Más szóval a két létrehozási operátor a szükséges módon nem végzi el az átjárást.
Ez egy egyszerű, de nem elegáns módon is orvosolható.
A javítás azt jelzi, hogy a Pauli-operátorok természetesen nem ingázik.
Különösen $XZ =-ZX $ és $YZ =-a ()
Így a interspersing $Z $ operátorokat a kezelő kiépítéséhez, a megfelelő anti-ingázást emulálni tudjuk.
A teljes konstrukció a következő: 

\begin{align} a ^ \ dagger_1 &= \left (\frac{X-iY} {2} \right) \otimes 1 \otimes 1 \otimes 1 \otimes \cdots \otimes 1, \\ \\ egy ^ \ dagger_2 &= Z\otimes\left (\frac{X-iY} {2} \right) \otimes 1 \ otimes 1 \otimes \cdots \otimes 1, \\ \\ a ^ \ dagger_3 &= Z\otimes Z\otimes \left (\frac{X-iY} {2} \right) \otimes 1 \otimes \cdots \otimes 1, \\ \\ & \Vdots \\ \\ a ^ \ dagger_N &= Z\otimes Z\otimes Z\otimes Z \otimes \cdots \otimes Z\otimes \left (\frac{X-iY} {2} \right). \label{EQ: JW} \end{align}

Azt is érdemes kipróbálni, hogy a szám operátorok, $n _j $, a Pauli-operátorok alapján legyenek kifejezve.
Szerencsére a $Z $ operátorok (más néven Jordan-Wigner karakterláncok) karakterláncai megszakítják ezt a helyettesítést.
Ennek elvégzése után (és emlékeztetve arra, hogy $X _jY_j = iZ_j $), \begin{Equation} n_j = a ^ \ dagger_j a_j = \frac{(1-Z_j)} {2} .
\end{equation}


## <a name="constructing-hamiltonians-in-jordan-wigner-representation"></a>Hamiltonians építése Jordániában – Wigner képviselet

Miután megtettük a Hamilton Wigner-képviseletét, a Pauli-operátorok összegének lefordításával egyenesen továbbítjuk.
Az egyik egyszerűen le kell cserélnie a Fermionic Hamilton összes $a ^ \dagger $ és $a $ operátorát a fent megadott Pauli-operátorok karakterláncával.
Ha az egyik végrehajtja ezt a helyettesítést, a Hamilton belül csak öt osztály szerepel.
Ez az öt osztály a $p, a q $ és a $p, a q, az r, a s $ lehetőségeknek az egytörzsű és a kéttörzsű kifejezésekben való kiválasztásának különböző módjaihoz tartozik a Hamilton.
Ez az öt osztály olyan esetben, amikor $p>q>r>s $ és valós értékű orbitális

\begin{align} h_ {PP} a_p ^ \dagger a_p &= \ sum_p \frac{h_ {PP}} {2} (1-Z_p) \\ \\ h_ {pq} (a_p ^ \dagger a_q + a ^ \ dagger_q a_p) &= \frac{h_ {pq}} {2} \left (\ prod_ {j = q + 1} ^ {p-1} Z_j \right) \left (X_pX_q + Y_pY_q \right) \\ \\ h_ {pqqp} n_p n_q &= \frac{h_ {pqqp}} {4} \left (1-Z_p-Z_q + Z_pZ_q \right) \\ \\ H_ {pqqr} &= \frac{h_ {pqqr}} {2} \left (\ prod_ {j = r + 1} ^ {p-1} Z_j \right) \left (X_pX_r + Y_pY_r \right) \left (\frac{1-Z_q} {2} \right) \\ \\ H_ {pqrs} &= \frac{h_ {pqrs}} {8} \ prod_ {j = s + 1} ^ {r-1} Z_j \ prod_ {k = q + 1} ^ {p-1} Z_k \Big (XXXX-XXYY + XYXY\nonumber \\ \\ & \qquad\qquad\qquad\qquad\qquad + YXXY + YXYX-YYXX\nonumber \\ \\ & \qquad\qquad\qquad\qquad\qquad + XYYX + YYYY\Big) \end{align}

Az ilyen Hamiltonians csak akkor hozható létre, ha csak ezeket a helyettesítő szabályokat igényli, így a nagy molekulák esetében nem valósítható meg, amelyek több millió Hamilton-kifejezésből állhatnak.
Egy másik lehetőség, hogy automatikusan létrehozza az `JordanWignerEncoding` adott `FermionHamiltonian` Hamilton.

```csharp
    // We load the namespace containing fermion and Pauli objects. 
    using Microsoft.Quantum.Chemistry.Fermion;
    using Microsoft.Quantum.Chemistry.Pauli;
    
    // We create an example `FermionHamiltonian` instance.
    var fermionHamiltonian = new FermionHamiltonian();

    // We convert this Fermion Hamiltonian to a Jordan-Wigner representation.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(QubitEncoding.JordanWigner);
```

Ha a Hamiltonians ezen az űrlapon vannak kiépítve, a Quantum szimulációs algoritmusok egy gazdagépét használva lefordíthatja a $e ^ {-iHt} $ által generált Dynamics elemet az elemi kapuk sorozatában (néhány felhasználó által definiált hibatűréssel).
Megbeszéljük a Quantum szimulációs, qubitization és Trotter – Suzuki-képletek két legnépszerűbb módszerét az algoritmusos dokumentációban. Mindkét módszer megvalósítását a Hamilton szimulációs könyvtárában biztosítjuk.
