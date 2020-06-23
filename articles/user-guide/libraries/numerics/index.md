---
title: A kvantumnumerikus kódtár bemutatása | Microsoft Docs
description: A kvantumnumerikus kódtár bemutatása
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.intro
ms.openlocfilehash: efd1a712616534ac281433fc008f0983271881d7
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85273641"
---
# <a name="introduction-to-the-quantum-numerics-library"></a>A kvantumnumerikus kódtár bemutatása

Sok kvantumalgoritmus olyan [orákulumokra](xref:microsoft.quantum.concepts.oracles) támaszkodik, amelyek a bemenetek szuperpozícióján értékelnek ki matematikai függvényeket.
Shor algoritmusának fő összetevője például kiértékeli az $f(x) = a^x\operatorname{mod} N$ függvényt, hogy megkapja a fix $a$ értéket, amely az $N$ együtthatójának kiszámolásához szükséges szám, illetve az $x$ értéket, amely egy $2n$ qubites egész szám egységes szuperpozícióban az összes $2n$ bites sztringben.

Ha Shor algoritmusát egy igazi kvantumszámítógépen szeretné futtatni, ezt a függvényt a célszámítógép natív műveleteivel kell megírni.
A $x$ bináris ábrázolását használva, ahol $x_i$ jelöli az $i$-edik bitet a legkevésbé fontos bittől számolva, az $f(x)$ a következőképpen írható meg: $f(x) = a^{\sum_{i=0}^{2n-1} x_i 2^i} \operatorname{mod} N$.
Ez viszont az $a^{2^i x_i}=(a^{2^i})^{x_i}$ kifejezések eredményeként (mod N) írható meg. Az $f(x)$ függvény így a $2n$ (moduláris) szorzatok sorozatával implementálható, ahol az $a^{2^i}$ feltételes az $x_i$-n nem nulla. Az $a^{2^i}$ állandók előre kiszámíthatók és modulo N-re csökkenthetők az algoritmus futtatása előtt.

A vezérelt moduláris szorzások sorozata tovább egyszerűsíthető: Minden szorzás az $n$-vezérelt moduláris hozzáadások sorozatával végezhető el; és mindegyik moduláris hozzáadás felépíthető egy hagyományos összeadásból és egy komparátorból.


Mivel ilyen sok lépésre van szükség a tényleges implementációig, rendkívül hasznos lenne, ha az ilyen funkciók már a legelejétől elérhetők lennének.
A Quantum Development Kit ezért támogatja a numerikus funkciók széles körét.


## <a name="functionality"></a>Funkció

A fentiekben említett egész számos aritmetika mellett a numerikus kódtár a következőket nyújtja:

 - (Nem) előjeles egész számokkal kapcsolatos funkciók (szorzás, négyzetre emelés, osztás maradékkal, inverzió stb.), ahol egy vagy két egész kvantumszám a bemenet
 - Fixpontos funkciók (hozzáadás/kivonás, szorzás, négyzetre emelés, 1/x, polinomértékelés), ahol egy vagy két fixpontos kvantumszám a bemenet

## <a name="getting-started"></a>Első lépések

A numerikus kódtár használatának megkezdéséhez tekintse át a [telepítési útmutatót](xref:microsoft.quantum.numerics.installation) és [a numerikus kódtár használatával](xref:microsoft.quantum.numerics.usage) kapcsolatos további információkat.
