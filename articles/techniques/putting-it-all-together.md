---
title: Q# technikák - Az egész összerakása
description: Végigvezet egy alapvető Q# programon, amely bemutatja a kvantum teleportációt.
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4bd91699017e4c1acd9f4449b8a65e39bd07878e
ms.sourcegitcommit: b6b8459eb654040f1e19f66411b29fc9e48e95c9
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/22/2020
ms.locfileid: "82030565"
---
# <a name="putting-it-all-together-teleportation"></a>Elhelyezés ez minden együtt: Teleportáció #
Térjünk vissza a Quantum Circuits-ben meghatározott teleportációs áramkör [példájához.](xref:microsoft.quantum.concepts.circuits) Ezt fogjuk használni, hogy bemutassuk az eddig megtanult fogalmakat. A kvantum teleportáció magyarázata az alábbiakban található azok számára, akik nem ismerik az elméletet, majd a q#-ban a kódimplementáció forgatókönyve. 

## <a name="quantum-teleportation-theory"></a>Quantum Teleportáció: Elmélet
Quantum teleportáció egy olyan technika küldésére ismeretlen kvantum állapot (amit majd hivatkozni, mint a "__üzenet__") egy qubit az egyik helyen, hogy a qubit egy másik helyen (majd hivatkozni ezeket a qubitek a "__itt__" és "__ott__", illetve). Üzenetünket __message__ vektorként tudjuk ábrázolni dirac jelöléssel: 

$$ \ket{\psi} = \alpha\ket{0} +{1} \beta\ket $$

Az __üzenet__ qubit állapota ismeretlen számunkra, mivel nem tudjuk az értékeket $\alpha$ és $\beta$.

### <a name="step-1-create-an-entangled-state"></a>1. lépés: Kusza állapot létrehozása
Annak érdekében, hogy küldje el az __üzenetet__ van szükségünk a qubit __itt__ kell kusza a qubit __ott__. Ez egy Hadamard kapu alkalmazásával érhető el, amelyet egy CNOT kapu követ. Nézzük meg a matekmögötti kapuműveleteket.

Kezdjük a qubits __itt-ott__ mind a{0}$ ket $ állapotban. __there__ Miután entangling ezek a qubits, ezek az állam:

$$ \ket{\phi^+} ={1}\frac{2}{\sqrt{00} }(\ket + \ket{11}) $$

### <a name="step-2-send-the-message"></a>2. lépés: Az üzenet elküldése
Az __üzenet__ elküldéséhez először egy CNOT kaput alkalmazunk a qubit __üzenettel__ és __itt__ qubit bemenetként (az __üzenet__ qubit a vezérlő és az __itt__ qubit a cél qubit, ebben az esetben). Ez a bemeneti állapot írható:

{0} $$ \ket{\psi}\ket{\phi^+} = (\alpha\ket +{1}\beta\ket{1})(\frac {\sqrt{2})(\ket{00} + \ket{11})) $$

Ez a következőkre terjed ki:

$${2}\ket{\psi}\ket{\phi^+} = \frac{\alpha}{\sqrt{000} }\ket + \frac{\alpha}{\sqrt{2}}\ket{011} {2}{100} {2}{111} +\frac{\beta}{\sqrt $!

Emlékeztetőül: a CNOT kapu megfordítja a cél qubitet, ha a vezérlő qubit 1. Így például a $\ket{000}$ bemenetnem eredményez változást, mivel az első qubit (a vezérlő) 0. Azonban, hogy egy esetben, ahol az első qubit 1{100}- például egy bemeneti $\ket $. Ebben az esetben a kimenet{110}$\ket $, mivel a második qubit (a cél) a CNOT kapuval van tükrözve.

Nézzük most úgy a kimenet, ha a CNOT kapu járt el a mi bemenet felett. Az eredmény:

{2}$$ \frac{\alpha}{\sqrt }\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{110} + \frac{\beta}{\sqrt{2}}\ket{101} $$

A következő lépés, hogy küldje el az __üzenetet,__ hogy alkalmazza a Hadamard kapu az __üzenet__ qubit (ez az első qubit minden kifejezés). 

Emlékeztetőül, a Hadamard kapu a következőket teszi:

Input (Bemenet) | Kimenet
---------------------------| ---------------------------------------------------------------
$\ket{0}$  | $\frac{1}{\sqrt{2}}(\ket{0} {1}+ \ket )$
$\ket{1}$  | $\frac{1}{\sqrt{2}}(\ket{0} {1}- \ket )$

Ha a Hadamard kaput a fenti kimenetminden egyes ciklusának első qubit-jára alkalmazzuk, a következő eredményt kapjuk:

$${2}\frac{\alpha}{\sqrt }(\frac{1}{\sqrt{2}{0} }(\ket + \ket{1})\ket{00} +{2}\frac{\alpha}{\sqrt }(\frac{0} {1}{11} {2}{1}{2}{0} {1}{10} {2}{1}{2}{0} {1}{01} {1}{\sqrt{2}}(\ket + \ket )\ket + \frac{\beta}{\sqrt }(\frac {\sqrt }(\ket - \ket )\ket + \frac{\beta}{\sqrt }(\frac {\sqrt }(\ket - \ket ))\ket $$

Ne feledje, hogy minden{1}kifejezésnek két{2}$\frac {\sqrt }$ tényezője van. Tudjuk szorozni ezeket ki, amely a következő eredményt:

$${2}\frac{\alpha} (\ket{0} {1}+ \ket )\ket{00} +{2}\frac{\alpha} (\ket{0} +{1}\ket )\ket{0} {1}{10} {2}{0} {1}{01} {11} + \frac{\beta}{2}(\ket - \ket )\ket + \frac{\beta} (\ket - \ket )\ket $$

A $\frac{1}{2}$ tényező minden egyes kifejezésnél gyakori, így most már a zárójelen kívül rekedhetünk:

{1}{2}$$ \frac{0} \big[\alpha(\ket{1}+ \ket )\ket{00} {0} + \alpha(\ket + \ket{1})\ket{11} + \beta(\ket{0} -{1}\ket )\ket{10} \beta(\ket - \ket -{0} \ket - \ket ) \ket{1}{01}

Ezután szorozzuk ki a zárójelben minden kifejezés, amely:

$${1}{2}\frac \big[\alfa\ket{000} +{100} \alpha\ket{011} + \alpha\ket +{111} \alpha\ket + \beta\ket{001} {101}{010} - \beta\ket{110} + \beta\ket - \beta\ket - \beta\ket - \beta\ket \beta\ket \beta\ket \big] $$

### <a name="step-3-measure-the-result"></a>3. lépés: Az eredmény mérése

Mivel __here__ __itt-ott,__ hogy kusza, minden mérés __itt__ hatással lesz az állam __ott__. Ha mérjük az első és a második qubit __(üzenet__ és __itt)__ meg tudjuk tanulni, milyen állapotban __van,__ mivel ez a tulajdonság a kuszaság. 

* Ha mérjük, és kap egy eredmény 00, a szuperpozíció összeomlik, így csak feltételek összhangban ezzel az eredménnyel. Ez $\alpha\ket{000} +\beta\ket{001}$. Ez $\ket{00}(\alpha\ket{0} +\beta\ket{1})$-ra refactorálható. Ezért ha mérjük az első és a második qubit, hogy 00, tudjuk, hogy a harmadik{0} qubit,{1} __ott__van az állam $(\alpha\ket +\beta\ket )$.
* Ha mérjük, és kap egy eredmény 01, a szuperpozíció összeomlik, így csak feltételek összhangban ezzel az eredménnyel. Ez $\alpha\ket{011} +\beta\ket{010}$. Ez $\ket{01}(\alpha\ket{1} +\beta\ket{0})$-ra refactorálható. Ezért, ha mérjük az első és a második qubit, hogy 01, tudjuk, hogy a{1} harmadik qubit,{0} __ott__van az állam $(\alpha\ket +\beta\ket )$.
* Ha mérjük, és kap egy eredményt 10, a szuperpozíció összeomlik, így csak feltételek összhangban ezzel az eredménnyel. Ez $\alpha\ket{100} -\beta\ket{101}$. Ez $\ket{10}(\alpha\ket{0} -\beta\ket{1})$-ra refactorálható. Ezért ha az első és a második qubit 10-es, akkor tudjuk, hogy a harmadik qubit, __ott__van az állam $(\alpha\ket{0} -\beta\ket{1})$.
* Ha mérjük, és kap egy eredményt 11, a szuperpozíció összeomlik, így csak feltételek összhangban ezzel az eredménnyel. Ez $\alpha\ket{111} -\beta\ket{110}$. Ez $\ket{11}(\alpha\ket{1} -\beta\ket{0})$-ra refactorálható. Ezért ha az első és a második qubit 11-es, akkor tudjuk, hogy a harmadik qubit, __ott__van az állam $(\alpha\ket{1} -\beta\ket{0})$.

### <a name="step-4-interpret-the-result"></a>4. lépés: Az eredmény értelmezése

Emlékeztetőül, az eredeti __üzenetet__ akartunk küldeni volt:

$$ \ket{\psi} = \alpha\ket{0} +{1} \beta\ket $$

Be kell juttatnunk __a__ qubit-et ebbe az állapotba, hogy a kapott állam az, amit szántak. 

* Ha mértük, és kapott egy eredmény 00, __there__akkor a harmadik qubit, ott{0} van az{1}állam $(\alpha\ket +\beta\ket )$. Mivel ez a kívánt __üzenet,__ nincs szükség változtatásra.
* Ha mértük, és kapott egy eredmény 01, __there__akkor a harmadik qubit, ott{1} van az{0}állam $(\alpha\ket +\beta\ket )$. Ez eltér a tervezett __üzenettől,__ azonban a NOT kapu alkalmazása megadja a{0} kívánt állapotot{1}$(\alpha\ket +\beta\ket )$.
* Ha mértük, és kapott egy eredmény 10, __there__akkor a harmadik qubit, ott{0} van az{1}állam $(\alpha\ket -\beta\ket )$. Ez eltér a tervezett __üzenettől,__ azonban a Z kapu alkalmazása megadja a{0} kívánt állapotot{1}$(\alpha\ket +\beta\ket )$.
* Ha mértük, és kapott egy eredmény 11, __there__akkor a harmadik qubit, ott{1} van az{0}állam $(\alpha\ket -\beta\ket )$. Ez eltér a tervezett __üzenettől,__ azonban a NOT kapu, majd a Z kapu alkalmazása{0} megadja nekünk{1}a kívánt állapotot $(\alpha\ket +\beta\ket )$.

Összefoglalva, ha mérjük, és az első qubit 1, a Z kapu kerül alkalmazásra. Ha mérjük, és a második qubit 1, a NOT kapu kerül alkalmazásra.

### <a name="summary"></a>Összefoglalás
Az alábbiakban egy tankönyv kvantumáramkör látható, amely megvalósítja a teleportálást. Balról jobbra haladva látható:
- 1. lépés: Entangling __itt-ott__ alkalmazásával Hadamard kapu és CNOT kapu. __here__
- 2. lépés: Az __üzenet__ elküldése egy CNOT kapu és egy Hadamard kapu segítségével.
- 3. lépés: Az első és a második qubit, __üzenet__ és __itt__mérése .
- 4. lépés: NOT vagy Z kapu alkalmazása a 3.

!["Teleport(msg : Qubit, ott: Qubit) : Egység"](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a>Quantum Teleportáció: Kód

Megvan a kvantum teleportáció áramköre:

!["Teleport(msg : Qubit, ott: Qubit) : Egység"](~/media/teleportation.svg)

Most már letudjuk fordítani a kvantumáramkör minden egyes lépését Q#-ra.

### <a name="step-0-definition"></a>0. lépés: Meghatározás
Amikor végzünk teleportáció, tudnunk kell az __üzenetet__ szeretnénk küldeni, és ahol szeretnénk küldeni __(ott__). Ezért kezdjük egy új teleport művelet meghatározásával, amely két qubitet `msg` `there`kap érvként, és:

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

Azt is meg kell `here` kiosztani a `using` qubit, amit elérni egy blokk:

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a>1. lépés: Kusza állapot létrehozása
Ezután létrehozhatjuk a kusza pár @"microsoft.quantum.intrinsic.h" @"microsoft.quantum.intrinsic.cnot" között `here` és `there` a műveletek segítségével:

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a>2. lépés: Az üzenet elküldése
Ezután a következő $\operatorname{CNOT}$ és $H$ kapukat használjuk az üzenet qubit áthelyezéséhez:

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a>3. & 4.
Végül, használjuk, @"microsoft.quantum.intrinsic.m" hogy végre a méréseket, és elvégzi a szükséges kapu `if` műveleteket, hogy a kívánt állapot, amint azt a nyilatkozatok:

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

### <a name="step-5-restarting-the-qubit-register"></a>5. lépés: A qubit regiszter újraindítása

Végén minden Q # művelet van szükségünk, hogy hagyja, hogy{0}a qubits az állam $\ket $. @"microsoft.quantum.intrinsic.reset" Használhatjuk, hogy indítsa újra az összes qubits a nulla állapot, és ez befejezi a műveletet.

```qsharp
        Reset(msg);
        Reset(here);
        Reset(there);
    }
}
```


