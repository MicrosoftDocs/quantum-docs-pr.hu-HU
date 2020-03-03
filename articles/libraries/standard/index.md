---
title: A Microsoft szabványos Q#-kódtárak bemutatása
description: Ismerje meg a Microsoft szabványos Q#-kódtárakat, amelyek meghatározzák a kvantumprogramokban használt műveleteket, függvényeket és adattípusokat.
author: QuantumWriter
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.intro
ms.openlocfilehash: 820ad885e7134aa723116d4c9f853d88210a5514
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907154"
---
# <a name="introduction-to-the-q-standard-libraries"></a>Bevezetés a szabványos Q#-kódtárak használatába #

A Q#-t számos olyan hasznos művelet, függvény és felhasználó által definiált típus támogatja, amelyek együttesen a Q# *szabványos kódtárát* alkotják.
A [telepítés és ellenőrzés](xref:microsoft.quantum.install) során telepített [`Microsoft.Quantum.Development.Kit` NuGet-csomag](https://www.nuget.org/packages/microsoft.quantum.development.kit) tartalmazza a Q#-fordítót, valamint a célszámítógépek által implementált szabványos kódtár részeit.
A [`Microsoft.Quantum.Standard` csomag](https://www.nuget.org/packages/microsoft.quantum.standard) tartalmazza a szabványos Q#-kódtárak azon részét, amely hordozható a célszámítógépek között.

A szabványos Q#-kódtárak által definiált szimbólumok sokkal nagyobb részletességgel vannak meghatározva az [API-dokumentációban](xref:microsoft.quantum.standardlibsintro).

A következő szakaszokban a szabványos kódtár egyes részeinek legfontosabb funkcióit soroljuk fel, és nagy általánosságban azt is ismertetjük, hogy az egyes funkciók hogyan használhatók a gyakorlatban.
