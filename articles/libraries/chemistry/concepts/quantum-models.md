---
title: Quantum modellek az elektronikus rendszerekhez | Microsoft Docs
description: Quantum modellek az elektronikus rendszerek fogalmi dokumentációja
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.quantummodels
ms.openlocfilehash: 45d134333c8a3c8937d206cb0a4a9cc6101a85df
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/26/2019
ms.locfileid: "73184151"
---
# <a name="quantum-models-for-electronic-systems"></a>Quantum modellek az elektronikus rendszerekhez

Az elektronikus rendszerek szimulálásához először a Hamilton megadásával kell kezdeni, amely a fent ismertetett Canonical kvantálási eljárásban érhető el.
Pontosabban, a $N _E $ elektronok, a Momenta $p _i $ (három dimenzióban) és a Mass $m _E $ és a pozíció vektorok $x _i $, valamint az olyan magok, amelyek díja $Z _K e $ a pozícióknál $y _K $, a Hamilton-kezelő beolvassa a \begin{Equation} \hat{H} = \sum\_{i = 1} ^ {N @no_ _t_1_ e} \frac{\hat{p}\_i ^ 2} {2m\_e} + \frac{1}{2}\sum\_{i\ne j} \frac{e ^ 2} {| \hat{x}\_i-\hat{x}\_j |}-\sum\_{i , k} \frac{Z\_ke ^ 2} {| \hat{x}\_i-{y}\_k |} + \frac{1}{2} \sum_{k\ne k '} \frac{Z\_kZ\_{k '} e ^ 2} {| y\_k-y\_k ' |}. \label{EQ: Ham} \end{Equation} a Momenta operátorok $ \hat{p}\_i ^ 2 $ megtekinthetők valós térben, Laplacian operátorként, azaz $ \hat{p}\_i ^ 2 =-\partial\_{x\_i} ^ 2-\partial\_{y\_i} ^ 2-\partial\_{z\_i} ^ 2 $.
Itt leegyszerűsítjük azt a feltételezést, hogy a magok a molekula nyugalmában vannak.
Ez az úgynevezett Oppenheimer közelítő, és általában érvényes a $ \hat{H} $ alacsony energiájú spektrumára, mivel az elektron tömege körülbelül 1/1836 $, a protonok tömege.
Ez a Hamilton operátor könnyen megtalálható az $N\_e $ elektronok rendszerének és a [Quantum dynamicsban](xref:microsoft.quantum.chemistry.concepts.quantumdynamics)ismertetett kanonikus kvantálási folyamatnak a kiírásával.

Ahhoz, hogy a $e ^ {-i\hat {H} t} $-hoz létre kell hoznia egy egységes mátrix-ábrázolást, a $ \hat{H} $ operátort mátrixként kell képviselni.
Ehhez ki kell választania egy koordináta-rendszerrendszert vagy-alapot, hogy az a-ben a problémát képviseljék.
Ha például a $ \psi_j $ a $N _E $ elektronhoz tartozó, merőlegesen használható függvények halmaza, akkor a mátrixot definiáljuk

\begin{Equation} H\_{i, j} = \int\_{-\infty} ^ \infty\int\_{-\infty} ^ \infty \psi ^ {\*}\_i (x\_1) \hat{H} \psi\_j (x\_2) \dd ^ 3x\_1 \dd ^ 3x\_2. \ címke {EQ: discreteHam} \end{Equation}

A $ \hat{H} $ operátor elvileg nem kötött, és nem egy véges dimenziós tárhelyre, hanem a $H\_\{i, j\}$ feletti mátrixra is vonatkozik.
Ez azt jelenti, hogy a hibák akkor merülnek fel, ha túl kicsi az alapkészletet. azonban a nagy mennyiségű kiválogatással a kémiai dinamika nem praktikus szimulálható.
Emiatt a probléma egyértelművé tételéhez olyan alapot kell választani, amely elengedhetetlen az elektronikus struktúra problémáinak megoldásához.

Számos megfelelő alap használható, és a probléma megfelelő kiválasztása a Quantum kémiájának nagy részét képezi.
Lehet, hogy a legegyszerűbb ilyen típusú készletek a (z) (a (z) (a (z) eigenfunctions (\hat{H} $) a hidrogén-hez hasonló atomok esetében a Schrödinger-egyenlet (azaz a (z)
Más alapkészletek, például a repülőgép-hullámok vagy a valós idejű pályák is használhatók, és részletesebben a kíváncsi olvasót a szabványos ["molekuláris elektronikus szerkezeti elmélet"](https://onlinelibrary.wiley.com/doi/book/10.1002/9781119019572) szövegre utalva Helgaker.

Míg a fenti modellben használt Államok tetszőlegesek lehetnek, a kvantum-mechanika a természetben található állapotokra vonatkozó korlátozásokat tartalmaz.
Különösen az összes érvényes elektronikus kvantum-állapotnak nem szimmetrikusnak kell lennie az elektron-címkék cseréjekor.
Ez azt jelenti, hogy ha a $ \psi (x_1, x_2) $ volt a Wave függvény a két elektron közös kvantum-állapotához, akkor a $ $ \psi (x_1, x_2) =-\psi (x_2, x_1) értékkel kell rendelkeznie.
$ $ A Pauli kizárási elv, amely megtiltja, hogy két elektron soha ne legyen ugyanazon a kvantum-állapotban, és lenyűgöző módon, közvetlenül a törvény közvetlen következménye, hogy ha két, ugyanazon a pozíción található elektronot cseréltek, akkor a \psi (x_1, x_1) \mapsto \psi ( x_1, x_1) \ne-\psi (x_1, x_1) $ kivéve, ha $ \psi (x_1, x_1) = 0 $.
Így a kezdeti állapotoknak meg kell egyezniük ennek a szimmetria-tulajdonságnak a betartása érdekében, viszont soha ne legyen két elektron ugyanabban az állapotban.
Ez rendkívül fontos az elektronikus struktúra esetében, mert több elektront Tilt le ugyanabban az állapotban, és lehetővé teszi, hogy a kvantum-számítógépek egyetlen kvantum-bitet használjanak az elektronok számának egy adott kvantum-állapotba való tárolásához.

Míg a kvantum-mechanika szimulálható egy kvantum-számítógépen ezen állapotok diszkretizálásával, a mező legtöbb munkája kihagyta ezt a megközelítést, mert számos qubits igényel az állapotok tárolásához, és bonyolult állapot-előkészítési eljárásra van szüksége a nem szimmetrikus kezdeti állapot.
Szerencsére előfordulhat, hogy ezek a problémák más szemszögből is sidestepped a szimulációs probléma megtekintésével.
