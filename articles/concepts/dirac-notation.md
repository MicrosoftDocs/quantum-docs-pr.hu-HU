---
title: Dirac-jelölés | Microsoft Docs
description: Dirac jelölése
author: QuantumWriter
uid: microsoft.quantum.concepts.dirac
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 33d964d079c94bd947e35d2c09516b29df1bba11
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/28/2019
ms.locfileid: "73184763"
---
# <a name="dirac-notation"></a>Dirac jelölése

Míg az oszlop vektoros jelölése mindenütt szerepel a lineáris algebraban, sokszor nehézkes a Quantum computingban, különösen ha több qubits van szó.  Ha például a $ \psi $ értéket egy vektorra definiáljuk, nem egyértelmű, hogy a $ \psi $ egy sor vagy egy oszlop vektora.  Így ha a $ \phi $ és a $ \psi $ a vektorok, akkor ugyanilyen módon nem egyértelmű, ha a $ \phi \psi $ értéke még definiálva van, mert a $ \phi $ és a $ \psi $ alakzat nem egyértelmű a kontextusban.  A vektorok alakzataival kapcsolatos kétértelműség mellett még a korábban bevezetett lineáris algebrai-jelölést használó egyszerű vektorok is nagyon nehézkesek lehetnek. Ha például egy $n $-qubit állapotot szeretnénk leírni, amelyben minden egyes qubit $0 $ értéket vesz igénybe, akkor a rendszer formálisan kifejezi az állapotot 

$ $ \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \cdots \otimes\begin{bmatrix}1 \\\\ 0 \end{bmatrix}. $$  

Természetesen a TEN-termék kiértékelése nem praktikus, mert a vektor egy exponenciálisan nagy térben található, ezért ez a jelölés valójában az előző jelöléssel megadható állapot legjobb leírása.  

A [*Dirac-jelöléssel*](https://en.wikipedia.org/wiki/Bra%E2%80%93ket_notation) megoldhatja ezeket a problémákat úgy, hogy egy új nyelvet mutat be a kvantummechanika pontos igényeinek megfelelően.  Ezért azt javasoljuk, hogy az olvasó ne tekintse meg az ebben a szakaszban szereplő példákat a kvantum-állapotok leírására szolgáló merev vényként, hanem az olvasót, hogy megtekintse ezeket olyan javaslatokként, amelyek segítségével tömören kifejezni a kvantum-ötleteket.

A Dirac két típusa létezik: a *melltartó* vektora és a *ket* vektor, így nevezték el, mert ha együtt *braket* vagy belső terméket alkotnak.  Ha a $ \psi $ egy oszlop vektor, akkor a Dirac-jelölést $ \ket{\psi} $ értékre írhatja, ahol a $ \ket{\cdot} $ azt jelzi, hogy az egység oszlop vektoros, azaz egy *két* pontból álló vektor.  Hasonlóképpen, a \psi ^ \dagger $ oszlop a $ \bra{\psi} $ értékkel van kifejezve. Más szóval a $ \psi ^ \dagger $ értéket a rendszer a beléptetési Wise-kifejezéseknek a $ \psi $ átültetésének elemeire való alkalmazásával szerzi be. A melltartó-ket jelölés közvetlenül azt jelenti, hogy a $ \braket{\psi | \psi} $ a Vector $ \psi $ belső terméke önmagában, amely a $1 $ definíció szerint van megadva.  

Általánosságban elmondható, hogy ha a $ \psi $ és a $ \phi $ a kvantum állapot vektorai a belső termékük $ \braket{\phi | \psi} $, ami azt jelenti, hogy a $ \ket{\psi} $ érték mérésének valószínűsége $ \ket{\phi} $ értéke $ | \braket{\phi | \psi} | ^ 2 $.  

A következő egyezmény a nulla és egy (az qubit számítási alap állapotú) értékek kódolására szolgáló kvantum-állapotok leírására szolgál:

$ $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} = \ket{0}, \qquad \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} = \ket{1}.
$$

### <a name="example-representing-the-hadamard-operation-with-dirac-notation"></a>Példa: a Hadamard műveletet jelképező Dirac-jelöléssel

A következő jelölést gyakran használják olyan állapotok leírására, amelyek a Hadamard-kapunak a $ \ket{0}$ és $ \ket{1}$ értékre való alkalmazásából erednek (amelyek megfelelnek a Bloch szférában a $ + x $ és a $-x $ utasításban szereplő egység-vektoroknak):

$ $ \frac{1}{\sqrt{2}} \begin{bmatrix} 1 \\\\ 1 \end{bmatrix} = H\ket{0} = \ket{+}, \qquad \frac{1}{\sqrt{2}} \begin{bmatrix} 1 \\\\-1 \end{bmatrix} = H\ket{1} = \ket{-} .
$$

Ezek az állapotok a Dirac-jelöléssel is bővíthetők a $ \ket{0}$ és a $ \ket{1}$ összegű összegek alapján:

$ $ \ket{+} = \frac{1}{\sqrt{2}} (\ket{0} + \ket{1}), \qquad \ket{-} = \frac{1}{\sqrt{2}} (\ket{0}-\ket{1}).
$$

### <a name="computational-basis-vectors"></a>Számítási alapú vektorok
Ez azt mutatja be, hogy az ilyen állapotok milyen gyakran nevezik *számítási alapnak*: minden egyes kvantum-állapot mindig kifejezhető számítási alapú vektorok összegével, és az ilyen összegeket egyszerűen Dirac-jelöléssel lehet kifejezni.  A Converse is igaz abban az állapotban, hogy a \ket{+} $ és a $ \ket{-}$ értékű állapotok a kvantum-állapotok alapjául is szolgálnak.  Ezt a tényt láthatja, hogy

$ $ \ket{0} = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}), \qquad \ket{1} = \frac{1}{\sqrt{2}} (\ket{+}-\ket{-}).
$$

Példaként tekintse meg a Dirac-jelölést, vegye figyelembe a braket $ \braket{0 | 1} $ értéket, amely a belső termék $0 $ és $1 $ közé esik.  A következőképpen írható 

$ $ \braket{0 | 1} = \begin{bmatrix} 1 & 0 \end{bmatrix}\begin{bmatrix}0\\\\ 1 \ End {bmatrix} = 0. $ $

Ez azt jelzi, hogy a $ \ket{0}$ és a $ \ket{1}$ a merőleges vektorok, ami azt jelenti, hogy a $ \braket{0 | 1} = \braket{1 | 0} = $0.  Szintén definíció szerint $ \braket{0 | 0} = \braket{1 | 1} = 1 $, ami azt jelenti, hogy a két számítási alap vektorok is meghívhatók *orthonormal*.
Ezek a orthonormal tulajdonságok az alábbi példában is hasznosak. Ha van állapot $ \ket{\psi} = {\frac{3}{5}} \ket{1} + {\frac{4}{5}} \ket{0}$, mert $ \braket{1 | 0} = $0 az $1 $ mérés valószínűsége  

$ $ \big | \braket{1 | \psi}\big | ^ 2 = \left | \frac{3}{5}\braket{1 | 1} + \frac{4}{5}\braket{1 | 0} \right | ^ 2 = \frac{9}{25}. $ $ 

### <a name="tensor-product-notation"></a>Tenser termék jelölése
A Dirac-jelölés magában foglalja az implicit tenser termék struktúráját is.  Ez azért fontos, mert a kvantum-számítástechnika esetében a két, nem korrelált kvantum-regiszter által ismertetett állapot-vektor a két állapotú vektor kétszintű terméke.  A tensing termék szerkezetének tömör leírása vagy ennek hiánya létfontosságú, ha meg szeretné magyarázni a kvantum-számításokat.  A tenser-termék szerkezete azt feltételezi, hogy a $ \psi \otimes \phi $ értéket írhatjuk bármely két kvantum-állapotú vektorhoz ($ \phi $ és $ \psi $ as $ \ket{\psi} \ket{\phi} $), időnként kifejezetten $ \ket{\psi} \otimes \ket{\phi} $-ként írt \otimes a vektorok között szükségtelen.  Például a nulla állapotba inicializált két qubits állapotot a következő adja meg:

$ $ \begin{bmatrix} 1 \\\\ 0 \\\\ 0 \\\\ 0 \end{bmatrix} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} = \ket{0} \ otimes \ket{0}= \ket{0} \ket{0}.
$$

Hasonlóképpen, a $ \ket{p} $ for Integer $p $ érték azt a kvantum-állapotot jelöli, amely bináris formátumban kódolja az egész $p $ értéket.  Ha például a $5 $ számot egy aláíratlan bináris kódolással szeretnénk kifejezni, akkor a következőhöz hasonló módon fejezzük ki:

$ $ \ket{1}\ket{0}\ket{1} = \ket{101} = \ket{5}.
$$

Ezen a jelölésen belül a $ \ket{0}$-ban nem kell egyetlen qubit állapotra hivatkoznia, hanem egy *qubit-regisztrációra* , amely a $0 $ bináris kódolást tárolja.  A két jelölés közötti különbségek általában a kontextusból törlődnek.  Ez az egyezmény hasznos lehet az első példa leegyszerűsítéséhez, amely a következő módokon írható:

$ $ \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \cdots \otimes\begin{bmatrix}1 \\\\ 0 \end{bmatrix} = \ket{0} \otimes \cdots \otimes \ket{0}= | 0 \ cdots 0 \ rangle = \ket{0}^ {\otimes n} = \ket{0}.
$$

### <a name="example-describing-superposition-with-dirac-notation"></a>Példa: a Dirac-jelöléssel való Felfekvés leírása
Egy másik példa arra, hogy miként használhatja a Dirac-jelölést a kvantum-állapot leírására, vegye figyelembe a következő egyenértékű módokat olyan kvantum-állapot írásához, amely egyenlő arányban van az összes lehetséges $n $ karakternél.

$ $ H ^ {\otimes n} \ket{0} = \frac{1}{2 ^ {n/2}} \sum_{j = 0} ^ {2 ^ n-1} \ket{j} = \ket{+} ^ {\otimes n}.
$$

Itt is csoda, hogy az összeg a $0 $ és a 2 ^ {n} – $1 közötti értékről $n $ BITS-re esik.  Először is vegye figyelembe, hogy 2 ^ {n} $ különböző konfiguráció van, amelyek $n $ BITS-t is igénybe vehetnek.  Ezt úgy tekintheti meg, hogy egy bit $2 $ értéket vehet igénybe, de két bit $4 $ értéket és így tovább. Általánosságban véve ez azt jelenti, hogy 2 ^ n $ különböző lehetséges bit sztring van, de a legnagyobb érték bármelyikük 1 \ cdots 1 = 2 ^ n-$1, így ez az összeg felső korlátja.
Ebben a példában nem a $ \ket{+} ^ {\otimes n} = \ket{+} $ értéket használta a következőhöz hasonlóan: $ \ket{0}^ {\otimes n} = \ket{0}$, mivel ez a jelölési konvenció általában a számítási alapokra van lefoglalva, minden qubit nullával inicializálva.  Habár ebben az esetben ez az egyezmény ésszerű lenne, nem alkalmazható a Quantum Computing-szakirodalom keretében.

### <a name="expressing-linearity-with-dirac-notation"></a>Lineárisság kifejező Dirac jelöléssel
A Dirac-jelölés egy másik szép funkciója az a tény, hogy lineáris.  Ha négy kvantum-állapotú vektort szeretne írni, 

$ $ (\alpha \ket{\psi} + \beta\ket{\phi}) \otimes (\gamma \ket{\chi} + \delta \ket{\omega}) = \alpha\gamma \ket{\psi}\ket{\chi} + \alpha\delta \ket{\psi}\ket{\omega} + \beta\gamma\ket{\phi}\ket{\chi} + \beta\delta\ket{\phi}\ket{\omega}. $ $

Ez azt jelenti, hogy a Dirac-jelöléssel terjesztheti a tízes termék jelölését, így az állapot-vektorok közötti tenser-termékek megtartása ugyanúgy zajlik, mint a hagyományos szorzás.

A melltartó-vektorok hasonló konvenciót követnek a két vektorhoz.  Például az $ \bra{\psi}\bra{\phi} $ vektor felel meg az állapot Vector $ \psi ^ \dagger \otimes \phi ^ \dagger = (\psi\otimes \phi) ^ \dagger $ értékkel. Ha a \ket{\psi} $ \alpha $ a $ \ket{0} + \beta \ket{1}$, akkor a vektor melltartó vektoros verziója $ \bra{\psi} = \ket{\psi} ^ \dagger = (\bra{0}\alpha ^ * + \bra{1}\beta ^ *) $.

Tegyük fel például, hogy szeretnénk kiszámítani a következő állapot mérésének valószínűségét: $ \ket{\psi} = \frac{3}{5} \ket{1} + \frac{4}{5} \ket{0}$ Quantum program használatával, amely az állapotok méréséhez $ \ket{+} $ vagy $ \ket értéket használ.{-}$. Ezt követően a valószínűsége annak, hogy az eszköz kimenete legyen, hogy az állapot $ \ket{-}$ 

$ $ | \braket{-| \psi} | ^ 2 = \left | \frac{1}{\sqrt{2}} (\bra{0}-\bra{1}) (\frac{3}{5} \ket{1} + \frac{4}{5} \ket{0}) \right | ^ 2 = \left |-\frac{3}{5 \ SQRT{2}} + \frac{4}{5 \ SQRT{2}} \right | ^ 2 = \frac{1}{50}. $ $

Az a tény, hogy a negatív előjel jelenik meg a valószínűség kiszámításakor, a kvantum-interferencia megnyilvánulása, amely az egyik olyan mechanizmus, amellyel a Quantum Computing előnyt élvez a klasszikus számítástechnika terén.

## <a name="ketbra-or-outer-product"></a>ketbra vagy külső termék
A Dirac jelölésének utolsó eleme a *ketbra* vagy külső termék.  A külső termék a $ \ket{\psi} \bra{\phi} $ Dirac, és más néven ketbras, mivel a melltartó és a kulcsfontosságú alaptechnológiák a brakets ellentétes sorrendben történnek.  A külső termék a mátrix szorzásán keresztül van definiálva, mint $ \ket{\psi} \bra{\phi} = \psi \phi ^ \dagger $ a Quantum State vectors $ \psi $ és $ \phi $ esetében.  Ennek a jelölésnek a legegyszerűbb és vitathatatlan leggyakoribb példája a következő

$ $ \ket{0} \bra{0} = \begin{bmatrix}1\\\\ 0 \end{bmatrix}\begin{bmatrix}1 & 0 \end{bmatrix} = \begin{bmatrix}1 & 0\\\\ 0 & 0 \ End {bmatrix} \qquad \ket{1} \bra{1} = \begin{bmatrix}0\\\\ 1 \end{bmatrix}\begin{bmatrix}0 & 1 \end{bmatrix} = \begin{bmatrix}0 & 0\\\\ 0 & 1 \ End {bmatrix}.
$$

A Ketbras gyakran nevezik kivetítőknek, mert a kvantum-állapotot egy rögzített értékre tervezik.  Mivel ezek a műveletek nem egységesek (és nem is őrzik meg a vektorok normáját), nem meglepő, hogy a kvantum-számítógép nem tud determinisztikus módon alkalmazni.  A kivetítők azonban szép munkát végeznek, amely leírja, hogy milyen műveletet végeznek a mérések kvantum-állapotban.  Ha például a $ \ket{\psi} $ értéket a $0 $ értékre mérjük, akkor az eredményül kapott átalakítás azt eredményezi, hogy az állapot a mérés eredményeképpen megtapasztalható.

  $ $ \ket{\psi} \rightarrow \frac{(\ket{0} \bra{0}) \ket{\psi}}{| \braket{0 | \psi} |} = \ket{0}, $ $

az egyik arra vár, hogy mérjük-e az állapotot, és megtalálhatja, hogy $ \ket{0}$.  Az ismételt próbálkozáshoz az ilyen kivetítőket nem lehet a kvantum-számítógép determinisztikus módon állapotában alkalmazni.  Ehelyett a legjobb esetben lehet véletlenszerűen alkalmazni, ha a $ \ket{0}$ értéket rögzített valószínűséggel megjelenő találat.  Egy ilyen mérték sikeres megírásának valószínűsége az állapotú kvantum-kivetítő várt értéke lehet.

$ $ \bra{\psi} (\ket{0} \bra{0}) \ket{\psi} = | \braket{\psi | 0} | ^ 2, $ $

Ez azt szemlélteti, hogy a kivetítők egyszerűen új módot adnak a mérési folyamat kifejezésére.

Ha ehelyett úgy gondoljuk, hogy a qubit-állapot első qubit a $1 $ értékre mérjük, akkor a folyamatot a kivetítők és a Dirac használatával is kényelmesen le tudjuk írni:

$ $ P (\text{First qubit = 1}) = \bra{\psi}\left (\ket{1}\bra{1}\otimes \boldone ^ {\otimes n-1} \right) \ket{\psi}.
$$

Itt az Identity Matrix is kényelmesen írható Dirac-jelöléssel

$ $ \boldone = \ket{0} \bra{0}+ \ket{1} \bra{1}= \begin{bmatrix}1 & 0\\\\ 0 & 1 \end{bmatrix}.
$$

Abban az esetben, ha két qubits a kivetítő kibontható 

$ $ \ket{1} \bra{1} \otimes \id = \ket{1}\bra{1} \otimes (\ket{0} \bra{0}+ \ket{1} \bra{1}) = \ket{10}\bra{10} + \ket{11}\bra{11}.
$$

Ezt követően láthatjuk, hogy ez összhangban van a multiqubit-állapotok oszlop-vektoros jelöléssel való használatának valószínűségével kapcsolatos megbeszélésekkel:

$ $ P (\text{First qubit = 1}) = \psi ^ \dagger (e\_{10}e\_{10}^ \dagger + e\_{11}e\_{11}^ \dagger) \psi = | e\_{10}^ \dagger \psi | ^ 2 + | e\_{11}^ \ tőr \psi | ^ 2, $ $

amely megfelel a többszörös qubit mérési vitának.  Ennek az eredménynek az általánosítása a többtényezős qubit esetében azonban valamivel egyszerűbb, ha Dirac-jelölést használ, mint az oszlop-vektoros jelölés, és teljesen egyenértékű a korábbi kezeléssel.

## <a name="density-operators"></a>Sűrűségi operátorok

Egy másik hasznos operátor, amely a Dirac jelölést *használja, más*néven *állapot*-kezelőként is ismert.
A Quantum State Vector sűrűségű operátora a következő formát veszi: $ \rho = \ket{\psi} \bra{\psi} $.
Ez a fogalom azt jelenti, hogy az államot mátrixként, nem pedig vektorként jelöli meg, általában azért, mert kényelmes módot biztosít a valószínűségi számítások ábrázolására, valamint lehetővé teszi, hogy az egyik a statisztikai bizonytalanságot és a kvantum-bizonytalanságot is leírja. ugyanazon a formalitáson belül.
A kvantum-számítástechnika egyes területein az általános kvantum-operátorok, a vektorok helyett mindenütt elérhetők, de nem szükségesek a mező alapjaihoz.
Az érdekelt olvasó számára javasoljuk, hogy olvassa el a [További tudnivalókat ismertető](xref:microsoft.quantum.more-information)füzetek egyikét.

## <a name="q-gate-sequences-equivalent-to-quantum-states"></a>A Q # Gate a Quantum állapotokkal egyenértékű részei
Az utolsó pont a kvantum-jelöléssel és a Q # programozási nyelvvel ér véget: a dokumentum kezdetén azt is említettük, hogy a kvantum-állapot a kvantum-számítástechnikai adatok alapvető tárgya.  Ekkor meglepőnek tűnhet, hogy a Q #-ban nincs a kvantum állapot fogalma.  Ehelyett az összes állapotot csak az előkészítéséhez használt műveletek írják le.  Az előző példa egy kiváló illusztráció.  Ahelyett, hogy egységes, a regiszterben lévő összes kvantum bites sztringre kifejezzék, az eredményt a $H ^ {\otimes n} \ket{0}$ értékkel láthatjuk.  Ennek az állapotnak az exponenciálisan rövidebb leírása nem csupán az előnye, hogy klasszikusan indokolja, de az algoritmus megvalósításához szükséges műveleteket is tömören definiálja.  Emiatt a Q # úgy van kialakítva, hogy a Quantum állapot helyett Gate-sorozatot bocsát ki. elméleti szinten azonban a két perspektíva egyenértékű.

