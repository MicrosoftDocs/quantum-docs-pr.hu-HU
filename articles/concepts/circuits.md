---
title: Kvantum-áramkörök | Microsoft Docs
description: Kvantum-áramkörök
author: QuantumWriter
uid: microsoft.quantum.concepts.circuits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 7c2afa58fd70d893529cf794ae07df480466aaec
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/31/2019
ms.locfileid: "73210643"
---
# <a name="quantum-circuits"></a>Kvantum-áramkörök
Vegyünk egy pillanatra az egységes átalakítás $ \text{CNEM} _{01}(H\otimes 1) $ értéket.
Ez a kapui sorozat alapvető jelentőséggel bír a kvantum-számítástechnika szempontjából, mivel a két qubit állapotot hozza létre:

$ $ \mathrm{CNOT}_{01}(H\otimes 1) \ket{00} = \frac{1}{\sqrt{2}} \left (\ket{00} + \ket{11} \right), $ $

Az ezzel vagy nagyobb bonyolultsággal rendelkező műveletek a kvantum-algoritmusokban és a kvantum-hibák kijavításában mindenütt elérhetők, ezért nagy mértékű feltételnek kell lennie, hogy a vizualizációk *egy egyszerű*metódust használjanak.
A maximálisan kusza kvantum-állapot előkészítésének áramköri diagramja a következő:

<!--- ![](.\media\1.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/Concepts1.png)

## <a name="quantum-circuit-diagram-conventions"></a>A Quantum Circuit diagram konvenciói
A kvantum-műveletek vizuális nyelve könnyebben emészthető, mint a kvantum-kör kifejezésére vonatkozó konvenciók megismerése.
Az alábbi konvenciókat tekintjük át.

Egy áramköri diagramon minden egyes folytonos vonal egy qubit vagy általánosabban qubit-regisztrációt ábrázol.
Az egyezmény szerint a legfelső sor a $0 $ qubit-regisztráció, a maradék pedig szekvenciálisan van megjelölve. A fenti példában szereplő áramkör két qubits (vagy egy qubit álló, egymással egyenértékű két regiszterből áll) való működésként van ábrázolva.
Az egy vagy több qubit-regiszteren eljáró kapuk mezőként vannak kijelölve.
Például a szimbólum

<!--- ![](.\media\2.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_2.png)

a [Hadamard](xref:microsoft.quantum.primitive.h) -kapu egy qubit-regiszteren működik.

A Quantum Gates kronológiai sorrendben vannak rendezve a bal szélső kapuval, amelyet a kapu először alkalmaz a qubits.
Más szóval, ha a vezetékeket a kvantum-állapot tárolásával ábrázolja, a vezetékek a diagram minden kapuján balról jobbra helyezik a kvantum-állapotot.
Azaz 

<!--- ![](.\media\3.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_3.png)

az egységes mátrix $CBA $.
A mátrix szorzása engedelmeskedik a szemközti konvenciónak: a jobb oldali mátrix először van alkalmazva. A Quantum Circuit-diagramoknál azonban először a bal szélső kaput alkalmazza a rendszer.
Ez a különbség időnként zavart eredményezhet, ezért fontos megjegyezni, hogy ez a különbség a lineáris algebrai jelölés és a kvantum-áramköri diagramok között jelentős.

## <a name="inputs-and-outputs-of-quantum-circuits"></a>A kvantum-áramkörök bemenetei és kimenetei
A megadott összes korábbi példa pontosan ugyanazokat a vezetékeket (qubits) adta hozzá a kvantum-kapuhoz, mint a kvantum-kapuból kimenő vezetékek száma.
Előfordulhat, hogy először úgy tűnik, hogy a kvantum-áramkörök több vagy kevesebb kimenettel rendelkeznek, mint általában a bemenetek.
Ez azonban nem lehetséges, mivel az összes kvantum-művelet, a mérték mentése, egységes és ezért reverzibilis.
Ha nem azonos számú kimenet szerepel a bemenetekben, nem vonhatók vissza, és így nem egységesek, ami ellentmond.
Ebben az esetben az áramköri diagramban rajzolt bármely mezőnek pontosan ugyanannyi drótot kell megadnia, mint kilép.

A multi-qubit áramköri diagramok hasonló konvenciókat követnek az qubit is.
Példaként meghatározhatunk egy kétqubites, egységes műveletet $B $-t a $ (H S\otimes X) $ értékre, és az áramkört egyenértékűként kell kifejezni

<!--- ![](.\media\4.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_4.png)

$B $-t úgy is megtekintheti, mintha egy qubit-regisztráción alapuló művelettel rendelkezik, és nem 2 1-qubit regisztrálja az áramkört használó környezettől függően. Az absztrakt áramköri diagramok leghasznosabb tulajdonsága az, hogy lehetővé teszik, hogy a bonyolult kvantum-algoritmusokat magas szinten írják le anélkül, hogy le kellene őket állítani az alapvető kapuk számára.
Ez azt jelenti, hogy a nagyméretű kvantum-algoritmusok adatforgalmával kapcsolatban nem kell megismernie az algoritmus működésével kapcsolatos összes alrutin részleteit.

## <a name="controlled-gates"></a>Vezérelt kapuk
A multi-qubit Quantum Circuit-diagramokba beépített másik összeállítás vezérli.
Egy olyan kvantum-vezérelt kapu művelete, amely a $ \Lambda (G) $ értéket jelöli, ahol egyetlen qubit érték vezérli $G $-t, a termék állapotára vonatkozó input $ \Lambda (G) következő példáját tekintheti meg (\alpha \ket{0} + \beta \ket{1}) \ket{\psi} = \alpha \ket{0} \ket{\psi} + \beta \ket{1} G\ket {\ psi} $.
Ez azt jelenti, hogy az ellenőrzött kapu $G $ értéket alkalmaz a $ \psi $-t tartalmazó regisztrációra, és csak akkor, ha a vezérlő qubit $1 $ értékű.
Általánosságban leírjuk, hogy milyen ellenőrzött műveleteket kell elvégeznie az áramköri diagramokban

<!--- ![](.\media\5.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_5.png)

Itt a fekete kör azt a kvantum-bitet jelöli, amelyen a kapu vezérelhető, és a vertikális huzal azt jelöli, hogy a vezérlő qubit a $1 $ értéket veszi figyelembe.
Azon speciális esetekben, ahol $G = X $ és $G = Z $ bevezetjük a következő jelölést a kapuk ellenőrzött verziójának leírásához (vegye figyelembe, hogy a vezérelt X Gate a [$CNOT $ Gate](xref:microsoft.quantum.primitive.cnot)):

<!--- ![](.\media\6.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_6.png)

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
![mérési áramkör](~/media/concepts_7.png)

A Q # erre a célra alkalmazza a [mérték kezelőjét](xref:microsoft.quantum.primitive.measure) .
További információt a [mérések című szakaszban](xref:microsoft.quantum.libraries.standard.prelude#measurements) talál.

Hasonlóképpen, az aláramkör

<!--- ![](.\media\8.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_8.png)

egy klasszikusan vezérelt kaput biztosít, ahol a $G $ a klasszikus vezérlési bit értéke $1 $.

## <a name="teleportation-circuit-diagram"></a>Teleportáló áramköri diagram
A [kvantum-teleportáció](xref:microsoft.quantum.techniques.puttingittogether) talán a legjobb kvantum-algoritmus ezen összetevők szemléltetésére.
A kvantum-teleportáció az a módszer, amellyel a kvantum-számítógépeken (vagy akár a kvantum-hálózaton lévő távoli kvantum-számítógépek között) is áthelyezheti az adatátvitelt a felakadás és a mérés használatával.
Érdekes, hogy valójában képes a kvantum állapotának áthelyezésére, azaz egy adott qubit értékének egy qubit a másikra való átállítására, anélkül, hogy a qubit értékének megtudhatja.
Erre azért van szükség, hogy a protokoll a Quantum Mechanics törvényeinek megfelelően működjön.
A kvantum-teleportáció áramkört az alábbi szakasz ismerteti. az áramkör megjegyzésekkel ellátott verzióját is megadja, hogy bemutassa a kvantum-áramkör beolvasásának módját.

<!--- ![](.\media\tp2.svg){ width=50% } --->
![](~/media/concepts_tp2.png)
