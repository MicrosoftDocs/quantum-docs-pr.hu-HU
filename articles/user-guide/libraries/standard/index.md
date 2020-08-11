---
title: A Microsoft szabványos Q#-kódtárak bemutatása
description: Ismerje meg a Microsoft szabványos Q#-kódtárakat, amelyek meghatározzák a kvantumprogramokban használt műveleteket, függvényeket és adattípusokat.
author: QuantumWriter
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4db227fcf159331f9f8456c474ce6d64111c21df
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868474"
---
# <a name="introduction-to-the-no-locq-standard-libraries"></a>Bevezetés a szabványos Q#-kódtárak használatába

A Q#-t számos olyan hasznos művelet, függvény és felhasználó által definiált típus támogatja, amelyek együttesen a Q# *szabványos kódtárát* alkotják.
A [telepítés és ellenőrzés](xref:microsoft.quantum.install) során telepített [`Microsoft.Quantum.Development.Kit` NuGet-csomag](https://www.nuget.org/packages/microsoft.quantum.development.kit) tartalmazza a Q#-fordítót, valamint a célszámítógépek által implementált szabványos kódtár részeit.
A [`Microsoft.Quantum.Standard` csomag](https://www.nuget.org/packages/microsoft.quantum.standard) tartalmazza a szabványos Q#-kódtárak azon részét, amely hordozható a célszámítógépek között.

A szabványos Q#-kódtárak által definiált szimbólumok sokkal nagyobb részletességgel vannak meghatározva az [API-dokumentációban](xref:microsoft.quantum.standardlibsintro).

A következő szakaszokban a szabványos kódtár egyes részeinek legfontosabb funkcióit soroljuk fel, és nagy általánosságban azt is ismertetjük, hogy az egyes funkciók hogyan használhatók a gyakorlatban.
