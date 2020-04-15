---
title: A kvantumnumerikus kódtár bemutatása | Microsoft Docs
description: A kvantumnumerikus kódtár bemutatása
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.intro
ms.openlocfilehash: efd1a712616534ac281433fc008f0983271881d7
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2020
ms.locfileid: "73442439"
---
# <a name="introduction-to-the-quantum-numerics-library"></a><span data-ttu-id="f20ca-103">A kvantumnumerikus kódtár bemutatása</span><span class="sxs-lookup"><span data-stu-id="f20ca-103">Introduction to the Quantum Numerics Library</span></span>

<span data-ttu-id="f20ca-104">Sok kvantumalgoritmus olyan [orákulumokra](xref:microsoft.quantum.concepts.oracles) támaszkodik, amelyek a bemenetek szuperpozícióján értékelnek ki matematikai függvényeket.</span><span class="sxs-lookup"><span data-stu-id="f20ca-104">Many quantum algorithms rely on [oracles](xref:microsoft.quantum.concepts.oracles) that evaluate mathematical functions on a superposition of inputs.</span></span>
<span data-ttu-id="f20ca-105">Shor algoritmusának fő összetevője például kiértékeli az $f(x) = a^x\operatorname{mod} N$ függvényt, hogy megkapja a fix $a$ értéket, amely az $N$ együtthatójának kiszámolásához szükséges szám, illetve az $x$ értéket, amely egy $2n$ qubites egész szám egységes szuperpozícióban az összes $2n$ bites sztringben.</span><span class="sxs-lookup"><span data-stu-id="f20ca-105">The main component of Shor's algorithm, for example, evaluates $f(x) = a^x\operatorname{mod} N$ for a fixed $a$, the number to factor $N$, and $x$ a $2n$-qubit integer in a uniform superposition over all $2n$-bit strings.</span></span>

<span data-ttu-id="f20ca-106">Ha Shor algoritmusát egy igazi kvantumszámítógépen szeretné futtatni, ezt a függvényt a célszámítógép natív műveleteivel kell megírni.</span><span class="sxs-lookup"><span data-stu-id="f20ca-106">To run Shor's algorithm on an actual quantum computer, this function has to be written in terms of the native operations of the target machine.</span></span>
<span data-ttu-id="f20ca-107">A $x$ bináris ábrázolását használva, ahol $x_i$ jelöli az $i$-edik bitet a legkevésbé fontos bittől számolva, az $f(x)$ a következőképpen írható meg: $f(x) = a^{\sum_{i=0}^{2n-1} x_i 2^i} \operatorname{mod} N$.</span><span class="sxs-lookup"><span data-stu-id="f20ca-107">Using the binary representation of $x$ with $x_i$ denoting the $i$-th bit counting from the least-significant bit, $f(x)$ can be written as $f(x) = a^{\sum_{i=0}^{2n-1} x_i 2^i} \operatorname{mod} N$.</span></span>
<span data-ttu-id="f20ca-108">Ez viszont az $a^{2^i x_i}=(a^{2^i})^{x_i}$ kifejezések eredményeként (mod N) írható meg.</span><span class="sxs-lookup"><span data-stu-id="f20ca-108">In turn, this can be written as a product (mod N) of terms $a^{2^i x_i}=(a^{2^i})^{x_i}$.</span></span> <span data-ttu-id="f20ca-109">Az $f(x)$ függvény így a $2n$ (moduláris) szorzatok sorozatával implementálható, ahol az $a^{2^i}$ feltételes az $x_i$-n nem nulla.</span><span class="sxs-lookup"><span data-stu-id="f20ca-109">The function $f(x)$ can thus be implemented using a sequence of $2n$ (modular) multiplications by $a^{2^i}$ conditional on $x_i$ being nonzero.</span></span> <span data-ttu-id="f20ca-110">Az $a^{2^i}$ állandók előre kiszámíthatók és modulo N-re csökkenthetők az algoritmus futtatása előtt.</span><span class="sxs-lookup"><span data-stu-id="f20ca-110">The constants $a^{2^i}$ can be precomputed and reduced modulo N before running the algorithm.</span></span>

<span data-ttu-id="f20ca-111">A vezérelt moduláris szorzások sorozata tovább egyszerűsíthető: Minden szorzás az $n$-vezérelt moduláris hozzáadások sorozatával végezhető el; és mindegyik moduláris hozzáadás felépíthető egy hagyományos összeadásból és egy komparátorból.</span><span class="sxs-lookup"><span data-stu-id="f20ca-111">This sequence of controlled modular multiplications can be simplified further: Each multiplication can be performed using a sequence of $n$ controlled modular additions; and each modular addition can be built from a regular addition and a comparator.</span></span>


<span data-ttu-id="f20ca-112">Mivel ilyen sok lépésre van szükség a tényleges implementációig, rendkívül hasznos lenne, ha az ilyen funkciók már a legelejétől elérhetők lennének.</span><span class="sxs-lookup"><span data-stu-id="f20ca-112">Given that so many steps are necessary to arrive at an actual implementation, it would be extremely helpful to have such functionality available from the start.</span></span>
<span data-ttu-id="f20ca-113">A Quantum Development Kit ezért támogatja a numerikus funkciók széles körét.</span><span class="sxs-lookup"><span data-stu-id="f20ca-113">This is why the Quantum Development Kit provides support for a wide range of numerics functionality.</span></span>


## <a name="functionality"></a><span data-ttu-id="f20ca-114">Funkció</span><span class="sxs-lookup"><span data-stu-id="f20ca-114">Functionality</span></span>

<span data-ttu-id="f20ca-115">A fentiekben említett egész számos aritmetika mellett a numerikus kódtár a következőket nyújtja:</span><span class="sxs-lookup"><span data-stu-id="f20ca-115">Besides the integer arithmetic mentioned thus far, the numerics library provides</span></span>

 - <span data-ttu-id="f20ca-116">(Nem) előjeles egész számokkal kapcsolatos funkciók (szorzás, négyzetre emelés, osztás maradékkal, inverzió stb.), ahol egy vagy két egész kvantumszám a bemenet</span><span class="sxs-lookup"><span data-stu-id="f20ca-116">(Un)signed integer functionality (multiply, square, division with remainder, inversion, ...) with one or two quantum integer numbers as input</span></span>
 - <span data-ttu-id="f20ca-117">Fixpontos funkciók (hozzáadás/kivonás, szorzás, négyzetre emelés, 1/x, polinomértékelés), ahol egy vagy két fixpontos kvantumszám a bemenet</span><span class="sxs-lookup"><span data-stu-id="f20ca-117">Fixed-point functionality (add / subtract, multiply, square, 1/x, polynomial evaluation) with one or two quantum fixed-point numbers as input</span></span>

## <a name="getting-started"></a><span data-ttu-id="f20ca-118">Első lépések</span><span class="sxs-lookup"><span data-stu-id="f20ca-118">Getting started</span></span>

<span data-ttu-id="f20ca-119">A numerikus kódtár használatának megkezdéséhez tekintse át a [telepítési útmutatót](xref:microsoft.quantum.numerics.installation) és [a numerikus kódtár használatával](xref:microsoft.quantum.numerics.usage) kapcsolatos további információkat.</span><span class="sxs-lookup"><span data-stu-id="f20ca-119">To get started with the Numerics Library, check out the [installation guide](xref:microsoft.quantum.numerics.installation) and more information on [using the Numerics Library](xref:microsoft.quantum.numerics.usage).</span></span>
