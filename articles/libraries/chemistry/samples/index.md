---
title: Kvantumkémiai mintaalkalmazások
description: A Microsoft Kvantumkémiai kódtárában található mintaalkalmazások megismerése
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples
ms.openlocfilehash: 5168fc8592d34a32ba67e5a0c4793aa17599fd35
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2020
ms.locfileid: "77906491"
---
# <a name="quantum-chemistry-examples"></a><span data-ttu-id="04b0b-103">Kvantumkémiai példák</span><span class="sxs-lookup"><span data-stu-id="04b0b-103">Quantum chemistry examples</span></span>

<span data-ttu-id="04b0b-104">A kvantumkémia alapelveivel foglalkozó részben manuálisan hoztunk létre a például szolgáló fermion Hamilton-operátorokat.</span><span class="sxs-lookup"><span data-stu-id="04b0b-104">In the quantum chemistry concepts, we manually constructed example fermion Hamiltonians.</span></span> <span data-ttu-id="04b0b-105">Most ötvözzük a [Hamilton-operátorok dinamikájának szimulálását ismertető](xref:microsoft.quantum.libraries.standard.algorithms) részben tárgyalt kémiai szimulációs algoritmusokat a kanonikus kódtárban található [kvantumfázis-becsléssel](xref:microsoft.quantum.libraries.characterization).</span><span class="sxs-lookup"><span data-stu-id="04b0b-105">We now combine the chemistry simulation algorithms outlined in [Simulating Hamiltonian dynamics](xref:microsoft.quantum.libraries.standard.algorithms) with [quantum phase estimation](xref:microsoft.quantum.libraries.characterization) in the canon library.</span></span> <span data-ttu-id="04b0b-106">Ez a kombináció lehetővé teszi az energiaszintek becslését a jelölt molekulában, ami a kvantumszámítógépes kvantumkémia egyik legfőbb alkalmazási területe.</span><span class="sxs-lookup"><span data-stu-id="04b0b-106">This combination allows us to obtain  estimates of energy levels in the represented molecule, which is one of the key applications of quantum chemistry on a quantum computer.</span></span> 

<span data-ttu-id="04b0b-107">A Hamilton-operátorok feltételeinek egyesével történő meghatározása helyett olyan példákat is használhatunk, amelyek lehetővé teszik kvantumkémiai kísérletek nagy léptékű végrehajtását.</span><span class="sxs-lookup"><span data-stu-id="04b0b-107">Instead of specifying terms of the Hamiltonian one-by-one, we also work through some examples that allow us to perform quantum chemistry experiments at scale.</span></span> <span data-ttu-id="04b0b-108">Kezdjük olyan példákkal, amelyek egy, a [Broombridge-sémába](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) kódolt kémiai Hamilton-operátort töltenek be.</span><span class="sxs-lookup"><span data-stu-id="04b0b-108">We begin with examples that load a chemistry Hamiltonian encoded in the [Broombridge schema](xref:microsoft.quantum.libraries.chemistry.schema.broombridge).</span></span>

<span data-ttu-id="04b0b-109">Az olyan molekulákon, amelyek túl nagyok ahhoz, hogy a [teljes állapotú szimulátorban](xref:microsoft.quantum.machines.full-state-simulator) szimulálhatók legyenek, érdekes tudományos műveletek végezhetők.</span><span class="sxs-lookup"><span data-stu-id="04b0b-109">For molecules that are too large to simulate on the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator), interesting science can still be performed.</span></span> <span data-ttu-id="04b0b-110">Előfordulhat például, hogy a nagy léptékű kémiai szimulációk végrehajtásának erőforrásköltsége továbbra is kiértékelhető a [nyomkövetési szimulátor](xref:microsoft.quantum.machines.qc-trace-simulator.intro) megcélzásával.</span><span class="sxs-lookup"><span data-stu-id="04b0b-110">For instance, the resource costs of performing large chemistry simulations may still be evaluated by targeting the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>

<span data-ttu-id="04b0b-111">A kémiai szimulációs kódtár érdekes alkalmazási eseteit néhány mintával illusztráljuk.</span><span class="sxs-lookup"><span data-stu-id="04b0b-111">Let us now illustrate interesting applications of the chemistry simulation library through a few of the provided samples.</span></span>
