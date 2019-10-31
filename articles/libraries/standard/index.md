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
# <a name="introduction-to-the-q-standard-libraries"></a><span data-ttu-id="ae34e-103">Bevezetés a szabványos Q#-kódtárak használatába</span><span class="sxs-lookup"><span data-stu-id="ae34e-103">Introduction to the Q# Standard Libraries</span></span> #

<span data-ttu-id="ae34e-104">A Q#-t számos olyan hasznos művelet, függvény és felhasználó által definiált típus támogatja, amelyek együttesen a Q# *szabványos kódtárát* alkotják.</span><span class="sxs-lookup"><span data-stu-id="ae34e-104">Q# is supported by a range of different useful operations, functions, and user-defined types that comprise the Q# *standard libraries*.</span></span>
<span data-ttu-id="ae34e-105">A [telepítés és ellenőrzés](xref:microsoft.quantum.install) során telepített [`Microsoft.Quantum.Development.Kit` NuGet-csomag](https://www.nuget.org/packages/microsoft.quantum.development.kit) tartalmazza a Q#-fordítót, valamint a célszámítógépek által implementált szabványos kódtár részeit.</span><span class="sxs-lookup"><span data-stu-id="ae34e-105">The [`Microsoft.Quantum.Development.Kit` NuGet package](https://www.nuget.org/packages/microsoft.quantum.development.kit) installed during [installation and validation](xref:microsoft.quantum.install) provides the Q# compiler, and parts of the standard library that are implemented by the target machines.</span></span>
<span data-ttu-id="ae34e-106">A [`Microsoft.Quantum.Standard` csomag](https://www.nuget.org/packages/microsoft.quantum.standard) tartalmazza a szabványos Q#-kódtárak azon részét, amely hordozható a célszámítógépek között.</span><span class="sxs-lookup"><span data-stu-id="ae34e-106">The [`Microsoft.Quantum.Standard` package](https://www.nuget.org/packages/microsoft.quantum.standard) provides the portion of the Q# standard libraries that are portable across target machines.</span></span>

<span data-ttu-id="ae34e-107">A szabványos Q#-kódtárak által definiált szimbólumok sokkal nagyobb részletességgel vannak meghatározva az [API-dokumentációban](xref:microsoft.quantum.standardlibsintro).</span><span class="sxs-lookup"><span data-stu-id="ae34e-107">The symbols defined by the Q# standard libraries are defined in much greater and more exhaustive detail in the [API documentation](xref:microsoft.quantum.standardlibsintro).</span></span>

<span data-ttu-id="ae34e-108">A következő szakaszokban a szabványos kódtár egyes részeinek legfontosabb funkcióit soroljuk fel, és nagy általánosságban azt is ismertetjük, hogy az egyes funkciók hogyan használhatók a gyakorlatban.</span><span class="sxs-lookup"><span data-stu-id="ae34e-108">In the following sections, we will outline the most salient features of each part of the standard library and provide some context about how each feature might be used in practice.</span></span>
