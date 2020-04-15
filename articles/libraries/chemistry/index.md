---
title: A kvantumkémiai kódtár bemutatása
description: Ismerje meg a Microsoft Kvantumkémiai kódtárát, és azt, hogy miként használható az elektronikus szerkezeti problémák kvantumszámítógépeken történő szimulációjához.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.intro
ms.openlocfilehash: 4268eafa5e53c0a026d179503ac6db88652a8f90
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2020
ms.locfileid: "77907324"
---
# <a name="introduction-to-the-quantum-chemistry-library"></a>A kvantumkémiai kódtár bemutatása

A fizikai rendszerek szimulációja régóta központi szerepet játszik a kvantum-számítástechnikában.  Ennek az az oka, hogy a kvantumdinamikáról széles körben úgy tartják, hogy a szimulálása kvantumszámítógépeken nyomon követhetetlen, ami azt jelenti, hogy a rendszer szimulálásának összetettsége a szóban forgó kvantumrendszer méretével együtt exponenciálisan nő.  A kémiai és anyagtudományi problémák szimulálása talán a kvantum-számítástechnika legelterjedtebb alkalmazási területe, amely lehetővé tette olyan kémiai reakciós mechanizmusok vizsgálatát, amelyeknek mérésére és szimulálására korábban nem voltunk képesek.  Emellett ezzel szimulálhatóvá váltak a korrelált elektronikus anyagok, például a magas hőmérsékletű szupravezetők is. A szakterület alkalmazási eseteinek listája rendkívül hosszú.

Jelen dokumentáció célja az, hogy rövid bevezetést nyújtson az elektronikus szerkezeti problémák kvantumszámítógépeken történő szimulálásába, és ezáltal feltárja az olvasó előtt, hogy a Hamilton-operátorok szimulációs kódtárának különböző aspektusai milyen szerepet töltenek be a szakterületen belül.  Kezdjük a kvantummechanika rövid ismertetésével, majd térjünk rá arra, hogy ezen belül hogyan modellezhetők az elektronikus rendszerek.  Ezt követően áttekintjük, hogy az ilyen kvantumdinamika hogyan emulálható egy kvantumszámítógéppel.  Miután ezzel végeztünk, ismertetjük a kvantumdinamika elemi kapuk sorozatává történő lefordításának két módját: a Trotter–Suzuki-dekompozíciókat és a qubitizációt.
