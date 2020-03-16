---
title: 'Quantum-algoritmusok a Q-ban #'
description: Ismerje meg az alapvető kvantum-számítási algoritmusokat, beleértve az amplitúdó-erősítést, a Fourier-transzformációt, a drapériát és a Beauregard-kiegészítéseket, valamint a fázisok
author: QuantumWriter
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.algorithms
ms.openlocfilehash: 8b8a9019e8bc419f42b0c6f7558354d19a157917
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/15/2020
ms.locfileid: "79402850"
---
# <a name="quantum-algorithms"></a>Quantum algoritmusok #

## <a name="amplitude-amplification"></a>Amplitúdó-erősítés ##

Az *amplitúdó-erősítés* a kvantum-számítástechnika alapvető eszközeinek egyike. Ez az alapvető elképzelés, hogy a megalapozott kutatás, az amplitúdó-becslés és számos Quantum Machine learning algoritmus.  Számos változat létezik, és a Q #-ban egy általános verziót biztosítunk, amely a részleges reflexiókkal ellátott, részben az alkalmazás legszélesebb területét lehetővé tevő, részleges reflexiókkal rendelkező, általánosan elérhető verzión alapul.

Az amplitúdó-erősítés mögötti központi elképzelés az, hogy kiterjesztheti a kívánt eredmény valószínűségét a reflexiók sorrendjének végrehajtásával.  Ezek a reflexiók a kezdeti állapotot közelebb viszik a kívánt cél állapothoz, amelyet gyakran jelölt állapotnak nevezünk.  Pontosabban, ha a kiindulási állapot jelölésének valószínűsége jelölt állapotban van, a $ \sin ^ 2 (\theta) $, majd az amplitúdó-$m erősítés alkalmazása után a siker valószínűsége $ \sin ^ 2 ((2m + 1) \theta) $ lesz.  Ez azt jelenti, hogy ha a $ \theta = \ Pi/[2 (2n + 1)] $ értéket adja meg a $ $n $ értéknél, akkor az amplitúdó-erősítés képes növelni a siker valószínűségét $100\\% $ után $n $ iterációs amplitúdó-erősítéssel.  Mivel a $ \theta = \sin ^{-1}(\sqrt{\Pr (Success)}) $ Ez azt jelenti, hogy a sikeres determinisztikus módon beszerzéséhez szükséges Ismétlések száma a következő, véletlenszerű mintavételezéssel nem determinisztikus módon megkereséséhez szükséges számú, a vártnál nagyobb számú.

Az amplitúdó-erősítés minden iterációja megköveteli, hogy két reflexiós operátor legyen megadva. Pontosabban, ha a $Q $ érték az amplitúdó erősítésének iterációja, és $P _0 $ egy kivetítő operátor a kezdeti alterületre, és $P _1 $ a kivetítő a megjelölt alterületre, majd $Q =-(\boldone-2P_0) (\boldone-2P_1) $.  Ne felejtse el, hogy a kivetítő olyan Hermitian operátor, amely eigenvalues $ + $1 és $0 $ értékű, és ennek eredményeképpen a $ (\boldone-2P_0) $ érték egységes, mert olyan eigenvalues rendelkezik, amely az egység gyökere (ebben az esetben a $ \pm $1). Tegyük fel például, hogy a kiindulási állapotú $H ^ {\otimes n} \ket{0}$ és a megjelölt állapot $ \ket{m} $, $P _0 = H ^ {\otimes n} \ket{0}\bra{0}H ^ {\otimes n} $ és $P _1 = \ket{m}\bra{m} $.  Az amplitúdó-erősítés legtöbb alkalmazásában a $P _0 $ egy kezdeti állapotba kerül, amely azt jelenti, hogy $P _0 = \boldone-2 \ ket {\ PSI} \ melltartó {\ PSI} $ egyes Vector $ \ket{\psi} $; a feledékenység amplitúdó-amplication $P _0 $ esetében azonban jellemzően sok kvantum-állapotot fog kiszolgálni (azaz a $P _0 $ $ + $1 sajátérték többszöröse meghaladja a $1 $-ot).

Az amplitúdó-erősítés mögötti logika közvetlenül a $Q $ Eigen-felbomlásával következik.  Pontosabban, a kezdeti állapotú, nem nulla szintű támogatással rendelkező $Q $ eigenvectors az $P _0 $ és $P _1 $ eigenvectors $ + $1-as lineáris kombinációját jeleníti meg.  Pontosabban, az amplitúdó-erősítés kezdeti állapota (feltételezve, hogy a $ + $1 eigenvector $P _0 $) írható $ $ \ket{\psi} = \frac{-i}{\sqrt{2}} \left (e ^ {i\theta} \ ket {\ psi_ +} + e ^ {-i\theta} \ ket {\ psi_-} \right), $ $, ahol a $ \ket{\ psi_ \pm} $ eigenvectors $Q $ eigenvalues $e ^ {\pm 2i \ Théta} $, és csak a $ + $1 eigenvectors támogatja a $P _0 $ és $P _1 $.  Az a tény, hogy a eigenvalues $e ^ {\pm i \theta} $, azt feltételezi, hogy a kezelő $Q $ elforgatást hajt végre a két kivetítő által meghatározott kétdimenziós alterületen, valamint a kezdeti állapotot, ahol a forgási szög $2 \ THÉTA $.  Ezért a siker valószínűsége $m $ iterációk után $Q $ a sikerességi valószínűség: $ \sin ^ 2 ([2m + 1] \theta) $.

Egy másik hasznos tulajdonság, amely abból ered, hogy a sajátérték $ \theta $ közvetlenül kapcsolódik annak valószínűségéhez, hogy a kezdeti állapot meg lesz jelölve (abban az esetben, ha $P _0 $ egy kivetítő csak a kezdeti állapotra).  Mivel a eigenphases $Q $ a $2 \ THÉTA = 2 \ Sin ^{-1}(\sqrt{\Pr (Success)}) $, akkor a következő lépés az, hogy ha a fázis-becslést a $Q $ értékre alkalmazzuk, akkor megtudhatjuk, hogy sikeres volt-e egy egységes kvantum-eljárás.  Ez azért hasznos, mert a kvantum-eljáráshoz tartozó, másodfokú módon kevesebb alkalmazásra van szükség, hogy megismerje a siker valószínűségét, mint egyébként.

A Q # amplitúdó-erősítést mutat be a feledékenység amplitúdó-erősítésének specializációja.  A feledékenység amplitúdó-erősítése ezt a monikert keresi, mert a kezdeti eigenspace kivetítőnek nem kell kivetítőnek lennie a kezdeti állapothoz.  Ebben az értelemben a protokoll a kezdeti állapotba kerül.  A feledékenység amplitúdó-erősítésének legfontosabb alkalmazása az egységes Hamilton-szimulációs módszerek bizonyos *lineáris kombinációjában* van, amelyben a kezdeti állapot ismeretlen, de a szimulált Ancilla-regiszterrel együtt válik elérhetővé a szimulációs protokollban.  Ha a Ancilla-regisztrációt rögzített értékre kell mérni, tegyük fel, hogy az $0 $, majd az ilyen szimulációs módszerek alkalmazza a kívánt egységes átalakítást a fennmaradó qubits (ezt a rendszerregisztrációnak nevezik).  Az összes többi mérési eredmény azonban sikertelen.  A feledékenység amplitúdó-erősítése lehetővé teszi a mérés sikerességének valószínűségét a $100\\% $ értékre a fenti indokok használatával.  Emellett a hagyományos amplitúdó-erősítés abban az esetben is megfelel, ha a rendszer regisztrálása üres.  Ezért a Q # a megfeledkezett az amplitúdó erősítését használja az alapvető amplitúdó-erősítési alrutinként.

Az általános rutin (`AmpAmpObliviousByReflectionPhases`) két regisztert tartalmaz, amelyeket `ancillaRegister` és `systemRegister`hívunk. Emellett két Oracle-t is elfogad a szükséges tükrözésekhez. A `ReflectionOracle` csak a `ancillaRegister` működik, míg a `ObliviousOracle` mindkét regiszteren közösen működik. A `ancillaRegister`ba való bevitelt inicializálni kell az első reflexiós operátor ($ \boldone-2P_1 $) 1 eigenstate.

Az Oracle általában a $ \ket{0...0} $ számítási alapon készíti el az állapotot. A megvalósítás során a `ancillaRegister` egy qubit (`flagQubit`) áll, amely a `stateOracle` és a többi kívánt ancillas vezérli. A `stateOracle` akkor lesz alkalmazva, ha a `flagQubit` $ \ket{1}$.

Az egyik lehetséges, hogy az Oracle-`StateOracle` és a `ObliviousOracle` a `AmpAmpObliviousByOraclePhases`hívása helyett a reflexiók helyett.

Ahogy említettük, a hagyományos amplitúdó-erősítés csak egy különleges eset a rutinok esetében, ahol `ObliviousOracle` az identitás operátora, és nincsenek rendszerszintű qubits (azaz `systemRegister` üresek). Ha részleges reflexiók (pl. a a (a "a", a, `AmpAmpPhasesStandard` a, a, a, a, a, a, a vagy a a, a a " A következő témakörben talál `DatabaseSearch.qs`t a a a a a a a a a a a a a a a a

Az qubit-elforgatási fázisokat a [G.H. Low, I. L.](https://arxiv.org/abs/1707.05391)című cikkben leírtak szerint összekapcsoljuk a reflexiós operátor fázisaival. A rögzített pontokra vonatkozó fázisok részletesen szerepelnek a [Yoder, az alacsony és](https://arxiv.org/abs/1409.3305) a leveles, valamint az [alacsony, Yoder és](https://arxiv.org/abs/1603.03996)fázisokban.

A háttérben elindulhat a [standard amplitúdó-erősítés](https://arxiv.org/abs/quant-ph/0005055) , majd bevezethető az ismeretlen [amplitúdó-erősítéssel](https://arxiv.org/abs/1312.1414) és az [alacsony és a](https://arxiv.org/abs/1610.06546)facsoportban ismertetett általánosításokkal. A teljes terület áttekintését (ahogy a Hamilton szimulációhoz kapcsolódik) a [Dominic Berry](http://www.dominicberry.org/presentations/Durban.pdf)adta meg.

## <a name="quantum-fourier-transform"></a>Quantum Fourier-transzformáció ##

A Fourier-transzformáció a klasszikus elemzés alapvető eszköze, és ugyanolyan fontos a kvantum-számításokhoz.
Emellett a *Quantum Fourier-transzformáció* (QFT) hatékonysága messze felülmúlja a klasszikus gépen elérhetővé tenni kívánt első eszközök egyikét.

A QFT hozzávetőleges általánosításával biztosítjuk a <xref:microsoft.quantum.canon.approximateqft> műveletet, amely lehetővé teszi a további optimalizálást olyan metszések esetében, amelyek nem feltétlenül szükségesek a kívánt algoritmus pontosságához.
A hozzávetőleges QFT működéséhez a dyadic $Z $-forgási művelet <xref:microsoft.quantum.intrinsic.rfrac> és a <xref:microsoft.quantum.intrinsic.h> művelet szükséges.
A bemenet és a kimenet a big endian kódolásban---, azaz az `0` indexet tartalmazó qubit a bináris egész számok bal szélső (legmagasabb) részében kódolva.
Ez a [két](xref:microsoft.quantum.concepts.dirac)pontra van igazítva, mivel a $ \ket{100}$ állapotú három qubits regisztrálása megfelel a $ \ket{1}$ állapotú $q _0 $ értéknek, míg a $q _1 $ és a $q _2 $ érték a $ \ket{0}$ állapotban van.
A (z) $a $ közelítési paraméter meghatározza a $Z $-Forgások, azaz $a \in [0.. n] $ metszési szintjét.
Ebben az esetben minden $Z $-Forgások $2 \ pi/2 ^ k $, ahol $k > a $ el lett távolítva a QFT áramkörből.
Ismert, hogy $k \ge \ log_2 (n) + \ log_2 (1/\epsilon) + $3. egy kötve $\\| \operatorname{QFT} – \operatorname{AQFT} \\| < \epsilon $.
Itt $\\| \cdot\\| $ az operátori norma, amely ebben az esetben a legnagyobb [sajátérték](xref:microsoft.quantum.concepts.matrix-advanced) ($ (\Operatorname{QFT}-\operatorname{AQFT}) (\Operatorname{QFT}-\operatorname{AQFT}) ^ \dagger $.

## <a name="arithmetic"></a>Aritmetikai ##

Csakúgy, mint a aritmetika a klasszikus számítástechnika központi szerepét játssza, a kvantum-számítástechnika is nélkülözhetetlen.  Az algoritmusok, például a rövid faktoring algoritmus, a Quantum szimulációs módszerek, valamint számos oracular-algoritmus koherens aritmetikai műveletekre támaszkodnak.  Az aritmetikai folyamatok többsége a Quantum vipera-áramkörökre épül.  A legegyszerűbb kiegészítés egy klasszikus input $b $, és hozzáadja az értéket egy olyan kvantum-állapothoz, amely egy egész $ \ket{a} $ számot tárol.  Matematikailag, a kiegészítőkre (amit a $ \operatorname{Add} (b) $ for klasszikus input $b $ esetében jelölünk

$ $ \operatorname{Add} (b) \ket{a} = \ket{a + b}.
$ $ Ez az alapszintű kiegészítési áramkör nagyobb a növekménynél, mint a kiegészítőkre.
Egy olyan kiegészítőkre konvertálható, amely két kvantum bemenettel rendelkezik a $ $ \operatorname{Add}\ket{a}\ket{b} = \ket{a}\ket{a + b} használatával. $ $ $n $ vezérelt alkalmazásokat használ a \begin{align} \operatorname{Add} \ket{a} \ket{b} & = \Lambda\_{a\_0} \left (\operatorname{Add} (1) \right) \Lambda\_{a\_1} \left (\operatorname{Add} (2) \right) \Lambda\_{a\_2} \left (\operatorname{Add} (4) \right) \cdots \Lambda\_{a\_{n-1}} \left (\ operatorname {Add} ({{n-1}}) \right) \ket{a}\ket{b} \\\\ & = \ket{a} \ket{b + a}, \end{align} $n $ bites egész számra $a $ és $b $, valamint a többtényezős $2 ^ n $ értéket.  Ne felejtse el, hogy a $ \Lambda\_x (A) $ jelölés a ($A $) művelethez a művelet ellenőrzött verziójára vonatkozik a qubit $x $ as vezérlővel.

Hasonlóképpen, a klasszikusan vezérelt szorzás (amely moduláris, amely elengedhetetlen a rövid faktoring algoritmushoz) az ellenőrzött kiegészítések hasonló sorozatával végezhető el: \begin{align} \operatorname{Mult} (a) \ket{x}\ket{b} & = \Lambda\_{x\_0} \left (\operatorname{Add} (2 ^ 0 a) \right) \Lambda\_{a\_1} \left (\operatorname{Add} (2 ^ 1a) \right) \Lambda\_{a\_2} \left (\operatorname{Add} (2 ^ 2 a) \right) \cdots \Lambda\_{x\_{ n-1}} \left (\operatorname{Add} ({2 ^ {n-1}} a) \right) \ket{x}\ket{b} \\\\ & = \ket{x}\ket{b + AX}.
a \end{align} olyan finomságokkal rendelkezik, amelyek a fenti $ \operatorname{Mult} $ definíció alapján megfigyelhető kvantum-számítógépeken is előfordulhatnak.  A hozzáadástól eltérően az áramkör Quantum verziója a bemeneti regiszter helyett egy kiegészítő regisztrációban tárolja a bemenetek termékét.  Ebben a példában a regiszter $b $ értékkel van inicializálva, de általában a nulla értéket fogja megkezdeni.  Erre azért van szükség, mert általánosságban nem létezik az általános $a $ és $x $ multiplikatív.  Mivel az összes kvantum-művelet, a mérések mentése megfordítható, meg kell őrizni a szükséges információkat a szorzás megfordításához.  Emiatt az eredményt egy különálló tömb tárolja.  Ezt a trükköt, amely egy visszafordíthatatlan művelet kimenetének, például a szorzásnak a megtakarítását, egy különálló regiszterben, a Charlie Bennett után a "Bennett Trick" néven ismert, amely a visszafordítható és a kvantum-számítástechnika egyik alapvető eszköze.

Számos kvantum-áramkör javasolt a hozzáadáshoz, és mindegyik különböző kompromisszumot vizsgál a qubits (szóköz) számának és a szükséges Gate-műveleteknek (Time) a száma alapján.  Két, az alábbiakban ismertetett, a drapéria-kiegészítőkre és a Beauregard-kiegészítőkre vonatkozó további, hatékony kiegészítést tekintünk át.

### <a name="draper-adder"></a>A drapéria kiegészítőkre ###

A drapéria kiegészítése vitathatatlanul az egyik legelegánsabb kvantum-kiegészítés, mivel közvetlenül a kvantum-tulajdonságokat hívja meg a Hozzáadás elvégzéséhez.  A drapéria kiegészítésének betekintése, hogy a Fourier-transzformáció felhasználható a fázisok eltolásának lefordítására egy kis eltolásban.  Ezután egy Fourier-transzformáció alkalmazásával, a megfelelő fázis-eltolások alkalmazásával, majd a Fourier-transzformáció visszavonásával végezheti el a kiegészítést.  A javasolt számos más kiegészítéstől eltérően a drapéria-kiegészítőkre explicit módon a Quantum Fourier-transzformáción keresztül bevezetett kvantum-hatásokat használják.  Nem rendelkezik természetes klasszikus munkatársaival.  A drapéria kiegészítésének konkrét lépéseit alább találja.

Tegyük fel, hogy két $n $ bites qubit regisztrál az egész számok tárolására $a $ és $b $, majd minden $a $ $ $ \operatorname{QFT}\ket{a} = \frac{1}{\sqrt{2 ^ n}} \sum\_{j = 0} ^ {2 ^ n-1} e ^ {i2\pi (AJ)/2 ^ n} \ket{j}.
$ $ Ha definiáljuk a $ $ \ket{\phi\_k (a)} = \frac{1}{\sqrt{2}} \left (\ket{0} + e ^ {i2\pi a/2 ^ k} \ket{1} \right), $ $, majd néhány algebra után láthatja, hogy a $ $ \operatorname{QFT}\ket{a} = \ket{\phi\_1 (a)} \otimes \cdots \otimes \ket{\phi\_n (a)}.
$ $ A kiegészítés végrehajtásának elérési útja akkor válik világossá, miután megfigyelte, hogy a bemenetek összege $ $ \ket{a + b} = \operatorname{QFT} ^{-1}\ket{\phi\_1 (a + b)} \otimes \cdots \otimes \ket{\phi\_n (a + b)}.
$ $ A $b $ és a $a $ közötti egész szám, amely a dekompozíció egyes qubits a $b $ as vezérlőkkel rendelkező bitek használatával felügyelt fázisú rotációs műveleteket végez.

Ez a bővítés tovább egyszerűsíthető azáltal, hogy bármely Integer $j $ és valós szám $x $, $e ^ {i2\pi (x + j)} = e ^ {i2\pi x} $.  Ennek az az oka, hogy ha egy körben elforgat $360 ^ {\circ} $ fok ($ 2 \ PI $ radián) értéket, akkor a végén pontosan megkezdheti a kezdeti lépéseket.  A ($e ^ {i2\pi x} $ $x $ értékének egyetlen fontos része, ezért $x $ töredékes részét képezi.  Pontosabban, ha az űrlap bináris bővítése $x = y +0. x\_0x\_2 \ ldots x\_n $, $e ^ {i2\pi x} = e ^ {i2\pi (0. x\_0x\_2 \ ldots x\_{n-1})} $ és így $ $ \ket{\phi\_k (a + b)} = \frac{1}{\sqrt{2}} \left (\ket{0} + e ^ {i2\pi [a/2 ^ k +0. b\_k\ldots b\_1]} \ket{1} \right). $ $ Ez azt jelenti, hogy ha elvégezjük a hozzáadást úgy, hogy növeli a több tízezer tényezőt a $ \ket{a} $ Fourier-átalakításának növekedésével, akkor a a Forgások száma $k $ értékkel csökken.  Ez jelentősen csökkenti a kiegészítésben szükséges kvantum-kapuk számát.  A Fourier-transzformációt, a fázisok hozzáadását és az inverz Fourier-transzformáció lépéseit jelöljük, amelyek a \operatorname{QFT} ^{-1} \left (\phi\\\!\operatorname{ADD}\right) \operatorname{QFT} $. Alább látható egy olyan kvantum-áramkör, amely ezt az egyszerűsítést használja a teljes folyamat megvalósításához.

![Az áramköri diagramként látható drapéria-kiegészítés](~/media/draper.svg)

Az áramkörben lévő minden ellenőrzött $e ^ {I2 \ PI/k} $ Gate a szabályozott fázisú kapura utal.  Az ilyen kapuk rendelkeznek a tulajdonsággal, amely azon qubits, amelyeken a művelet, $ \ket{00}\mapsto \ket{00}$, de $ \ket{11}\mapsto e ^ {I2 \ PI/k} \ ket{11}$.  Ez az áramkör lehetővé teszi a hozzáadást további qubits nélkül, a bemenetek és a kimenetek tárolásához szükséges beállítások mellett.

### <a name="beauregard-adder"></a>Beauregard-kiegészítőkre ###

A Beauregard vipera egy olyan kvantum-moduláris kiegészítés, amely a drapéria-kiegészítést használja, hogy egy tetszőleges értékkel rendelkező, pozitív egész számú, $N $ értékű $N  A Quantum Modular-kiegészítések, például a Beauregard-kiegészítőkre jelentősége nagy mértékben kihasználja az rövid algoritmusának a hatványozására-modulban való használatát.  A kvantum-moduláris kiegészítés a következő művelettel rendelkezik a Quantum input $ \ket{b} $ és a klasszikus input $a $ esetén, ahol a $a $ és a $b $ értéket a rendszer megígérte, hogy egész számú mod $N $, ami azt jelenti, hogy a $ [0, \ldots, N-1] $ intervallumban szerepelnek.

$ $ \ket{b}\rightarrow \ket{b + a \text{mod} N} = \begin{Cases} \ket{b + a}, & b + a < N\\\\ \ket{b + a-N}, & (b + a) \ge N \end{Cases}.
$$

A Beauregard kiegészítőkre a drapéria kiegészítőkre, vagy pontosabban $ \phi\\\!\operatorname{ADD} $-t használ, hogy $a $ és $b $ értéket vegyen fel a fázisba.  Ezután ugyanazzal a művelettel azonosítja, hogy a $a + b < N $ $N $ kivonásával és tesztelésével, ha $a + b-N < 0 $.  Az áramkör ezt az információt egy kiegészítő qubit tárolja, majd hozzáadja $N $ vissza a regisztrációt, ha $a + b < N $.  Ezt követően a kiegészítő bit kiszámításával zárul le (ez a lépés szükséges annak biztosításához, hogy a Ancilla a kiegészítés meghívása után is kiosztható legyen).  Az alábbi, a Beauregard-kiegészítőkre vonatkozó áramkört adja meg.

![A Beauregard-kiegészítőkre áramköri diagramként jelenik meg](~/media/beau.svg)

Itt a Gate $ \Phi\\\!\operatorname{ADD} $ a $ \Phi\\\!\operatorname{ADD} $ értéket veszi át, azzal a különbséggel, hogy ebben a kontextusban a bemenet klasszikus, nem pedig a Quantum.  Ez lehetővé teszi, hogy a $ \Phi\\\!\operatorname{ADD} $ által vezérelt fázisok lecserélve legyenek a fázisokra, amelyek ezután kevesebb műveletre fordíthatók le, hogy csökkentsék a qubits számát és a kiegészítéshez szükséges kapuk számát.

További részletekért tekintse meg az [M. Roetteler, a th. Beth](http://doi.org/10.1007/s00200-008-0072-2 ) és a [D. Coppersmith](https://arxiv.org/abs/quant-ph/0201067).

### <a name="quantum-phase-estimation"></a>Kvantumfázisbecslés ###

A Quantum Fourier-transzformáció egyik különösen fontos alkalmazása, hogy megismerje az egységes operátorok eigenvalues, amely a *fázisok becslésének*ismert problémája.
Vegyünk egy egységes $U $ és egy State $ \ket{\phi} $ értéket, amely szerint a $ \ket{\phi} $ eigenstate $U $, ismeretlen sajátérték $ \phi $, \begin{Equation} U\ket {\ Phi} = \phi\ket{\phi}.
\end{Equation}, ha csak $U $ Oracle-hez fér hozzá, akkor a $ \phi $ fázisban megtudhatjuk, $Z hogy egy vezérelt művelet céljára alkalmazott $ rotációs műveletet propagálja vissza a vezérlőre.

Tegyük fel, hogy $V $ $U $ vezérelt alkalmazás, például a \begin{align} V (\ket{0} \otimes \ket{\phi}) & = \ket{0} \otimes \ket{\phi} \\\\ \textrm{és} V (\ket{1} \otimes \ket{\phi}) & = e ^ {i \phi} \ket{1} \otimes \ket{\phi}.
\end{align} ezt követően: linearitás, \begin{align} V (\ket{+} \otimes \ket{\phi}) & = \frac{(\ket{0} \otimes \ket{\phi}) + e ^ {i \phi} (\ket{1} \otimes \ket{\phi})} {\sqrt{2}}.
a \end{align} a \begin{align} V (\ket{+} \otimes \ket{\phi}) & = \frac{\ket{0} + e ^ {i \phi} \ket{1}} {\sqrt{2}} \otimes \ket{\phi} \\\\ & = (R_1 (\phi) \ket{+}) \otimes \ket{\phi}, \end{align}, ahol $R _1 $ a <xref:microsoft.quantum.intrinsic.r1> művelet által használt egységes alkalmazás.
Másképpen fogalmazva, a $V $ alkalmazásának hatása pontosan ugyanaz, mint a $R _1 $ ismeretlen szögben való alkalmazása, noha csak a $V $ Oracle-hez férhet hozzá.
Így a vita további részében a $R _1 (\phi) $ kifejezéssel megbeszéljük a fázisok becslését, amelyet az úgynevezett *fázis-visszarúgás*használatával implementálunk.

Mivel a vezérlés és a cél regisztrálása a folyamat után nem látható, a $ \ket{\phi} $ értéket újra felhasználhatjuk a $U ^ $2 ellenőrzött alkalmazásának céljára, hogy előkészítsünk egy második vezérlőelem-qubit a _1 (2 \phi) \ket{+} $ $R állapotban.
Így továbbra is beszerezhetjük a \begin{align} \ket{\psi} & = \ sum_ {j = 0} ^ n R_1 (2 ^ j \phi) \ket{+} \\\\ & \propto \ bigotimes_ {j = 0} ^ {n} \left (\ket{0} + \exp (i 2 ^ {j} \phi) \ket{1}\right) \\\\ & \propto \ sum_ {k = 0} ^ {2 ^ n-1} \exp (i \phi k) \ket{k} \end{align}, ahol a $n $ a szükséges bitek száma. és hogy hol használták a ${} \propto {}$ értéket, jelezve, hogy letiltottuk a $1/\sqrt normalizálás tényezőjét {2 ^ n} $.

Ha feltételezzük, hogy a $ \phi = 2 \pi p/2 ^ k $ értéket egy egész szám $p $ értékre, akkor ezt a következőt ismerjük fel: $ \ket{\psi} = \operatorname{QFT} \ket{p_0 p_1 \dots p_n} $, ahol $p _j $ a $j ^ {\textrm{th}} $ bit of $2 \pi \phi $.
A Quantum Fourier-transzformáció adjoint alkalmazásával ezért a rendszer kvantum-állapotként kódolja a fázis bináris ábrázolását.

A Q #-ban ez a <xref:microsoft.quantum.characterization.quantumphaseestimation> művelettel valósul meg, amely <xref:microsoft.quantum.oracles.discreteoracle> $U ^ millió $-ra alkalmazza a pozitív egész számok függvényében $m $ értéket.
