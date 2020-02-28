---
title: 'Helyi változók – Q # technikák'
description: 'Megtudhatja, hogyan határozhat meg és dolgozhat fel helyi változókat a Q # használatával.'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.local-variables
ms.openlocfilehash: cb6c662137c31a13c3dd6e9ca3f67879c469f788
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906865"
---
# <a name="local-variables"></a><span data-ttu-id="1aa67-103">Helyi változók</span><span class="sxs-lookup"><span data-stu-id="1aa67-103">Local Variables</span></span> #

<span data-ttu-id="1aa67-104">A Q # bármelyik típusának értéke hozzárendelhető egy változóhoz egy műveleten vagy függvényen belül az `let` kulcsszó használatával.</span><span class="sxs-lookup"><span data-stu-id="1aa67-104">A value of any type in Q# can be assigned to a variable for reuse within an operation or function by using the `let` keyword.</span></span>
<span data-ttu-id="1aa67-105">Például:</span><span class="sxs-lookup"><span data-stu-id="1aa67-105">For instance:</span></span>

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

<span data-ttu-id="1aa67-106">Ez a Pauli-operátorok egy adott tömbjét rendeli hozzá egy `measurementOperator`nevű változóhoz.</span><span class="sxs-lookup"><span data-stu-id="1aa67-106">This assigns a particular array of Pauli operators to a variable called `measurementOperator`.</span></span>

> [!TIP]
> <span data-ttu-id="1aa67-107">Ne feledje, hogy nem kell explicit módon megadnia az új változó típusát, mivel a `let` utasítás jobb oldalán lévő kifejezés nem egyértelmű, és a típust a fordító következteti ki.</span><span class="sxs-lookup"><span data-stu-id="1aa67-107">Note that we did not need to explicitly specify the type of our new variable, as the expression on the right-hand side of the `let` statement is unambiguous and the type is inferred by the compiler.</span></span> 

<span data-ttu-id="1aa67-108">A Q # változói nem *változtathatók*meg, ami azt jelenti, hogy ha egy változót ily módon definiáltak, akkor már nem módosítható semmilyen módon.</span><span class="sxs-lookup"><span data-stu-id="1aa67-108">Variables in Q# are *immutable*, meaning that once a variable has been defined in this way, it can no longer be changed in any way.</span></span>
<span data-ttu-id="1aa67-109">Ez számos hasznos optimalizálást tesz lehetővé, beleértve a változók `Adjoint` változatának átrendezésére szolgáló klasszikus logika optimalizálását.</span><span class="sxs-lookup"><span data-stu-id="1aa67-109">This allows for several beneficial optimizations, including optimization of the classical logic acting on variables to be reordered for applying the `Adjoint` variant of an operation.</span></span>

<span data-ttu-id="1aa67-110">A `let` kötés használatával meghatározott változók egy adott hatókörön belül helyiek, például egy művelet törzse vagy egy `for` hurok tartalma.</span><span class="sxs-lookup"><span data-stu-id="1aa67-110">Variables defined using the `let` binding as above are local to a particular scope, such as the body of an operation or the contents of a `for` loop.</span></span>


## <a name="mutability"></a><span data-ttu-id="1aa67-111">Változékonyság</span><span class="sxs-lookup"><span data-stu-id="1aa67-111">Mutability</span></span> ##

<span data-ttu-id="1aa67-112">A `let`-vel való változó létrehozásának alternatívájaként a `mutable` kulcsszó egy speciális, módosítható változót hoz létre, amely újra köthető az `set` kulcsszó használatával.</span><span class="sxs-lookup"><span data-stu-id="1aa67-112">As an alternative to creating a variable with `let`, the `mutable` keyword will create a special mutable variable that can be re-bound after it is initially created by using the `set` keyword.</span></span>

```qsharp
operation RandomInts(maxInt : Int, nrSamples : Int) : Int[] {
    mutable samples = new Int[0];
    for (i in 1 .. nrSamples) {
        set samples += [RandomInt(maxInt)];
    }
    return samples;
}
```

<span data-ttu-id="1aa67-113">A Q # összes típusa, beleértve a tömböket, az érték szemantikai követése.</span><span class="sxs-lookup"><span data-stu-id="1aa67-113">All types in Q#, including arrays, follow value semantics.</span></span> <span data-ttu-id="1aa67-114">Különösen nem lehetséges a tömb elemeinek frissítése.</span><span class="sxs-lookup"><span data-stu-id="1aa67-114">In particular, it is not possible to update array items.</span></span> <span data-ttu-id="1aa67-115">Egy meglévő tömb módosításához a másolási és frissítési mechanizmust is ugyanúgy kell kihasználnia, mint a rekordokban F#.</span><span class="sxs-lookup"><span data-stu-id="1aa67-115">To modify an existing array requires leveraging a copy-and-update mechanism much like the one for records in F#.</span></span> <span data-ttu-id="1aa67-116">A [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays)által biztosított tömbökhöz tartozó függvénytár-eszközök használatával például egyszerűen definiálhat egy olyan függvényt, amely Paulis tömböt ad vissza, ahol a Pauli at index `i` a megadott értéket és az összes többi bejegyzést az identitás:</span><span class="sxs-lookup"><span data-stu-id="1aa67-116">Using the library tools for arrays provided in [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays), we can e.g. easily define a function that returns an array of Paulis where the Pauli at index `i` takes the given value and all other entries are the identity:</span></span> 

```qsharp
function EmbedPauli (pauli : Pauli, i : Int, n : Int) : Pauli[] {
    
    let arr = ConstantArray(n, PauliI); // creates an array of filled with PauliI
    return arr w/ i <- pauli; // constructs a new array based on arr except that entry i is set to pauli
}
```

<span data-ttu-id="1aa67-117">A Q # utasítások és kifejezések megvitatásakor további tudnivalókat fogunk kidolgozni a tömbök használatáról.</span><span class="sxs-lookup"><span data-stu-id="1aa67-117">We will elaborate more on how to work with arrays when discussing Q# statements and expressions.</span></span> 

<span data-ttu-id="1aa67-118">A Q # változékonyság egy olyan fogalom, amely típus vagy érték helyett *szimbólumra* vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="1aa67-118">Mutability within Q# is a concept that applies to a *symbol* rather than a type or value.</span></span> <span data-ttu-id="1aa67-119">Pontosabban nem rendelkezik a típusrendszer, implicit módon vagy explicit módon, valamint attól, hogy a kötés módosítható-e (ahogy azt a `mutable` kulcsszó jelezte) vagy a nem változtatható (ahogyan az `let`) nem változtatja meg a kötött változó (k) típusát.</span><span class="sxs-lookup"><span data-stu-id="1aa67-119">Specifically, it does not have a representation in the type system, implicitly or explicitly, and whether or not a binding is mutable (as indicated by the `mutable` keyword) or immutable (as indicated by `let`) does not change the type of the bound variable(s).</span></span> <span data-ttu-id="1aa67-120">Ez fontos módszert kínál a változékonyság elkülönítésére a speciális funkciókon és műveleteken belül.</span><span class="sxs-lookup"><span data-stu-id="1aa67-120">This provides an important way to isolate mutability inside specialized functions and operations.</span></span>
<span data-ttu-id="1aa67-121">Különösen annak ellenére, hogy egy változtatható változót használó művelethez adjoint specializáció nem hozható létre automatikusan, az automatikus generálás jól működik a változékonyság-t használó függvényt meghívó művelethez.</span><span class="sxs-lookup"><span data-stu-id="1aa67-121">In particular, even though an adjoint specialization for an operation which uses a mutable variable cannot be auto-generated, auto-generation works fine for an operation calling a function which uses mutability.</span></span>
<span data-ttu-id="1aa67-122">Ezért célszerű olyan függvényeket és műveleteket készíteni, amelyek a lehető legrövidebb és kompakt változékonyság használják, így a kvantum-program többi része megváltoztathatatlan változók használatával is írható.</span><span class="sxs-lookup"><span data-stu-id="1aa67-122">For this reason, it is a good practice to make functions and operations which use mutability as short and compact as possible, so that the rest of the quantum program can be written using ordinary immutable variables.</span></span>


## <a name="deconstruction"></a><span data-ttu-id="1aa67-123">Dekonstrukció</span><span class="sxs-lookup"><span data-stu-id="1aa67-123">Deconstruction</span></span> ##

<span data-ttu-id="1aa67-124">Egyetlen változó hozzárendelésén kívül a `let` és `mutable` kulcsszavakat – vagy valójában bármilyen más kötési összeállítást is – lehetővé teszi egy [rekord típusú](xref:microsoft.quantum.language.type-model#tuple-types)tartalom kicsomagolását.</span><span class="sxs-lookup"><span data-stu-id="1aa67-124">In addition to assigning a single variable, the `let` and `mutable` keywords - or in fact any other binding construct - also allow for unpacking the contents of a [tuple type](xref:microsoft.quantum.language.type-model#tuple-types).</span></span>
<span data-ttu-id="1aa67-125">Az űrlap kiosztása a rekord elemeinek *kiépítése* .</span><span class="sxs-lookup"><span data-stu-id="1aa67-125">An assignment of this form is said to *deconstruct* the elements of that tuple.</span></span>
<span data-ttu-id="1aa67-126">Ha például egy rekordban egy Hamilton egy kifejezést modellezünk, akkor a dekonstrukcióval elérheti azokat a különböző adattípusokat, amelyekre az adott időszak alatt szimulálni kell:</span><span class="sxs-lookup"><span data-stu-id="1aa67-126">For instance, if we model a term in a Hamiltonian by a tuple, then we can use deconstruction to access the different data that we need to simulate under that term:</span></span>

```qsharp
// Represents H = 3.1 X_0 Z_1.
let (_, (paulis, idxQubits)) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // paulis and idxQubits are both immutable variables
mutable ((c1, c2), _) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // c1 and c2 are both mutable variables
```


