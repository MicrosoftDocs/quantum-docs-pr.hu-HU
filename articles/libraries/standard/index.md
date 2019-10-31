---
title: Bevezetés a szabványos Q#-kódtárak használatába | Microsoft Docs
description: Bevezetés a szabványos Q#-kódtárak használatába
author: QuantumWriter
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.intro
ms.openlocfilehash: 547f4f6066e3ead627cd2a5970b1555999e988bb
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73056382"
---
# <a name="introduction-to-the-q-standard-libraries"></a>Bevezetés a szabványos Q#-kódtárak használatába #

A Q#-t számos olyan hasznos művelet, függvény és felhasználó által definiált típus támogatja, amelyek együttesen a Q# *szabványos kódtárát* alkotják.
A [telepítés és ellenőrzés](xref:microsoft.quantum.install) során telepített [`Microsoft.Quantum.Development.Kit` NuGet-csomag](https://www.nuget.org/packages/microsoft.quantum.development.kit) tartalmazza a Q#-fordítót, valamint a célszámítógépek által implementált szabványos kódtár részeit.
A [`Microsoft.Quantum.Standard` csomag](https://www.nuget.org/packages/microsoft.quantum.standard) tartalmazza a szabványos Q#-kódtárak azon részét, amely hordozható a célszámítógépek között.

A szabványos Q#-kódtárak által definiált szimbólumok sokkal nagyobb részletességgel vannak meghatározva az [API-dokumentációban](xref:microsoft.quantum.standardlibsintro).

A következő szakaszokban a szabványos kódtár egyes részeinek legfontosabb funkcióit soroljuk fel, és nagy általánosságban azt is ismertetjük, hogy az egyes funkciók hogyan használhatók a gyakorlatban.
