---
title: A kvantumkémiai kódtár bemutatása
description: Ismerje meg a Microsoft Kvantumkémiai kódtárát, és azt, hogy miként használható az elektronikus szerkezeti problémák kvantumszámítógépeken történő szimulációjához.
author: QuantumWriter
ms.author: ageller
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 15439a34933bd561dc011acf48e669abeb031e33
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835791"
---
# <a name="introduction-to-the-quantum-chemistry-library"></a>A kvantumkémiai kódtár bemutatása

A fizikai rendszerek szimulációja régóta központi szerepet játszik a kvantum-számítástechnikában.  Ennek az az oka, hogy a kvantumdinamikáról széles körben úgy tartják, hogy a szimulálása kvantumszámítógépeken nyomon követhetetlen, ami azt jelenti, hogy a rendszer szimulálásának összetettsége a szóban forgó kvantumrendszer méretével együtt exponenciálisan nő.  A kémiai és anyagtudományi problémák szimulálása talán a kvantum-számítástechnika legelterjedtebb alkalmazási területe, amely lehetővé tette olyan kémiai reakciós mechanizmusok vizsgálatát, amelyeknek mérésére és szimulálására korábban nem voltunk képesek.  Emellett ezzel szimulálhatóvá váltak a korrelált elektronikus anyagok, például a magas hőmérsékletű szupravezetők is. A szakterület alkalmazási eseteinek listája rendkívül hosszú.

Jelen dokumentáció célja az, hogy rövid bevezetést nyújtson az elektronikus szerkezeti problémák kvantumszámítógépeken történő szimulálásába, és ezáltal feltárja az olvasó előtt, hogy a Hamilton-operátorok szimulációs kódtárának különböző aspektusai milyen szerepet töltenek be a szakterületen belül.  Kezdjük a kvantummechanika rövid ismertetésével, majd térjünk rá arra, hogy ezen belül hogyan modellezhetők az elektronikus rendszerek.  Ezt követően áttekintjük, hogy az ilyen kvantumdinamika hogyan emulálható egy kvantumszámítógéppel.  Miután ezzel végeztünk, ismertetjük a kvantumdinamika elemi kapuk sorozatává történő lefordításának két módját: a Trotter–Suzuki-dekompozíciókat és a qubitizációt.
