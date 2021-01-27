---
title: A kvantumkémiai kódtár bemutatása
description: Ismerje meg a Microsoft Kvantumkémiai kódtárát, és azt, hogy miként használható az elektronikus szerkezeti problémák kvantumszámítógépeken történő szimulációjához.
author: QuantumWriter
ms.author: ageller
ms.date: 12/11/2017
ms.topic: conceptual
uid: microsoft.quantum.chemistry.concepts.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 3fa606600db1641b9f8b86ccefebb7681f181b92
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847490"
---
# <a name="introduction-to-the-quantum-chemistry-library"></a>A kvantumkémiai kódtár bemutatása

A fizikai rendszerek szimulációja régóta központi szerepet játszik a kvantum-számítástechnikában.  Ennek az az oka, hogy a kvantumdinamikáról széles körben úgy tartják, hogy a szimulálása kvantumszámítógépeken nyomon követhetetlen, ami azt jelenti, hogy a rendszer szimulálásának összetettsége a szóban forgó kvantumrendszer méretével együtt exponenciálisan nő.  A kémiai és anyagtudományi problémák szimulálása talán a kvantum-számítástechnika legelterjedtebb alkalmazási területe, amely lehetővé tette olyan kémiai reakciós mechanizmusok vizsgálatát, amelyeknek mérésére és szimulálására korábban nem voltunk képesek.  Emellett ezzel szimulálhatóvá váltak a korrelált elektronikus anyagok, például a magas hőmérsékletű szupravezetők is. A szakterület alkalmazási eseteinek listája rendkívül hosszú.

Jelen dokumentáció célja az, hogy rövid bevezetést nyújtson az elektronikus szerkezeti problémák kvantumszámítógépeken történő szimulálásába, és ezáltal feltárja az olvasó előtt, hogy a Hamilton-operátorok szimulációs kódtárának különböző aspektusai milyen szerepet töltenek be a szakterületen belül.  Kezdjük a kvantummechanika rövid ismertetésével, majd térjünk rá arra, hogy ezen belül hogyan modellezhetők az elektronikus rendszerek.  Ezt követően áttekintjük, hogy az ilyen kvantumdinamika hogyan emulálható egy kvantumszámítógéppel.  Miután ezzel végeztünk, ismertetjük a kvantumdinamika elemi kapuk sorozatává történő lefordításának két módját: a Trotter–Suzuki-dekompozíciókat és a qubitizációt.
