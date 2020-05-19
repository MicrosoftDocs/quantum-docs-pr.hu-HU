---
title: A Q# használati útmutatója
description: A felhasználói útmutató céljának és tartalmának áttekintése
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
ms.openlocfilehash: f535aaedbe6ce181375d48f7023409ad8212c702
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430611"
---
# <a name="the-q-user-guide"></a><span data-ttu-id="127f4-103">A Q# használati útmutatója</span><span class="sxs-lookup"><span data-stu-id="127f4-103">The Q# User Guide</span></span>

<span data-ttu-id="127f4-104">Üdvözli Önt a Q# használati útmutatója!</span><span class="sxs-lookup"><span data-stu-id="127f4-104">Welcome to the Q# User Guide!</span></span> 

<span data-ttu-id="127f4-105">Itt részletesen ismertetjük a Q# nyelv alapvető fogalmait és az összes olyan információt, amelyre szükség lehet kvantumprogramok írásához.</span><span class="sxs-lookup"><span data-stu-id="127f4-105">Here we detail the core concepts of the Q# language and all the information you need to write quantum programs.</span></span>

## <a name="user-guide-contents"></a><span data-ttu-id="127f4-106">A felhasználói útmutató tartalma</span><span class="sxs-lookup"><span data-stu-id="127f4-106">User Guide Contents</span></span>

- <span data-ttu-id="127f4-107">A [Q# alapjai](xref:microsoft.quantum.guide.basics) szakasz a Q# programozási nyelv célját és funkcióját bemutató áttekintés.</span><span class="sxs-lookup"><span data-stu-id="127f4-107">[Q# Basics](xref:microsoft.quantum.guide.basics): an introductory overview of the purpose and functionality of the Q# programming language.</span></span> 

### <a name="q-language"></a><span data-ttu-id="127f4-108">A Q# nyelv</span><span class="sxs-lookup"><span data-stu-id="127f4-108">Q# Language</span></span>

- <span data-ttu-id="127f4-109">A [Típusok Q#-ban](xref:microsoft.quantum.guide.types) szakasz ismerteti a Q#-típusmodellt és bemutatja a típusok megadásának és használatának szintaxisát.</span><span class="sxs-lookup"><span data-stu-id="127f4-109">[Types in Q#](xref:microsoft.quantum.guide.types): lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>

- <span data-ttu-id="127f4-110">A [Típuskifejezések](xref:microsoft.quantum.guide.expressions) szakasz részletesen ismerteti az értékek megadását, hivatkozását, összevonását és üzemeltetését a Q# minden típusához.</span><span class="sxs-lookup"><span data-stu-id="127f4-110">[Type Expressions](xref:microsoft.quantum.guide.expressions): details how to specify, reference, combine, and operate on values of each type in Q#.</span></span> 

### <a name="using-q"></a><span data-ttu-id="127f4-111">A Q# használata</span><span class="sxs-lookup"><span data-stu-id="127f4-111">Using Q#</span></span>

- <span data-ttu-id="127f4-112">A [Q#-fájlstruktúra](xref:microsoft.quantum.guide.filestructure) szakasz egy `*.qs` Q#-fájl struktúráját és szintaxisát ismerteti.</span><span class="sxs-lookup"><span data-stu-id="127f4-112">[Q# File Structure](xref:microsoft.quantum.guide.filestructure): describes the structure and syntax of a `*.qs` Q# file.</span></span>

- <span data-ttu-id="127f4-113">A [Műveletek és a függvények](xref:microsoft.quantum.guide.operationsfunctions) szakasz a Q# nyelv két hívható típusát részletezi: ezek a *műveletek*, amelyek magukba foglalják a qubitregiszterek műveleteit és a *függvények*, amelyek kizárólag a klasszikus információkkal működnek.</span><span class="sxs-lookup"><span data-stu-id="127f4-113">[Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions): details the two callable types of the Q# language: *operations*, which include action on qubit registers and *functions*, which strictly work with classical information.</span></span> 
    <span data-ttu-id="127f4-114">Itt láthatja, hogyan határozhatja meg és hívhatja meg őket, beleértve a kvantumműveletek kapcsolt és vezérelt verzióit.</span><span class="sxs-lookup"><span data-stu-id="127f4-114">Here you see how to define and call them, including the adjoint and controlled versions of quantum operations.</span></span>

- <span data-ttu-id="127f4-115">A [Változók](xref:microsoft.quantum.guide.variables) szakasz a Q#-programokban lévő változók szerepét és hatékony kihasználását ismerteti.</span><span class="sxs-lookup"><span data-stu-id="127f4-115">[Variables](xref:microsoft.quantum.guide.variables): describes the role of variables within Q# programs and how to leverage them effectively.</span></span> 
    <span data-ttu-id="127f4-116">Talál például információt a hatókörök kötéséről, valamint a nem módosítható és módosítható változók közötti különbségről, illetve a hozzárendelésükről és az újbóli hozzárendelésükről.</span><span class="sxs-lookup"><span data-stu-id="127f4-116">For example, you can find information about binding scopes, as well as the difference between immutable/mutable variables and how to assign/re-assign them.</span></span>

- <span data-ttu-id="127f4-117">A [Munkavégzés qubitekkel](xref:microsoft.quantum.guide.qubits) szakasz a Q# azon funkcióit ismerteti, amelyek az egyes qubitekhez és qubitrendszerekhez használhatók.</span><span class="sxs-lookup"><span data-stu-id="127f4-117">[Working with qubits](xref:microsoft.quantum.guide.qubits): describes the features of Q# used to address individual qubits and systems of qubits.</span></span> 
    <span data-ttu-id="127f4-118">A szakasz kitér a kiosztásukra, a rajtuk végzett műveletekre és a mérésükre.</span><span class="sxs-lookup"><span data-stu-id="127f4-118">Specifically, that entails their allocation, performing operations on them, and ultimately their measurement.</span></span> 

- <span data-ttu-id="127f4-119">Az [Átvitelvezérlés](xref:microsoft.quantum.guide.controlflow) szakasz részletesen bemutatja a Q#-ban elérhető programozás-átvitelvezérlési mintákat, amelybe beletartozik számos standard technika (feltételes végrehajtás, for hurkok, while hurkok stb.), valamint a kvantumspecifikus „sikerességig ismétlődő” mintát.</span><span class="sxs-lookup"><span data-stu-id="127f4-119">[Control Flow](xref:microsoft.quantum.guide.controlflow): details the programming control flow patterns available in Q#, which includes many standard techniques (conditional execution, for loops, while loops, etc.) as well as the quantum-specific "Repeat-Until-Success" pattern.</span></span>

- <span data-ttu-id="127f4-120">A [Tesztelés és hibakeresés](xref:microsoft.quantum.guide.testingdebugging) szakasz részletesen ismertet néhány módszert, amelyek segítségével meggyőződhet róla, hogy a kódja úgy működik, ahogyan kell.</span><span class="sxs-lookup"><span data-stu-id="127f4-120">[Testing and debugging](xref:microsoft.quantum.guide.testingdebugging): details some techniques for making sure your code is doing what it is supposed to do.</span></span> 
    <span data-ttu-id="127f4-121">A kvantuminformációk általános átlátszatlansága miatt egy kvantumprogram hibakereséséhez speciális módszerekre lehet szükség.</span><span class="sxs-lookup"><span data-stu-id="127f4-121">Due to the general opacity of quantum information, debugging a quantum program can require specialized techniques.</span></span> 
    <span data-ttu-id="127f4-122">Szerencsére a Q# támogat számos, a programozok által alkalmazott klasszikus hibakeresési módszert, valamint kvantumspecifikus módszereket is.</span><span class="sxs-lookup"><span data-stu-id="127f4-122">Fortunately, Q# supports many of the classical debugging techniques programmers are used to, as well as those that are quantum-specific.</span></span> <span data-ttu-id="127f4-123">Ilyenek például az egységtesztek létrehozása/futtatása Q#-ban, a kódban szereplő értékekre és valószínűségekre vonatkozó *helyességi feltételek* beágyazása, valamint azok a `Dump` függvények, amelyek a célszámítógép állapotát adják vissza.</span><span class="sxs-lookup"><span data-stu-id="127f4-123">These include creating/running unit tests in Q#, embedding *assertions* on values and probabilities in your code, and the `Dump` functions which output the state of target machine.</span></span> 
    <span data-ttu-id="127f4-124">Az utóbbi használható a teljes körű funkciókkal rendelkező szimulátor mellett a számítások bizonyos részeinek hibakereséséhez, bizonyos kvantumkorlátozások (például a másolhatatlansági tétel) megkerülésével.</span><span class="sxs-lookup"><span data-stu-id="127f4-124">The latter can be used alongside our full-state simulator to debug certain parts of computations by skirting some quantum limitations (e.g. the no-cloning theorem).</span></span>

### <a name="quantum-simulators-and-resource-estimators"></a><span data-ttu-id="127f4-125">Kvantumszimulátorok és erőforrásbecslők</span><span class="sxs-lookup"><span data-stu-id="127f4-125">Quantum Simulators and Resource Estimators</span></span>

- <span data-ttu-id="127f4-126">[Kvantumszimulátorok és gazdaalkalmazások](xref:microsoft.quantum.machines): a különböző elérhető szimulátorok, valamint a gazdaprogram és a célgépek közötti általános végrehajtási modell áttekintése.</span><span class="sxs-lookup"><span data-stu-id="127f4-126">[Quantum simulators and host applications](xref:microsoft.quantum.machines): an overview of the different simulators available, as well as the general execution model between host program and target machines.</span></span>

- <span data-ttu-id="127f4-127">[Teljes körű funkciókkal rendelkező szimulátor](xref:microsoft.quantum.machines.full-state-simulator): a teljes kvantumállapotot szimuláló célgép.</span><span class="sxs-lookup"><span data-stu-id="127f4-127">[Full state simulator](xref:microsoft.quantum.machines.full-state-simulator): the target machine which simulates the full quantum state.</span></span> <span data-ttu-id="127f4-128">Hasznos a kisebb méretezésű (kevesebb mint pár tucat qubitból álló) programok teljes végrehajtásához vagy hibakereséséhez</span><span class="sxs-lookup"><span data-stu-id="127f4-128">Useful for fully executing or debugging smaller scale programs (less than a couple dozen qubits)</span></span>

- <span data-ttu-id="127f4-129">[Erőforrásbecslő](xref:microsoft.quantum.machines.resources-estimator): megbecsüli a Q#-művelet adott példányának a kvantumszámítógépen való futtatásához szükséges erőforrásokat.</span><span class="sxs-lookup"><span data-stu-id="127f4-129">[Resources estimator](xref:microsoft.quantum.machines.resources-estimator): estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>

- <span data-ttu-id="127f4-130">[Nyomkövetési szimulátor](xref:microsoft.quantum.machines.qc-trace-simulator.intro): végrehajt egy kvantumprogramot a kvantumszámítógép állapotának tényleges szimulálása nélkül, ezáltal végrehajthat több ezer qubitet használó kvantumprogramokat.</span><span class="sxs-lookup"><span data-stu-id="127f4-130">[Trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro): executes a quantum program without actually simulating the state of a quantum computer, and therefore can execute quantum programs that use thousands of qubits.</span></span> <span data-ttu-id="127f4-131">Hasznos kvantumprogramban lévő klasszikus kódok hibakeresésekor, valamint a szükséges erőforrások megbecsülésekor.</span><span class="sxs-lookup"><span data-stu-id="127f4-131">Useful for debugging classical code within a quantum program, as well as estimating resources required.</span></span>

- <span data-ttu-id="127f4-132">[Toffoli-szimulátor](xref:microsoft.quantum.machines.toffoli-simulator): egy speciális célú kvantumszimulátor, amely használható több millió qubittel, de csak korlátozott kvantumművelet-készletet (X, CNOT és több elem által vezérelt X műveleteket) tartalmazó programok esetében.</span><span class="sxs-lookup"><span data-stu-id="127f4-132">[Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator): a special purpose quantum simulator that can be used with millions of qubits, but only for programs with a restricted set of quantum operations (namely X, CNOT, and multi-controlled X).</span></span>

### <a name="quick-reference-pages"></a><span data-ttu-id="127f4-133">Gyorsútmutató-oldalak</span><span class="sxs-lookup"><span data-stu-id="127f4-133">Quick Reference Pages</span></span>

- <span data-ttu-id="127f4-134">[IQ# Magic parancsok](xref:microsoft.quantum.guide.quickref.iqsharp): IQ# Magic parancsok Q# Jupyter-notebookokhoz – Gyorsútmutató-oldal.</span><span class="sxs-lookup"><span data-stu-id="127f4-134">[IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp): Quick reference page for IQ# magic commands within Q# Jupyter Notebooks.</span></span>
