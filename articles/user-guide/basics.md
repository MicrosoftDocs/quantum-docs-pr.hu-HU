---
title: Q# Alapjai
description: Alapvető fogalmak Q#
author: gillenhaalb
ms.author: a-gibec
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
no-loc:
- Q#
- $$v
ms.openlocfilehash: 86f6538cf383f4e7c14255b38cfb1c141c8f991b
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835519"
---
# <a name="no-locq-basics"></a><span data-ttu-id="bda47-103">Q# Alapjai</span><span class="sxs-lookup"><span data-stu-id="bda47-103">Q# Basics</span></span>

<span data-ttu-id="bda47-104">Ez a cikk röviden bemutatja a alapszintű építőelemeit Q# .</span><span class="sxs-lookup"><span data-stu-id="bda47-104">This article presents a brief introduction to the basic building blocks of Q#.</span></span>

<span data-ttu-id="bda47-105">A mi Q# [az Q# ?](xref:microsoft.quantum.overview.q-sharp)című témakörből megtudhatja, hogy mi az, és hol illeszkedik a Quantum Development Kit alapvető összetevőjéhez.</span><span class="sxs-lookup"><span data-stu-id="bda47-105">For an overview of what Q# is and where it fits in as a fundamental component of the Quantum Development Kit, see [What is Q#?](xref:microsoft.quantum.overview.q-sharp).</span></span> 

## <a name="what-is-a-quantum-program"></a><span data-ttu-id="bda47-106">Mi az a Quantum program?</span><span class="sxs-lookup"><span data-stu-id="bda47-106">What is a quantum program?</span></span>

<span data-ttu-id="bda47-107">Technikai szempontból a Quantum program a klasszikus alrutinok egy adott készlete, amely a híváskor bizonyos műveleteket hajt végre a kvantum-rendszeren.</span><span class="sxs-lookup"><span data-stu-id="bda47-107">From a technical perspective, a quantum program is a particular set of classical subroutines which, when called, perform certain operations on a quantum system.</span></span>
<span data-ttu-id="bda47-108">Ennek a nézetnek a fontos következménye, hogy egy Q# program nem maga közvetlenül modellezi a qubits, hanem azt is leírja, hogyan kommunikál a klasszikusan vezérelt számítógépek a qubits.</span><span class="sxs-lookup"><span data-stu-id="bda47-108">An important consequence of that view is that a Q# program does not directly model qubits themselves, but rather describes how a classically controlled computer interacts with those qubits.</span></span>
<span data-ttu-id="bda47-109">A kialakítás szerint a nem Q# határozza meg a kvantum-állapotokat vagy a kvantummechanika egyéb tulajdonságait közvetlenül.</span><span class="sxs-lookup"><span data-stu-id="bda47-109">By design, Q# does not define quantum states or other properties of quantum mechanics directly.</span></span>
<span data-ttu-id="bda47-110">Vegyük például a {0} {1} {2} [Quantum Computing fogalmakat](xref:microsoft.quantum.concepts.intro) ismertető útmutatóban a $ \ket{+} = \left (\ket + \ket \right)/\sqrt $ állapotot.</span><span class="sxs-lookup"><span data-stu-id="bda47-110">For instance, consider the state $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ discussed in the [Quantum Computing Concepts](xref:microsoft.quantum.concepts.intro) guide.</span></span>
<span data-ttu-id="bda47-111">Ha ezt az állapotot szeretné előkészíteni a alkalmazásban Q# , kezdje azzal a ténnyel, hogy a qubits a $ \ket {0} $ állapotban inicializálják, és hogy a $ \ket{+} = H\ket {0} $, ahol a $H $ a [ `H` művelet](xref:microsoft.quantum.intrinsic.h)által megvalósított [Hadamard-transzformáció](xref:microsoft.quantum.glossary#hadamard).</span><span class="sxs-lookup"><span data-stu-id="bda47-111">To prepare this state in Q#, start with the facts that the qubits are initialized in the $\ket{0}$ state, and that $\ket{+} = H\ket{0}$, where $H$ is the [Hadamard transform](xref:microsoft.quantum.glossary#hadamard), implemented by the [`H` operation](xref:microsoft.quantum.intrinsic.h).</span></span> <span data-ttu-id="bda47-112">A Q# qubit inicializálásához és átalakításához szükséges alapszintű kód a következőképpen néz ki:</span><span class="sxs-lookup"><span data-stu-id="bda47-112">The basic Q# code to initialize and transform a qubit, then, looks like this:</span></span>

```qsharp
using (qubit = Qubit()) {
    // At this point, the qubit is in the state |0⟩.
    H(qubit);
    // H is now applied, such that the qubit is in H|0⟩ = |+⟩, as desired.
}
```
<span data-ttu-id="bda47-113">A qubits inicializálásával és *lefoglalásával*kapcsolatos további információkért lásd: [a qubits használata](xref:microsoft.quantum.guide.qubits).</span><span class="sxs-lookup"><span data-stu-id="bda47-113">For more information on initializing, or *allocating*, qubits, see [Working with qubits](xref:microsoft.quantum.guide.qubits).</span></span>

## <a name="quantum-states-in-no-locq"></a><span data-ttu-id="bda47-114">Quantum állapotok a-ben Q#</span><span class="sxs-lookup"><span data-stu-id="bda47-114">Quantum states in Q#</span></span>

<span data-ttu-id="bda47-115">Fontos, hogy az előző program nem hivatkozik explicit módon az állapotra, Q# de azt is ismerteti, hogy a program hogyan *alakította át* az állapotot.</span><span class="sxs-lookup"><span data-stu-id="bda47-115">Importantly, the previous program does not explicitly refer to the state within Q# but described how our program *transformed* the state.</span></span>
<span data-ttu-id="bda47-116">Ezzel a megközelítéssel teljesen agnosztikus lehet arról, hogy mi *is az egyes* célszámítógépen a kvantum-állapot, ami eltérő értelmezésekkel rendelkezhet a számítógéptől függően.</span><span class="sxs-lookup"><span data-stu-id="bda47-116">With this approach, you can be entirely agnostic about what a quantum state even *is* on each target machine, which might have different interpretations depending on the machine.</span></span> 

<span data-ttu-id="bda47-117">Egy Q# program nem tud betekintést qubit állapotára.</span><span class="sxs-lookup"><span data-stu-id="bda47-117">A Q# program cannot introspect into the state of a qubit.</span></span>
<span data-ttu-id="bda47-118">Ehelyett egy program olyan műveleteket hívhat meg, mint például a [`Measure`](xref:microsoft.quantum.intrinsic.measure) qubit származó információk megismerése, és olyan műveletek hívása, mint például a [`X`](xref:microsoft.quantum.intrinsic.x) és a [`H`](xref:microsoft.quantum.intrinsic.h) qubit állapotának elvégzése.</span><span class="sxs-lookup"><span data-stu-id="bda47-118">Instead, a program can call operations such as [`Measure`](xref:microsoft.quantum.intrinsic.measure) to learn information from a qubit, and call operations such as [`X`](xref:microsoft.quantum.intrinsic.x) and [`H`](xref:microsoft.quantum.intrinsic.h) to act on the state of a qubit.</span></span>
<span data-ttu-id="bda47-119">Ezeket a *műveleteket ténylegesen csak* az adott program futtatására használt célszámítógép végzi Q# .</span><span class="sxs-lookup"><span data-stu-id="bda47-119">What these operations actually *do* is only made concrete by the target machine used to run the particular Q# program.</span></span>
<span data-ttu-id="bda47-120">Ha például a programot a [teljes állapotú szimulátoron](xref:microsoft.quantum.machines.full-state-simulator)futtatja, a szimulátor a szimulált kvantum-rendszernek megfelelő matematikai műveleteket hajtja végre.</span><span class="sxs-lookup"><span data-stu-id="bda47-120">For example, if running the program on our [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), the simulator performs the corresponding mathematical operations to the simulated quantum system.</span></span>
<span data-ttu-id="bda47-121">De a jövő irányába szemlélve, amikor a célszámítógép egy valódi kvantum-számítógép, az ilyen műveletek meghívásával a Q# kvantum-számítógép a *valódi* kvantumrendszer megfelelő *valós* műveleteinek elvégzésére, például pontosan időzített lézeres impulzusokra irányítja a rendszert.</span><span class="sxs-lookup"><span data-stu-id="bda47-121">But looking toward the future, when the target machine is a real quantum computer, calling such operations in Q# directs the quantum computer to perform the corresponding *real* operations on the *real* quantum system, for example, precisely timed laser pulses).</span></span>

<span data-ttu-id="bda47-122">A Q# program újrakombinálja ezeket a műveleteket a célszámítógép által meghatározott módon, hogy új, magasabb szintű műveleteket hozzon létre a kvantum-számításokhoz.</span><span class="sxs-lookup"><span data-stu-id="bda47-122">A Q# program recombines these operations as defined by a target machine to create new, higher-level operations to express quantum computation.</span></span>
<span data-ttu-id="bda47-123">Ily módon megkönnyíti Q# a Quantum és a hibrid kvantum – klasszikus algoritmusok kiépítését, valamint a célszámítógép vagy szimulátor struktúrájára vonatkozó általános szempontokat is.</span><span class="sxs-lookup"><span data-stu-id="bda47-123">In this way, Q# makes it easy to express the logic underlying quantum and hybrid quantum–classical algorithms, while also being general with respect to the structure of a target machine or simulator.</span></span>

## <a name="no-locq-operations-and-functions"></a><span data-ttu-id="bda47-124">Q# műveletek és függvények</span><span class="sxs-lookup"><span data-stu-id="bda47-124">Q# operations and functions</span></span>

<span data-ttu-id="bda47-125">Konkrétan a Q# program a *műveleteket*, a *függvényeket*és bármely felhasználó által definiált típust magában foglalja.</span><span class="sxs-lookup"><span data-stu-id="bda47-125">Concretely, a Q# program comprises *operations*, *functions*, and any user-defined types.</span></span> 

<span data-ttu-id="bda47-126">A műveletek a kvantum-rendszerek átalakításának leírására szolgálnak, és a programok legalapvetőbb építőelemei Q# .</span><span class="sxs-lookup"><span data-stu-id="bda47-126">Operations are used to describe the transformations of quantum systems and are the most fundamental building block of Q# programs.</span></span> <span data-ttu-id="bda47-127">Előfordulhat, hogy a ben definiált minden művelet Q# tetszőleges számú egyéb műveletet hív meg.</span><span class="sxs-lookup"><span data-stu-id="bda47-127">Each operation defined in Q# may then call any number of other operations.</span></span>

<span data-ttu-id="bda47-128">A műveletekkel szemben a functions a tisztán *determinisztikus* klasszikus viselkedés leírására szolgál, és nem gyakorol semmilyen hatást a klasszikus számítástechnikai értékek mellett.</span><span class="sxs-lookup"><span data-stu-id="bda47-128">In contrast to operations, functions are used to describe purely *deterministic* classical behavior and do not have any effects besides computing classical values.</span></span> <span data-ttu-id="bda47-129">Tegyük fel például, hogy egy program végén szeretné mérni a qubits, és hozzáadja a mérési eredményeket egy tömbhöz.</span><span class="sxs-lookup"><span data-stu-id="bda47-129">For example, suppose you want to measure the qubits at the end of a program and add the measurement results to an array.</span></span>
<span data-ttu-id="bda47-130">Ebben az esetben `Measure` egy *művelet* , amely arra utasítja a célszámítógépet, hogy a (valós vagy szimulált) qubits mérést végezzen.</span><span class="sxs-lookup"><span data-stu-id="bda47-130">In this case, `Measure` is an *operation* that instructs the target machine to perform a measurement on the (real or simulated) qubits.</span></span> <span data-ttu-id="bda47-131">Ugyanakkor a *functions* kezeli a visszaadott eredmények tömbbe való felvételének klasszikus folyamatát.</span><span class="sxs-lookup"><span data-stu-id="bda47-131">At the same time, *functions* handle the classical process of adding the returned results to an array.</span></span>

<span data-ttu-id="bda47-132">A műveletek és a függvények együtt *callables*néven ismertek.</span><span class="sxs-lookup"><span data-stu-id="bda47-132">Together, operations and functions are known as *callables*.</span></span> <span data-ttu-id="bda47-133">A rendszer az alapul szolgáló struktúrát és viselkedést is bevezeti és részletezi a [alkalmazásban Q# ](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="bda47-133">Their underlying structure and behavior are introduced and detailed in [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span>


## <a name="no-locq-syntax-overview"></a><span data-ttu-id="bda47-134">Q# szintaxis áttekintése</span><span class="sxs-lookup"><span data-stu-id="bda47-134">Q# syntax overview</span></span>

<span data-ttu-id="bda47-135">A nyelv szintaxisa a szintaktikai módon helyes programot alkotó szimbólumok különböző kombinációit írja le.</span><span class="sxs-lookup"><span data-stu-id="bda47-135">The syntax of a language describes the different combinations of symbols that form a syntactically correct program.</span></span>
<span data-ttu-id="bda47-136">A alkalmazásban a Q# szintaktikai elemek három különböző csoportba sorolhatók: típusok, kifejezések és utasítások.</span><span class="sxs-lookup"><span data-stu-id="bda47-136">In Q#, syntax elements are classified into three different groups: types, expressions, and statements.</span></span>

### <a name="types"></a><span data-ttu-id="bda47-137">Típusok</span><span class="sxs-lookup"><span data-stu-id="bda47-137">Types</span></span>
<span data-ttu-id="bda47-138">Q# a egy erősen gépelt nyelv, amely lehetővé teszi, hogy a típusok körültekintő használata segíthet a fordítónak a programokkal kapcsolatos erős garanciák biztosításában a Q# fordítási idő alatt.</span><span class="sxs-lookup"><span data-stu-id="bda47-138">Q# is a strongly-typed language, such that careful use of types can help the compiler provide strong guarantees about Q# programs at compile time.</span></span>
<span data-ttu-id="bda47-139">A standard és a kvantum-specifikus beépített primitív típusok (például,,, `Int` `Bool` és) mellett a `Qubit` `Result` Q# felhasználó által definiált típusokhoz is támogatást biztosít.</span><span class="sxs-lookup"><span data-stu-id="bda47-139">In addition to standard and quantum-specific built-in primitive types, for example, `Int`, `Bool`, `Qubit`, and `Result`, Q# provides support for user-defined types.</span></span>

<span data-ttu-id="bda47-140">Az összes primitív típus leírását, a tömb-és a rekordos típusok részleteit, valamint az új típusok fájlon belüli definiálásának lépéseit a következő Q# témakörben talál [ Q# ](xref:microsoft.quantum.guide.types):.</span><span class="sxs-lookup"><span data-stu-id="bda47-140">For descriptions of all the primitive types, details for array and tuple types, and steps to define new types within a Q# file, see [Types in Q#](xref:microsoft.quantum.guide.types).</span></span>

### <a name="expressions"></a><span data-ttu-id="bda47-141">Kifejezések</span><span class="sxs-lookup"><span data-stu-id="bda47-141">Expressions</span></span>
<span data-ttu-id="bda47-142">A programozási nyelv kifejezése egy vagy több állandó, változó, operátor és függvény kombinációja, amelyet a programozási nyelv értelmez és kiértékel egy adott értékre.</span><span class="sxs-lookup"><span data-stu-id="bda47-142">An expression in a programming language is a combination of one or more constants, variables, operators, and functions that the programming language interprets and evaluates to a specific value.</span></span>
<span data-ttu-id="bda47-143">A legtöbb esetben a nyelv minden típusához az adott típusú kifejezés lehet *literál* vagy szimbólum, amely egy adott típusú értékhez van kötve.</span><span class="sxs-lookup"><span data-stu-id="bda47-143">Most simply, for every type in a language, expressions of that type can be either *literals* or symbols bound to a value of that type.</span></span>
<span data-ttu-id="bda47-144">Például `5` egy `Int` literál (azaz típusú kifejezés `Int` ), és ha a szimbólum az `count` egész értékhez van kötve `5` , akkor az `count` egész szám kifejezés is.</span><span class="sxs-lookup"><span data-stu-id="bda47-144">For example, `5` is an `Int` literal (thus also an expression of type `Int`), and if the symbol `count` is bound to the integer value `5`, then `count` is also an integer expression.</span></span>

<span data-ttu-id="bda47-145">Egy kifejezés továbbá tartalmazhat más, bizonyos operátorok által összevont kifejezéseket is.</span><span class="sxs-lookup"><span data-stu-id="bda47-145">Additionally, an expression can consist of other expressions combined by certain operators.</span></span>
<span data-ttu-id="bda47-146">Például egy másik `Int` kifejezés, amely kiértékeli a következőt: `5` `2+3` .</span><span class="sxs-lookup"><span data-stu-id="bda47-146">For example, another `Int` expression that evaluates to `5` is `2+3`.</span></span>

<span data-ttu-id="bda47-147">A kifejezésekkel és a kompatibilis operátorokkal kapcsolatos további információkért Q# lásd: [kifejezések Q# beírása a alkalmazásban ](xref:microsoft.quantum.guide.expressions).</span><span class="sxs-lookup"><span data-stu-id="bda47-147">For more information about expressions and compatible operators in Q#, see [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions).</span></span> 

### <a name="statements"></a><span data-ttu-id="bda47-148">Utasítások</span><span class="sxs-lookup"><span data-stu-id="bda47-148">Statements</span></span> 
<span data-ttu-id="bda47-149">Az utasítás egy kötelező programozási nyelv szintaktikai egysége, amely némi művelet elvégzését fejezi ki. Az utasításokban szereplő kifejezések kontrasztja nem adja vissza az eredményeket, és kizárólag azok mellékhatásait futtatja.</span><span class="sxs-lookup"><span data-stu-id="bda47-149">A statement is a syntactic unit of an imperative programming language that expresses some action to carry out. Statements contrast with expressions in that statements do not return results and are run solely for their side effects.</span></span> <span data-ttu-id="bda47-150">A kifejezések azonban mindig visszaadnak egy eredményt, és gyakran nincsenek mellékhatásai.</span><span class="sxs-lookup"><span data-stu-id="bda47-150">Expressions, however, always return a result and often do not have any side effects.</span></span> <span data-ttu-id="bda47-151">Röviden, az Q# utasítások futnak, míg a kifejezések kiértékelése megtörténik.</span><span class="sxs-lookup"><span data-stu-id="bda47-151">In short, Q# statements are run, while expressions are evaluated.</span></span>

<span data-ttu-id="bda47-152">Egy utasítás egyszerű példája egy Q# szimbólum társítása egy kifejezéshez:</span><span class="sxs-lookup"><span data-stu-id="bda47-152">A simple example of a statement in Q# is assigning a symbol to an expression:</span></span>
```qsharp
let count = 5;
```

<span data-ttu-id="bda47-153">Érdekes példa az `for` iterációt támogató utasítás, amely egy *utasítási blokkot*tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="bda47-153">A more interesting example is the `for` statement which supports iteration and includes a *statement block*.</span></span>
<span data-ttu-id="bda47-154">Tegyük fel, `qubits` hogy a szimbólum a qubits (technika típusa `Qubit[]` vagy típusú tömb) egy regiszteréhez van kötve `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="bda47-154">Suppose `qubits` is the symbol bound to a register of qubits (technically of type `Qubit[]`, or an array of `Qubit` types).</span></span> <span data-ttu-id="bda47-155">Majd</span><span class="sxs-lookup"><span data-stu-id="bda47-155">Then</span></span>
```qsharp
for (qubit in qubits) {
    H(qubit);
}
```
<span data-ttu-id="bda47-156">a egy olyan utasítás, amely a regisztráció minden qubit megismétli a műveletet, és mindegyiken végrehajtja a `H` műveletet.</span><span class="sxs-lookup"><span data-stu-id="bda47-156">is a statement that iterates over each qubit in the register, performing the `H` operation on each one.</span></span> <span data-ttu-id="bda47-157">Vegye figyelembe, hogy `H(qubit);` egy utasítás önmagában is szerepel.</span><span class="sxs-lookup"><span data-stu-id="bda47-157">Note that `H(qubit);` is a statement in itself as well.</span></span>

<span data-ttu-id="bda47-158">Bármilyen típusú hívási kifejezést használhat `Unit` (a `Unit` típus nem ad vissza adatokat) utasításként.</span><span class="sxs-lookup"><span data-stu-id="bda47-158">You can use any call expression of type `Unit` (a `Unit` type does not return any information) as a statement.</span></span>
<span data-ttu-id="bda47-159">Ez a típusú kifejezés akkor hasznos, ha olyan qubits-műveleteket hív meg, amelyek visszaadnak, `Unit` mert az utasítás célja az implicit kvantum állapotának módosítása.</span><span class="sxs-lookup"><span data-stu-id="bda47-159">This type of expression is useful when calling operations on qubits that return `Unit` because the purpose of the statement is to modify the implicit quantum state.</span></span>
<span data-ttu-id="bda47-160">A kifejezés-értékelési utasításokhoz pontosvesszőt kell lezárni.</span><span class="sxs-lookup"><span data-stu-id="bda47-160">Expression evaluation statements require a terminating semicolon.</span></span>

<span data-ttu-id="bda47-161">A utasítások segítségével szinte minden aspektusát felépítheti egy Q# programba, és egyetlen oldal sem terjedhet ki a rájuk vonatkozó összes információra.</span><span class="sxs-lookup"><span data-stu-id="bda47-161">You use statements to build nearly every aspect of a Q# program, and no single page could encompass all the information relating to them.</span></span>
<span data-ttu-id="bda47-162">További információ a lexikális szerkezetről és a formázásról: a [ Q# fájl szerkezete](xref:microsoft.quantum.guide.filestructure); a szimbólum-kötési hozzárendeléshez és a hatókörhöz lásd: [változók Q# a ](xref:microsoft.quantum.guide.variables)alkalmazásban, valamint vezérlési folyamati hurkok `for` , például: [ Q# vezérlési ](xref:microsoft.quantum.guide.controlflow)folyamat.</span><span class="sxs-lookup"><span data-stu-id="bda47-162">For more information about their lexical structure and formatting, see [Q# File Structure](xref:microsoft.quantum.guide.filestructure); for symbol binding assignment and scope, see [Variables in Q#](xref:microsoft.quantum.guide.variables); and for control flow loops such as `for`, see [Control Flow in Q#](xref:microsoft.quantum.guide.controlflow).</span></span>

## <a name="next-steps"></a><span data-ttu-id="bda47-163">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="bda47-163">Next steps</span></span>

<span data-ttu-id="bda47-164">Megkezdheti [a típusok Q# megismerését a alkalmazásban ](xref:microsoft.quantum.guide.types).</span><span class="sxs-lookup"><span data-stu-id="bda47-164">Start learning about [Types in Q#](xref:microsoft.quantum.guide.types).</span></span>

<span data-ttu-id="bda47-165">További információ az alapokról és a motivációról Q# : [Miért van szükségünk Q# ?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).</span><span class="sxs-lookup"><span data-stu-id="bda47-165">For more background about the foundations and motivation behind Q#, see [Why do we need Q#?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).</span></span>
