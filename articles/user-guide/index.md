---
title: A Q# használati útmutatója
description: A felhasználói útmutató céljának és tartalmának áttekintése
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
no-loc:
- Q#
- $$v
ms.openlocfilehash: 979e468cc743bd9125eaba0b71f794977c914447
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231757"
---
# <a name="the-no-locq-user-guide"></a><span data-ttu-id="8c982-103">A Q# használati útmutatója</span><span class="sxs-lookup"><span data-stu-id="8c982-103">The Q# User Guide</span></span>

<span data-ttu-id="8c982-104">Üdvözli Önt a Q# használati útmutatója!</span><span class="sxs-lookup"><span data-stu-id="8c982-104">Welcome to the Q# User Guide!</span></span> 

<span data-ttu-id="8c982-105">A jelen útmutató különböző témaköreiben ismertetjük a kvantumprogramok Q# használatával való fejlesztésének alapjait.</span><span class="sxs-lookup"><span data-stu-id="8c982-105">In the different topics of this guide, we introduce some of the basics for developing quantum programs using Q#.</span></span>

<span data-ttu-id="8c982-106">A Q# kvantumprogramozási nyelv teljes specifikációját és dokumentációját a [Q# nyelvi útmutatójában](xref:microsoft.quantum.qsharp.index) találja.</span><span class="sxs-lookup"><span data-stu-id="8c982-106">We refer to the [Q# language guide](xref:microsoft.quantum.qsharp.index) for a full specification and documentation of the Q# quantum programming language.</span></span> 

## <a name="user-guide-contents"></a><span data-ttu-id="8c982-107">A felhasználói útmutató tartalma</span><span class="sxs-lookup"><span data-stu-id="8c982-107">User Guide Contents</span></span>

- <span data-ttu-id="8c982-108">[Q#-programok](xref:microsoft.quantum.guide.programs): Rövid bevezetés a Q# nyelvű kvantumprogramokba.</span><span class="sxs-lookup"><span data-stu-id="8c982-108">[Q# programs](xref:microsoft.quantum.guide.programs): An quick introduction to quantum programs in Q#.</span></span> 

- <span data-ttu-id="8c982-109">[A Q#-programok futtatásának módjai](xref:microsoft.quantum.guide.host-programs): a Q#-programok futtatásának módját ismerteti, valamint áttekintést nyújt a program meghívásának különböző módjairól: a parancssorból, a Q# Jupyter-notebookokból vagy a Python vagy .NET nyelven írt klasszikus gazdaprogramokból.</span><span class="sxs-lookup"><span data-stu-id="8c982-109">[Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs): describes how a Q# program is run, and provides an overview of the various ways you can call the program: from the command line, in Q# Jupyter Notebooks, or from a classical host program written in Python or a .NET language.</span></span>

- <span data-ttu-id="8c982-110">[Tesztelés és hibakeresés](xref:microsoft.quantum.guide.testingdebugging): Részletesen ismertet néhány módszert, amelyek segítségével meggyőződhet róla, hogy a kódja úgy működik, ahogyan kell.</span><span class="sxs-lookup"><span data-stu-id="8c982-110">[Testing and debugging](xref:microsoft.quantum.guide.testingdebugging): Details some techniques for making sure your code is doing what it is supposed to do.</span></span> 
    <span data-ttu-id="8c982-111">A kvantuminformációk általános átlátszatlansága miatt egy kvantumprogram hibakereséséhez speciális módszerekre lehet szükség.</span><span class="sxs-lookup"><span data-stu-id="8c982-111">Due to the general opacity of quantum information, debugging a quantum program can require specialized techniques.</span></span> 
    <span data-ttu-id="8c982-112">Szerencsére a Q# számos, a programozok által jól ismert klasszikus hibakeresési módszert is támogat a kvantumspecifikus módszerek mellett.</span><span class="sxs-lookup"><span data-stu-id="8c982-112">Fortunately, Q# supports many of the classical debugging techniques programmers are familiar with, as well as those that are quantum-specific.</span></span> <span data-ttu-id="8c982-113">Ilyenek például az egységtesztek létrehozása és futtatása Q#-ban, a kódban szereplő értékekre és valószínűségekre vonatkozó *helyességi feltételek* beágyazása, valamint azok a `Dump` függvények, amelyek a célszámítógépek állapotát adják vissza.</span><span class="sxs-lookup"><span data-stu-id="8c982-113">These include creating and running unit tests in Q#, embedding *assertions* on values and probabilities in your code, and the `Dump` functions which output the states of target machines.</span></span> 
    <span data-ttu-id="8c982-114">Az utóbbi használható a teljes körű funkciókkal rendelkező szimulátor mellett a számítások bizonyos részeinek hibakereséséhez, bizonyos kvantumkorlátozások – például a [másolhatatlansági tétel](xref:microsoft.quantum.concepts.pauli) – megkerülésével.</span><span class="sxs-lookup"><span data-stu-id="8c982-114">The latter can be used alongside our full-state simulator to debug certain parts of computations by skirting some quantum limitations, for example, the [no-cloning theorem](xref:microsoft.quantum.concepts.pauli).</span></span>

### <a name="quantum-simulators-and-resource-estimators"></a><span data-ttu-id="8c982-115">Kvantumszimulátorok és erőforrásbecslők</span><span class="sxs-lookup"><span data-stu-id="8c982-115">Quantum Simulators and Resource Estimators</span></span>

- <span data-ttu-id="8c982-116">[Kvantumszimulátorok és gazdaalkalmazások](xref:microsoft.quantum.machines): A különböző elérhető szimulátorok, valamint a gazdaprogramok és a célgépek Q#-programok futtatásához való együttműködésének áttekintése.</span><span class="sxs-lookup"><span data-stu-id="8c982-116">[Quantum simulators and host applications](xref:microsoft.quantum.machines): An overview of the different simulators available, as well of how host programs and target machines work together to run Q# programs.</span></span>

- <span data-ttu-id="8c982-117">[Teljes körű funkciókkal rendelkező szimulátor](xref:microsoft.quantum.machines.full-state-simulator): A teljes kvantumállapotot szimuláló célgép.</span><span class="sxs-lookup"><span data-stu-id="8c982-117">[Full state simulator](xref:microsoft.quantum.machines.full-state-simulator): The target machine which simulates the full quantum state.</span></span> <span data-ttu-id="8c982-118">Hasznos a kisebb méretezésű (kevesebb mint pár tucat qubitból álló) programok teljes futtatásához vagy hibakereséséhez.</span><span class="sxs-lookup"><span data-stu-id="8c982-118">Useful for fully running or debugging smaller-scale programs (less than a few dozen qubits)</span></span>

- <span data-ttu-id="8c982-119">[Erőforrásbecslő](xref:microsoft.quantum.machines.resources-estimator): Megbecsüli a Q#-művelet adott példányának a kvantumszámítógépen való futtatásához szükséges erőforrásokat.</span><span class="sxs-lookup"><span data-stu-id="8c982-119">[Resources estimator](xref:microsoft.quantum.machines.resources-estimator): Estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>

- <span data-ttu-id="8c982-120">[Nyomkövetési szimulátor](xref:microsoft.quantum.machines.qc-trace-simulator.intro): A kvantumszámítógép állapotának tényleges szimulálása nélkül futtat kvantumprogramokat, így több ezer qubitet használó kvantumprogramok futtatására is képes.</span><span class="sxs-lookup"><span data-stu-id="8c982-120">[Trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro): Runs a quantum program without actually simulating the state of a quantum computer, and therefore can run quantum programs that use thousands of qubits.</span></span> <span data-ttu-id="8c982-121">Hasznos kvantumprogramban lévő klasszikus kódok hibakeresésekor, valamint a szükséges erőforrások megbecsülésekor.</span><span class="sxs-lookup"><span data-stu-id="8c982-121">Useful for debugging classical code within a quantum program, as well as estimating resources required.</span></span>

- <span data-ttu-id="8c982-122">[Toffoli-szimulátor](xref:microsoft.quantum.machines.toffoli-simulator): Egy speciális célú kvantumszimulátor, amely használható több millió qubittel, de csak korlátozott kvantumművelet-készletet – X, CNOT, több elem által vezérelt X műveletek – tartalmazó programok esetében.</span><span class="sxs-lookup"><span data-stu-id="8c982-122">[Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator): A special-purpose quantum simulator that can be used with millions of qubits, but only for programs with a restricted set of quantum operations - X, CNOT, and multi-controlled X.</span></span>

### <a name="quick-reference-pages"></a><span data-ttu-id="8c982-123">Gyorsútmutató-oldalak</span><span class="sxs-lookup"><span data-stu-id="8c982-123">Quick Reference Pages</span></span>

- <span data-ttu-id="8c982-124">[IQ# Magic parancsok](xref:microsoft.quantum.guide.quickref.iqsharp): IQ# Magic parancsok Q# Jupyter-notebookokhoz – Gyorsútmutató-oldal.</span><span class="sxs-lookup"><span data-stu-id="8c982-124">[IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp): Quick reference page for IQ# magic commands within Q# Jupyter Notebooks.</span></span>
