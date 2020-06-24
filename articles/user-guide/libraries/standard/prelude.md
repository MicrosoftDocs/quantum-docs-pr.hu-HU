---
title: Belső műveletek és függvények a QDK
description: Ismerje meg a QDK belső műveleteit és funkcióit, beleértve a klasszikus funkciókat, valamint az egységes, rotációs és mérési műveleteket.
author: QuantumWriter
uid: microsoft.quantum.libraries.standard.prelude
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 19674620475e68b41c855023807a5fd1f7945ec9
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274960"
---
# <a name="the-prelude"></a>A bevezetés #

A Q # fordítóprogram és a Quantum Development Kit részét képező cél gépek olyan belső funkciókat és műveleteket biztosítanak, amelyek a Quantum-programok a Q #-ban való írásakor használhatók.

## <a name="intrinsic-operations-and-functions"></a>Belső műveletek és függvények ##

A standard könyvtárban definiált belső műveletek nagyjából a különböző kategóriák valamelyikébe tartoznak:

- A névtérben összegyűjtött alapvető klasszikus függvények <xref:microsoft.quantum.core> .
- [Clifford és $T $ gatesből](xref:microsoft.quantum.concepts.qubit)álló unitaries képviselő műveletek.
- A különböző operátorok rotációit képviselő műveletek.
- A méréseket végrehajtó műveletek.

Mivel a Clifford + $T $ Gate készlet [univerzális](xref:microsoft.quantum.concepts.multiple-qubits) a kvantum-számítástechnika számára, ezek a műveletek elegendőek ahhoz, hogy nagyjából implementálják a elhanyagolható mértékben kis hibán belüli kvantum-algoritmusokat.
A Q # lehetővé teszi, hogy a programozók a single qubit egységes és CNEM Gate könyvtárán belül is működjenek. Ez a kódtár sokkal könnyebben gondolkodik, mert nem igényli, hogy a programozó közvetlenül fejezzék ki a Clifford + $T $ dekompozíciót, és mivel igen hatékony módszerek léteznek az egyetlen qubit-unitaries a Clifford és a $T $ gatesbe való fordításához (további információt [itt](xref:microsoft.quantum.more-information) talál).

Ha lehetséges, az qubits-ben a bevezetés során meghatározott műveletek lehetővé teszik a Variant alkalmazását `Controlled` , így a célszámítógép a megfelelő dekompozíciót fogja végezni.

Az előzetes verzió ezen részében meghatározott függvények és műveletek többsége a @"microsoft.quantum.intrinsic" névtérben található, így a legtöbb Q # forrásfájlokat tartalmazó `open Microsoft.Quantum.Intrinsic;` direktíva közvetlenül a kezdeti névtér deklarációja után fog rendelkezni.
A <xref:microsoft.quantum.core> rendszer automatikusan megnyitja a névteret, így a <xref:microsoft.quantum.core.length> (z) függvény, amely nem tartalmaz `open` utasítást.

### <a name="common-single-qubit-unitary-operations"></a>Közös Qubit – egységes műveletek ###

A bevezetés számos gyakori [qubit műveletet](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)is meghatároz.
Az összes művelet lehetővé teszi mind a, mind a következő műveleteket `Controlled` `Adjoint` .

#### <a name="pauli-operators"></a>Pauli-operátorok ####

A <xref:microsoft.quantum.intrinsic.x> művelet végrehajtja a Pauli $X $ operátort.
Ez más néven a `NOT` kapu.
Aláírással rendelkezik `(Qubit => Unit is Adj + Ctl)` .
Az egységes qubit felel meg:

\begin{Equation} \begin{bmatrix} 0 & 1 \\ \\ % FIXME: ez jelenleg a quadwhack Hack-t használja.
1 & 0 \end{bmatrix} \end{Equation}

A <xref:microsoft.quantum.intrinsic.y> művelet végrehajtja a Pauli $Y $ operátort.
Aláírással rendelkezik `(Qubit => Unit is Adj + Ctl)` .
Az egységes qubit felel meg:

\begin{Equation} \begin{bmatrix} 0 &-i \\ \\ % FIXME: ez jelenleg a quadwhack Hack-t használja.
& 0 \end{bmatrix} \end{Equation}

A <xref:microsoft.quantum.intrinsic.z> művelet végrehajtja a Pauli $Z $ operátort.
Aláírással rendelkezik `(Qubit => Unit is Adj + Ctl)` .
Az egységes qubit felel meg:

\begin{Equation} \begin{bmatrix} 1 & 0 \\ \\ % FIXME: ez jelenleg a quadwhack Hack-t használja.
0 & – 1 \end{bmatrix} \end{Equation}

Alább láthatók a [Bloch szférához](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) rendelt átalakítások (az egyes esetekben a rotációs tengely vörös színnel jelenik meg):

![A Bloch szférára leképezett Pauli-műveletek](~/media/prelude_pauliBloch.png)

Fontos megjegyezni, hogy ugyanazt a Pauli-kaput kétszer alkalmazza ugyanarra a qubit, de megszakítja a műveletet (mivel most a 2π (360 °) teljes rotációját hajtotta végre a felszínen a Bloch szférára, így a kiindulási pontra érkezett vissza. Ez a következő identitáshoz vezet:

$ $ X ^ 2 = Y ^ 2 = Z ^ 2 = \boldone $ $

Ez a Bloch szférában látható:

![XX = I](~/media/prelude_blochIdentity.png)

#### <a name="other-single-qubit-cliffords"></a>Más, egyetlen Qubit Cliffords ####

A <xref:microsoft.quantum.intrinsic.h> művelet megvalósítja a Hadamard kaput.
Ezzel a megoldással a megcélzott qubit Pauli $X $ és $Z $ tengelyét változtatja meg, például $H \ket {0} = \ket{+} \mathrel{: =} (\ket {0} + \ket {1} )/\sqrt {2} $ és $H \ket{+} = \ket {0} $.
Aláírással rendelkezik `(Qubit => Unit is Adj + Ctl)` , és az egységes qubit felel meg:

\begin{Equation} \frac {1} {\sqrt {2} } \begin{bmatrix} 1 & 1 \\ \\ % FIXME: ez jelenleg a quadwhack Hack-et használja.
1 & – 1 \end{bmatrix} \end{Equation}

A Hadamard Gate különösen fontos, mivel a $ \ket {0} $ és a $ \ket {1} $ állapotú példányok létrehozásához is használható. A Bloch szféra képviseletében a legkönnyebben úgy gondolja, hogy ez a $ \ket{\psi} $ érték forgása az x tengely körül $ \pi $ radián ($ 180 ^ \circ $), majd az y tengely körüli elforgatása $ \ pi/2 $ radián ($ 90 ^ \circ $):

![A Hadamard művelet a Bloch szférára van leképezve](~/media/prelude_hadamardBloch.png)

A <xref:microsoft.quantum.intrinsic.s> művelet végrehajtja a Phase gate $S $ értéket.
Ez a Pauli $Z $ művelet mátrix-négyzetének gyökere.
Vagyis $S ^ 2 = Z $.
Aláírással rendelkezik `(Qubit => Unit is Adj + Ctl)` , és az egységes qubit felel meg:

\begin{Equation} \begin{bmatrix} 1 & 0 \\ \\ % FIXME: ez jelenleg a quadwhack Hack-t használja.
0 & \end{bmatrix} \end{Equation}

#### <a name="rotations"></a>Cserélgetésére ####

A fenti Pauli és Clifford műveleteken kívül a Q # Prelude számos módszert kínál a Forgások kifejezésére.
Az [qubit műveletekben](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)leírtak szerint az elforgatási képesség kritikus fontosságú a kvantum-algoritmusok számára.

Kezdjük azzal, hogy a $H $ és a $T $ Gates használatával bármilyen egyetlen qubit műveletet kifejezzük, ahol $H $ a Hadamard művelet, és ahol a \begin{Equation} T \mathrel{: =} \begin{bmatrix} 1 & 0 \\ \\ % FIXME: ez jelenleg a quad back Hack-T használja.
0 & e ^ {i \pi/4} \end{bmatrix} \end{Equation} ez a művelet négyzet gyökere <xref:microsoft.quantum.intrinsic.s> , például $T ^ 2 = S $.
A $T $ kaput a művelet implementálja <xref:microsoft.quantum.intrinsic.t> , és aláírással rendelkezik, amely azt `(Qubit => Unit is Adj + Ctl)` jelzi, hogy egy egységes művelet egy qubit.

Annak ellenére, hogy ez elvileg elegendő ahhoz, hogy bármilyen tetszőleges qubit műveletet le lehessen írni, a különböző célszámítógépek hatékonyabb ábrázolással rendelkezhetnek a Pauli-operátorokkal kapcsolatos rotációs műveletekhez, például a bevezetés számos módszert tartalmaz a convienently kiváltására.
A legalapvetőbb ilyen <xref:microsoft.quantum.intrinsic.r> művelet, amely egy megadott Pauli-tengely, \Begin{Equation} R (\sigma, \phi) \mathrel{: =} \exp (-i \phi \sigma/2), \end{Equation}, ahol a $ \sigma $ egy Pauli operátor, a $ \phi $ egy szög, és ahol a $ \exp $ a mátrix exponenciális értéket jelöli.
Aláírással rendelkezik `((Pauli, Double, Qubit) => Unit is Adj + Ctl)` , ahol a bemenet első két része a $ \sigma $ és a $ \phi $ klasszikus argumentumokat jelöli, amelyek az egységes operátor megadásához szükségesek $R (\sigma, \phi) $.
Részben alkalmazhatjuk a $ \sigma $ és a $ \phi $ értéket egy olyan művelet beszerzéséhez, amelynek a típusa egyetlen qubit egységes.
Például a `R(PauliZ, PI() / 4, _)` típusa `(Qubit => Unit is Adj + Ctl)` .

> [!NOTE]
> A <xref:microsoft.quantum.intrinsic.r> művelet a bemeneti szöget 2 értékre osztja, és a-1 értékkel szorozza meg.
> $Z $ forgás esetén ez azt jelenti, hogy a $ \ket {0} $ eigenstate a $-\phi/$2, a $ \ket $ eigenstate pedig a $ \phi/$2 által elforgatott érték, hogy a $ \ket $ eigenstate a $ \phi $ \ket {1} {1} képest legyen elforgatva {0} .
>
> Ez különösen azt jelenti, hogy `T` csak a nem `R(PauliZ, PI() / 8, _)` releváns [globális fázisokban](xref:microsoft.quantum.glossary#global-phase)térnek el egymástól.
> Emiatt $T $ \frac{\pi} $-Gate néven is ismert {8} .
>
> Vegye figyelembe azt is, hogy az elforgatás körülbelül `PauliI` a $ \phi/$2 globális fázisát alkalmazza. Habár az ilyen fázisok nem relevánsak, ahogy azt [a koncepcionális dokumentumok](xref:microsoft.quantum.concepts.qubit)is felmutatják, az ellenőrzött rotációk szempontjából fontosak `PauliI` .

A kvantum-algoritmusokon belül gyakran hasznos a rotációk dyadic-frakcióként való kimutatása, például a $ \phi = \pi k/2 ^ n $ használata néhány $k \in \mathbb{Z} $ és $n \in \mathbb{N} $ esetében.
A <xref:microsoft.quantum.intrinsic.rfrac> művelet a megadott Pauli-tengely körüli rotációt valósít meg az egyezmény használatával.
Eltér attól, <xref:microsoft.quantum.intrinsic.r> hogy az elforgatási szög két típusú bemenetként van megadva `Int` , dyadic-frakcióként értelmezve.
Így `RFrac` az aláírással rendelkezik `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)` .
Implementálja az qubit egységes $ \exp (i \pi k \sigma/2 ^ n) $ értéket, ahol a $ \sigma $ az első argumentumnak megfelelő Pauli-mátrix, $k $ a második argumentum, és $n $ a harmadik argumentum.
`RFrac(_,k,n,_)`ugyanaz, mint a ( `R(_,-πk/2^n,_)` ). Megjegyzendő, hogy a szög a frakció *negatív* értéke.

A <xref:microsoft.quantum.intrinsic.rx> művelet egy rotációs műveletet valósít meg a Pauli $X $ tengely körül.
Aláírással rendelkezik `((Double, Qubit) => Unit is Adj + Ctl)` .
`Rx(_, _)`ugyanaz, mint `R(PauliX, _, _)` .

A <xref:microsoft.quantum.intrinsic.ry> művelet egy rotációs műveletet valósít meg a Pauli $Y $ tengely körül.
Aláírással rendelkezik `((Double, Qubit) => Unit is Adj + Ctl)` .
`Ry(_, _)`ugyanaz, mint `R(PauliY,_ , _)` .

A <xref:microsoft.quantum.intrinsic.rz> művelet egy rotációs műveletet valósít meg a Pauli $Z $ tengely körül.
Aláírással rendelkezik `((Double, Qubit) => Unit is Adj + Ctl)` .
`Rz(_, _)`ugyanaz, mint `R(PauliZ, _, _)` .

A <xref:microsoft.quantum.intrinsic.r1> művelet egy rotációt valósít meg a $ \ket {1} $, a $-$1 eigenstate $Z $ érték körüli megadott összeggel.
Aláírással rendelkezik `((Double, Qubit) => Unit is Adj + Ctl)` .
`R1(phi,_)`ugyanaz, mint amit a `R(PauliZ,phi,_)` követ `R(PauliI,-phi,_)` .

A <xref:microsoft.quantum.intrinsic.r1frac> művelet egy töredékes rotációt valósít meg a Z = 1 eigenstate körüli megadott összeggel.
Aláírással rendelkezik `((Int,Int, Qubit) => Unit is Adj + Ctl)` .
`R1Frac(k,n,_)`ugyanaz, mint amit a `RFrac(PauliZ,-k.n+1,_)` követ `RFrac(PauliI,k,n+1,_)` .

Alább látható egy példa egy rotációs műveletre (az ebben az esetben a Pauli $Z $ tengelyen, ebben a példányban), amely a Bloch szférára van leképezve:

![A Bloch szférára leképezett rotációs művelet](~/media/prelude_rotationBloch.png)

#### <a name="multi-qubit-operations"></a>Több Qubit műveletek ####

A fenti qubit műveletek mellett a Prelude számos több qubit műveletet is meghatároz.

Először a <xref:microsoft.quantum.intrinsic.cnot> művelet elvégzi a standard szintű vezérelt- `NOT` Gate, \begin{Equation} \operatorname{CNOT} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{bmatrix}.
\end{Equation} aláírással rendelkezik `((Qubit, Qubit) => Unit is Adj + Ctl)` , ami azt jelenti, hogy a $ \operatorname{CNOT} $ unitarily két önálló qubits.
`CNOT(q1, q2)`ugyanaz, mint `(Controlled X)([q1], q2)` .
Mivel az elválasztó `Controlled` lehetővé teszi a regisztrációt, a tömb szövegkonstans használatával `[q1]` jelezheti, hogy csak az egyetlen vezérlőt szeretnénk használni.

A <xref:microsoft.quantum.intrinsic.ccnot> művelet kétszeresen vezérelt nem kaput, más néven a Toffoli kaput hajt végre.
Aláírással rendelkezik `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)` .
`CCNOT(q1, q2, q3)`ugyanaz, mint `(Controlled X)([q1, q2], q3)` .

A <xref:microsoft.quantum.intrinsic.swap> művelet felcseréli a két qubits Quantum állapotait.
Ez azt is megvalósítja, hogy implementálja az egységes mátrix \begin{Equation} \operatorname{SWAP} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ 0 & 0 & 0 & \\ 1 \end{bmatrix}.
\end{Equation} aláírása `((Qubit, Qubit) => Unit is Adj + Ctl)` .
`SWAP(q1,q2)`egyenértékű a következővel, `CNOT(q1, q2)` `CNOT(q2, q1)` és utána `CNOT(q1, q2)` .

> [!NOTE]
> A SWAP-kapu *nem* egyezik meg a típussal rendelkező változó elemeinek átrendezésével `Qubit[]` .
> A alkalmazás a `SWAP(q1, q2)` és a által hivatkozott qubits állapotának módosítását okozza `q1` `q2` , miközben `let swappedRegister = [q2, q1];` csak azt befolyásolja, hogyan hivatkozunk ezekre a qubits.
> Emellett `(Controlled SWAP)([q0], (q1, q2))` lehetővé teszi, `SWAP` hogy a a harmadik qubit állapotára is felkerüljön, amelyet az elemek átrendezése nem jelenthet.
> A vezérelt SWAP-kapu, más néven a Fredkin-kapu, elég erős ahhoz, hogy tartalmazza az összes klasszikus számítást.

Végül a Prelude két műveletet biztosít a több qubit Pauli-operátorok exponenciális ábrázolásához.
A <xref:microsoft.quantum.intrinsic.exp> művelet a Pauli-mátrixok egy tízes szorzatán alapuló rotációs műveletet hajt végre. a többszörös qubit egységes \Begin{Equation} \operatorname{exp} (\vec{\sigma}, \phi) \mathrel{: =} \exp\left (i \phi \ sigma_0 \otimes \ sigma_1 \otimes \cdots \otimes \ sigma_n \right), a \end{Equation}, ahol a $ \vec{\sigma} = (\ sigma_0, \ sigma_1, \dots, \ sigma_n) $ az egyetlen Qubit Pauli-operátorok sorozata, és ahol a $ \phi $ egy szög.
Az `Exp` elforgatás a $ \vec{\sigma} $ elemet jelenti elemek tömbje `Pauli` , például aláírással `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)` .

A <xref:microsoft.quantum.intrinsic.expfrac> művelet ugyanazt a rotációs műveletet hajtja végre, a fentebb tárgyalt dyadic-frakciós jelölés használatával.
Aláírással rendelkezik `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)` .

> [!WARNING]
> A Pauli-operátorok tenser-termékének exponenciális száma nem egyezik meg a Pauli-operátorok exponenciálisan működő termékeivel.
> Vagyis $e ^ {i (Z \otimes Z) \phi} \ne e ^ {i Z \phi} \otimes e ^ {i Z \phi} $.

### <a name="measurements"></a>Mérések ###

A méréskor a mért operátor + 1 sajátérték egy `Zero` eredménynek felel meg, és az-1 sajátérték `One` .

> [!NOTE]
> Habár ez az egyezmény páratlannak tűnhet, két nagyon jó előnye van.
> Először is, a $ \ket {0} $ értéknek a megfigyelt `Result` értéke az érték `Zero` , míg a $ \ket $ megfigyelése {1} megfelel `One` a következőnek:.
> Másodszor, azt is kiírhatjuk, hogy a sajátérték $ \lambda $ megfelel egy eredménynek, $r $ értéke $ \lambda = (-1) ^ r $.

A mérési műveletek sem a, `Adjoint` sem a nem működőt támogatják `Controlled` .

A <xref:microsoft.quantum.intrinsic.measure> művelet egy vagy több qubits közös mérését végzi a Pauli-operátorok megadott termékében.
Ha a Pauli tömb és a qubit tömb eltérő hosszúságú, akkor a művelet sikertelen lesz.
`Measure`aláírással rendelkezik `((Pauli[], Qubit[]) => Result)` .

Vegye figyelembe, hogy a közös mérések nem egyeznek meg egyenként a qubit mérésével.
Vegyük például a következő állapotot: $ \ket {11} = \ket {1} \otimes \Ket {1} = X\otimes X \ket {00} $.
A $Z _0 $ és a $Z _1 $ mérése egyenként történik, $r _0 = $1 és $r _1 = $1.
$Z _0 Z_1 $ mérésével azonban egyetlen eredmény $r _ {\textrm{Joint}} = $0 lesz, ami azt jelenti, hogy a $ \ket $ párosítása {11} pozitív.
Másképpen fogalmazva, $ (-1) ^ {r_0 + r_1} = (-1) ^ r_ {\textrm{Joint}}) $.
Kritikus fontosságú, mivel a rendszer *csak* az ebből a mérésből származó paritást tanulja meg, a pozitív paritású 2 2 – qubit állapotok közötti, a \ket $ és a $ \ket $ közötti kapcsolatban szereplő kvantum-információk {00} {11} megmaradnak.
Ezt a tulajdonságot később kell megtekinteni, ahogy a hibajavításról van szó.

A kényelem érdekében a bevezetés két további műveletet is biztosít a qubits méréséhez.
Először is, mivel az qubit mérések végrehajtása meglehetősen gyakori, a bevezetés egy gyorsírást határoz meg ebben az esetben.
A <xref:microsoft.quantum.intrinsic.m> művelet a Pauli $Z $ operátort méri egyetlen qubit, és aláírással rendelkezik `(Qubit => Result)` .
`M(q)`egyenértékű a következővel: `Measure([PauliZ], [q])` .

A a <xref:microsoft.quantum.measurement.multim> Pauli $Z $ operátort a qubits minden egyes tömbje számára *külön* méri, és az egyes qubit kapott értékek *tömbjét* adja vissza `Result` .
Bizonyos esetekben ez optimalizálható. Rendelkezik aláírással ( `Qubit[] => Result[])` .
`MultiM(qs)`egyenértékű a következővel:

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
A névtér például olyan <xref:microsoft.quantum.math> hasznos műveleteket határoz meg, mint a <xref:microsoft.quantum.math.sin> és a <xref:microsoft.quantum.math.log> .
A Quantum Development Kit által biztosított implementáció a klasszikus .NET alaposztály-függvénytárat használja, így további kommunikációs kört eredményezhet a kvantum-programok és a klasszikus illesztőprogramjaik között.
Habár ez nem jelent problémát a helyi szimulátor esetében, ez a probléma akkor lehet teljesítményproblémák, ha távoli szimulátort vagy tényleges hardvert használ célként.
Ez azt is okozhatja, hogy az adott rendszer esetében az egyes célszámítógép befolyásolhatja a teljesítményt, ha felülbírálja ezeket a műveleteket az adott rendszeren hatékonyabb verziókkal.

### <a name="math"></a>Matematikai ###

A <xref:microsoft.quantum.math> névtér számos hasznos funkciót biztosít a .net alaposztály könyvtárának [ `System.Math` osztályában](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1).
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

Végül a <xref:microsoft.quantum.bitwise> névtér számos hasznos függvényt biztosít az egész számok bitenkénti-operátoron keresztüli módosításához.
A például <xref:microsoft.quantum.bitwise.parity> egy egész szám bitenkénti paritását adja vissza egy másik egész számként.
