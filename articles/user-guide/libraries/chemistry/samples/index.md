---
title: Kvantumkémiai mintaalkalmazások
description: A Microsoft Kvantumkémiai kódtárában található mintaalkalmazások megismerése
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: conceptual
uid: microsoft.quantum.chemistry.examples
no-loc:
- Q#
- $$v
ms.openlocfilehash: b2a8740f9c94ca733e24012aaf5c80b15b731c2e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858923"
---
# <a name="quantum-chemistry-examples"></a>Kvantumkémiai példák

A kvantumkémia alapelveivel foglalkozó részben manuálisan hoztunk létre a például szolgáló fermion Hamilton-operátorokat. Most ötvözzük a [Hamilton-operátorok dinamikájának szimulálását ismertető](xref:microsoft.quantum.libraries.standard.algorithms) részben tárgyalt kémiai szimulációs algoritmusokat a kanonikus kódtárban található [kvantumfázis-becsléssel](xref:microsoft.quantum.libraries.characterization). Ez a kombináció lehetővé teszi az energiaszintek becslését a jelölt molekulában, ami a kvantumszámítógépes kvantumkémia egyik legfőbb alkalmazási területe. 

A Hamilton-operátorok feltételeinek egyesével történő meghatározása helyett olyan példákat is használhatunk, amelyek lehetővé teszik kvantumkémiai kísérletek nagy léptékű végrehajtását. Kezdjük olyan példákkal, amelyek egy, a [Broombridge-sémába](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) kódolt kémiai Hamilton-operátort töltenek be.

Az olyan molekulákon, amelyek túl nagyok ahhoz, hogy a [teljes állapotú szimulátorban](xref:microsoft.quantum.machines.full-state-simulator) szimulálhatók legyenek, érdekes tudományos műveletek végezhetők. Előfordulhat például, hogy a nagy léptékű kémiai szimulációk végrehajtásának erőforrásköltsége továbbra is kiértékelhető a [nyomkövetési szimulátor](xref:microsoft.quantum.machines.qc-trace-simulator.intro) megcélzásával.

A kémiai szimulációs kódtár érdekes alkalmazási eseteit néhány mintával illusztráljuk.
