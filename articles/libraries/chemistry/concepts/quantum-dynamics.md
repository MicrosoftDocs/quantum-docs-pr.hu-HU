---
title: Quantum Dynamics | Microsoft Docs
description: Quantum Dynamics – elméleti dokumentumok
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.quantumdynamics
ms.openlocfilehash: 0fd27e59921fdf8429bf164c4c64cfa3b8e44160
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185341"
---
# <a name="quantum-dynamics"></a>Quantum Dynamics

A kvantum-mechanika nagyrészt a Quantum Dynamics tanulmányozása, amely arra törekszik, hogy megértse, hogyan változik az idő a kezdeti Quantum State $ \ket{\psi (0)} $ értékkel (lásd a Quantum Computing [fogalmi dokumentumait](xref:microsoft.quantum.concepts.dirac) a Dirac-jelöléssel kapcsolatos további információkért).
Pontosabban, mivel ez a kezdeti feltétel a kvantum-állapot, az evolúciós idő és a kvantum-dinamikai rendszer specifikációja, a rendszer a Quantum State $ \ket{\psi (t)} $ értéket kéri.
A kvantum-dinamika megismerése előtt hasznos lehet egy lépést visszavenni a klasszikus Dynamics szolgáltatásba, mivel betekintést nyújt arról, hogy a kvantummechanika valójában nem különbözik a klasszikus dynamicstól.

A klasszikus dinamikában tudjuk, hogy a Newton második törvénye szerint a részecskék helyzete $F (x, t) = ma = m\frac {\ NN ^ 2} {\dd t ^ 2} {x} (t) $, ahol $F (x, t) $ a Force, $m $ a Mass és $a $ a gyorsulás.
Ezután a kezdeti pozícióban $x (0) $, az Evolution Time $t $ és a részecske által feltett erők leírása alapján megtalálhatja a $x (t) $ értéket a Newton által az $x (t) $-hoz tartozó egyenletek által megadott különbözeti egyenlet megoldásával.
A haderők ily módon történő meghatározása egy kis fájdalom.
Ezért gyakran kifejezzük a haderőt a rendszer lehetséges energiája szempontjából, ami a következőt adja: US $-\partial_x V (x, t) = m \frac{\dd ^ 2} {\dd t ^ 2} {x} (t) $.
A részecskék esetében tehát a rendszer dinamikáját csak a lehetséges energia-funkció, a részecske tömege és a kialakulási idő határozza meg.

A klasszikus Dynamics esetében gyakran előfordul szélesebb nyelv, amely $F = ma $-ra esik.
Az egyik megfogalmazás, amely különösen hasznos a Quantum mechanikaban, a Hamilton mechanika.
A Hamilton-mechanika esetében a rendszer és az (általánosított) pozíciók és a Momenta teljes energiaA minden olyan információt megad, amely egy tetszőleges klasszikus objektum mozgásának leírásához szükséges.
Pontosabban, legyen $f (x, p, t) $ az általánosított pozíciók néhány funkciója $x $ és a Momenta $p $ rendszer, és hagyja $H (x, p, t) $ a Hamilton függvényt.
Ha például igénybe vesszük $f (x, p, t) = x (t) $ és $H (x, p, t) = p ^ 2 (t)/2m-V (x, t) $, akkor a newtoni Dynamics fenti esetét fogjuk helyreállítani.
Általánosságban elmondható, hogy a \begin{align} \frac{d}{DT} f & = \partial_t f-(\partial_x H\partial_p f + \partial_p H\partial_x f)\\\\ & \defeq \partial_t f + \\{f, H\\}.
a \end{align} itt $\\{f, H\\} $ néven a [Poisson-zárójelnek](https://en.wikipedia.org/wiki/Poisson_bracket) kell lennie, és a klasszikus dinamikában, a Dynamics meghatározása során játszott központi szerepkör miatt mindenütt megjelenik.

A kvantum-dinamika pontosan ugyanazt a nyelvet használhatja.
A Hamilton vagy az összes energia teljes mértékben meghatározza a lezárt kvantum-rendszerek dinamikáját.
Van azonban néhány lényeges különbség a két elmélet között.
A klasszikus mechanika $x $ és a $p $ csak számok, míg a kvantum-mechanika nem.
Valójában még nem ingázik: $xp \ne px $.

A nem áttekintő objektumok leírására szolgáló megfelelő matematikai koncepció egy operátor, amely olyan esetekben, amikor a $x $ és a $p $ esetében csak egy különálló érték elvégzése egybeesik egy mátrix koncepciójának használatával.
Így az egyszerűség kedvéért feltételezzük, hogy a kvantumrendszer véges, [és vektorok és mátrixok](xref:microsoft.quantum.concepts.vectors)használatával van leírva.
További követelmény, hogy ezek a mátrixok Hermitian legyenek (ami azt jelenti, hogy a mátrix átültetése megegyezik az eredeti mátrixtal).
Ez garantálja, hogy a mátrixok eigenvalues valós értékűek legyenek; egy olyan feltételt, amely alapján biztosítjuk, hogy ha egy olyan mennyiséget mérjük, amely nem kap vissza egy képzeletbeli számot.

Ugyanúgy, ahogy a Quantum Mechanics pozíciójának és a lendületének analóg elemeit a kezelőknek le kell cserélniük, a Hamilton függvényt hasonlóan egy operátornak kell lecserélnie.
Például egy szabad területhez tartozó részecske esetében $H (x, p) = p ^ 2/2m $, míg a Quantum mechanikaban a Hamilton operátor $ \hat{H} $ értéke $ \hat{H} = \hat{p} ^ 2/2m $, ahol a $ \hat{p} $ a lendületet kezelő operátor.
Ebből a szemszögből a klasszikusról a Quantum Dynamics-re való váltás csupán a szokványos dinamikában a kezelők által használt változók cseréjét jelenti.
Miután felépítettük a Hamilton-kezelőt úgy, hogy a hagyományos klasszikus Hamilton a Quantum Language-re fordítjuk, egy tetszőleges kvantum-mechanikus mennyiség (azaz a Quantum Mechanical Operator) \hat{f} (t) fejállítás} \frac{d}{DT} \hat{f} = \partial_t \hat{f} + [\hat{f}, \hat{H}], \end{align}, ahol $ [f, H] = fH-HF $ néven ismert commutator.
Ez a kifejezés pontosan ugyanúgy, mint a fent megadott klasszikus kifejezés azzal a különbséggel, hogy a Poisson zárójel $\\{f, H\\} $ helyett a $f $ és a $H $ közötti commutator vált.
Ez a folyamat a klasszikus Hamilton, és azt használva, hogy megkeresse a kvantum-Hamilton a Quantum zsargonban, mint a Canonical kvantálás.

Milyen operátorok $f $ érdeklik?  A kérdésre adott válasz a megoldandó problémától függ.
Előfordulhat, hogy a legkönnyebben keresett mennyiség a Quantum State operátor, amely a korábbi fogalmi dokumentációban tárgyalva mindent Kinyer, amit a dinamika megismeréséhez szeretnénk.
Miután ezt megtette (és leegyszerűsíti az eredményt arra az esetre, amikor az egyik tiszta állapottal rendelkezik), a kvantum-állapothoz tartozó Schrödinger-egyenlet található a \begin{align} i\partial_t \ket{\psi (t)} = \hat{H} (t) \ket{\psi (t)}.
\end{align}

Ez az egyenlet, bár talán kevésbé intuitív, mint a fentiekben, a a legegyszerűbb kifejezést adja meg annak megértéséhez, hogyan szimulálható a Quantum Dynamics a Quantum vagy a klasszikus számítógépeken.
Ennek az az oka, hogy a különbözeti egyenlet megoldását a következő formában lehet kifejezni (ha a Hamilton állandó a $t $) \begin{align} \ket{\psi (t)} = e ^ {-iHt} \ket{\psi (0)}.
\end{align} itt $e ^ {-iHt} $ egy egységes mátrix.
Ez azt jelenti, hogy létezik egy olyan kvantum-áramkör, amely úgy van kialakítva, hogy a kvantum-számítógépek szigorúan közelítsék meg az egységes mátrixot.
Ez a művelet olyan kvantum-kör megkeresését eredményezi, amely a Quantum Time Evolution operátort $e ^ {-iHt} $ értékkel valósítja meg, amit gyakran kvantum-szimulációnak vagy különösen dinamikus kvantum-szimulációnak nevezünk.
