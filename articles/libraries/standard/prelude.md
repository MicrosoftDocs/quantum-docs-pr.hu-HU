---
title: 'Q # standard könyvtárak – Prelude | Microsoft Docs'
description: 'Q # standard könyvtárak – bevezetés'
author: QuantumWriter
uid: microsoft.quantum.libraries.standard.prelude
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: dddb3d4a5ebcdca16da41a5ae5520d98ea900a7f
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73183233"
---
# <a name="the-prelude"></a>A bevezetés #

A Q # fordítóprogram és a Quantum Development Kit részét képező cél gépek olyan belső funkciókat és műveleteket biztosítanak, amelyek a Quantum-programok a Q #-ban való írásakor használhatók.

## <a name="intrinsic-operations-and-functions"></a>Belső műveletek és függvények ##

A standard könyvtárban definiált belső műveletek nagyjából a különböző kategóriák valamelyikébe tartoznak:

- A <xref:microsoft.quantum.core> névtérben összegyűjtött alapvető klasszikus függvények.
- [Clifford és $T $ gatesből](xref:microsoft.quantum.concepts.qubit)álló unitaries képviselő műveletek.
- A különböző operátorok rotációit képviselő műveletek.
- A méréseket végrehajtó műveletek.

Mivel a Clifford + $T $ Gate készlet [univerzális](xref:microsoft.quantum.concepts.multiple-qubits) a kvantum-számítástechnika számára, ezek a műveletek elegendőek ahhoz, hogy nagyjából implementálják a elhanyagolható mértékben kis hibán belüli kvantum-algoritmusokat.
A Q # lehetővé teszi, hogy a programozók a single qubit egységes és CNEM Gate könyvtárán belül is működjenek. Ez a kódtár sokkal könnyebben gondolkodik, mert nem igényli, hogy a programozó közvetlenül fejezzék ki a Clifford + $T $ dekompozíciót, és mivel igen hatékony módszerek léteznek egyetlen qubit-unitaries a Clifford és a $T $ gatesbe való fordításához (lásd [itt](xref:microsoft.quantum.more-information) További információ:.

Ha lehetséges, a qubits-ben a bevezetés során meghatározott műveletek lehetővé teszik a `Controlled` változat alkalmazását, például hogy a célszámítógép végrehajtja a megfelelő dekompozíciót.

A bevezetés ezen részében meghatározott függvények és műveletek közül sok a @"microsoft.quantum.intrinsic" névtérben van, így a legtöbb Q # forrásfájlokat tartalmazó `open Microsoft.Quantum.Intrinsic;` direktíva közvetlenül a kezdeti névtér deklarációja után fog rendelkezni.
A rendszer automatikusan megnyit <xref:microsoft.quantum.core> névteret, így a függvények, például a <xref:microsoft.quantum.core.length> `open` utasítás nélkül is használhatók.

### <a name="common-single-qubit-unitary-operations"></a>Közös Qubit – egységes műveletek ###

A bevezetés számos gyakori [qubit műveletet](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)is meghatároz.
Az összes művelet lehetővé teszi mind a `Controlled`, mind a `Adjoint`-belit.

#### <a name="pauli-operators"></a>Pauli-operátorok ####

A <xref:microsoft.quantum.intrinsic.x> művelet végrehajtja a Pauli $X $ operátort.
Ez más néven a `NOT` kapu.
Aláírása `(Qubit => Unit is Adj + Ctl)`.
Az egységes qubit felel meg:

\begin{Equation} \begin{bmatrix} 0 & 1 \\\\% FIXME: ez jelenleg a quadwhack Hack-t használja.
1 & 0 \end{bmatrix} \end{Equation}

A <xref:microsoft.quantum.intrinsic.y> művelet végrehajtja a Pauli $Y $ operátort.
Aláírása `(Qubit => Unit is Adj + Ctl)`.
Az egységes qubit felel meg:

\begin{Equation} \begin{bmatrix} 0 &-i \\\\% FIXME: ez jelenleg a quadwhack Hack-t használja.
& 0 \end{bmatrix} \end{Equation}

A <xref:microsoft.quantum.intrinsic.z> művelet végrehajtja a Pauli $Z $ operátort.
Aláírása `(Qubit => Unit is Adj + Ctl)`.
Az egységes qubit felel meg:

\begin{Equation} \begin{bmatrix} 1 & 0 \\\\% FIXME: ez jelenleg a quadwhack Hack-t használja.
0 & – 1 \end{bmatrix} \end{Equation}

Alább láthatók a [Bloch szférához](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) rendelt átalakítások (az egyes esetekben a rotációs tengely vörös színnel jelenik meg):

![A Bloch szférára leképezett Pauli-műveletek](~/media/prelude_pauliBloch.png)

Fontos megjegyezni, hogy ugyanazt a Pauli-kaput kétszer alkalmazza ugyanarra a qubit, de megszakítja a műveletet (mivel most a 2π (360 °) teljes rotációját hajtotta végre a felszínen a Bloch szférára, így a kiindulási pontra érkezett vissza. Ez a következő identitáshoz vezet:

$ $ X ^ 2 = Y ^ 2 = Z ^ 2 = \boldone $ $

Ez a Bloch szférában látható:

![XX = I](~/media/prelude_blochIdentity.png)

#### <a name="other-single-qubit-cliffords"></a>Más, egyetlen Qubit Cliffords ####

A <xref:microsoft.quantum.intrinsic.h> művelet megvalósítja a Hadamard kaput.
Ezzel a megoldással a megcélzott qubit Pauli $X $ és $Z $ tengelyét változtatja meg, például $H \ket{0} = \ket{+} \mathrel{: =} (\ket{0} + \ket{1})/\sqrt{2}$ és $H \ket{+} = \ket{0}$.
Aláírási `(Qubit => Unit is Adj + Ctl)`rendelkezik, és az egységes qubit felel meg:

\begin{Equation} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\% FIXME: ez jelenleg a quadwhack Hack-t használja.
1 & – 1 \end{bmatrix} \end{Equation}

A Hadamard Gate különösen fontos, mivel a $ \ket{0}$ és $ \ket{1}$ állapotú példányok létrehozásához is használható. A Bloch szféra képviseletében a legkönnyebben úgy gondolja, hogy ez a $ \ket{\psi} $ érték forgása az x tengely körül $ \pi $ radián ($ 180 ^ \circ $), majd az y tengely körüli elforgatása $ \ pi/2 $ radián ($ 90 ^ \circ $):

![A Hadamard művelet a Bloch szférára van leképezve](~/media/prelude_hadamardBloch.png)

A <xref:microsoft.quantum.intrinsic.s> művelet megvalósítja a Phase Gate $S $ értéket.
Ez a Pauli $Z $ művelet mátrix-négyzetének gyökere.
Vagyis $S ^ 2 = Z $.
Aláírási `(Qubit => Unit is Adj + Ctl)`rendelkezik, és az egységes qubit felel meg:

\begin{Equation} \begin{bmatrix} 1 & 0 \\\\% FIXME: ez jelenleg a quadwhack Hack-t használja.
0 & \end{bmatrix} \end{Equation}

#### <a name="rotations"></a>Cserélgetésére ####

A fenti Pauli és Clifford műveleteken kívül a Q # Prelude számos módszert kínál a Forgások kifejezésére.
Az [qubit műveletekben](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)leírtak szerint az elforgatási képesség kritikus fontosságú a kvantum-algoritmusok számára.

Kezdjük azzal, hogy a $H $ és a $T $ Gates használatával bármilyen egyetlen qubit műveletet kifejezzük, ahol a $H $ a Hadamard művelet, és ahol a \begin{Equation} T \mathrel{: =} \begin{bmatrix} 1 & 0 \\\\% FIXME: ez jelenleg a quad back-T használja fel ütés Hack.
0 & e ^ {i \pi/4} \end{bmatrix} \end{Equation} ez a <xref:microsoft.quantum.intrinsic.s> művelet négyzet gyökere, például $T ^ 2 = S $.
A $T $ Gate a <xref:microsoft.quantum.intrinsic.t> művelettel van megvalósítva, és aláírási `(Qubit => Unit is Adj + Ctl)`rendelkezik, amely azt jelzi, hogy ez egy egységes művelet egyetlen qubit.

Annak ellenére, hogy ez elvileg elegendő ahhoz, hogy bármilyen tetszőleges qubit műveletet le lehessen írni, a különböző célszámítógépek hatékonyabb ábrázolással rendelkezhetnek a Pauli-operátorokkal kapcsolatos rotációs műveletekhez, például a bevezetés számos különféle módszert tartalmaz a convienently ilyen elfordulások kifejezése.
A legalapvetőbb ilyen a <xref:microsoft.quantum.intrinsic.r> művelet, amely egy megadott Pauli-tengely, \begin{Equation} R (\sigma, \phi) \mathrel{: =} \exp (-i \phi \sigma/2), \end{Equation}, ahol a $ \sigma $ egy Pauli operátor, $ \phi $ egy szög, és ahol $ a \exp $ a mátrix exponenciális értéket jelöli.
Aláírási `((Pauli, Double, Qubit) => Unit is Adj + Ctl)`rendelkezik, ahol a bemenet első két része a $ \sigma $ és a $ \phi $ klasszikus argumentumokat jelöli, amelyek az egységes operátor $R (\sigma, \phi) $ értékének megadásához szükségesek.
Részben alkalmazhatjuk a $ \sigma $ és a $ \phi $ értéket egy olyan művelet beszerzéséhez, amelynek a típusa egyetlen qubit egységes.
Például `R(PauliZ, PI() / 4, _)` típusa `(Qubit => Unit is Adj + Ctl)`.

> [!NOTE]
> A <xref:microsoft.quantum.intrinsic.r> művelet a bemeneti szöget 2 értékre osztja, és szorozza meg a-1 értékkel.
> $Z $ forgás esetén ez azt jelenti, hogy a $ \ket{0}$ eigenstate a $-\phi/$2, a $ \ket{1}$ eigenstate pedig a $ \phi/$2 által elforgatva, így a $ \ket{1}$ eigenstate a $ \phi $ értékkel, a $ \ket{0}$ eigenstate-hez képest forog.
>
> Ez különösen azt jelenti, hogy a `T` és a `R(PauliZ, PI() / 8, _)` csak a irreleváns [globális fázisban](xref:microsoft.quantum.glossary#global-phase)térnek el egymástól.
> Emiatt a $T $ \frac{\pi}{8}$-Gate néven is ismert.
>
> Vegye figyelembe azt is, hogy a `PauliI` körüli forgatás egyszerűen a $ \phi/$2 globális fázisát alkalmazza. Habár az ilyen fázisok nem relevánsak, ahogy azt [a fogalmi dokumentumok](xref:microsoft.quantum.concepts.qubit)is felmutatják, az ellenőrzött `PauliI` rotációk szempontjából fontosak.

A kvantum-algoritmusokon belül gyakran hasznos a rotációk dyadic-frakcióként való kimutatása, például a $ \phi = \pi k/2 ^ n $ használata néhány $k \in \mathbb{Z} $ és $n \in \mathbb{N} $ esetében.
A <xref:microsoft.quantum.intrinsic.rfrac> művelet egy megadott Pauli-tengely körüli rotációt valósít meg az egyezmény használatával.
Eltér a <xref:microsoft.quantum.intrinsic.r>tól, hogy az elforgatási szög két `Int`típusú bemenetként van megadva, dyadic-frakcióként értelmezve.
Így a `RFrac` aláírása `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)`.
Implementálja az qubit egységes $ \exp (i \pi k \sigma/2 ^ n) $ értéket, ahol a $ \sigma $ az első argumentumnak megfelelő Pauli-mátrix, $k $ a második argumentum, és $n $ a harmadik argumentum.
`RFrac(_,k,n,_)` ugyanaz, mint `R(_,-πk/2^n,_)`; vegye figyelembe, hogy a szög a frakció *negatív* értéke.

A <xref:microsoft.quantum.intrinsic.rx> művelet egy rotációs műveletet valósít meg a Pauli $X $ tengely körül.
Aláírása `((Double, Qubit) => Unit is Adj + Ctl)`.
`Rx(_, _)` ugyanaz, mint `R(PauliX, _, _)`.

A <xref:microsoft.quantum.intrinsic.ry> művelet egy rotációs műveletet valósít meg a Pauli $Y $ tengely körül.
Aláírása `((Double, Qubit) => Unit is Adj + Ctl)`.
`Ry(_, _)` ugyanaz, mint `R(PauliY,_ , _)`.

A <xref:microsoft.quantum.intrinsic.rz> művelet egy rotációs műveletet valósít meg a Pauli $Z $ tengely körül.
Aláírása `((Double, Qubit) => Unit is Adj + Ctl)`.
`Rz(_, _)` ugyanaz, mint `R(PauliZ, _, _)`.

A <xref:microsoft.quantum.intrinsic.r1> művelet elforgatást hajt végre a megadott összeggel a $ \ket{1}$, a $-$1 eigenstate $Z $ értéknél.
Aláírása `((Double, Qubit) => Unit is Adj + Ctl)`.
`R1(phi,_)` ugyanaz, mint `R(PauliZ,phi,_)`, majd `R(PauliI,-phi,_)`.

A <xref:microsoft.quantum.intrinsic.r1frac> művelet egy tört forgást valósít meg a Z = 1 eigenstate körüli megadott összeggel.
Aláírása `((Int,Int, Qubit) => Unit is Adj + Ctl)`.
`R1Frac(k,n,_)` ugyanaz, mint `RFrac(PauliZ,-k.n+1,_)`, majd `RFrac(PauliI,k,n+1,_)`.

Alább látható egy példa egy rotációs műveletre (az ebben az esetben a Pauli $Z $ tengelyen, ebben a példányban), amely a Bloch szférára van leképezve:

![A Bloch szférára leképezett rotációs művelet](~/media/prelude_rotationBloch.png)

#### <a name="multi-qubit-operations"></a>Több Qubit műveletek ####

A fenti qubit műveletek mellett a Prelude számos több qubit műveletet is meghatároz.

Először is a <xref:microsoft.quantum.intrinsic.cnot> művelet elvégzi a standard szintű vezérlésű`NOT` kaput, a \begin{Equation} \operatorname{CNOT} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}.
\end{Equation} aláírási `((Qubit, Qubit) => Unit is Adj + Ctl)`, ami azt jelenti, hogy a $ \operatorname{CNOT} $ unitarily két önálló qubits.
`CNOT(q1, q2)` ugyanaz, mint `(Controlled X)([q1], q2)`.
Mivel a `Controlled`-kezelő lehetővé teszi a regisztrációt, a tömb literál `[q1]` használatával jelezheti, hogy csak az egyetlen vezérlőt szeretnénk használni.

A <xref:microsoft.quantum.intrinsic.ccnot> művelet kétszeresen vezérelt nem kaput hajt végre, néha Toffoli kapuként is ismert.
Aláírása `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)`.
`CCNOT(q1, q2, q3)` ugyanaz, mint `(Controlled X)([q1, q2], q3)`.

A <xref:microsoft.quantum.intrinsic.swap> művelet felcseréli két qubits Quantum állapotait.
Ez azt is megvalósítja, hogy implementálja az egységes mátrix \begin{Equation} \operatorname{SWAP} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix}.
\end{Equation} aláírása `((Qubit, Qubit) => Unit is Adj + Ctl)`.
`SWAP(q1,q2)` egyenértékű a `CNOT(q1, q2)`, majd a `CNOT(q2, q1)` után `CNOT(q1, q2)`.

> [!NOTE]
> A SWAP-kapu *nem* azonos a `Qubit[]`típusú változók elemeinek átrendezésével.
> A `SWAP(q1, q2)` alkalmazása a `q1` és a `q2`által hivatkozott qubits állapotának módosítását eredményezi, míg `let swappedRegister = [q2, q1];` csak azt befolyásolja, hogyan hivatkozunk ezekre a qubits.
> Emellett `(Controlled SWAP)([q0], (q1, q2))` lehetővé teszi, hogy a `SWAP` egy harmadik qubit állapotára lehessen felvenni, amelyet az elemek átrendezése nem jelenthet.
> A vezérelt SWAP-kapu, más néven a Fredkin-kapu, elég erős ahhoz, hogy tartalmazza az összes klasszikus számítást.

Végül a Prelude két műveletet biztosít a több qubit Pauli-operátorok exponenciális ábrázolásához.
A <xref:microsoft.quantum.intrinsic.exp> művelet elvégzi a rotációs (Pauli) mátrixok alapján elforgatást, amelyet a többszörös qubit egységes \begin{Equation} \operatorname{Exp} (\vec{\sigma}, \phi) \mathrel{: =} \exp\left (i \phi \sigma_0 \otimes \sigma_1 \otimes \ cdots \otimes \sigma_n \right), \end{Equation}, ahol a $ \vec{\sigma} = (\sigma_0, \sigma_1, \dots, \sigma_n) $ az egyetlen qubit Pauli-operátorok sorozata, ahol a $ \phi $ egy szög.
A `Exp` forgás a $ \vec{\sigma} $ értéket jelöli `Pauli` elemek tömbje, például aláírási `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)`.

A <xref:microsoft.quantum.intrinsic.expfrac> művelet ugyanazt a rotációs műveletet hajtja végre, a fentebb tárgyalt dyadic-frakciós jelölés használatával.
Aláírása `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)`.

> [!WARNING]
> A Pauli-operátorok tenser-termékének exponenciális száma nem egyezik meg a Pauli-operátorok exponenciálisan működő termékeivel.
> Vagyis $e ^ {i (Z \otimes Z) \phi} \ne e ^ {i Z \phi} \otimes e ^ {i Z \phi} $.

### <a name="measurements"></a>Mérések ###

A méréskor a mért operátor + 1 sajátérték `Zero` eredménynek felel meg, és az-1 sajátérték `One` eredmény.

> [!NOTE]
> Habár ez az egyezmény páratlannak tűnhet, két nagyon jó előnye van.
> Először is, ha a $ \ket{0}$ értéket jelöli a `Result` érték `Zero`, a $ \ket{1}$ megfigyelve pedig `One`nak felel meg.
> Másodszor, azt is kiírhatjuk, hogy a sajátérték $ \lambda $ megfelel egy eredménynek, $r $ értéke $ \lambda = (-1) ^ r $.

A mérési műveletek sem a `Adjoint`, sem a `Controlled`-belit nem támogatják.

A <xref:microsoft.quantum.intrinsic.measure> művelet egy vagy több qubits együttes mérését hajtja végre a Pauli-operátorok megadott termékében.
Ha a Pauli tömb és a qubit tömb eltérő hosszúságú, akkor a művelet sikertelen lesz.
`Measure` aláírása `((Pauli[], Qubit[]) => Result)`.

Vegye figyelembe, hogy a közös mérések nem egyeznek meg egyenként a qubit mérésével.
Tegyük fel például, hogy a $ \ket{11} = \ket{1} \otimes \ket{1} = X\otimes X \ket{00}$ értéket adja meg.
A $Z _0 $ és a $Z _1 $ mérése egyenként történik, $r _0 = $1 és $r _1 = $1.
A $Z _0 Z_1 $ mérésével azonban egyetlen eredményt kapunk, $r _ {\textrm{Joint}} = $0, ami azt jelenti, hogy a $ \ket{11}$ párosítása pozitív.
Másképpen fogalmazva, $ (-1) ^ {r_0 + r_1} = (-1) ^ r_ {\textrm{Joint}}) $.
Kritikus fontosságú, mivel *csak* a mértékből Tanuljuk meg a paritást, a 2 2 – qubit állapotú pozitív paritás, a $ \ket{00}$ és a $ \ket{11}$ közötti kapcsolatban szereplő kvantum-információk megmaradnak.
Ezt a tulajdonságot később kell megtekinteni, ahogy a hibajavításról van szó.

A kényelem érdekében a bevezetés két további műveletet is biztosít a qubits méréséhez.
Először is, mivel az qubit mérések végrehajtása meglehetősen gyakori, a bevezetés egy gyorsírást határoz meg ebben az esetben.
A <xref:microsoft.quantum.intrinsic.m> művelet a Pauli $Z $ operátort méri egyetlen qubit, és aláírási `(Qubit => Result)`rendelkezik.
`M(q)` egyenértékű a `Measure([PauliZ], [q])`.

A <xref:microsoft.quantum.measurement.multim> a Pauli $Z $ operátort a qubits minden egyes tömbje számára *külön* méri, így az egyes qubit kapott `Result` értékek *tömbjét* adja vissza.
Bizonyos esetekben ez optimalizálható. Aláírása (`Qubit[] => Result[])`.
`MultiM(qs)` egyenértékű a következővel:

```qsharp
mutable rs = new Result[Length(qs)];
for (index in 0..Length(qs)-1)
{
    set rs[index] = M(qs[index]);
}
return rs;
```

## <a name="extension-functions-and-operations"></a>Bővítmény-függvények és-műveletek ##

Emellett a bevezetés a matematikai és a típusú átalakítási függvények gazdag készletét határozza meg a .NET-szinten a Q # kódban való használatra.
Például a <xref:microsoft.quantum.extensions.math> névtér olyan hasznos műveleteket határoz meg, mint például a <xref:microsoft.quantum.extensions.math.sin> és a <xref:microsoft.quantum.extensions.math.log>.
A Quantum Development Kit által biztosított implementáció a klasszikus .NET alaposztály-függvénytárat használja, így további kommunikációs kört eredményezhet a kvantum-programok és a klasszikus illesztőprogramjaik között.
Habár ez nem jelent problémát a helyi szimulátor esetében, ez a probléma akkor lehet teljesítményproblémák, ha távoli szimulátort vagy tényleges hardvert használ célként.
Ez azt is okozhatja, hogy az adott rendszer esetében az egyes célszámítógép befolyásolhatja a teljesítményt, ha felülbírálja ezeket a műveleteket az adott rendszeren hatékonyabb verziókkal.

### <a name="math"></a>Matematikai ###

A <xref:microsoft.quantum.extensions.math> névtér számos hasznos funkciót biztosít a .NET alaposztály könyvtárának [`System.Math` osztályában](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1).
Ezek a függvények ugyanúgy használhatók, mint bármely más Q # függvény:

```qsharp
open Microsoft.Quantum.Math;
// ...
let y = Sin(theta);
```

Ha a .NET statikus metódus túlterhelt az argumentumok típusa alapján, a megfelelő Q # függvényt a rendszer a bemenetének típusát jelző utótaggal jelöli meg:

```qsharp
let x = AbsI(-3); // x : Int = 3
let y = AbsD(-PI()); // y : Double = 3.1415...
```


### <a name="bitwise-operations"></a>Bitenkénti-műveletek ###

Végül a <xref:microsoft.quantum.extensions.bitwise> névtér számos hasznos függvényt biztosít az egész számok bitenkénti-operátoron keresztüli módosításához.
A <xref:microsoft.quantum.extensions.bitwise.parity> például egy egész szám bitenkénti paritását adja vissza egy másik egész számként.
