---
title: Quantum-algoritmusok a-benQ#
description: Ismerje meg az alapvető kvantum-számítási algoritmusokat, beleértve az amplitúdó-erősítést, a Fourier-transzformációt, a drapériát és a Beauregard-kiegészítéseket, valamint a fázisok
author: QuantumWriter
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.algorithms
no-loc:
- Q#
- $$v
ms.openlocfilehash: 0b5972480061c460345057285bbfe53305acc122
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868814"
---
# <a name="quantum-algorithms"></a>Quantum algoritmusok #

## <a name="amplitude-amplification"></a>Amplitúdó-erősítés ##

Az *amplitúdó-erősítés* a kvantum-számítástechnika alapvető eszközeinek egyike. Ez az alapvető elképzelés, hogy a megalapozott kutatás, az amplitúdó-becslés és számos Quantum Machine learning algoritmus.  Számos változat létezik, és a-ben Q# egy általános verziót biztosítunk, amely a részleges reflexiókkal ellátott, az alkalmazás legszélesebb területét lehetővé tevő, részben megjelenő, a teljes adatmennyiséget eredményező,

Az amplitúdó-erősítés mögötti központi elképzelés az, hogy kiterjesztheti a kívánt eredmény valószínűségét a reflexiók sorrendjének végrehajtásával.  Ezek a reflexiók a kezdeti állapotot közelebb viszik a kívánt cél állapothoz, amelyet gyakran jelölt állapotnak nevezünk.  Pontosabban, ha a kiindulási állapot jelölésének valószínűsége jelölt állapotban van, a $ \sin ^ 2 (\theta) $, majd az amplitúdó-$m erősítés alkalmazása után a siker valószínűsége $ \sin ^ 2 ((2m + 1) \theta) $ lesz.  Ez azt jelenti, hogy ha a $ \theta = \ Pi/[2 (2n + 1)] $ értéket adja meg a $ $n $ értéknél, akkor az amplitúdó-erősítés képes növelni a siker valószínűségét $100 \\ % $ után $n $ iterációk amplitúdó-erősítéssel.  Mivel a $ \theta = \sin ^ {-1} (\sqrt{\Pr (sikeres)}) $ Ez azt jelenti, hogy a sikeres determinisztikus módon beszerzéséhez szükséges Ismétlések száma másodfokúan alacsonyabb, mint a várt szám, amely nem determinisztikus módon véletlenszerű mintavétel használatával.

Az amplitúdó-erősítés minden iterációja megköveteli, hogy két reflexiós operátor legyen megadva. Pontosabban, ha a $Q $ érték az amplitúdó erősítésének iterációja, és $P _0 $ egy kivetítő operátor a kezdeti alterületre, és $P _1 $ a kivetítő a megjelölt alterületre, majd $Q =-(\boldone-2P_0) (\boldone-2P_1) $.  Ne felejtse el, hogy a kivetítő olyan Hermitian operátor, amely eigenvalues $ + $1 és $0 $ értékű, és ennek eredményeképpen a $ (\boldone-2P_0) $ érték egységes, mert olyan eigenvalues rendelkezik, amely az egység gyökere (ebben az esetben a $ \pm $1). Tegyük fel például, hogy az első állapotú $H ^ {\otimes n} \ket {0} $ és a megjelölt állapot $ \ket{m} $, $P _0 = H ^ {\otimes n} \ket {0} \bra {0} H ^ {\otimes n} $ és $P _1 = \ket{m}\bra{m} $.  Az amplitúdó-erősítés legtöbb alkalmazásában a $P _0 $ egy kezdeti állapotba kerül, amely azt jelenti, hogy $P _0 = \boldone-2 \ ket {\ PSI} \ melltartó {\ PSI} $ egyes Vector $ \ket{\psi} $; a feledékenység amplitúdó-amplication $P _0 $ esetében azonban jellemzően sok kvantum-állapotot fog kiszolgálni (azaz a $P _0 $ $ + $1 sajátérték többszöröse meghaladja a $1 $-ot).

Az amplitúdó-erősítés mögötti logika közvetlenül a $Q $ Eigen-felbomlásával következik.  Pontosabban, a kezdeti állapotú, nem nulla szintű támogatással rendelkező $Q $ eigenvectors az $P _0 $ és $P _1 $ eigenvectors $ + $1-as lineáris kombinációját jeleníti meg.  Az amplitúdó-erősítés kezdeti állapota (feltételezve, hogy a $P _0 $ érték $ + $1 eigenvector) írható $ $ \ket{\psi} = \frac{-i}{\sqrt {2} } \left (e ^ {i\theta} \ ket {\ psi_ +} + e ^ {-i\theta} \ ket {\ psi_-} \right), $ $, ahol a $ \ket{\ psi_ \pm} $ eigenvectors $Q $ eigenvalues $e ^ {\pm 2i \ Théta} $, és csak a $ + $1 eigenvectors támogatja a $P _0 $ és $P _1 $.  Az a tény, hogy a eigenvalues $e ^ {\pm i \theta} $, azt feltételezi, hogy a kezelő $Q $ elforgatást hajt végre a két kivetítő által meghatározott kétdimenziós alterületen, valamint a kezdeti állapotot, ahol a forgási szög $2 \ THÉTA $.  Ezért a siker valószínűsége $m $ iterációk után $Q $ a sikerességi valószínűség: $ \sin ^ 2 ([2m + 1] \theta) $.

Egy másik hasznos tulajdonság, amely abból ered, hogy a sajátérték $ \theta $ közvetlenül kapcsolódik annak valószínűségéhez, hogy a kezdeti állapot meg lesz jelölve (abban az esetben, ha $P _0 $ egy kivetítő csak a kezdeti állapotra).  Mivel a eigenphases $Q $ a $2 \ THÉTA = 2 \ Sin ^ {-1} (\sqrt{\Pr (sikeres)}) $, akkor a következő lépés az, hogy ha a fázisok becslését $Q $ értékre alkalmazzuk, akkor megtudhatjuk, hogy mi a siker valószínűsége egy egységes kvantum-eljárás esetében.  Ez azért hasznos, mert a kvantum-eljáráshoz tartozó, másodfokú módon kevesebb alkalmazásra van szükség, hogy megismerje a siker valószínűségét, mint egyébként.

Q#bevezeti az amplitúdó-erősítést a feledékenység amplitúdó-erősítésének specializációja.  A feledékenység amplitúdó-erősítése ezt a monikert keresi, mert a kezdeti eigenspace kivetítőnek nem kell kivetítőnek lennie a kezdeti állapothoz.  Ebben az értelemben a protokoll a kezdeti állapotba kerül.  A feledékenység amplitúdó-erősítésének legfontosabb alkalmazása az egységes Hamilton-szimulációs módszerek bizonyos *lineáris kombinációjában* van, amelyben a kezdeti állapot ismeretlen, de a szimulált Ancilla-regiszterrel együtt válik elérhetővé a szimulációs protokollban.  Ha a Ancilla-regisztrációt rögzített értékre kell mérni, tegyük fel, hogy az $0 $, majd az ilyen szimulációs módszerek alkalmazza a kívánt egységes átalakítást a fennmaradó qubits (ezt a rendszerregisztrációnak nevezik).  Az összes többi mérési eredmény azonban sikertelen.  A feledékenység amplitúdó-erősítése lehetővé teszi a mérés sikerességének valószínűségét a $100 \\ % $ értékre a fenti indokok használatával.  Emellett a hagyományos amplitúdó-erősítés abban az esetben is megfelel, ha a rendszer regisztrálása üres.  Ez az oka, hogy az amplitúdó-erősítést az Q# alapvető amplitúdó-erősítési alrutinként használja.

Az általános rutin ( `AmpAmpObliviousByReflectionPhases` ) két regisztert tartalmaz, amelyek hívására `ancillaRegister` és `systemRegister` . Emellett két Oracle-t is elfogad a szükséges tükrözésekhez. A `ReflectionOracle` csak a `ancillaRegister` két regisztráción alapuló műveleteket végezheti el `ObliviousOracle` . A bemenetet az `ancillaRegister` első reflexiós operátor ($ \boldone-2P_1 $) 1 eigenstate kell inicializálni.

Az Oracle általában a $ \ket{0...0} $ számítási alapon készíti el az állapotot. A megvalósításban az `ancillaRegister` egy qubit () áll, `flagQubit` amely az `stateOracle` és a többi kívánt ancillas vezérli. A a `stateOracle` `flagQubit` $ \ket $ értékre lesz alkalmazva {1} .

Az is előfordulhat, hogy az Oracle `StateOracle` -ket és a `ObliviousOracle` reflexiók helyett a hívását is megadja `AmpAmpObliviousByOraclePhases` .

Ahogy említettük, a hagyományos amplitúdó-erősítés csak egy speciális eset a rutinok esetében, ahol az `ObliviousOracle` identitás-kezelő, és nincsenek rendszerszintű qubits (azaz `systemRegister` üres). Ha részleges tükrözésekhez (pl.: a, a, a, a, a, a, a, a, a, a, a, a, a és a a `AmpAmpPhasesStandard` A a következő témakörben talál példákat a a a a a a a a a a a fa- `DatabaseSearch.qs` algoritmus

Az qubit-elforgatási fázisokat a [G.H. Low, I. L.](https://arxiv.org/abs/1707.05391)című cikkben leírtak szerint összekapcsoljuk a reflexiós operátor fázisaival. A rögzített pontokra vonatkozó fázisok részletesen szerepelnek a [Yoder, az alacsony és](https://arxiv.org/abs/1409.3305) a leveles, valamint az [alacsony, Yoder és](https://arxiv.org/abs/1603.03996)fázisokban.

A háttérben elindulhat a [standard amplitúdó-erősítés](https://arxiv.org/abs/quant-ph/0005055) , majd bevezethető az ismeretlen [amplitúdó-erősítéssel](https://arxiv.org/abs/1312.1414) és az [alacsony és a](https://arxiv.org/abs/1610.06546)facsoportban ismertetett általánosításokkal. A teljes terület áttekintését (ahogy a Hamilton szimulációhoz kapcsolódik) a [Dominic Berry](http://www.dominicberry.org/presentations/Durban.pdf)adta meg.

## <a name="quantum-fourier-transform"></a>Quantum Fourier-transzformáció ##

A Fourier-transzformáció a klasszikus elemzés alapvető eszköze, és ugyanolyan fontos a kvantum-számításokhoz.
Emellett a *Quantum Fourier-transzformáció* (QFT) hatékonysága messze felülmúlja a klasszikus gépen elérhetővé tenni kívánt első eszközök egyikét.

A QFT hozzávetőleges általánosításával biztosítjuk a <xref:microsoft.quantum.canon.approximateqft> műveletet, amely lehetővé teszi a további optimalizálást olyan metszési forgatásokkal, amelyek nem feltétlenül szükségesek a kívánt algoritmus pontosságához.
A hozzávetőleges QFT az $Z dyadic $-rotációs művelet <xref:microsoft.quantum.intrinsic.rfrac> és a művelet végrehajtásához szükséges <xref:microsoft.quantum.intrinsic.h> .
A bemenet és a kimenet a big endian-kódolásban---feltételezve, hogy az indextel rendelkező qubit a `0` bináris egész számok bal szélső (legmagasabb) kis részébe van kódolva.
Ez a [két](xref:microsoft.quantum.concepts.dirac)pontra van igazítva, mivel a $ \ket $ állapotú három qubits regisztrálása megfelel a $ {100} \ket $ állapotú _0 $ $q értéknek, {1} míg a $q _1 $ és a $q _2 $ érték a $ \ket $ állapotú {0} .
A (z) $a $ közelítési paraméter meghatározza a $Z $-Forgások, azaz $a \in [0.. n] $ metszési szintjét.
Ebben az esetben minden $Z $-Forgások $2 \ pi/2 ^ k $, ahol $k > a $ el lett távolítva a QFT áramkörből.
Ismert, hogy $k \ge \ log_2 (n) + \ log_2 (1/\epsilon) + $3. az egyik lehet kötve $ \\ | \operatorname{QFT}-\operatorname{AQFT} \\ | < \epsilon $.
Itt $ \\ | \cdot \\ | $ az operátori norma, amely ebben az esetben a legnagyobb [sajátérték](xref:microsoft.quantum.concepts.matrix-advanced) ($ (\operatorname{QFT}-\operatorname{AQFT}) (\operatorname{QFT}-\operatorname{AQFT}) ^ \dagger $.

## <a name="arithmetic"></a>Aritmetikai ##

Csakúgy, mint a aritmetika a klasszikus számítástechnika központi szerepét játssza, a kvantum-számítástechnika is nélkülözhetetlen.  Az algoritmusok, például a rövid faktoring algoritmus, a Quantum szimulációs módszerek, valamint számos oracular-algoritmus koherens aritmetikai műveletekre támaszkodnak.  Az aritmetikai folyamatok többsége a Quantum vipera-áramkörökre épül.  A legegyszerűbb kiegészítés egy klasszikus input $b $, és hozzáadja az értéket egy olyan kvantum-állapothoz, amely egy egész $ \ket{a} $ számot tárol.  Matematikailag, a kiegészítőkre (amit a $ \operatorname{Add} (b) $ for klasszikus input $b $ esetében jelölünk

$ $ \operatorname{Add} (b) \ket{a} = \ket{a + b}.
$ $ Ez az alapszintű kiegészítési áramkör nagyobb a növekménynél, mint a kiegészítőkre.
Olyan kiegészítőkre alakítható át, amely két kvantum-bemenettel rendelkezik a $ $ \operatorname{Add}\ket{a}\ket{b} = \ket{a}\ket{a + b}, $ $ $n használatával, amely a \begin{align} \operatorname{Add} \ket{a} \ket{b} & = \Lambda \_ {a \_ 0} \Left (\operatorname{Add} (1) \Right) \Lambda \_ {a \_ 1} \left (\operatorname{Add} (2) \right) \Lambda \_ {a \_ 2} \left (\operatorname{Add} (4) \right) \cdots \Lambda \_ {a { \_ n-1}} \left (\operatorname{Add} ({{n-1}}) \right) \ket{a}\ket{b} \\ \\ & = \ket{a} \ket{b + a}, \end{align} $n $-bites egész számra $a $ és $b $, valamint a többtényezős $2 ^ n $ értéket.  Ne felejtse el, hogy a $ \Lambda \_ x (A) $ (a) $ jelölés a ($A $) művelethez a művelet ellenőrzött verziójára hivatkozik, a qubit $x $ vezérlővel.

Hasonlóképpen, a klasszikusan vezérelt szorzás (amely moduláris, amely elengedhetetlen a rövid faktoring algoritmushoz) az ellenőrzött kiegészítések hasonló sorozatával végezhető el: \begin{align} \operatorname{Mult} (a) \ket{x}\ket{b} & = \Lambda \_ {x \_ 0} \Left (\operatorname{Add} (2 ^ 0 a) \Right) \Lambda \_ {a \_ 1} \left (\operatorname{Add} (2 ^ 1a) \right) \Lambda \_ {a \_ 2} \left (\operatorname{Add} (2 ^ 2 a) \right) \cdots \Lambda \_ {x \_ {n-1}} \left (\operatorname{Add} ({2 ^ {n-1}} a) \right) \ket{x}\ket{b} \\ \\ & = \ket{x}\ket{b + AX}.
a \end{align} olyan finomságokkal rendelkezik, amelyek a fenti $ \operatorname{Mult} $ definíció alapján megfigyelhető kvantum-számítógépeken is előfordulhatnak.  A hozzáadástól eltérően az áramkör Quantum verziója a bemeneti regiszter helyett egy kiegészítő regisztrációban tárolja a bemenetek termékét.  Ebben a példában a regiszter $b $ értékkel van inicializálva, de általában a nulla értéket fogja megkezdeni.  Erre azért van szükség, mert általánosságban nem létezik az általános $a $ és $x $ multiplikatív.  Mivel az összes kvantum-művelet, a mérések mentése megfordítható, meg kell őrizni a szükséges információkat a szorzás megfordításához.  Emiatt az eredményt egy különálló tömb tárolja.  Ezt a trükköt, amely egy visszafordíthatatlan művelet kimenetének, például a szorzásnak a megtakarítását, egy különálló regiszterben, a Charlie Bennett után a "Bennett Trick" néven ismert, amely a visszafordítható és a kvantum-számítástechnika egyik alapvető eszköze.

Számos kvantum-áramkör javasolt a hozzáadáshoz, és mindegyik különböző kompromisszumot vizsgál a qubits (szóköz) számának és a szükséges Gate-műveleteknek (Time) a száma alapján.  Két, az alábbiakban ismertetett, a drapéria-kiegészítőkre és a Beauregard-kiegészítőkre vonatkozó további, hatékony kiegészítést tekintünk át.

### <a name="draper-adder"></a>A drapéria kiegészítőkre ###

A drapéria kiegészítése vitathatatlanul az egyik legelegánsabb kvantum-kiegészítés, mivel közvetlenül a kvantum-tulajdonságokat hívja meg a Hozzáadás elvégzéséhez.  A drapéria kiegészítésének betekintése, hogy a Fourier-transzformáció felhasználható a fázisok eltolásának lefordítására egy kis eltolásban.  Ezután egy Fourier-transzformáció alkalmazásával, a megfelelő fázis-eltolások alkalmazásával, majd a Fourier-transzformáció visszavonásával végezheti el a kiegészítést.  A javasolt számos más kiegészítéstől eltérően a drapéria-kiegészítőkre explicit módon a Quantum Fourier-transzformáción keresztül bevezetett kvantum-hatásokat használják.  Nem rendelkezik természetes klasszikus munkatársaival.  A drapéria kiegészítésének konkrét lépéseit alább találja.

Tegyük fel, hogy két $n $ bites qubit regisztrál az egész számok tárolására $a $ és $b $, majd minden $a $ $ $ \operatorname{QFT}\ket{a} = \frac {1} {\sqrt{2 ^ n}} \sum \_ {j = 0} ^ {2 ^ n-1} e ^ {i2\pi (AJ)/2 ^ n} \ket{j}.
$ $ Ha definiáljuk a $ $ \ket{\phi \_ k (a)} = \frac {1} {\sqrt {2} } \left (\ket {0} + e ^ {i2\pi a/2 ^ k} \ket {1} \right), $ $, majd néhány algebra után láthatja, hogy $ $ \operatorname{QFT}\ket{a} = \ket{\phi \_ 1 (a)} \otimes \cdots \otimes \ket{\phi \_ n (a)}.
$ $ A kiegészítés végrehajtásának elérési útja akkor válik világossá, miután megfigyelte, hogy a bemenetek összege $ $ \ket{a + b} = \operatorname{QFT} ^ {-1} \ket{\phi \_ 1 (a + b)} \otimes \cdots \otimes \ket{\phi \_ n (a + b)}.
$ $ A $b $ és a $a $ közötti egész szám, amely a dekompozíció egyes qubits a $b $ as vezérlőkkel rendelkező bitek használatával felügyelt fázisú rotációs műveleteket végez.

Ez a bővítés tovább egyszerűsíthető azáltal, hogy bármely Integer $j $ és valós szám $x $, $e ^ {i2\pi (x + j)} = e ^ {i2\pi x} $.  Ennek az az oka, hogy ha egy körben elforgat $360 ^ {\circ} $ fok ($ 2 \ PI $ radián) értéket, akkor a végén pontosan megkezdheti a kezdeti lépéseket.  A ($e ^ {i2\pi x} $ $x $ értékének egyetlen fontos része, ezért $x $ töredékes részét képezi.  Pontosabban, ha az űrlap bináris kiterjesztése $x = y +0. x \_ 0x \_ 2 \ ldots x \_ n $, majd $e ^ {i2\pi x} = e ^ {i2\pi (0. x \_ 0x \_ 2 \ ldots x \_ {n-1})} $, így $ $ \ket{\phi \_ k (a + b)} = \frac {1} {\sqrt {2} } \left (\ket {0} + e ^ {i2\pi [a/2 ^ k +0. b \_ K\ldots b \_ 1]} \ket {1} \right). $ $ Ez azt jelenti, hogy ha elvégezjük a hozzáadást úgy, hogy növeli az egyes tenser-tényezőket a $ \ket{a} $ Fourier-átalakításának bővülése során, akkor a Forgások száma $k $ csökkenéssel csökken.  Ez jelentősen csökkenti a kiegészítésben szükséges kvantum-kapuk számát.  A Fourier-transzformáció, a fázis és az inverz Fourier-transzformációs lépések jelölését jelöli, amelyek a "\operatorname{QFT} ^ {-1} \left (\Phi \\ \! \operatorname{Add}\right) \operatorname{QFT} $" a drapéria-kiegészítőkre épülnek. Alább látható egy olyan kvantum-áramkör, amely ezt az egyszerűsítést használja a teljes folyamat megvalósításához.

![Az áramköri diagramként látható drapéria-kiegészítés](~/media/draper.svg)

Az áramkörben lévő minden ellenőrzött $e ^ {I2 \ PI/k} $ Gate a szabályozott fázisú kapura utal.  Ilyen kapuk rendelkeznek a tulajdonsággal, amely azon qubits, amelyeken a művelet, $ \ket {00} \mapsto \ket {00} $, de $ \ket {11} \mapsto e ^ {I2 \ PI/k} \ ket {11} $.  Ez az áramkör lehetővé teszi a hozzáadást további qubits nélkül, a bemenetek és a kimenetek tárolásához szükséges beállítások mellett.

### <a name="beauregard-adder"></a>Beauregard-kiegészítőkre ###

A Beauregard vipera egy olyan kvantum-moduláris kiegészítés, amely a drapéria-kiegészítést használja, hogy egy tetszőleges értékkel rendelkező, pozitív egész számú, $N $ értékű $N  A Quantum Modular-kiegészítések, például a Beauregard-kiegészítőkre jelentősége nagy mértékben kihasználja az rövid algoritmusának a hatványozására-modulban való használatát.  A kvantum-moduláris kiegészítés a következő művelettel rendelkezik a Quantum input $ \ket{b} $ és a klasszikus input $a $ esetén, ahol a $a $ és a $b $ értéket a rendszer megígérte, hogy egész számú mod $N $, ami azt jelenti, hogy a $ [0, \ldots, N-1] $ intervallumban szerepelnek.

$ $ \ket{b}\rightarrow \ket{b + a \text{mod} N} = \begin{Cases} \ket{b + a}, & b + a < N \\ \\ \ket{b + a-N}, & (b + a) \ge n \end{Cases}.
$$

A Beauregard-kiegészítés a drapéria-kiegészítőkre, vagy konkrétabban a $ \phi \\ \! \operatorname{Add} $-t használja a $a $ és $b $ szakasz hozzáadásához.  Ezután ugyanazzal a művelettel azonosítja, hogy $a + b <N $ $N $ kivonásával és tesztelésével, ha $a + b-N<$0.  Az áramkör ezt az információt egy kiegészítő qubit tárolja, majd hozzáadja $N $ vissza a regisztrációt, ha $a + b<N $.  Ezt követően a kiegészítő bit kiszámításával zárul le (ez a lépés szükséges annak biztosításához, hogy a Ancilla a kiegészítés meghívása után is kiosztható legyen).  Az alábbi, a Beauregard-kiegészítőkre vonatkozó áramkört adja meg.

![A Beauregard-kiegészítőkre áramköri diagramként jelenik meg](~/media/beau.svg)

Itt a Gate $ \Phi \\ \! \operatorname{Add} $ ugyanaz az űrlap lesz, mint a $ \Phi \\ \! \operatorname{Add} $, kivéve, ha ebben a kontextusban a bemenet a klasszikus helyett a Quantum.  Ez lehetővé teszi, hogy a $ \Phi \Operatorname{Add} $ által vezérelt fázisok \\ \! lecserélve legyenek a Phase Gates-be, amelyek ezután kevesebb műveletre fordíthatók le, hogy csökkentsék a qubits számát és a szükséges kapuk számát.

További részletekért tekintse meg az [M. Roetteler, a th. Beth](http://doi.org/10.1007/s00200-008-0072-2 ) és a [D. Coppersmith](https://arxiv.org/abs/quant-ph/0201067).

### <a name="quantum-phase-estimation"></a>Kvantumfázisbecslés ###

A Quantum Fourier-transzformáció egyik különösen fontos alkalmazása, hogy megismerje az egységes operátorok eigenvalues, amely a *fázisok becslésének*ismert problémája.
Vegyünk egy egységes $U $ és egy State $ \ket{\phi} $ értéket, amely szerint a $ \ket{\phi} $ eigenstate $U $, ismeretlen sajátérték $ \phi $, \begin{Equation} U\ket {\ Phi} = \phi\ket{\phi}.
\end{Equation}, ha csak $U $ Oracle-hez fér hozzá, akkor a $ \phi $ fázisban megtudhatjuk, $Z hogy egy vezérelt művelet céljára alkalmazott $ rotációs műveletet propagálja vissza a vezérlőre.

Tegyük fel, hogy $V $ $U $ vezérelt alkalmazás, például \begin{align} V (\ket {0} \otimes \ket{\phi}) & = \ket {0} \otimes \ket{\phi} \textrm{ \\ \\ és} V (\ket \otimes {1} \ket{\phi}) & = e ^ {i \phi} \ket {1} \otimes \ket{\phi}.
\end{align} ezt követően: linearitás, \begin{align} V (\ket{+} \otimes \ket{\phi}) & = \frac{(\ket {0} \otimes \ket{\phi}) + e ^ {i \phi} (\ket {1} \otimes \ket{\phi})} {\sqrt {2} }.
\end{align} gyűjthetjük a \begin{align} V (\ket{+} \otimes \ket{\phi}) & = \frac{\ket {0} + e ^ {i \phi} \ket {1} } {\sqrt {2} } \otimes \ket{\phi} \\ \\ & = (R_1 (\phi) \ket{+}) \otimes \ket{\phi}, \end{align}, ahol a $R _1 $ a művelet által alkalmazott egységes érték <xref:microsoft.quantum.intrinsic.r1> .
Másképpen fogalmazva, a $V $ alkalmazásának hatása pontosan ugyanaz, mint a $R _1 $ ismeretlen szögben való alkalmazása, noha csak a $V $ Oracle-hez férhet hozzá.
Így a vita további részében a $R _1 (\phi) $ kifejezéssel megbeszéljük a fázisok becslését, amelyet az úgynevezett *fázis-visszarúgás*használatával implementálunk.

Mivel a vezérlés és a cél regisztrálása a folyamat után nem látható, a $ \ket{\phi} $ értéket újra felhasználhatjuk a $U ^ $2 ellenőrzött alkalmazásának céljára, hogy előkészítsünk egy második vezérlőelem-qubit a _1 (2 \phi) \ket{+} $ $R állapotban.
Így továbbra is regisztrálhat a \begin{align} \ket{\psi} & = \ sum_ {j = 0} ^ n R_1 (2 ^ j \phi) \ket{+} \\ \\ & \propto \ bigotimes_ {j = 0} ^ {n} \left (\ket {0} + \exp (i 2 ^ {j} \phi) \ket {1} \right) \\ \\ & \propto \ sum_ {k = 0} ^ {2 ^ n-1} \exp (i \phi k) \ket{k} \end{align}, ahol a $n $ a szükséges bitek száma. és hogy hol használták {} a $ \propto {} $ értéket, jelezve, hogy letiltottuk a $1/\sqrt{2 ^ n} $ normalizálás tényezőjét.

Ha feltételezzük, hogy a $ \phi = 2 \pi p/2 ^ k $ értéket egy egész szám $p $ értékre, akkor ezt a következőt ismerjük fel: $ \ket{\psi} = \operatorname{QFT} \ket{p_0 p_1 \dots p_n} $, ahol $p _j $ a $j ^ {\textrm{th}} $ bit of $2 \pi \phi $.
A Quantum Fourier-transzformáció adjoint alkalmazásával ezért a rendszer kvantum-állapotként kódolja a fázis bináris ábrázolását.

A-ben Q# ezt a műveletet hajtja végre <xref:microsoft.quantum.characterization.quantumphaseestimation> , amely a <xref:microsoft.quantum.oracles.discreteoracle> $U ^ m $ implementációs alkalmazást alkalmazza $m $ pozitív egész számok függvényében.
