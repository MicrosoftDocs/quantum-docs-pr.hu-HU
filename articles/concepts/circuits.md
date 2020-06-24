---
title: Kvantumkörök
description: Megtudhatja, hogyan ábrázolhat egyszerű és összetett kvantum-műveleteket a Quantum Circuit-diagramok használatával.
author: QuantumWriter
uid: microsoft.quantum.concepts.circuits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- $
- $
- $
- $
- $
- $
- '\cdots'
- bmatrix
- '\ddots'
- '\equiv'
- '\sum'
- '\begin'
- '\end'
- '\sqrt'
- '\otimes'
- '{'
- '}'
- '\text'
- '\phi'
- '\kappa'
- '\psi'
- '\alpha'
- '\beta'
- '\gamma'
- '\delta'
- '\omega'
- '\bra'
- '\ket'
- '\boldone'
- '\\\\'
- '\\'
- =
- '\frac'
- '\text'
- '\mapsto'
- '\dagger'
- '\to'
- "\begin{cases}"
- "\end{cases}"
- '\operatorname'
- '\braket'
- '\id'
- '\expect'
- '\defeq'
- '\variance'
- '\dd'
- '&'
- "\begin{align}"
- "\end{align}"
- '\Lambda'
- '\lambda'
- '\Omega'
- '\mathrm'
- '\left'
- '\right'
- '\qquad'
- '\times'
- '\big'
- '\langle'
- '\rangle'
- '\bigg'
- '\Big'
- '|'
- '\mathbb'
- '\vec'
- '\in'
- '\texttt'
- '\ne'
- <
- '>'
- '\leq'
- '\geq'
- ~~
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- '\_'
ms.openlocfilehash: 59c32928ddc9252009ad101a3cf3ac33f4968e28
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269609"
---
# <a name="quantum-circuits"></a>Kvantum-áramkörök
Vegyünk egy pillanatra az egységes átalakítás $ \text { cnem} _ {01 } (H \otimes 1) $ értéket.
Ez a kapui sorozat alapvető jelentőséggel bír a kvantum-számítástechnika szempontjából, mivel a két qubit állapotot hozza létre:

$ $ \mathrm{CNOT}_{01 } (H \otimes 1) \ket{00 } = \frac{1 } {\sqrt{2 } } \left (\ket{00 } + \ket{11 } \right), $ $

Az ezzel vagy nagyobb bonyolultsággal rendelkező műveletek a kvantum-algoritmusokban és a kvantum-hibák kijavításában mindenütt elérhetők, ezért nagy mértékű feltételnek kell lennie, hogy a vizualizációk *egy egyszerű*metódust használjanak.
A maximálisan kusza kvantum-állapot előkészítésének áramköri diagramja a következő:

<!--- ![](.\media\1.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![Áramköri diagram maximálisan összekeverhető kétqubit állapothoz](~/media/1.svg)

## <a name="quantum-circuit-diagram-conventions"></a>A Quantum Circuit diagram konvenciói
A kvantum-műveletek vizuális nyelve könnyebben emészthető, mint a kvantum-kör kifejezésére vonatkozó konvenciók megismerése.
Az alábbi konvenciókat tekintjük át.

Egy áramköri diagramon minden egyes folytonos vonal egy qubit vagy általánosabban qubit-regisztrációt ábrázol.
Az egyezmény szerint a felső sor a $0 $ -es qubit-regisztráció, a maradék pedig szekvenciálisan van megjelölve. A fenti példában szereplő áramkör két qubits (vagy egy qubit álló, egymással egyenértékű két regiszterből áll) való működésként van ábrázolva.
Az egy vagy több qubit-regiszteren eljáró kapuk mezőként vannak kijelölve.
Például a szimbólum

<!--- ![](.\media\2.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![Egy qubit-regiszteren működő Hadamard művelet szimbóluma](~/media/2.svg)

egy qubit-regisztráción alapuló [Hadamard](xref:microsoft.quantum.intrinsic.h) művelet.

A Quantum Gates kronológiai sorrendben vannak rendezve a bal szélső kapuval, amelyet a kapu először alkalmaz a qubits.
Más szóval, ha a vezetékeket a kvantum-állapot tárolásával ábrázolja, a vezetékek a diagram minden kapuján balról jobbra helyezik a kvantum-állapotot.
Azaz 

<!--- ![](.\media\3.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![A Quantum Gates diagramja balról jobbra van alkalmazva](~/media/3.svg)

az egységes mátrix $CBA $ .
A mátrix szorzása engedelmeskedik a szemközti konvenciónak: a jobb oldali mátrix először van alkalmazva. A Quantum Circuit-diagramoknál azonban először a bal szélső kaput alkalmazza a rendszer.
Ez a különbség időnként zavart eredményezhet, ezért fontos megjegyezni, hogy ez a különbség a lineáris algebrai jelölés és a kvantum-áramköri diagramok között jelentős.

## <a name="inputs-and-outputs-of-quantum-circuits"></a>A kvantum-áramkörök bemenetei és kimenetei
A megadott összes korábbi példa pontosan ugyanazokat a vezetékeket (qubits) adta hozzá a kvantum-kapuhoz, mint a kvantum-kapuból kimenő vezetékek száma.
Előfordulhat, hogy először úgy tűnik, hogy a kvantum-áramkörök több vagy kevesebb kimenettel rendelkeznek, mint általában a bemenetek.
Ez azonban nem lehetséges, mivel az összes kvantum-művelet, a mérték mentése, egységes és ezért reverzibilis.
Ha nem azonos számú kimenet szerepel a bemenetekben, nem vonhatók vissza, és így nem egységesek, ami ellentmond.
Ebben az esetben az áramköri diagramban rajzolt bármely mezőnek pontosan ugyanannyi drótot kell megadnia, mint kilép.

A multi-qubit áramköri diagramok hasonló konvenciókat követnek az qubit is.
Példaként meghatározhatunk egy kétqubites, egységes műveleti $B $ a $ (H S \otimes X) $ értékre, és az áramkört egyenértékűként kell kifejezni

<!--- ![](.\media\4.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![Kétqubitű egységes művelet áramköri diagramja](~/media/4.svg)

Azt is megtekintheti $B, hogy a $ művelet egy qubit-regisztráción alapul, és nem 2 1-qubit regisztrálja az áramkört használó környezettől függően. Az absztrakt áramköri diagramok leghasznosabb tulajdonsága az, hogy lehetővé teszik, hogy a bonyolult kvantum-algoritmusokat magas szinten írják le anélkül, hogy le kellene őket állítani az alapvető kapuk számára.
Ez azt jelenti, hogy a nagyméretű kvantum-algoritmusok adatforgalmával kapcsolatban nem kell megismernie az algoritmus működésével kapcsolatos összes alrutin részleteit.

## <a name="controlled-gates"></a>Vezérelt kapuk
A multi-qubit Quantum Circuit-diagramokba beépített másik összeállítás vezérli.
Egy olyan kvantum-vezérelt kapu művelete, amely a $ \Lambda (G) $ értéket jelöli, ahol egyetlen qubit érték vezérli a $G alkalmazását $ , a következő példa a termék állapotának bevitele: \Lambda (g) (\alpha \ket{0 } + \beta \ket{1 } ) \ket { \psi } = \alpha \ket{0 } \ket { \psi } + \beta \ket{1 } G \ket { \psi } $.
Ez azt jelenti, hogy az ellenőrzött kapu $G $ a $ \psi-t tartalmazó regisztrációra vonatkozik, $ Ha pedig csak akkor, ha a vezérlő qubit $1 értéket vesz igénybe $ .
Általánosságban leírjuk, hogy milyen ellenőrzött műveleteket kell elvégeznie az áramköri diagramokban

<!--- ![](.\media\5.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![Egy megfelelően vezérelt kapu áramköri diagramja](~/media/5.svg)

Itt a fekete kör azt a kvantum-bitet jelöli, amelyen a kapu vezérelhető, és a vertikális huzal azt jelöli, hogy a vezérlő qubit a $1 értéket veszi figyelembe $ .
Azoknál a speciális esetekben, ahol a $G = X $ és $G = Z a $ kapuk ellenőrzött verziójának leírásához bevezetjük a következő jelölést (vegye figyelembe, hogy a vezérelt X kapu a [$CNOT $ Gate](xref:microsoft.quantum.intrinsic.cnot)):

<!--- ![](.\media\6.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![Irányított kapuk speciális eseteinek áramköri diagramja](~/media/6.svg)

A Q # olyan metódusokat biztosít, amelyek automatikusan előállítják egy művelet ellenőrzött verzióját, amely elmenti a programozótól, hogy ezeket a műveleteket manuálisan kell megadnia. Alább látható egy példa:

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl { // Auto-generate the controlled specialization of the operation
    H(qubit);
}
```

## <a name="measurement-operator"></a>Mérési operátor
Az áramköri diagramok megjelenítésének hátralévő művelete a mérés.
A mérés qubit regisztrálja, méri azt, és az eredményt klasszikus információként adja vissza.
Egy mérőszám szimbóluma egy mérési műveletet jelöl, és mindig bemenetként fogadja a qubit-regisztrációt (ezt egy folytonos vonal jelöli), és a klasszikus információ kimeneteit (egy dupla vonallal jelöli).
Az ilyen alhálózatok például a következőkre hasonlítanak:

<!--- ![](.\media\7.svg) ---->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![Mérési műveletet jelölő szimbólum](~/media/7.svg)

A Q # erre a célra alkalmazza a [mérték kezelőjét](xref:microsoft.quantum.intrinsic.measure) .
További információt a [mérések című szakaszban](xref:microsoft.quantum.libraries.standard.prelude#measurements) talál.

Hasonlóképpen, az aláramkör

<!--- ![](.\media\8.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![Ellenőrzött műveletet jelképező áramköri diagram](~/media/8.svg)

egy klasszikusan vezérelt kaput biztosít, ahol $ a $G a klasszikus vezérlési bit $1 értékre van alkalmazva $ .

## <a name="teleportation-circuit-diagram"></a>Teleportáló áramköri diagram
A kvantum-teleportáció talán a legjobb kvantum-algoritmus ezen összetevők szemléltetésére.
Megtudhatja, hogy a megfelelő [Quantum Kata](xref:microsoft.quantum.overview.katas) -alapú kvantum-teleportáció hogyan helyezheti át az információkat a kvantum-számítógépeken (vagy akár a kvantum-hálózaton lévő távoli Quantum számítógépek között) a felakadás és a mérés használatával.
Érdekes, hogy valójában képes a kvantum állapotának áthelyezésére, azaz egy adott qubit értékének egy qubit a másikra való átállítására, anélkül, hogy a qubit értékének megtudhatja.
Erre azért van szükség, hogy a protokoll a Quantum Mechanics törvényeinek megfelelően működjön.
A kvantum-teleportáció áramkört az alábbi szakasz ismerteti. az áramkör megjegyzésekkel ellátott verzióját is megadja, hogy bemutassa a kvantum-áramkör beolvasásának módját.

<!--- ![](.\media\tp2.svg){ width=50% } --->
![Quantum teleportáció-áramkör](~/media/tp2.svg)
