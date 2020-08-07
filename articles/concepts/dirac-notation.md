---
title: Dirac-jelölés leírása: megismerheti a Dirac-jelölés használatát a kvantum-állapotok, valamint a kvantum-műveletek szimulálása érdekében.
Szerző: QuantumWriter UID: Microsoft. Quantum. Concepts. Dirac MS. Author: nawiebe@microsoft.com MS. Date: 12/11/2017 MS. topic: cikk No-Loc:
- "Q#"
- "$$v"
- "$$"
- "$$"
- "$"
- "$"
- "$"
- "$$"
- "\cdots"
- "bmatrix"
- "\ddots"
- "\equiv"
- "\sum"
- "\begin"
- "\end"
- "\sqrt"
- "\otimes"
- "{"
- "}"
- "\text"
- "\phi"
- "\kappa"
- "\psi"
- "\alpha"
- "\beta"
- "\gamma"
- "\delta"
- "\omega"
- "\bra"
- "\ket"
- "\boldone"
- "\\\\"
- "\\"
- "="
- "\frac"
- "\text"
- "\mapsto"
- "\dagger"
- "\to"
- "\begin{cases}"
- "\end{cases}"
- "\operatorname"
- "\braket"
- "\id"
- "\expect"
- "\defeq"
- "\variance"
- "\dd"
- "&"
- "\begin{align}"
- "\end{align}"
- "\Lambda"
- "\lambda"
- "\Omega"
- "\mathrm"
- "\left"
- "\right"
- "\qquad"
- "\times"
- "\big"
- "\langle"
- "\rangle"
- "\bigg"
- "\Big"
- "|"
- "\mathbb"
- "\vec"
- "\in"
- "\texttt"
- "\ne"
- "<"
- ">"
- "\leq"
- "\geq"
- "~~"
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- "\_"

---

# <a name="dirac-notation"></a>Dirac jelölése

Míg az oszlop vektoros jelölése mindenütt szerepel a lineáris algebraban, sokszor nehézkes a Quantum computingban, különösen ha több qubits van szó.  Ha például $ \psi $ egy vektort definiálunk, nem egyértelmű, hogy $ \psi $ sor vagy oszlop vektoros-e.  Így ha a $ \phi $ és $ \psi $ a vektorok, akkor ugyanilyen módon nem egyértelmű, ha $ \phi \psi $ még definiálva van, mert a $ \phi $ és a $ \psi $ környezet alakzatai nem egyértelműek.  A vektorok alakzataival kapcsolatos kétértelműség mellett még a korábban bevezetett lineáris algebrai-jelölést használó egyszerű vektorok is nagyon nehézkesek lehetnek. Ha például egy $ n $ -qubit állapotot szeretnénk leírni, amelyben minden qubit 0 értéket vesz igénybe, $ $ akkor a rendszer formálisan kifejezzük az állapotot 

$$\begin{bmatrix}1 \\\\ 0 \end{bmatrix} \otimes \cdots \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} . $$  

Természetesen a TEN-termék kiértékelése nem praktikus, mert a vektor egy exponenciálisan nagy térben található, ezért ez a jelölés valójában az előző jelöléssel megadható állapot legjobb leírása.  

A [*Dirac-jelöléssel*](https://en.wikipedia.org/wiki/Bra%E2%80%93ket_notation) megoldhatja ezeket a problémákat úgy, hogy egy új nyelvet mutat be a kvantummechanika pontos igényeinek megfelelően.  Ezért azt javasoljuk, hogy az olvasó ne tekintse meg az ebben a szakaszban szereplő példákat a kvantum-állapotok leírására szolgáló merev vényként, hanem az olvasót, hogy megtekintse ezeket olyan javaslatokként, amelyek segítségével tömören kifejezni a kvantum-ötleteket.

A Dirac két típusa létezik: a *melltartó* vektora és a *ket* vektor, így nevezték el, mert ha együtt *braket* vagy belső terméket alkotnak.  Ha $ \psi $ az egy oszlop vektora, akkor azt Dirac-jelöléssel írhatjuk $ \ket { \psi } $ , ahol a $ \ket { \cdot } $ azt jelöli, hogy az egység oszlop vektoros, azaz a *két* pont vektora.  Hasonlóképpen, a sor vektora a $ \psi ^ \dagger $ következőképpen van kifejezve: $ \bra { \psi } $ . Más szóval a $ \psi ^ \dagger $ beléptetés-Wise összetett ragozás a átültetésének elemeire való alkalmazásával szerezhető be $ \psi $ . A melltartó-ket jelölés közvetlenül azt jelenti, hogy $ \braket { \psi | \psi } $ a vektor belső terméke $ \psi $ önmagában, amely az 1. definíció szerint van $ $ .  

Általánosabb esetben, ha a $ \psi $ és $ \phi $ a kvantum-állapot vektoros belső termékük, $ \braket { \phi | \psi } $ ami azt jelenti, hogy az állapot mérésének valószínűsége a következő: $ \ket { \psi } $ $ \ket { \phi } $ $ | \braket { \phi | \psi } | ^ 2 $ .  

A következő egyezmény a nulla és egy (az qubit számítási alap állapotú) értékek kódolására szolgáló kvantum-állapotok leírására szolgál:

$$
\begin{bmatrix}1 \\\\ 0 \end{bmatrix} = \ket { 0 } ,\qquad
\begin{bmatrix}0 \\\\ 1 \end{bmatrix} = \ket { 1 } .
$$

### <a name="example-representing-the-hadamard-operation-with-dirac-notation"></a>Példa: a Hadamard műveletet jelképező Dirac-jelöléssel

A következő jelölést gyakran használják olyan állapotok leírására, amelyek a Hadamard kapunak a 0 és 1 értékre való alkalmazásából erednek $ \ket { } $ $ \ket { } $ (amelyek a $ Bloch szférában található + x és-x irányban lévő egység-vektoroknak felelnek $ $ $ meg):

$$
\frac{1 } { \sqrt { 2 } } \begin{bmatrix} 1 \\\\ 1 \end{bmatrix} = H \ket { 0 } = \ket { + } ,\qquad
\frac{1 } { \sqrt { 2 } } \begin{bmatrix} 1 \\\\ – 1 \end{bmatrix} = H \ket { 1 } = \ket { - } .
$$

Ezek az állapotok a Dirac-jelöléssel bővíthetők $ \ket { 0 } $ és $ \ket { 1 } $ összegként:

$$
\ket{+}= \frac{ 1 } { \sqrt { 2 } } ( \ket { 0 }  +  \ket { 1 } ), \qquad \ket { - } = \frac { 1 } { \sqrt { 2 } } ( \ket { 0 }  -  \ket { 1 } ).
$$

### <a name="computational-basis-vectors"></a>Számítási alapú vektorok
Ez azt mutatja be, hogy az ilyen állapotok milyen gyakran nevezik *számítási alapnak*: minden egyes kvantum-állapot mindig kifejezhető számítási alapú vektorok összegével, és az ilyen összegeket egyszerűen Dirac-jelöléssel lehet kifejezni.  A Converse is igaz, hogy az állapotok $ \ket { + } $ és a $ \ket { - } $ kvantum-állapotok alapja is.  Ezt a tényt láthatja, hogy

$$
\ket{0 } = \frac { 1 } { \sqrt { 2 } } ( \ket { + }  +  \ket { - } ), \qquad \ket { 1 } = \frac { 1 } { \sqrt { 2 } } ( \ket { + }  -  \ket { - } ).
$$

Példa a Dirac-jelölésre, vegye figyelembe a braket $ \braket { 0 | 1 } $ , amely a belső termék $ 0 $ és 1 $ között $ .  A következőképpen írható 

$$\braket{0 1, 0 0 | } = \begin{bmatrix} & \end{bmatrix} \begin{bmatrix} \\\\ 1 \end{bmatrix} = 0.$$

Ez azt jelzi, hogy a $ \ket { 0 } $ és az $ \ket { 1 } $ merőleges vektor, ami azt jelenti, hogy $ \braket { 0 | 1 } = \braket { | 0 0 } = $ .  Továbbá a 0 0 1 1 1 $ \braket { | } = \braket { | } = $ ., ami azt jelenti, hogy a két számítási alap vektorok is *orthonormal*néven hívhatók.
Ezek a orthonormal tulajdonságok az alábbi példában is hasznosak. Ha $ \ket { \psi } = { \frac { az állapot 3 } { 5 } } \ket { 1 }  +  { \frac { 4 } { 5 } } \ket { 0 } $ , akkor mivel $ \braket { 1 | 0 } = 0 az 1. $ mérési valószínűség $ $  

$$\big|\braket{1 | \psi } \big | ^ 2 = \left | \frac { 3 } { 5 } \braket { 1 | 1 }  + \frac { 4 } { 5 } \braket { 1 | 0 } \right | ^ 2 = \frac { 9 } { 25 } .$$ 

### <a name="tensor-product-notation"></a>Tenser termék jelölése
A Dirac-jelölés magában foglalja az implicit tenser termék struktúráját is.  Ez azért fontos, mert a kvantum-számítástechnika esetében a két, nem korrelált kvantum-regiszter által ismertetett állapot-vektor a két állapotú vektor kétszintű terméke.  A tensing termék szerkezetének tömör leírása vagy ennek hiánya létfontosságú, ha meg szeretné magyarázni a kvantum-számításokat.  A kétszintű termék szerkezete azt feltételezi, hogy $ \psi \otimes \phi $ bármilyen két kvantum-állapotú vektort írhatunk, és a ( $ \phi $ $ \psi $ $ \ket { \psi } \ket { \phi } $ más néven explicit módon $ \ket { \psi } \otimes \ket { \phi } $ ), $ \otimes $ a vektorok közötti írással azonban szükségtelen.  Például a nulla állapotba inicializált két qubits állapotot a következő adja meg:

$$
\begin{bmatrix}1 \\\\ 0 \\\\ 0 \\\\ 0 \end{bmatrix} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} = \ket { } \otimes \ket { } = \ket { } \ket { } 0 0 0 0.
$$

Hasonlóképpen, a p Integer p állapota $ \ket { } $ $ $ olyan kvantum-állapotot jelöl, amely bináris formában kódolja a $ p egész számot $ .  Ha például azt szeretnénk, hogy az 5. számot $ $ egy aláíratlan bináris kódolással fejezzük ki, ugyanúgy kifejezzük

$$
\ket{1 } \ket { 0 } \ket { 1 } = \ket { 101 } = \ket { 5 } .
$$

Ebben a jelölésben a $ \ket { 0 } $ nem igényel egyetlen qubit állapotot, hanem egy *qubit-regisztrációt* , amely a 0 bináris kódolást tárolja $ $ .  A két jelölés közötti különbségek általában a kontextusból törlődnek.  Ez az egyezmény hasznos lehet az első példa leegyszerűsítéséhez, amely a következő módokon írható:

$$
\begin{bmatrix}1 0 1 0 0 0 0 0 0 \\\\ \end{bmatrix} \otimes \cdots \otimes \begin{bmatrix} \\\\ \end{bmatrix} = \ket { } \otimes \cdots \otimes \ket { } = | \cdots \rangle = \ket { } ^ { \otimes n } = \ket { 0 } .
$$

### <a name="example-describing-superposition-with-dirac-notation"></a>Példa: a Dirac-jelöléssel való Felfekvés leírása
Egy másik példa arra, hogy miként használhatja a Dirac-jelölést a kvantum-állapot leírására, vegye figyelembe a következő egyenértékű módokat olyan kvantum-állapot írásához, amely egyenlő arányban jelenik meg az n érték minden lehetséges kis hosszában. $$

$$
H ^ { \otimes n } \ket { 0 } = \frac { 1 } { 2 ^ { n/2 } } \sum _ { j = 0 } ^ { 2 ^ n-1 } \ket { j } = \ket { + } ^ { \otimes n } .
$$

Itt az is előfordulhat, hogy az összeg az $ $ $ n BITS esetében 0 és 2 ^ { n } – 1 közötti értékre mutat $ $ $ .  Először is vegye figyelembe, hogy az $ { } $ $ n BITS által elvégezhető 2 ^ n különböző konfiguráció $ .  Ezt úgy tekintheti meg, hogy az egyik bit 2 értéket vehet igénybe, $ $ de két bit $ 4 értéket vehet igénybe $ , és így tovább. Általánosságban véve ez azt jelenti, hogy $ 2 ^ n $ különböző lehetséges bites sztring van, de a legnagyobb érték $ 1 \cdots 1 = 2 ^ n-1 $ , így ez az összeg felső korlátja.
Ennek a példának a megjelölése, hogy ebben a példában nem használunk $ \ket { + } ^ { \otimes n } = \ket { + } $ -t analógia $ \ket { 0 n 0-ra, } ^ { \otimes } = \ket { } $ mert ez a jelölési egyezmény általában a számítási alapállapothoz van fenntartva, és minden qubit nullára van inicializálva.  Habár ebben az esetben ez az egyezmény ésszerű lenne, nem alkalmazható a Quantum Computing-szakirodalom keretében.

### <a name="expressing-linearity-with-dirac-notation"></a>Lineárisság kifejező Dirac jelöléssel
A Dirac-jelölés egy másik szép funkciója az a tény, hogy lineáris.  Ha négy kvantum-állapotú vektort szeretne írni, 

$$( \alpha \ket { \psi }  + \beta \ket { \phi } ) \otimes ( \gamma \ket { \chi }  +  \delta \ket { \omega } ) = \alpha \gamma \ket { \psi } \ket { \chi }  +  \alpha \delta \ket { \psi } \ket { \omega } + \beta \gamma \ket { \phi } \ket { \chi } + \beta \delta \ket { \phi } \ket { \omega } .$$

Ez azt jelenti, hogy a Dirac-jelöléssel terjesztheti a tízes termék jelölését, így az állapot-vektorok közötti tenser-termékek megtartása ugyanúgy zajlik, mint a hagyományos szorzás.

A melltartó-vektorok hasonló konvenciót követnek a két vektorhoz.  A vektor például $ \bra { \psi } \bra { \phi } $ megegyezik az állapot vektor $ \psi ^ \dagger \otimes \phi ^ \dagger = ( \psi \otimes \phi ) ^ \dagger $ értékével. Ha a két pont vektora $ \ket { \psi } $ $ \alpha \ket { 0 }  +  \beta \ket { 1, } $ akkor a vektor melltartó vektoros verziója $ \bra { \psi } = \ket { \psi } ^ \dagger = ( \bra { 0 } \alpha ^ * + \bra { 1 } \beta ^ *) $ .

Tegyük fel például, hogy szeretnénk kiszámítani azt a valószínűséget, hogy a $ \ket { \psi } = \frac { 3 } { 5 } \ket { 1 }  +  \frac { 4 } { 5 0 állapotot } \ket { } $ egy Quantum program használatával mérjük, amely a következő lehet: $ \ket { + } $ vagy $ \ket { - } $ . Ezt követően a valószínűsége, hogy az eszköz kiírja a következő állapotot $ \ket { - } $ 

$$|\braket{- |\psi}| ^ 2 = \left | \frac { 1 } { \sqrt { 2 } } ( \bra { 0 }  -  \bra { 1 } ) ( \frac { 3 } { 5 } \ket { 1 }  +  \frac { 4 } { 5 } \ket { 0 } ) \right | ^ 2 = \left | - \frac { 3 } { 5 \sqrt { 2 } }  +  \frac { 4 } { 5 \sqrt { 2 } } \right | ^ 2 = \frac { 1 } { 50 } .$$

Az a tény, hogy a negatív előjel jelenik meg a valószínűség kiszámításakor, a kvantum-interferencia megnyilvánulása, amely az egyik olyan mechanizmus, amellyel a Quantum Computing előnyt élvez a klasszikus számítástechnika terén.

## <a name="ketbra-or-outer-product"></a>ketbra vagy külső termék
A Dirac jelölésének utolsó eleme a *ketbra* vagy külső termék.  A külső termék a Dirac-jelöléseken belül szerepel $ \ket { \psi } \bra { \phi } $ , és más néven ketbras, mivel a melltartó és a kulcsfontosságú alaptechnológiák a brakets ellentétes sorrendben történnek.  A külső termék a mátrixok szorzásán keresztül van definiálva, mint $ \ket { \psi } \bra { \phi } = \psi \phi ^ \dagger $ a Quantum State vectors $ \psi $ és a $ \phi $ .  Ennek a jelölésnek a legegyszerűbb és vitathatatlan leggyakoribb példája a következő

$$
\ket{0 } \bra { 0 } = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \begin{bmatrix} 1 & 0 1 0 0 \end{bmatrix} = \begin{bmatrix} & \\\\ & 0 \end{bmatrix} \qquad \ket { 1 } \bra { 1 } = \begin{bmatrix} 0 \\\\ 1 0 \end{bmatrix} \begin{bmatrix} & 1 \end{bmatrix} = \begin{bmatrix} 0 & \\\\ & \end{bmatrix} 0 0 1.
$$

A Ketbras gyakran nevezik kivetítőknek, mert a kvantum-állapotot egy rögzített értékre tervezik.  Mivel ezek a műveletek nem egységesek (és nem is őrzik meg a vektorok normáját), nem meglepő, hogy a kvantum-számítógép nem tud determinisztikus módon alkalmazni.  A kivetítők azonban szép munkát végeznek, amely leírja, hogy milyen műveletet végeznek a mérések kvantum-állapotban.  Ha például egy állapotot $ \ket { \psi } $ 0 értékre mérjük, $ $ akkor az azt eredményezi, hogy az állapot a mérés eredményeképpen a következőképpen alakul:

  $$\ket{\psi}\right \frac nyíl { ( \ket { 0 } \bra { 0 } ) \ket { \psi } } { | \braket { 0 | \psi } | } = \ket { 0 } ,$$

az egyik arra vár, hogy mérjük-e az állapotot, és hogy $ \ket { 0 legyen } $ .  Az ismételt próbálkozáshoz az ilyen kivetítőket nem lehet a kvantum-számítógép determinisztikus módon állapotában alkalmazni.  Ehelyett a legjobb esetben véletlenszerűen lesznek alkalmazva, ha a $ \ket { 0 eredmény } $ bizonyos rögzített valószínűséggel van meghatározva.  Egy ilyen mérték sikeres megírásának valószínűsége az állapotú kvantum-kivetítő várt értéke lehet.

$$
\bra{\psi}( \ket { 0 } \bra { 0 } ) \ket { \psi } = | \braket { \psi | 0 } | ^ 2,$$

Ez azt szemlélteti, hogy a kivetítők egyszerűen új módot adnak a mérési folyamat kifejezésére.

Ha ehelyett egy többqubits állapot első qubit kell mérnie, $ $ akkor ezt a folyamatot a kivetítők és a Dirac-jelölések használatával is kényelmesen le tudjuk írni:

$$
P ( \text { első qubit = 1 } ) = \bra { \psi } \left (1 \ket { } \bra { 1 } \otimes \boldone ^ { \otimes n-1 } \right ) \ket { \psi } .
$$

Itt az Identity Matrix is kényelmesen írható Dirac-jelöléssel

$$
\boldone= \ket{ 0 0 1 1 1 } \bra { } + \ket { } \bra { } = \begin{bmatrix} & 0 \\\\ 0 & 1 \end{bmatrix} .
$$

Abban az esetben, ha két qubits a kivetítő kibontható 

$$
\ket{1 1 1 } \bra { } \otimes \id = \ket { } \bra { 1 } \otimes ( \ket { 0 } \bra { 0 } + \ket { 1 } \bra { 1 } ) = \ket { 10 } \bra { 10 }  +  \ket { 11 } \bra { 11 } .
$$

Ezt követően láthatjuk, hogy ez összhangban van a multiqubit-állapotok oszlop-vektoros jelöléssel való használatának valószínűségével kapcsolatos megbeszélésekkel:

$$
P ( \text { első qubit = 1 } ) = \psi ^ \dagger (e \_ { 10 } e \_ { 10 } ^ \dagger + e \_ { 11 } e \_ { 11 } ^ \dagger ) \psi = | e \_ { 10 } ^ \dagger \psi | ^ 2 + | e \_ { 11 } ^ \dagger \psi | ^ 2,$$

amely megfelel a többszörös qubit mérési vitának.  Ennek az eredménynek az általánosítása a többtényezős qubit esetében azonban valamivel egyszerűbb, ha Dirac-jelölést használ, mint az oszlop-vektoros jelölés, és teljesen egyenértékű a korábbi kezeléssel.

## <a name="density-operators"></a>Sűrűségi operátorok

Egy másik hasznos operátor, amely a Dirac jelölést *használja, más*néven *állapot*-kezelőként is ismert.
A Quantum State Vector sűrűségű operátora a \rho formáját $ ölti = \ket { \psi } \bra { \psi } $ .
Ez a fogalom azt jelenti, hogy az államot mátrixként, nem pedig vektorként jelöli meg, általában azért, mert kényelmes módot biztosít a valószínűségi számítások ábrázolására, valamint lehetővé teszi, hogy az egyik a statisztikai bizonytalanságot is leírja, valamint a kvantum-bizonytalanságot ugyanazon a formalitáson belül.
A kvantum-számítástechnika egyes területein az általános kvantum-operátorok, a vektorok helyett mindenütt elérhetők, de nem szükségesek a mező alapjaihoz.
Az érdekelt olvasó számára javasoljuk, hogy olvassa el a [További tudnivalókat ismertető](xref:microsoft.quantum.more-information)füzetek egyikét.

## <a name="no-locq-gate-sequences-equivalent-to-quantum-states"></a>Q#a kvantum-állapotoknak megfelelő Gate-sequencek
Az utolsó pont a kvantum-jelöléssel és a Q# programozási nyelvvel ér véget: a dokumentum kezdetén megemlítettük, hogy a kvantum-állapot a kvantum-számítástechnikai információk alapvető célja.  Ekkor meglepőnek tűnhet, hogy a kvantum- Q# állapot fogalma nincs.  Ehelyett az összes állapotot csak az előkészítéséhez használt műveletek írják le.  Az előző példa egy kiváló illusztráció.  Ahelyett, hogy egységes, a regiszterben lévő összes kvantum-sztringre kifejezzék a pozíciót, az eredmény a következők egyike lehet: $ H ^ { \otimes n } \ket { 0 } $ .  Ennek az állapotnak az exponenciálisan rövidebb leírása nem csupán az előnye, hogy klasszikusan indokolja, de az algoritmus megvalósításához szükséges műveleteket is tömören definiálja.  Emiatt úgy tervezték, hogy a kiindulási és a Q# kvantum-állapot helyett a Gate-sorozatot bocsátja ki, azonban elméleti szinten a két perspektíva egyenértékű.
