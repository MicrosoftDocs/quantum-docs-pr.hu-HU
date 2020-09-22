---
title: Quantum Development Kit-kódtárak
description: A Microsoft Quantum Development Kitben található standard, kémiai és numerikus kódtárak áttekintése
author: cgranade
ms.author: chgranad
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries
no-loc:
- Q#
- $$v
ms.openlocfilehash: 90672b6ec78bf8305bdb3ab8326002cf8ce34bfe
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835723"
---
# <a name="overview-of-no-locq-libraries"></a>A Q#-kódtárak áttekintése
A Quantum Development Kit számos olyan kódtárat tartalmaz, melyek megkönnyítik a kvantumalkalmazások Q# nyelven történő fejlesztését.
A dokumentáció e szakaszában ismertetjük ezeket a kódtárakat és a programokban való felhasználásukat.

- [**Standard kódtárak**](xref:microsoft.quantum.libraries.standard.intro): Ez a szakasz ismerteti a bevezetőt, amely meghatározza a Q#-programok és a célszámítógépek közötti felületet, valamint a kánont, azaz egy általános célú műveleteket és függvényeket tartalmazó Q#-kódtárat a Q#-programok írásához.
- [**A kvantumkémiai kódtár**](xref:microsoft.quantum.chemistry.concepts.intro): Ez a szakasz ismerteti a kvantumkémiai kódtárat, amely egy adatmodellt biztosít a fermion Hamilton-operátorok és a kvantumszimulációs műveletek jelölésének, valamint az ezekhez kapcsolódó függvényeknek a betöltéséhez.
- [**A kvantumnumerikus kódtár**](xref:microsoft.quantum.numerics.intro): Ez a szakasz ismerteti a kvantumnumerikus kódtárat, amely számos matematikai függvény implementációját biztosítja. A kódtár támogatja az egész számos (előjeles és előjel nélküli) és a fixpontos jelöléseket.
- [**Kvantum gépi tanulási kódtár**](xref:microsoft.quantum.machine-learning.concepts.intro): Ez a szakasz a kvantum gépi tanulási kódtárat mutatja be, amely a szekvenciális osztályozók azon implementációját biztosítja, amely kvantum-számítástechnikát használ az adatok értelmezéséhez.

A kódtárak forrásanyagai és kódmintái a GitHubon elérhetők.
További információért tekintse meg a [Licencelés](xref:microsoft.quantum.libraries.licensing) szakaszt. Vegye figyelembe, hogy a kódtárakhoz referenciacsomagok („bináris fájlok”) is elérhetők, és ezek újabb módot kínálnak a kódtárak projektekbe való belefoglalására.
Ezeket a [NuGet](https://nuget.org) használatával lehet kényelmesen beszerezni.
