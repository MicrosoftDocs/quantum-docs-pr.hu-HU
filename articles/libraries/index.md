---
title: Quantum Development Kit-kódtárak
description: A Microsoft Quantum Development Kitben található standard, kémiai és numerikus kódtárak áttekintése
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries
ms.openlocfilehash: 89612aaa5c11e1a5e0d418256e96366953fdd3fe
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2020
ms.locfileid: "77906406"
---
# <a name="overview-of-q-libraries"></a><span data-ttu-id="45f0d-103">A Q#-kódtárak áttekintése</span><span class="sxs-lookup"><span data-stu-id="45f0d-103">Overview of Q# Libraries</span></span>
<span data-ttu-id="45f0d-104">A Quantum Development Kit számos olyan kódtárat tartalmaz, melyek megkönnyítik a kvantumalkalmazások Q# nyelven történő fejlesztését.</span><span class="sxs-lookup"><span data-stu-id="45f0d-104">The Quantum Development Kit is provided with several libraries to make it easier to develop quantum applications in Q#.</span></span>
<span data-ttu-id="45f0d-105">A dokumentáció e szakaszában ismertetjük ezeket a kódtárakat és a programokban való felhasználásukat.</span><span class="sxs-lookup"><span data-stu-id="45f0d-105">In this section of the documentation, we describe these libraries and how to use them in your programs.</span></span>

- <span data-ttu-id="45f0d-106">[**Standard kódtárak**](xref:microsoft.quantum.libraries.standard.intro): Ez a szakasz ismerteti a bevezetőt, amely meghatározza a Q#-programok és a célszámítógépek közötti felületet, valamint a kánont, azaz egy általános célú műveleteket és függvényeket tartalmazó Q#-kódtárat a Q#-programok írásához.</span><span class="sxs-lookup"><span data-stu-id="45f0d-106">[**Standard libraries**](xref:microsoft.quantum.libraries.standard.intro): This section describes the prelude, which defines the interface between Q# programs and target machines, and the canon, a Q# library that provides general-purpose operations and functions for use in writing Q# programs.</span></span>
- <span data-ttu-id="45f0d-107">[**A kvantumkémiai kódtár**](xref:microsoft.quantum.chemistry.concepts.intro): Ez a szakasz ismerteti a kvantumkémiai kódtárat, amely egy adatmodellt biztosít a fermion Hamilton-operátorok és a kvantumszimulációs műveletek jelölésének, valamint az ezekhez kapcsolódó függvényeknek a betöltéséhez.</span><span class="sxs-lookup"><span data-stu-id="45f0d-107">[**Quantum chemistry library**](xref:microsoft.quantum.chemistry.concepts.intro): This section describes the quantum chemistry library, which provides a data model for loading representations of fermionic Hamiltonians and quantum simulation operations and functions which act on these representations.</span></span>
- <span data-ttu-id="45f0d-108">[**A kvantumnumerikus kódtár**](xref:microsoft.quantum.numerics.intro): Ez a szakasz ismerteti a kvantumnumerikus kódtárat, amely számos matematikai függvény implementációját biztosítja.</span><span class="sxs-lookup"><span data-stu-id="45f0d-108">[**Quantum numerics library**](xref:microsoft.quantum.numerics.intro): This section describes the quantum numerics library, which provides implementations for a host of mathematical functions.</span></span> <span data-ttu-id="45f0d-109">A kódtár támogatja az egész számos (előjeles és előjel nélküli) és a fixpontos jelöléseket.</span><span class="sxs-lookup"><span data-stu-id="45f0d-109">It supports integer (signed & unsigned) and fixed-point representations.</span></span>

<span data-ttu-id="45f0d-110">A kódtárak forrásanyagai és kódmintái a GitHubon elérhetők.</span><span class="sxs-lookup"><span data-stu-id="45f0d-110">Sources of the libraries as well as code samples can be obtained from GitHub.</span></span> <span data-ttu-id="45f0d-111">További információért lásd még a [licenceléssel](xref:microsoft.quantum.libraries.licensing) foglalkozó szakaszt.</span><span class="sxs-lookup"><span data-stu-id="45f0d-111">See also the [licensing](xref:microsoft.quantum.libraries.licensing) section for further information.</span></span> <span data-ttu-id="45f0d-112">Érdemes megjegyezni, hogy a kódtárakhoz referenciacsomagok („bináris fájlok”) is elérhetők, amelyek újabb módot kínálnak a kódtárak a projektekben való felhasználására.</span><span class="sxs-lookup"><span data-stu-id="45f0d-112">It should be noted that package references ("binaries") are available also for the libraries which offers another way of including the libraries in projects.</span></span> <span data-ttu-id="45f0d-113">Ezeket a [nuget](https://nuget.org) használatával lehet kényelmesen beszerezni.</span><span class="sxs-lookup"><span data-stu-id="45f0d-113">A convenient way of obtaining them is via [nuget](https://nuget.org).</span></span>
