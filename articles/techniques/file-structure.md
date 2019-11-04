---
title: Quantum Development Techniques – bevezetés | Microsoft Docs
description: Quantum Development-technikák bemutatása
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 9c266fe16b8e2a265d91a99f8574a6acfcf03160
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183250"
---
# <a name="what-is-q"></a>Mi az a Q#? #

A Q # egy méretezhető, több paradigma, tartományszintű programozási nyelv a kvantum-számítástechnika számára. A Q # egy Quantum programozási nyelv, amelynek segítségével leírható, hogy a rendszer hogyan hajtja végre az utasításokat a kvantum-gépeken. Azok a gépek, amelyek megcélozható a szimulátorok és a tényleges kvantum-hardver között. A Q # méretezhető: egyszerű bemutató programokat írhat, például a teleportot, amely néhány qubits fut, de támogatja a nagyméretű és kifinomult programok írását is, mint például az összetett molekulák szimulálása, amelyeknek több millió qubits kell lennie. Annak ellenére, hogy a nagyméretű fizikai gépek továbbra is a jövőben vannak, a Q # lehetővé teszi a programozók számára, hogy az összetett kvantum-algoritmusokat. Mi több, a Q # támogatja a különböző feladatokat, például a hibakeresést, a profilkészítést, az erőforrás-becslést és bizonyos speciális célú szimulációkat méretezhető módon. 

Technikai szempontból a kvantum-program a klasszikus függvények egy adott készletének tekinthető, amely a meghívottak szerint a kvantum-áramköröket eredményezi. Ennek a nézetnek a fontos következménye, hogy a Q #-ban írt program nem qubits magukat közvetlenül, hanem azt is leírja, hogyan kommunikál a klasszikus vezérlő számítógépek a qubits.
A tervezés szerint a Q # így nem határozza meg a kvantum-állapotokat vagy a kvantummechanika egyéb tulajdonságait közvetlenül, hanem a nyelvben definiált különböző alrutinok műveletén keresztül.
Vegyük például a következőt: $ \ket{+} = \left (\ket{0} + \ket{1}\right)/\sqrt{2}$ a [Quantum Computing Concepts](xref:microsoft.quantum.concepts.intro) útmutatójában.
Ha ezt az állapotot Q #-ban szeretné felkészíteni, a qubits a $ \ket{0}$ állapotban inicializálja, és hogy a $ \ket{+} = H\ket{0}$, ahol $H $ a Hadamard-átalakító:

```qsharp
using (qubit = Qubit()) {
    // At this point, qubit is in the state |0〉.
    H(qubit);
    // We've now applied H, such that our qubit is in H|0〉 = |+〉, as we wanted.
}
```
## <a name="q-tranformations-of-quantum-states"></a>Q # tranformations Quantum állapotok

Fontos, hogy a fenti program írásakor nem kifejezetten a Q #-on belüli állapotra hivatkozunk, hanem azt is, hogy a program hogyan *alakította át* az állapotot.
Így a Graphics shader program az egyes csúcspontokra való átalakítások leírását is hasonlítja össze, a Q #-ban lévő Quantum program pedig a kvantum-állapotokra gyűjti az átalakításokat.
Ez lehetővé teszi számunkra, hogy teljesen függetlenek legyenek attól, hogy milyen kvantum-állapotot biztosítanak *az egyes* célszámítógépeken, ami különböző értelmezésekkel rendelkezhet a gépen. 

A Q # program szemszögéből a qubit egy teljesen átlátszatlan hivatkozás a célszámítógép belső struktúrájára.
A Q # programnak nincs lehetősége arra, hogy betekintést végezzen egy qubit, annak ábrázolását a célszámítógépen, vagy akár ugyanazt a qubit, mint a program által elérhető többi qubit.
Ehelyett a program olyan műveleteket hívhat meg, mint például a `Measure`, hogy qubit az információkat, és olyan műveleteket hívjon fel, mint például a `X` és a `H`, hogy egy qubit állapotára cselekedjenek.
Ezeknek a műveleteknek nincs belső definíciója a nyelven belül, és csak az adott Q # program futtatására használt célszámítógép végzi el a konkrét műveleteket.
A Q # program újrakombinálja ezeket a műveleteket a célszámítógép által meghatározott módon, hogy új, magasabb szintű műveleteket hozzon létre a kvantum-számításokhoz.
Így a Q # megkönnyíti a kvantum-és hibrid kvantum-klasszikus algoritmusok kiépítését, ugyanakkor általános megoldást is biztosít a célszámítógép vagy a szimulátor struktúrájára vonatkozóan.

## <a name="q-operations-and-functions"></a>Q # műveletek és függvények

Konkrétan a Q # program egy vagy több *műveletből*áll, egy vagy több *függvényből*és egy felhasználó által definiált típusból. A műveletek a kvantum-gép állapotának átalakítását írják le, és a Q # programok legalapvetőbb építőelemei. A Q # által meghatározott minden művelet hívhat tetszőleges számú egyéb műveletet, beleértve a célszámítógép által megvalósított beépített *belső* műveleteket is.
A fordítás során az egyes műveletek .NET-osztályként jelennek meg, amely megadható a célszámítógép számára.

A műveletekkel szemben a függvények a tisztán klasszikus viselkedés leírására szolgálnak, és nem gyakorolnak semmilyen hatást a klasszikus számítástechnikai értékek mellett. A Q # egy erősen gépelt nyelv, amely beépített primitív típusokat és a felhasználó által definiált típusok támogatását is tartalmazza. 

Az útmutató további részében azt fogjuk látni, hogyan használhatunk különböző nyelvi fogalmakat és szerkezeteket a műveletek, függvények és típusok alapvető építőelemei segítségével. 

## <a name="structure-of-q-source-files"></a>A Q # forrásfájlok szerkezete

Minimálisan a Q # forrásfájl egy *névtér-deklarációból*áll, amely egy olyan .net-névteret határoz meg, amely a forrásfájl definícióit fogja tartalmazni.
A más Q # forrásfájlokat és könyvtárakat tartalmazó definíciók a `open` utasítás használatával is felvehetők.
Az alapvető kapukat meghatározó műveletek többsége például a <xref:microsoft.quantum.intrinsic> névtérben van meghatározva.
Ahhoz, hogy ez elérhető legyen a kód számára, egyszerűen `open` a névteret az egyes fájlok tetején:

```qsharp
namespace Example {
    open Microsoft.Quantum.Intrinsic;

    // ...
}
```

A névtéren belül minden Q # forrásfájl meghatározhatja a *műveletek*, a *függvények*és a *felhasználó által definiált típusok*tetszőleges kombinációját.
A szakasz további részében bemutatjuk, hogyan használhatók a gyakorlatban a hasznos kvantum-programok használatával.
