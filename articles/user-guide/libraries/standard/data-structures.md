---
title: Adatstruktúrák a Q# standard könyvtárakban
description: Ismerje meg az adatstruktúrákat, az Oracle-ket és a dinamikus generátorokat a Microsoft Q# szabványos könyvtáraiban.
author: QuantumWriter
uid: microsoft.quantum.libraries.data-structures
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: c3ce5d531618c269d15be3e4eb58ecbb597a022c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92692230"
---
# <a name="data-structures-and-modeling"></a>Adatstruktúrák és-modellezés #

## <a name="classical-data-structures"></a>Klasszikus adatstruktúrák ##

A kvantum-fogalmakat jelképező, felhasználó által definiált típusokkal együtt a Canon a Quantum Systems vezérléséhez használt klasszikus adatokkal kapcsolatos műveleteket, funkciókat és típusokat is biztosít.
A <xref:Microsoft.Quantum.Arrays.Reversed> függvény például bemenetként fogad egy tömböt, és fordított sorrendben adja vissza ugyanazt a tömböt.
Ezt követően felhasználható egy típusú tömbben `Qubit[]` , hogy ne kelljen felesleges $ \operatorname{swap} $ gateset alkalmaznia, ha az egész számok kvantum-ábrázolásai között vált.
Hasonlóképpen láttuk az előző szakaszban, hogy az űrlap típusa `(Int, Int -> T)` hasznos lehet a véletlen hozzáférésű gyűjtemények ábrázolásához, így a <xref:Microsoft.Quantum.Arrays.LookupFunction> függvény kényelmes módszert biztosít az ilyen típusú típusok tömbből való összeállításához.

### <a name="pairs"></a>Párok ###

A Canon támogatja a párok funkcionális stílusú jelölését, amely kiegészíti a rekordok való hozzáférését:

```qsharp
let pair = (PauliZ, register); // type (Pauli, Qubit[])
ApplyToEach(H, Snd(pair)); // No need to deconstruct to access the register.
```

### <a name="arrays"></a>Tömbök ###

A Canon számos funkciót biztosít a tömbök manipulálására.
Ezek a függvények Type-paraméteres, így bármilyen típusú tömbökkel használhatók Q# .
A <xref:Microsoft.Quantum.Arrays.Reversed> függvény például egy olyan új tömböt ad vissza, amelynek elemei fordított sorrendben vannak a bemenettől.
Ezzel megváltoztathatja, hogy a rendszer hogyan jelenítse meg a kvantum-regisztereket a műveletek meghívásakor:

```qsharp
let leRegister = LittleEndian(register);
// QFT expects a BigEndian, so we can reverse before calling.
QFT(BigEndian(Reversed(leRegister!)));
// This is how the LittleEndianAsBigEndian function is implemented:
QFT(LittleEndianAsBigEndian(leRegister));
```

Hasonlóképpen, a <xref:Microsoft.Quantum.Arrays.Subarray> függvény használható a tömb elemeinek átrendezésére vagy az elemek részhalmazának elvégzésére:

```qsharp
// Applies H to qubits 2 and 5.
ApplyToEach(H, Subarray([2, 5], register));
```

A Flow Control szolgáltatással kombinálva a Array manipulációs függvények, például a (z) <xref:Microsoft.Quantum.Arrays.Zipped> hatékony módot biztosítanak a kvantum-programok kiírására:

```qsharp
// Applies X₃ Y₁ Z₇ to a register of any size.
ApplyToEach(
    ApplyPauli(_, register),
    Map(
        EmbedPauli(_, _, Length(register)),
        Zipped([PauliX, PauliY, PauliZ], [3, 1, 7])
    )
);
```

## <a name="oracles"></a>Jóslatok ##

A [fázisok becslése](https://en.wikipedia.org/wiki/Quantum_phase_estimation_algorithm) és az [amplitúdó-erősítési](https://en.wikipedia.org/wiki/Amplitude_amplification) irodalomban gyakran megjelenik egy Oracle koncepciója.
Itt az Oracle kifejezés olyan tábla-kvantum-alrutint jelöl, amely qubits végez, és a választ fázisként adja vissza.
Ez az alrutin gyakran úgy gondolja, mint egy olyan kvantum-algoritmus bemenete, amely más paraméterek mellett is elfogadja az Oracle-t, és egy sor kvantum-műveletet alkalmaz, és a kvantum-alrutin hívását kezeli, mintha egy alapvető kapu lenne.
Természetesen ahhoz, hogy a nagyobb algoritmus ténylegesen megvalósítható legyen, meg kell adni az Oracle-nek az alapvető kapuk konkrét összetételét, de az Oracle-t meghívó algoritmus megismeréséhez nincs szükség ilyen felbomlásra.
A-ben Q# Ez a művelet az első osztályú értékeket használja, így a műveletek átadhatók a kvantum-algoritmusok megvalósításához a fekete dobozos módon.
Emellett a felhasználó által definiált típusok a különböző Oracle-adatábrázolások típusos biztonságos módon történő címkézésére szolgálnak, így megnehezítik a különböző típusú fekete Box-műveletek véletlen kicsomagolását.

Az ilyen Oracle-k számos különböző kontextusban jelennek meg, beleértve az olyan híres példákat is, mint például a a a megtalált [Keresés](https://en.wikipedia.org/wiki/Grover%27s_algorithm) és a Quantum szimulációs algoritmusok.
Itt a csak két alkalmazáshoz szükséges Oracle-ket vesszük figyelembe: az amplitúdó erősítése és a fázisok becslése.
Első lépésként megbeszéljük az amplitúdó-bővítési Oracle-ket.

### <a name="amplitude-amplification-oracles"></a>Amplitúdó-erősítés Oracles ###

Az amplitúdó-erősítési algoritmus célja, hogy elvégezze a kezdeti állapot és a végső állapot közötti rotációs műveletet az állapot reflexiós sorrendjének alkalmazásával.
Ahhoz, hogy az algoritmus működjön, mindkét állapotnak meg kell határoznia.
Ezeket a specifikációkat két Oracle adja meg.
Ezek a jóslatok úgy működnek, hogy a bemeneteket két szóközre, egy "cél" alterületre és egy "kezdeti" alterületre bontja.
Az Oracle-k azonosítják az ilyen alterületeket, hasonlóan ahhoz, ahogyan a Pauli-operátorok két szóközt azonosítanak, egy $ \pm $1 fázist alkalmazva ezekre a szóközökre.
A fő különbség az, hogy ezek a szóközök nem szükségesek az alkalmazásban.
Azt is vegye figyelembe, hogy ez a két alterület általában nem zárják ki egymást: mindkét szóköz tagjai lesznek.
Ha ez nem igaz, az amplitúdó-erősítésnek nincs hatása, ezért a kezdeti alterületnek nem kell átfedésben lennie a cél alterülettel.

A következő művelet végrehajtásához meg kell adni az első Oracle-t, amelyre az amplitúdó-erősítésre van szükségünk $P \_ $0.  Minden, a "kezdeti" alterületen a $ \ket{x} $ értékkel rendelkező állapothoz $P \_ 0 \ket{x} =-\ket{x} $ és minden olyan állapothoz $ \ket{y} $, amely nem ebben az altérben van $P \_ 0 \ket{y} = \ket{y} $.
A célként megadott alterületet ($P _1 $) jelölő Oracle pontosan ugyanazt az űrlapot veszi fel.
Minden állapothoz $ \ket{x} $ a célként megadott alterületen (azaz minden olyan állapot esetében, amelynek a kimenetét szeretné kiadni), $P _1 \ ket {x} =-\ket{x} $.
Hasonlóképpen, az összes olyan állam esetében, amely nem a \ket{y} $ $P _1 \ ket {y} = \ket{y} $.
Ezt a két reflexiót egyesítjük egy olyan operátor kialakításával, amely az amplitúdó erősítésének egyetlen lépését, $Q =-P_0 P_1 $ értéket adja meg, ahol a teljes mínusz jel csak az ellenőrzött alkalmazások esetében fontos.
Az amplitúdó-erősítés ezután egy kezdeti állapotba kerül, amely a kezdeti alterületen található $ \ket{\psi} $, majd végrehajtja a $ \ket{\psi} \mapsto Q ^ m \ket{\psi} $ értéket.
Az ilyen iterációk elvégzése garantálja, hogy ha az egyik kezdeti állapottal rendelkezik, amely átfedésben van a $ \sin ^ 2 (\theta) $ karakterrel a megjelölt területtel, akkor $m $ iteráció után az átfedés lesz $ \sin ^ 2 ([2m + 1] \theta) $.
Ezért általában úgy szeretnénk kiválasztani $m $-t, hogy legyen egy ingyenes paraméter, például $ [2m + 1] \theta = \ pi/2 $; azonban az ilyen merev megoldások nem annyira fontosak az amplitúdó-erősítés bizonyos formáinál, például a rögzített pont amplitúdójának erősítése.
Ez a folyamat lehetővé teszi, hogy egy olyan állapotot Készítsünk elő a megjelölt alterületen, amely a jelölési függvénynek és az állapot-előkészítési függvénynek csak egy szigorúan klasszikus eszközön való használata esetén lehetséges.
Ezért fontos, hogy az amplitúdó-erősítés a kvantum-számítástechnika számos alkalmazásának jelentős építőeleme.

Az algoritmus használatának megismeréséhez hasznos lehet olyan példát biztosítani, amely az Oracle-ket is felépíti.  Ebben a beállításban érdemes megfontolni a a kiinduló adatbázis-keresésekhez szükséges a a a a a
A a a \ket{+} ^ {\otimes n} = H ^ {\otimes n} \ket $ értéket az {0} egyik (potenciálisan) számos megjelölt állapotba alakítja a.
A további egyszerűsítés érdekében nézzük meg azt az esetet, amikor az egyetlen megjelölt állapot $ \ket {0} $.
Ezt követően két Oracle-t tervezünk: az egyiket, amely csak az $ \ket{+} ^ {\otimes n} $ kezdeti állapotot jelöli mínusz jellel, egy másikat, amely mínusz jellel jelöli meg a megjelölt állapotot ($ \ket {0} $).
Az utóbbi kaput a következő eljárással lehet megvalósítani a Canon vezérlési folyamat műveleteinek használatával:

```qsharp
operation ReflectAboutAllZeros(register : Qubit[]) : Unit 
is Adj + Ctl {

    // Apply $X$ gates to every qubit.
    ApplyToEach(X, register);

    // Apply an $n-1$ controlled $Z$-gate to the $n^{\text{th}}$ qubit.
    // This gate will lead to a sign flip if and only if every qubit is
    // $1$, which happens only if each of the qubits were $0$ before step 1.
    Controlled Z(Most(register), Tail(register));

    // Apply $X$ gates to every qubit.
    ApplyToEach(X, register);
}
```

Ez az Oracle a művelet egy speciális esete <xref:Microsoft.Quantum.Canon.RAll1> , amely lehetővé teszi, hogy tetszőleges fázisban forgatható legyen a $ \phi = \pi $ reflexiós eset helyett.
Ebben az esetben `RAll1` hasonló az <xref:Microsoft.Quantum.Intrinsic.R1> előlépési művelethez, mert az a $ \ket{11\cdots1} $-t a qubit állapot ($ \ket $) helyett elforgatja {1} .

A kezdeti alterületet jelölő Oracle hasonló módon építhető ki.
A pseudocode-ben:

1. $H $ kaput alkalmazzon minden qubit.
2. $X $ kaput alkalmazzon minden qubit.
3. Alkalmazzon egy $n-$1 vezérelt $Z $-Gate értéket a $n ^ {\text{th}} $ qubit.
4. $X $ kaput alkalmazzon minden qubit.
5. $H $ kaput alkalmazzon minden qubit.

Ezúttal <xref:Microsoft.Quantum.Canon.ApplyWith> a <xref:Microsoft.Quantum.Canon.RAll1> fent ismertetett művelettel együtt is bemutatjuk a használatát:

```qsharp
operation ReflectAboutInitial(register : Qubit[]) : Unit
is Adj + Ctl {
    ApplyWithCA(ApplyToEach(H, _), ApplyWith(ApplyToEach(X, _), RAll1(_, PI()), _), register);
}
```

Ezt a két Oracle-t összekapcsoljuk a két állapot és a determinisztikus módon átalakítás $ \ket{+} ^ {\otimes n} $ és $ \ket $ közötti elforgatásával, {0} amely számos, a $ Hadamard ^ n} számú réteggel rendelkező \sqrt{2 $ (ie $m \propto \sqrt{2 ^ n} $) és a nagyjából 2 ^ n $ rétegek, amelyek szükségesek a nem determinisztikus módon előkészíteni a $ \ket {0} $ állapotot a kezdeti állapot előkészítésével és mérésével, amíg meg nem történik a $0 $ megfigyelve.

### <a name="phase-estimation-oracles"></a>Fázisok becslése Oracles ###

A fázisok becsléséhez az Oracles valamivel több természetesebb.
A fokozatos becslés célja, hogy olyan alrutint tervezzen, amely képes egy egységes mátrix eigenvalues való mintavételre.
Ez a módszer nem feltétlenül elengedhetetlen a Quantum szimulációban, mert a kémia és az anyagi tudományok számos fizikai problémája miatt ezek a eigenvalues a kvantum-rendszerek talajközeli energiáit biztosítják, amelyek értékes információkat biztosítanak az anyagok és a molekulák reagálási dinamikájának fázis-diagramjairól.
A fázisok becslésének minden íz-bemenetének egységesnek kell lennie.
Ez az egységes szolgáltatás a két Oracle-típus egyikének megfelelően van leírva.

> [!TIP]
> Az alábbiakban ismertetett Oracle-típusok mindegyike szerepel a mintákban.
> Ha többet szeretne megtudni a folyamatos lekérdezési Oracle-ról, tekintse meg a [ **PhaseEstimation** mintát](https://github.com/microsoft/Quantum/tree/main/samples/characterization/phase-estimation).
> Ha többet szeretne megtudni a diszkrét lekérdezési Oracle-ról, tekintse meg a [ **IsingPhaseEstimation** mintát](https://github.com/microsoft/Quantum/tree/main/samples/simulation/ising/phase-estimation).

Az Oracle első típusa, amely egy különálló lekérdezési Oracle-t hív meg, és a felhasználó által definiált típusnak felel meg <xref:Microsoft.Quantum.Oracles.DiscreteOracle> , egyszerűen magában foglal egy egységes mátrixot.
Ha $U $ az az egységes, amelynek a eigenvalues szeretnénk megbecsülni, akkor az Oracle for $U $ egyszerűen egy olyan alrutinra vonatkozik, amely megvalósítja a $U $-t.
Előfordulhat például, hogy az $U $ értéket kell megadnia az amplitúdó-becsléshez a fentiekben megadott Oracle $Q $ értékre.
A mátrix eigenvalues felhasználható a kezdeti és a megcélzott állapotok, a $ \sin ^ 2 (\theta) $ közötti átfedés megbecslésére, amely a másodfokú módon kevesebb mintát használ, mint amennyit egyébként kellene.
Ez a szakasz becslésének alkalmazásával keresi a következőt: a ($Q $, az amplitúdó-becslések monikere.
Egy másik gyakori alkalmazás, amely a kvantum-metrológiaban széles körben használatos, egy kis elforgatási szöget eredményez.
Más szóval a $ \theta $ értéket szeretnénk megbecsülni egy ismeretlen rotációs kapun $R _z (\theta) $ formában.
Ilyen esetekben az az alrutin, amelyet a \theta $ értékkel való együttműködéshez szeretne használni a kapun, $ $ \begin{align} U & = R_z (\theta) \\ \\ & = \begin{bmatrix} e ^ {-i \theta/2} & 0 \\ \\ 0 & e ^ {i \ THÉTA/2} \end{bmatrix}.
\end{align} $ $

A fázisok becslésében használt második Oracle a folyamatos lekérdezési Oracle, amelyet a típus képvisel <xref:Microsoft.Quantum.Oracles.ContinuousOracle> .
A folyamatos lekérdezési Oracle a fázis becsléséhez $U (t) $, ahol $t $ egy klasszikusan ismert valós szám.
Ha hagyjuk, hogy a $U $ legyen rögzített, akkor a folyamatos lekérdezési Oracle az űrlapot $U (t) = U ^ t $ értéket veszi fel.
Ez lehetővé teszi, hogy lekérdezzen egy olyan mátrixot, mint például a $ \sqrt{U} $, amely nem valósítható meg közvetlenül a diszkrét lekérdezési modellben.

Ez a típusú Oracle akkor hasznos, ha nem egy adott egységes adattípust végez, hanem szeretné megismerni az egységes szolgáltatás létrehozójának tulajdonságait.
A dinamikus kvantum-szimulációban például az a cél, hogy olyan kvantum-áramköröket dolgozzon ki, amelyek szorosan megközelítik $U (t) = e ^ {-i H t} $-t a Hermitian-mátrixhoz $H $ és az Evolution Time $t $ értéknél.
$U (t) $ eigenvalues közvetlenül kapcsolódik a $H $ eigenvalues.
Ezt úgy tekintheti meg, hogy $H $: $H \ket{E} = E\ket {E} $ eigenvector, így könnyen látható, hogy milyen a mátrix exponenciálisa, hogy $U (t) \ket{E} = e ^ {i\phi} \ ket {E} = e ^ {-iEt} \ket{E} $.
Így a $U (t) $ eigenphase becslése megadja a sajátérték $E $ értéket, feltételezve, hogy a eigenvector $ \ket{E} $ bemenet bekerül a fázis-becslési algoritmusba.
Ebben az esetben azonban a $t $ érték megadható a felhasználó saját belátása szerint, mert az $t $ sajátérték $E $ értékkel rendelkező $E =-\ Phi/t $ használatával egyedileg visszaállíthatók.
Mivel a kvantum-szimulációs módszerek lehetővé teszik a töredékes evolúció végrehajtását, ez a fázis-értékelési algoritmusok további szabadságot biztosítanak az egységes állapot lekérdezése során, különösen, ha a diszkrét lekérdezési modell lehetővé teszi, hogy csak a unitaries $U ^ j $ értéket alkalmazza a $t $U $j rendszer
Ez azért fontos, hogy a fázis-becslési algoritmusok alapján minden utolsó uncia hatékonyságot megnyomjon, mert lehetővé teszi számunkra, hogy pontosan olyan kísérletet válasszon, amely a legtöbbet a $E $; míg a különálló lekérdezéseken alapuló metódusoknak a kiegyezéssel kell rendelkezniük az algoritmusban található lekérdezések legjobb egész számának kiválasztásával.

Ennek konkrét példája, ha nem a kapu elforgatási szögét, hanem egy forgó kvantum-rendszer feldolgozási gyakoriságát kívánja megbecsülni.
Az ilyen kvantum-dinamika leírása $U (t) = R_z (2 \ Omega t) $ az Evolution Time $t $ és a $ \omega $ ismeretlen gyakorisággal.
Ebben a kontextusban a $U (t) $ értéket szimulálhatja bármely $t $-hez egyetlen $R _z $ Gate használatával, és így nem kell korlátoznia magunkat arra, hogy csak a különálló lekérdezésekre korlátozódjon.
Az ilyen folyamatos modell azt a tulajdonságot is megtudhatja, hogy a $2 \ PI $-nál nagyobb frekvenciákon a folyamatos lekérdezéseket használó fázis-becslési folyamatokból megtudhatja, hogy milyen fázis-információk láthatók a logaritmus-függvény elágazásával, a $t $ nem arányos értékeit érintő kísérletek eredményeiből.
Így olyan problémákhoz, mint például az Oracle fázis-becsléshez kapcsolódó folyamatos lekérdezési modellek, nem csupán megfelelőek, de a diszkrét lekérdezési modell esetében is előnyösek.
Emiatt a Q# lekérdezések mindkét formájához van funkció, és a felhasználónak el kell döntenie, hogy egy fázis-becslési algoritmust válasszon az igényeinek megfelelően, valamint a rendelkezésre álló Oracle típusát.

## <a name="dynamical-generator-modeling"></a>Dinamikus generátor modellezése ##

A Time-Evolution generátorai ismertetik az állapotok időbeli alakulását. Például a $ \ket{\psi} $ kvantum-állapot dinamikáját a következő Schrödinger-egyenlet szabályozza: $ $ \begin{align} i\frac {d \ket{\psi (t)}} {d t} & = H \ket{\psi (t)}, \end{align} $ $ Hermitian-mátrixmal $H $, amely a Hamilton néven is ismert. Adott kezdeti állapot: $ \ket{\psi (0)} $ $t = $0, a formális megoldás erre az egyenletre $t $ időpontban is, elvileg a $ $ \begin{align} \ket{\psi (t)} = U (t) \ket{\psi (0)}, \end{align} $ $, ahol a mátrix exponenciális $U (t) = e ^ {-i H t} $-t nevezzük az egységes idő-Evolution operátornak. Bár az alábbi űrlap-generátorokra koncentrálunk, Kiemeljük, hogy a koncepció szélesebb körben, például a nyílt kvantum-rendszerek szimulációján vagy az absztrakt különbözeti egyenletek esetében.

A dinamikus szimuláció elsődleges célja az, hogy az idő-evolúciós operátort egy kvantum-számítógép qubits kódolva hajtsa végre.  Sok esetben előfordulhat, hogy a Hamilton néhány $d $ egyszerűbb kifejezésből álló összegre van bontva

$ $ \begin{align} H & = \sum ^ {d-1} _ {j = 0} H_j, \end{align} $ $

a kvantum-számítógépeken egyszerűen megvalósítható az egyes kifejezések időbeli alakulása. Ha például $H _j $ egy Pauli $X _1X_2 $ operátor, amely a qubit-regisztráció 1. és 2. részében tevékenykedik `qubits` , a Time-Evolutiont a $t $-ig bármikor megvalósíthatja a művelet meghívásával `Exp([PauliX,PauliX], t, qubits[1..2])` , amely aláírást tartalmaz `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)` . Ahogy az a Hamilton szimulációban is szerepel, az egyik megoldás, hogy az $H $ értékkel közelítse meg az időbeli alakulást az egyszerűbb műveletek sorozatával.

$ $ \begin{align} U (t) & = \left (e ^ {-iH \_ 0 t/r} e ^ {-IH \_ 1 t/r} \cdots e ^ {-IH \_ {d-1} t/r} \right) ^ {r} + \mathcal{O} (d ^ 2 \ max_j \\ | H \_ j \\ | ^ 2 t ^ 2/r), \end{align} $ $

ahol az egész szám $r > $0 a közelítési hibát vezérli.

A dinamikus generátor modellező könyvtára keretet biztosít a bonyolult generátorok szisztematikus kódolásához az egyszerűbb generátorok szempontjából. Ezt a leírást később átadhatják a szimulációs függvénytárnak, amely egy tetszőleges szimulációs algoritmussal valósítja meg a Time-Evolutiont, számos részletet pedig automatikusan elintéz.

> [!TIP]
> Az alább ismertetett dinamikus létrehozó függvénytárat a minták tartalmazzák. A Ising modellen alapuló példáért tekintse meg a [ **IsingGenerators** mintát](https://github.com/microsoft/Quantum/tree/main/samples/simulation/ising/generators).
> A molekuláris hidrogénen alapuló példákért tekintse meg a [**H2SimulationCmdLine**](https://github.com/microsoft/Quantum/tree/main/samples/simulation/h2/command-line) és a [**H2SimulationGUI**](https://github.com/microsoft/Quantum/tree/main/samples/simulation/h2/gui) mintákat.

### <a name="complete-description-of-a-generator"></a>Generátor leírásának teljes leírása ###

A legfelső szinten a Hamilton teljes leírása szerepel a `EvolutionGenerator` felhasználó által definiált típusban, amely két összetevőből áll:

```qsharp
newtype EvolutionGenerator = (EvolutionSet, GeneratorSystem);
```

A `GeneratorSystem` felhasználó által definiált típus a Hamilton klasszikus leírása.

```qsharp
newtype GeneratorSystem = (Int, (Int -> GeneratorIndex));
```

A rekord első eleme `Int` tárolja a $d $ értéket a Hamilton, a második elem `(Int -> GeneratorIndex)` pedig egy függvény, amely egy egész indexet képez le \{ 0, 1,..., d-1 \} $ értékről egy `GeneratorIndex` felhasználó által definiált típusra, amely egyedileg azonosítja az egyes primitív kifejezéseket a Hamilton. Vegye figyelembe, hogy a Hamilton lévő feltételek gyűjteményének a tömb helyett függvényként való kifejezése `GeneratorIndex[]` lehetővé teszi az on-fly számítást, `GeneratorIndex` amely különösen akkor hasznos, ha a Hamiltonians nagy számú kifejezéssel van ellátva.

Alapvetően nem határozunk meg olyan konvenciót, amely alapján a könnyen szimulálható, hogy milyen primitív feltételekkel rendelkezik `GeneratorIndex` . Előfordulhat például, hogy az egyszerű feltételek a fentiekben említettek szerint Pauli-operátorok, de a kvantum-kémia szimulációjában gyakran használt megsemmisítési és Fermionic is lehetnek. Önmagában a értelmetlen, `GeneratorIndex` mert nem írja le, hogy az adott kifejezés alapján hogyan alakulhat ki az idő – az evolúció a kvantum-áramkörként.

Ezt úgy oldja meg, hogy egy `EvolutionSet` felhasználó által definiált típust határoz meg, amely egy bizonyos Canonical-készletből leképezett leképezést végez, `GeneratorIndex` egy egységes operátorra, a `EvolutionUnitary` -ra, amely kvantum-áramkörként van kifejezve. A `EvolutionSet` meghatározza, hogy a hogyan `GeneratorIndex` legyen strukturálva, és meghatározza a lehetséges készletet is `GeneratorIndex` .

```qsharp
newtype EvolutionSet = (GeneratorIndex -> EvolutionUnitary);
```

### <a name="pauli-operator-generators"></a>Pauli-kezelő generátorok ###

A generátorok konkrét és hasznos példája olyan Hamiltonians, amely a Pauli-operátorok összessége, amelyek mindegyike valószínűleg eltérő együtthatóval rendelkezik.
$ $ \begin{align} H & = \sum ^ {d-1} _ {j = 0} a_j H_j, \end{align} $ $, ahol minden $ \hat H_j $ a Pauli csoportból lett kirajzolva. Ilyen rendszerek esetén olyan `PauliEvolutionSet()` típusú típust biztosítunk, `EvolutionSet` amely meghatározza a Pauli-csoport egy elemének, valamint egy együttható azonosítására szolgáló konvenciót `GeneratorIndex` , amely a következő aláírással rendelkezik.

```qsharp
newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```

A kódolásban az első paraméter `Int[]` egy Pauli-karakterláncot határoz meg, ahol a $ \Hat I\rightarrow $0, a $ \Hat X\rightarrow $1, a $ \Hat Y\rightarrow $2 és a $ \Hat Z\rightarrow $3. A második paraméter a `Double[]` Pauli-karakterlánc együtthatóját tárolja a Hamilton. Vegye figyelembe, hogy a tömbnek csak az első eleme van használatban. A harmadik paraméter `Int[]` indexeli azokat a qubits, amelyeken ez a Pauli-karakterlánc működik, és nem rendelkezhet duplikált elemekkel. Így a $0,4 \hat X_0 \hat Y_8 \hat I_2 \hat Z_1 $ Hamilton kifejezés a következőképpen jelenhet meg

```qsharp
let generatorIndexExample = GeneratorIndex(([1,2,0,3], [0.4]]), [0,8,2,1]);
```

Az `PauliEvolutionSet()` egy olyan függvény, amely az űrlap bármelyikét leképezi `GeneratorIndex` `EvolutionUnitary` a következő aláírással.

```qsharp
newtype EvolutionUnitary = ((Double, Qubit[]) => Unit is Adj + Ctl);
```

Az első paraméter az időtartamot jelöli, amelyet a (z) és a (z `GeneratorIndex` ) egységes evolúciós együtthatója szoroz. A második paraméter a qubit regisztrálja az egységes műveleteket. 

### <a name="time-dependent-generators"></a>Time-Dependent generátorok ###

Sok esetben érdeklik az időfüggő generátorok modellezése is, például a következő Schrödinger-egyenletben: $ $ \begin{align} i\frac {d \ket{\psi (t)}} {d t} & = \hat H (t) \ket{\psi (t)}, \end{align} $ $, ahol a generátor $ \hat H (t) $ most időfügg. Ebben az esetben a fenti időponttól független generátorok kiterjesztése egyszerű. Ahelyett, hogy rögzítette `GeneratorSystem` a Hamilton összes $t $-os időpontra vonatkozó leírását, a `GeneratorSystemTimeDependent` felhasználó által definiált típust kell használnia.

```qsharp
newtype GeneratorSystemTimeDependent = (Double -> GeneratorSystem);
```

Az első paraméter egy folytonos ütemezett paraméter, $s \in [0, 1] $, és az ilyen típusú függvények az `GeneratorSystem` adott ütemtervhez adott értéket adnak vissza. Vegye figyelembe, hogy az ütemezett paraméter lineárisan kapcsolódhat a fizikai idő paraméterhez (például $s = t/T $) a szimulációs $T $-hoz tartozó összes időpontig. Általánosságban azonban ez nem szükséges.

Ehhez hasonlóan a generátor teljes leírására van szükség `EvolutionSet` , ezért definiáljuk a `EvolutionSchedule` felhasználó által definiált típust.

```qsharp
newtype EvolutionSchedule = (EvolutionSet, GeneratorSystemTimeDependent);
```
