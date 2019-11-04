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
# <a name="the-q-programming-language"></a><span data-ttu-id="73228-103">A Q# programozási nyelv</span><span class="sxs-lookup"><span data-stu-id="73228-103">The Q# Programming Language</span></span>

## <a name="introduction"></a><span data-ttu-id="73228-104">Bevezetés</span><span class="sxs-lookup"><span data-stu-id="73228-104">Introduction</span></span>

<span data-ttu-id="73228-105">A kvantum-számítástechnika természetes modellje szerint a kvantumszámítógépet a GPU-k, FPGA-k és egyéb segédprocesszorok esetében használthoz hasonló koprocesszornak kell tekinteni.</span><span class="sxs-lookup"><span data-stu-id="73228-105">A natural model for quantum computation is to treat the quantum computer as a coprocessor, similar to that used for GPUs, FPGAs, and other adjunct processors.</span></span>
<span data-ttu-id="73228-106">Az elsődleges vezérlőlogika hagyományos kódot futtat a hagyományos „gazdagépen”.</span><span class="sxs-lookup"><span data-stu-id="73228-106">The primary control logic runs classical code on a classical "host" computer.</span></span>
<span data-ttu-id="73228-107">Ha szükséges, a gazdaprogram alrutint hívhat meg, amely a segédprocesszoron fut.</span><span class="sxs-lookup"><span data-stu-id="73228-107">When appropriate and necessary, the host program can invoke a subroutine that runs on the adjunct processor.</span></span>
<span data-ttu-id="73228-108">Az alrutin befejeztével a gazdaprogram hozzáférést nyer az alrutin eredményeihez.</span><span class="sxs-lookup"><span data-stu-id="73228-108">When the subroutine completes, the host program gets access to the subroutine's results.</span></span>

<span data-ttu-id="73228-109">A Q# (Q-sharp) egy tartományspecifikus programozási nyelv, amely a kvantumalgoritmusok kifejezésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="73228-109">Q# (Q-sharp) is a domain-specific programming language used for expressing quantum algorithms.</span></span>
<span data-ttu-id="73228-110">Olyan alrutinok írására használható, amelyek végrehajtása egy segéd-kvantumprocesszoron történik egy hagyományos gazdaprogram és számítógép vezérlése alatt.</span><span class="sxs-lookup"><span data-stu-id="73228-110">It is to be used for writing subroutines that execute on an adjunct quantum processor, under the control of a classical host program and computer.</span></span>
<span data-ttu-id="73228-111">Amíg a kvantumprocesszorok széles körben elérhetővé válnak, a Q#-alrutinok egy szimulátoron futnak.</span><span class="sxs-lookup"><span data-stu-id="73228-111">Until quantum processors are widely available, Q# subroutines execute on a simulator.</span></span>

<span data-ttu-id="73228-112">A Q# egyszerű típusok apró készletét, valamint két módszert (tömböket és rekordokat) tartalmaz az új, strukturált típusok létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="73228-112">Q# provides a small set of primitive types, along with two ways (arrays and tuples) for creating new, structured types.</span></span>
<span data-ttu-id="73228-113">A programok írásához alapszintű eljárási modellt támogat hurkokkal és ha-akkor típusú utasításokkal.</span><span class="sxs-lookup"><span data-stu-id="73228-113">It supports a basic procedural model for writing programs, with loops and if/then statements.</span></span>
<span data-ttu-id="73228-114">A Q# legfelső szintű szerkezetei a felhasználó által definiált típusok, műveletek és függvények.</span><span class="sxs-lookup"><span data-stu-id="73228-114">The top-level constructs in Q# are user defined types, operations, and functions.</span></span>

<span data-ttu-id="73228-115">A következő szakaszok az alábbiakat ismertetik:</span><span class="sxs-lookup"><span data-stu-id="73228-115">The following sections detail:</span></span>
- [<span data-ttu-id="73228-116">A típusmodell</span><span class="sxs-lookup"><span data-stu-id="73228-116">The Type Model</span></span>](xref:microsoft.quantum.language.type-model)
- [<span data-ttu-id="73228-117">Kifejezések</span><span class="sxs-lookup"><span data-stu-id="73228-117">Expressions</span></span>](xref:microsoft.quantum.language.expressions)
- [<span data-ttu-id="73228-118">Utasítások</span><span class="sxs-lookup"><span data-stu-id="73228-118">Statements</span></span>](xref:microsoft.quantum.language.statements)
- [<span data-ttu-id="73228-119">Fájlstruktúra</span><span class="sxs-lookup"><span data-stu-id="73228-119">File Structure</span></span>](xref:microsoft.quantum.language.file-structure)

## <a name="conventions"></a><span data-ttu-id="73228-120">Konvenciók</span><span class="sxs-lookup"><span data-stu-id="73228-120">Conventions</span></span>

<span data-ttu-id="73228-121">Dolgozunk azon, hogy a gyakori írásjelek minden környezetben következetesen legyenek használva.</span><span class="sxs-lookup"><span data-stu-id="73228-121">We are working to ensure that common punctuation marks are used consistently in all situations.</span></span>
<span data-ttu-id="73228-122">Reméljük, hogy ezáltal a Q# elsajátítása és olvasása egyszerűbbé válik, hiszen a jelek minden esetben ugyanazt jelentik, és az azonos fogalmak mindig azonos módon lesznek kifejezve.</span><span class="sxs-lookup"><span data-stu-id="73228-122">We expect that this will make Q# easier to learn and to read because these marks always mean the same thing, and the same concept is always represented the same way.</span></span>

<span data-ttu-id="73228-123">Ezek:</span><span class="sxs-lookup"><span data-stu-id="73228-123">Specifically:</span></span>

- <span data-ttu-id="73228-124">A pontosvessző (`;`) az utasítások vagy egysoros irányelvek lezárásához használatos.</span><span class="sxs-lookup"><span data-stu-id="73228-124">The semi-colon, `;`, is used to end a statement or single-line directive.</span></span>
  <span data-ttu-id="73228-125">Más célra nem használható.</span><span class="sxs-lookup"><span data-stu-id="73228-125">It is not used for any other purpose.</span></span>
- <span data-ttu-id="73228-126">A vessző (`,`) egy sorozat elemeit választja el.</span><span class="sxs-lookup"><span data-stu-id="73228-126">The comma, `,`, is used to separate elements of a sequence.</span></span> <span data-ttu-id="73228-127">Rekordliterálok, tömbliterálok, argumentumlisták, rekorddefiníciók és típuslisták esetében használatos.</span><span class="sxs-lookup"><span data-stu-id="73228-127">It is used for tuple literals, array literals, argument lists, tuple definitions, and type lists.</span></span> <span data-ttu-id="73228-128">**A korábbi verzióktól eltérően a `;` karakter már nem támogatott tömbliterálok elválasztójaként.**</span><span class="sxs-lookup"><span data-stu-id="73228-128">**In a change from earlier versions, `;` is no longer supported as an array literal separator.**</span></span>
- <span data-ttu-id="73228-129">A kettőspont (`:`) típusjegyzet bevezetésére használatos.</span><span class="sxs-lookup"><span data-stu-id="73228-129">The colon, `:`, is used to introduce a type annotation.</span></span> <span data-ttu-id="73228-130">Elsősorban meghívható aláírások esetében használják.</span><span class="sxs-lookup"><span data-stu-id="73228-130">It is primarily used in callable signatures.</span></span>
  <span data-ttu-id="73228-131">Mivel a kettőspont mindig típusaláírást vezet be, a 0.3-as verzióban bevezetett hármas feltételes operátor egy függőleges vonalat (`|`) használ az igaz és hamis értékek elválasztásához, így a Q# a C-től eltérő módon kettőspont helyett `cond ? tval | fval` karaktert használ az elválasztáshoz.</span><span class="sxs-lookup"><span data-stu-id="73228-131">Because colon always introduces a type signature, the ternary conditional operator introduced in 0.3 uses a vertical bar, `|`, to separate the true and false values; thus, Q# uses `cond ? tval | fval` instead of the colon as separator as in C.</span></span>
  
