---
title: IQ# Magic parancsok
description: 'Gyors hivatkozási oldal az IQ # Magic parancsaihoz Q # Jupyter notebookokkal'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
uid: microsoft.quantum.guide.quickref.iqsharp
ms.openlocfilehash: 0cd1a2289132e2760a21fd9d4f4083696353e271
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431019"
---
# <a name="iq-magic-commands"></a><span data-ttu-id="82585-103">IQ# Magic parancsok</span><span class="sxs-lookup"><span data-stu-id="82585-103">IQ# Magic Commands</span></span>

### <a name="general"></a><span data-ttu-id="82585-104">Általános kérdések</span><span class="sxs-lookup"><span data-stu-id="82585-104">General</span></span>

- <span data-ttu-id="82585-105">`%config`: Beállítja vagy lekéri a konfigurációs beállításokat.</span><span class="sxs-lookup"><span data-stu-id="82585-105">`%config`: Sets or gets configuration preferences.</span></span>
- <span data-ttu-id="82585-106">`%estimate`: Egy adott függvény vagy művelet futtatása a QuantumSimulator célszámítógépen.</span><span class="sxs-lookup"><span data-stu-id="82585-106">`%estimate`: Runs a given function or operation on the QuantumSimulator target machine.</span></span>
- <span data-ttu-id="82585-107">`%lsmagic`: Az aktuálisan elérhető Magic-parancsok listáját adja vissza.</span><span class="sxs-lookup"><span data-stu-id="82585-107">`%lsmagic`: Returns a list of all currently available magic commands.</span></span>
- <span data-ttu-id="82585-108">`%package`: Lehetővé teszi a Nuget-csomagok betöltését.</span><span class="sxs-lookup"><span data-stu-id="82585-108">`%package`: Provides the ability to load a Nuget package.</span></span>
- <span data-ttu-id="82585-109">`%performance`: A kernel aktuális teljesítmény-metrikáit jelenti.</span><span class="sxs-lookup"><span data-stu-id="82585-109">`%performance`: Reports current performance metrics for this kernel.</span></span>
- <span data-ttu-id="82585-110">`%simulate`: Egy adott függvény vagy művelet futtatása a QuantumSimulator célszámítógépen.</span><span class="sxs-lookup"><span data-stu-id="82585-110">`%simulate`: Runs a given function or operation on the QuantumSimulator target machine.</span></span>
- <span data-ttu-id="82585-111">`%toffoli`: Egy adott függvény vagy művelet futtatása a ToffoliSimulator Simulator célszámítógépen.</span><span class="sxs-lookup"><span data-stu-id="82585-111">`%toffoli`: Runs a given function or operation on the ToffoliSimulator simulator target machine.</span></span>
- <span data-ttu-id="82585-112">`%who`: Az aktuális munkaterülettel kapcsolatos műveleteket biztosít.</span><span class="sxs-lookup"><span data-stu-id="82585-112">`%who`: Provides actions related to the current workspace.</span></span>
- <span data-ttu-id="82585-113">`%workspace`: Az aktuális munkamenetben definiált összes művelet és függvény listáját adja vissza, akár interaktív módon, akár az aktuális munkaterületről betöltve.</span><span class="sxs-lookup"><span data-stu-id="82585-113">`%workspace`: Returns a list of all operations and functions defined in the current session, either interactively or loaded from the current workspace.</span></span>

### <a name="chemistry"></a><span data-ttu-id="82585-114">Vegyi összetétel</span><span class="sxs-lookup"><span data-stu-id="82585-114">Chemistry</span></span>

- <span data-ttu-id="82585-115">`%chemistry.broombridge`: Betölti és visszaadja a Broombridge elektronikus szerkezetének problémás ábrázolását egy adott. YAML fájlból.</span><span class="sxs-lookup"><span data-stu-id="82585-115">`%chemistry.broombridge`: Loads and returns Broombridge electronic structure problem representation from a given .yaml file.</span></span>
- <span data-ttu-id="82585-116">`%chemistry.encode`: Egy Fermion Hamilton kódol a Q # használatával.</span><span class="sxs-lookup"><span data-stu-id="82585-116">`%chemistry.encode`: Encodes a fermion Hamiltonian to a format consumable by Q#.</span></span>
- <span data-ttu-id="82585-117">`%chemistry.fh.add_terms`: Feltételt hoz létre egy Fermion-Hamilton.</span><span class="sxs-lookup"><span data-stu-id="82585-117">`%chemistry.fh.add_terms`: Adds terms to a fermion Hamiltonian.</span></span>
- <span data-ttu-id="82585-118">`%chemistry.fh.load`: Betölti a Fermion Hamilton egy elektronikus szerkezettel kapcsolatos problémára.</span><span class="sxs-lookup"><span data-stu-id="82585-118">`%chemistry.fh.load`: Loads the fermion Hamiltonian for an electronic structure problem.</span></span> <span data-ttu-id="82585-119">A probléma betöltése egy fájlból történik, vagy argumentumként van megadva.</span><span class="sxs-lookup"><span data-stu-id="82585-119">The problem is loaded from a file or passed as an argument.</span></span>
- <span data-ttu-id="82585-120">`%chemistry.inputstate.load`: Betölti a Broombridge elektronikus szerkezetével kapcsolatos problémát, és visszaadja a kiválasztott bemeneti állapotot.</span><span class="sxs-lookup"><span data-stu-id="82585-120">`%chemistry.inputstate.load`: Loads Broombridge electronic structure problem and returns selected input state.</span></span>

### <a name="from-microsoftquantumkatas-package"></a><span data-ttu-id="82585-121">A Microsoft. Quantum. katas csomagból</span><span class="sxs-lookup"><span data-stu-id="82585-121">From Microsoft.Quantum.Katas package</span></span>

- <span data-ttu-id="82585-122">`%kata`: Egyetlen tesztet hajt végre, és jelentést készít arról, hogy a teszt sikeresen sikeres-e.</span><span class="sxs-lookup"><span data-stu-id="82585-122">`%kata`: Executes a single test, and reports whether the test passed successfully.</span></span>
- <span data-ttu-id="82585-123">`%check_kata`: Egy Kata-tesztre vonatkozó hivatkozás-implementáció ellenőrzése.</span><span class="sxs-lookup"><span data-stu-id="82585-123">`%check_kata`: Checks the reference implementation for a single kata's test.</span></span>
    <span data-ttu-id="82585-124">Pontosabban helyettesíti az egyetlen feladatra vonatkozó hivatkozási implementációt a cellába, és azt jelzi, hogy a teszt sikeresen sikeres volt-e.</span><span class="sxs-lookup"><span data-stu-id="82585-124">Specifically, it substitutes the reference implementation for a single task into the cell, and reports whether the test passed successfully.</span></span>
