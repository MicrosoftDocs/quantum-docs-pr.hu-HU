---
title: A Q# programozási nyelv | Microsoft Docs
description: A Q# programozási nyelv
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.intro
ms.openlocfilehash: 560926f6f3e05c32a935f01ca5107a614e743ee2
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442471"
---
# <a name="the-q-programming-language"></a>A Q# programozási nyelv

## <a name="introduction"></a>Bevezetés

A kvantum-számítástechnika természetes modellje szerint a kvantumszámítógépet a GPU-k, FPGA-k és egyéb segédprocesszorok esetében használthoz hasonló koprocesszornak kell tekinteni.
Az elsődleges vezérlőlogika hagyományos kódot futtat a hagyományos „gazdagépen”.
Ha szükséges, a gazdaprogram alrutint hívhat meg, amely a segédprocesszoron fut.
Az alrutin befejeztével a gazdaprogram hozzáférést nyer az alrutin eredményeihez.

A Q# (Q-sharp) egy tartományspecifikus programozási nyelv, amely a kvantumalgoritmusok kifejezésére szolgál.
Olyan alrutinok írására használható, amelyek végrehajtása egy segéd-kvantumprocesszoron történik egy hagyományos gazdaprogram és számítógép vezérlése alatt.
Amíg a kvantumprocesszorok széles körben elérhetővé válnak, a Q#-alrutinok egy szimulátoron futnak.

A Q# egyszerű típusok apró készletét, valamint két módszert (tömböket és rekordokat) tartalmaz az új, strukturált típusok létrehozásához.
A programok írásához alapszintű eljárási modellt támogat hurkokkal és ha-akkor típusú utasításokkal.
A Q# legfelső szintű szerkezetei a felhasználó által definiált típusok, műveletek és függvények.

A következő szakaszok az alábbiakat ismertetik:
- [A típusmodell](xref:microsoft.quantum.language.type-model)
- [Kifejezések](xref:microsoft.quantum.language.expressions)
- [Utasítások](xref:microsoft.quantum.language.statements)
- [Fájlstruktúra](xref:microsoft.quantum.language.file-structure)

## <a name="conventions"></a>Konvenciók

Dolgozunk azon, hogy a gyakori írásjelek minden környezetben következetesen legyenek használva.
Reméljük, hogy ezáltal a Q# elsajátítása és olvasása egyszerűbbé válik, hiszen a jelek minden esetben ugyanazt jelentik, és az azonos fogalmak mindig azonos módon lesznek kifejezve.

Ezek:

- A pontosvessző (`;`) az utasítások vagy egysoros irányelvek lezárásához használatos.
  Más célra nem használható.
- A vessző (`,`) egy sorozat elemeit választja el. Rekordliterálok, tömbliterálok, argumentumlisták, rekorddefiníciók és típuslisták esetében használatos. **A korábbi verzióktól eltérően a `;` karakter már nem támogatott tömbliterálok elválasztójaként.**
- A kettőspont (`:`) típusjegyzet bevezetésére használatos. Elsősorban meghívható aláírások esetében használják.
  Mivel a kettőspont mindig típusaláírást vezet be, a 0.3-as verzióban bevezetett hármas feltételes operátor egy függőleges vonalat (`|`) használ az igaz és hamis értékek elválasztásához, így a Q# a C-től eltérő módon kettőspont helyett `cond ? tval | fval` karaktert használ az elválasztáshoz.
  
