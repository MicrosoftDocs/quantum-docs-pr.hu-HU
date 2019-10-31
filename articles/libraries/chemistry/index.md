---
title: A kvantumkémiai csomag bemutatása | Microsoft Docs
description: A kvantumkémiai csomag bemutatása
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.intro
ms.openlocfilehash: e5a9dd70874f1ae0baf4b781346278195a980a7e
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/26/2019
ms.locfileid: "72960423"
---
# <a name="introduction-to-the-quantum-chemistry-library"></a>A kvantumkémiai kódtár bemutatása

A fizikai rendszerek szimulációja régóta központi szerepet játszik a kvantum-számítástechnikában.  Ennek az az oka, hogy a kvantumdinamikáról széles körben úgy tartják, hogy a szimulálása kvantumszámítógépeken nyomon követhetetlen, ami azt jelenti, hogy a rendszer szimulálásának összetettsége a szóban forgó kvantumrendszer méretével együtt exponenciálisan nő.  A kémiai és anyagtudományi problémák szimulálása talán a kvantum-számítástechnika legelterjedtebb alkalmazási területe, amely lehetővé tette olyan kémiai reakciós mechanizmusok vizsgálatát, amelyeknek mérésére és szimulálására korábban nem voltunk képesek.  Emellett ezzel szimulálhatóvá váltak a korrelált elektronikus anyagok, például a magas hőmérsékletű szupravezetők is. A szakterület alkalmazási eseteinek listája rendkívül hosszú.

Jelen dokumentáció célja az, hogy rövid bevezetést nyújtson az elektronikus szerkezeti problémák kvantumszámítógépeken történő szimulálásába, és ezáltal feltárja az olvasó előtt, hogy a Hamilton-operátorok szimulációs kódtárának különböző aspektusai milyen szerepet töltenek be a szakterületen belül.  Kezdjük a kvantummechanika rövid ismertetésével, majd térjünk rá arra, hogy ezen belül hogyan modellezhetők az elektronikus rendszerek.  Ezt követően áttekintjük, hogy az ilyen kvantumdinamika hogyan emulálható egy kvantumszámítógéppel.  Miután ezzel végeztünk, ismertetjük a kvantumdinamika elemi kapuk sorozatává történő lefordításának két módját: a Trotter–Suzuki-dekompozíciókat és a qubitizációt.
