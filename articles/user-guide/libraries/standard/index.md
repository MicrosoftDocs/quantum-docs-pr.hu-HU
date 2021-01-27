---
title: A Microsoft szabványos Q#-kódtárak bemutatása
description: Ismerje meg a Microsoft szabványos Q#-kódtárakat, amelyek meghatározzák a kvantumprogramokban használt műveleteket, függvényeket és adattípusokat.
author: QuantumWriter
ms.author: martinro
ms.date: 12/11/2017
ms.topic: conceptual
uid: microsoft.quantum.libraries.standard.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 58e271fefba84e45c5558eeee066bc37c22bf63b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858319"
---
# <a name="introduction-to-the-no-locq-standard-libraries"></a>Bevezetés a szabványos Q#-kódtárak használatába

A Q#-t számos olyan hasznos művelet, függvény és felhasználó által definiált típus támogatja, amelyek együttesen a Q# *szabványos kódtárát* alkotják.
A [telepítés és ellenőrzés](xref:microsoft.quantum.install) során telepített [`Microsoft.Quantum.Development.Kit` NuGet-csomag](https://www.nuget.org/packages/microsoft.quantum.development.kit) tartalmazza a Q#-fordítót, valamint a célszámítógépek által implementált szabványos kódtár részeit.
A [`Microsoft.Quantum.Standard` csomag](https://www.nuget.org/packages/microsoft.quantum.standard) tartalmazza a szabványos Q#-kódtárak azon részét, amely hordozható a célszámítógépek között.

A szabványos Q#-kódtárak által definiált szimbólumok sokkal nagyobb részletességgel vannak meghatározva az [API-dokumentációban](xref:microsoft.quantum.apiref-intro).

A következő szakaszokban a szabványos kódtár egyes részeinek legfontosabb funkcióit soroljuk fel, és nagy általánosságban azt is ismertetjük, hogy az egyes funkciók hogyan használhatók a gyakorlatban.
