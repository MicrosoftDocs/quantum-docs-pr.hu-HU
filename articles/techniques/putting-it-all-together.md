---
title: 'Q # technikák – az összes összeállítása'
description: 'Haladjon végig egy alapszintű Q # programban, amely a kvantum-teleportáció mutatja be.'
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 6c988f77ef6e433945dbf21dfb41204c74bdda3e
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906831"
---
# <a name="putting-it-all-together-teleportation"></a>Az összes egyesítése: teleportáció #
Térjen vissza a [kvantum-áramkörökben](xref:microsoft.quantum.concepts.circuits)definiált teleportáció-kör példára. Ezt az eddig megtanult fogalmak szemléltetésére fogjuk használni. A Quantum teleportáció magyarázatát alább találja azok számára, akik nem ismerik az elméletet, majd a kód megvalósításának bemutatóját a Q #-ban. 

## <a name="quantum-teleportation-theory"></a>Quantum teleportáció: elmélet
A kvantum-teleportáció olyan technika, amely egy ismeretlen kvantum-állapot küldését teszi elérhetővé (amit "__üzenetnek__" nevezünk) egy adott helyen lévő qubit egy másik helyen lévő qubit (ezt a qubits a "Here" és a "__here__"kifejezéssel tekintjük meg). Az Dirac-jelölést használó vektorként az __üzenetet__ is képviseljük: 

$ $ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $ $

Az __üzenet__ qubit ismeretlen a számunkra, mert nem tudjuk a $ \alpha $ és a $ \beta $ értékeit.

### <a name="step-1-create-an-entangled-state"></a>1\. lépés: kusza állapot létrehozása
Ahhoz, hogy el lehessen küldeni az __üzenetet__ , a qubit __itt__ kell összekeverni __a qubit.__ Ez egy Hadamard-kapu, majd egy CNEM-kapu után érhető el. Nézzük meg a kapu műveletei mögötti matematikai műveleteket.

A qubits __itt__ és a $ \ket{0}$ __állapotban is__ megkezdődik. A qubits összekeverve a következő állapotban vannak:

$ $ \ket{\phi ^ +} = \frac{1}{\sqrt{2}} (\ket{00} + \ket{11}) $ $

### <a name="step-2-send-the-message"></a>2\. lépés: az üzenet elküldése
Az __üzenet__ elküldéséhez először alkalmazzon egy cnem-kaput az __üzenet__ qubit, és __itt__ qubit bemenetként (az __üzenet__ qubit, amely a vezérlő __, a qubit pedig a cél__ qubit, ebben a példányban). Ezt a bemeneti állapotot lehet írni:

$ $ \ket{\psi}\ket{\phi ^ +} = (\alpha\ket{0} + \beta\ket{1}) (\frac{1}{\sqrt{2}} (\ket{00} + \ket{11})) $ $

Ez a következőre bővül:

$ $ \ket{\psi}\ket{\phi ^ +} = \frac{\alpha}{\sqrt{2}} \ket{000} + \frac{\alpha}{\sqrt{2}} \ket{011} + \frac{\beta}{\sqrt{2}} \ket{100} + \frac{\beta}{\sqrt{2}} \ket{111} $ $

Emlékeztetőként a CNEM-kapu megfordítja a cél qubit, amikor a vezérlő qubit értéke 1. Így például a $ \ket{000}$ bemenet nem változik, mert az első qubit (a vezérlő) 0. Azonban tegyük fel, hogy az első qubit 1 – például a $ \ket{100}$ bemenet. Ebben az esetben a kimenet a $ \ket{110}$, mivel a második qubit (a cél) a CNEM-kapu tükrözött.

Most nézzük meg a kimenetet, ha a CNEM kapu a fenti bemeneten működött. Az eredmény a következőket eredményezi:

$ $ \frac{\alpha}{\sqrt{2}} \ket{000} + \frac{\alpha}{\sqrt{2}} \ket{011} + \frac{\beta}{\sqrt{2}} \ket{110} + \frac{\beta}{\sqrt{2}} \ket{101} $ $

Az __üzenet__ elküldésének következő lépése egy Hadamard-kapu alkalmazása az __üzenet__ qubit (ez az egyes kifejezések első qubit). 

Emlékeztetőként a Hadamard Gate a következő műveleteket végzi el:

Input (Bemenet) | Kimenet
---------------------------| ---------------------------------------------------------------
$ \ket{0}$  | $ \frac{1}{\sqrt{2}} (\ket{0} + \ket{1}) $
$ \ket{1}$  | $ \frac{1}{\sqrt{2}} (\ket{0}-\ket{1}) $

Ha a Hadamard kaput a fenti kimenet minden egyes időszakának első qubit alkalmazza, a következő eredményt értjük:

$ $ \frac{\alpha}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0} + \ket{1})) \ket{00} + \frac{\alpha}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0} + \ket{1})) \ket{11} + \frac{\beta}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0}-\ket{1})) \ket{10} + \frac{\beta}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0}-\ket{1})) \ket{01} $ $

Vegye figyelembe, hogy az egyes feltételek $2 \frac{1}{\sqrt{2}} $ tényezővel rendelkeznek. Ezeket az eredményeket a következő eredmény megadásával tudjuk megszorozni:

$ $ \frac{\alpha}{2}(\ket{0} + \ket{1}) \ket{00} + \frac{\alpha}{2}(\ket{0} + \ket{1}) \ket{11} + \frac{\beta}{2}(\ket{0}-\ket{1}) \ket{10} + \frac{\beta}{2}(\ket{0}-\ket{1}) \ket{01} $ $

A $ \frac{1}{2}$ Factor az egyes kifejezések esetében közös, így most már a zárójeleken kívül is elhelyezhetők:

$ $ \frac{1}{2}\big [\alpha (\ket{0} + \ket{1}) \ket{00} + \alpha (\ket{0} + \ket{1}) \ket{11} + \beta (\ket{0}-\ket{1}) \ket{10} + \beta (\ket{0}-\ket{1}) \ket{01}\big] $ $

Ezután a zárójeleket a következő kifejezésekkel szorozva adhatja meg:

$ $ \frac{1}{2}\big [\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010}-\beta\ket{110} + \beta\ket{001}-\beta\ket{101}\big] $ $

### <a name="step-3-measure-the-result"></a>3\. lépés: az eredmény mérése

Mivel __itt__ van, és __nincs__ összekeverve, a mérések __itt__ is hatással __lesznek.__ Ha mérjük az első és a második qubit (__üzenet__ és __itt__), megtudhatjuk, __milyen állapotban van a-__ ben, a felakadás ezen tulajdonsága miatt. 

* Ha méri és lekéri a 00 értéket, a rendszer összecsukja az eredményt, így csak a feltételek konzisztensek. Ez a $ \alpha\ket{000} + \beta\ket{001}$. Ez a $ \ket{00}(\alpha\ket{0} + \beta\ket{1}) $ értékre állítható át. Ezért ha az első és második qubit 00-ra mérjük, __tudjuk, hogy__a harmadik qubit a következő állapotban van: $ (\alpha\ket{0} + \beta\ket{1}) $.
* Ha a rendszer kiértékeli és beolvassa az eredmény 01 értéket, a rendszer összecsukja az eredményt, így csak a feltételek konzisztensek. Ez a $ \alpha\ket{011} + \beta\ket{010}$. Ez a $ \ket{01}(\alpha\ket{1} + \beta\ket{0}) $ értékre állítható át. Ezért ha az első és második qubit 01-re mérjük, __tudjuk, hogy__a harmadik qubit a következő állapotban van: $ (\alpha\ket{1} + \beta\ket{0}) $.
* Ha mérjük és megkapjuk a 10. eredményt, a rendszer összeomlik, és csak az ezzel az eredménnyel konzisztens kifejezéseket hagyja. Ez a $ \alpha\ket{100}-\beta\ket{101}$. Ezt a $ \ket{10}(\alpha\ket{0}-\beta\ket{1}) $ értékre lehet átvenni. Ezért __, ha__az első és második qubit 10 értékre mérjük, tudjuk, hogy a harmadik qubit a következő állapotban van: $ (\alpha\ket{0}-\beta\ket{1}) $.
* Ha mérjük és beolvasjuk a 11. eredményt, a rendszer Összecsukja a feltételt, és csak az ezzel az eredménnyel konzisztens kifejezéseket hagyja. Ez a $ \alpha\ket{111}-\beta\ket{110}$. Ezt a $ \ket{11}(\alpha\ket{1}-\beta\ket{0}) $ értékre lehet átvenni. Ezért ha az első és második qubit 11-re mérjük, __tudjuk, hogy__a harmadik qubit a következő állapotban van: $ (\alpha\ket{1}-\beta\ket{0}) $.

### <a name="step-4-interpret-the-result"></a>4\. lépés: az eredmény értelmezése

Emlékeztetőként az eredetileg elküldeni kívánt __üzenet__ a következő volt:

$ $ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $ $

Be kell szereznie a __qubit ebbe az__ állapotba, hogy a kapott állapot legyen a kívánt érték. 

* Ha a mért érték a 00, a harmadik qubit pedig a következő __állapotban van:__ $ (\alpha\ket{0} + \beta\ket{1}) $. Mivel ez a kívánt __üzenet__, nincs szükség módosításra.
* Ha a mért érték a 01, akkor a harmadik qubit a (\alpha\ket{1} + \beta\ket{0}) $ __állapotban van.__ Ez eltér a kívánt __üzenettől__, de a nem kapu alkalmazása a kívánt állapotot adja meg (\alpha\ket{0} + \beta\ket{1}) $.
* Ha a mért érték 10, akkor a harmadik qubit a (\alpha\ket{0}-\beta\ket{1}) $ __állapotban van.__ Ez eltér a kívánt __üzenettől__, azonban a Z-kapu alkalmazása a kívánt állapotot adja meg (\alpha\ket{0} + \beta\ket{1}) $.
* Ha a mért érték 11, akkor a harmadik qubit a (\alpha\ket{1}-\beta\ket{0}) $ __állapotban van.__ Ez különbözik a kívánt __üzenettől__, de a nem kaput, majd egy Z kapun a kívánt állapotot ($ (\alpha\ket{0} + \beta\ket{1}) $ értéket adja meg nekünk.

Ha a mérés és az első qubit értéke 1, a rendszer a Z kaput alkalmazza. Ha mérjük, és a második qubit értéke 1, a rendszer nem alkalmaz egy kaput.

### <a name="summary"></a>Összegzés
Alább látható egy szöveges könyvből álló kvantum-kör, amely megvalósítja a teleportáció. Balról jobbra haladva a következőt láthatja:
- 1\. lépés: a __Hadamard-kapu__ és a cnem-kapu alkalmazásával összekeverhető __itt__ .
- 2\. lépés: az __üzenet__ elküldése egy cnem-kapuval és egy Hadamard-kapuval.
- 3\. lépés: az első és a második qubits, az __üzenet__ és az __itt__mért érték mérése.
- 4\. lépés: nem kapu vagy Z kapu alkalmazása a 3. lépésben mért mértéktől függően.

!["Teleport (msg: Qubit, ott: Qubit): egység"](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a>Quantum teleportáció: kód

A Quantum teleportáció:

!["Teleport (msg: Qubit, ott: Qubit): egység"](~/media/teleportation.svg)

Most már lefordíthatja az ebben a kvantum-áramkörben lévő lépéseket Q #-ra.

### <a name="step-0-definition"></a>0\. lépés: definíció
A teleportálás elvégzése után tudnunk kell, hogy milyen __üzenetet__ szeretnénk elküldeni, és hová szeretnénk elküldeni (__ott__). Éppen ezért egy új, az argumentumként megadott teleport-művelet definiálásával kezdjük, `msg` és `there`:

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

Szükség van egy qubit-`here` kiosztására is, amelyet egy `using` blokkmal érhetünk el:

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a>1\. lépés: kusza állapot létrehozása
Ezután az @"microsoft.quantum.intrinsic.h" és a @"microsoft.quantum.intrinsic.cnot" műveletekkel hozhatjuk létre a kusza párokat `here` és `there` között:

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a>2\. lépés: az üzenet elküldése
Ezt követően a következő $ \operatorname{CNOT} $ és $H $ Gates használatával helyezheti át az üzenet qubit:

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a>3\. lépés & 4: az eredmény mérése és értelmezése
Végül a @"microsoft.quantum.intrinsic.m" használatával hajtjuk végre a méréseket, és végrehajtjuk a szükséges kiindulási műveleteket a kívánt állapot eléréséhez, `if` utasítások szerint:

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

Ez befejezi a teleportáló operátor definícióját, így felszabadítjuk `here`, befejezve a törzset, és befejezjük a műveletet.

```qsharp
    }
}
```
