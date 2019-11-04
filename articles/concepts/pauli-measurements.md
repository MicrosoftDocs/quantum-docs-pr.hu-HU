---
title: Pauli-mérések | Microsoft Docs
description: Pauli-mérések
author: QuantumWriter
uid: microsoft.quantum.concepts.pauli
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 7bea821be7e26e72f2860278486d35be676ca63d
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183709"
---
# <a name="pauli-measurements"></a>Pauli-mérések

Az előző megbeszélésekben a számítási szempontok alapján történik a mérés.  Valójában vannak olyan gyakori mérések is, amelyek a kvantum-számítástechnika során a kiértékelési szempontból kényelmesek a számítási eredmények alapján.  A mérések leggyakoribb halmaza a *Pauli-mérés*.  Ilyen esetekben gyakori, hogy megbeszéljük a Pauli-operátorok mérését, általában egy operátort, például $X, Y, Z $ vagy $Z \otimes Z, X\otimes X, X\otimes Y $ és így tovább.  A kiértékelése a Pauli-operátorok esetében különösen gyakori a kvantum-hibák helyesbítésének almezőjében. A Q # esetében egy hasonló konvenciót követünk. most a mérések alternatív nézetét magyarázjuk.

A Pauli-mérések részleteinek megismerése előtt érdemes meggondolni, hogy a kvantum-számítógépeken belüli egyetlen qubit hogyan mérhető a kvantum állapot.  Képzelje el, hogy van egy $n qubit kvantum-állapota; Ezután az egyik qubit mérése azonnal kiírja a $2 ^ n $ lehetőség felét, amely az állapot lehet.  Ez azt jelenti, hogy a mérték a kvantum-állapotot a két fél szóköz egyikére vetíti.  Általánosíthatja a mérést úgy gondoljuk, hogy ezt tükrözze.

Az alterületek tömör azonosításához szükség van egy nyelvre a leírásához.  Ezt úgy teheti meg, hogy a két alterületet írja le úgy, hogy egy olyan mátrixon keresztül adja meg őket, amely csak két egyedi eigenvalues rendelkezik, az egyezmény szerint pedig $ \pm $1.  A legegyszerűbb példa erre:

$ $ Z = \begin{bmatrix} 1 & 0 \\\\ 0 &-1 \end{bmatrix}.
$$

A Pauli-$Z $ mátrix egyértelműen két eigenvectors $ \ket{0}$ és $ \ket{1}$, eigenvalues $ \pm $1.  Így ha mérjük a qubit, és beszerezzük a $ \ket{0}$-t, akkor a $ + $1 eigenspace (az összes olyan vektor, amely csak pozitív vagy csak negatív eigenvalues), és ha a $ \ket{1}$ értéket mérjük, a $-$1 ei $Z $ genspace.  Ezt a folyamatot a Pauli-mérések "Pauli $Z $" mérési nyelvén kell megtekinteni, és a folyamat teljes mértékben megfelel a számítási alapokra vonatkozó mérések elvégzésének.

Természetesen minden $2 \ Times $2 mátrix, amely a $Z $ egységes átalakítása, szintén megfelel ennek a feltételnek.  Ennek az az oka, hogy a mátrix $A = U ^ \dagger Z U $, bármely egységes mátrixú $U $ esetében is megfontolandó, hogy olyan mátrixot adjon meg, amely meghatározza a mérés két eredményét a $ \pm $1 eigenvectors.  A Pauli-mérések jelölése úgy hivatkozik rá, hogy $X, Y, Z $ méréseket azonosít.  Ezek a mérések az alábbiakban láthatók a kényelem érdekében.

$ $ \begin{Array}{| c | c |} \text{Pauli mérés} & U\\\\ Z & \boldone\\\\ X & H\\\\ Y & HS ^ \dagger\\\\ \end{Array} $ $

Ez a nyelv használata esetén a "mérték $Y $" egyenértékű a $HS ^ \dagger $-re való alkalmazásával, majd a számítási folyamat alapján történő méréssel, ahol a $S $ a által megadott úgynevezett Phase Gate

$ $ \begin{bmatrix}1 & 0\\\\ 0 & i\end {bmatrix}.
$$

A $HS ^ \dagger $ és a Quantum State Vector, majd a $Z $ mérése is egyenértékű.  A megfelelő állapotot a rendszer úgy fogja megtalálni, hogy visszaalakítja a számítási alapot, amely a $SH $ értéket alkalmazza a kvantum-állapot vektorára.

## <a name="q-outcome-classical-information-obtained-from-quantum-state"></a>Q # a kvantum-állapotból beszerzett klasszikus információk végeredménye
A Q # azt mondjuk, hogy a kinyert klasszikus információ az állammal való interakcióból származik, $j $, amely a $\{0, 1\}$ $ értékben van, ha az eredmény az $ (-1) ^ j $ eigenspace van, amely a Pauli operátort méri.

A több-qubit Pauli-operátorok mérései hasonló módon vannak definiálva, ahogy a következőkben is látható:

$ $ Z\otimes Z = \begin{bmatrix}1 & 0 & 0 & 0\\\\ 0 &-1 & 0 & 0\\\\ 0 & 0 &-1 & 0\\\\ 0 & 0 & 0 & 1 \ End {bmatrix}.
$$

Így a két Pauli-$Z $ operátorral rendelkező kétféle, a két szóközből álló mátrix a $ + $1 és a $-$1 eigenvalues áll.  Az qubit esethez hasonlóan mindkettő fél helyet jelent, ami azt jelenti, hogy az elérhető vektor területének fele a $ + $1 eigenspace és a fennmaradó fele a $-$1 eigenspace-hez tartozik.  Általánosságban elmondható, hogy a kéttényezős termék definíciója alapján a Pauli-$Z $ operátorok és az identitás a következőt is betartja.  Például:

$ $ Z\otimes\boldone = \begin{bmatrix} 1 & 0 & 0 & 0\\\\ 0 & 1 & 0 & 0\\\\ 0 & 0 &-1 & 0\\\\ 0 & 0 & 0 & – 1 \ End {bmatrix}.
$$

Ahogy korábban is, az ilyen mátrixok egységes átalakítása a $ \pm $1 eigenvalues által címkézett két fél szóközt is ismerteti.  Például $X \otimes X = H\otimes H (Z\otimes Z) H\otimes H $ értéket az identitásból, amely $Z = HXH $.  Az qubit esethez hasonlóan mind a két qubit (Pauli) mérések írhatók $U ^ \dagger (Z\otimes \id) U $ for $4 \ Times $4 egységes mátrixok $U $ használatával.  A következő táblázatban szereplő transzformációk számbavétele során bemutatjuk a qubits $0 $ és $1 $: $ \operatorname{SWAP} = \operatorname{CNOT}\_{01}\operatorname{CNOT}\_{10}\operatorname{ CNEM}\_{01}$:

$ $ \begin{Array}{| c | c |} \text{Pauli mérés} & U\\\\ \hline Z\otimes \boldone & \boldone\otimes \boldone\\\\ X\otimes \boldone & H\otimes \boldone\\\\ Y\otimes \boldone & HS ^ \dagger\ otimes \boldone\\\\ \boldone \otimes Z & \operatorname{SWAP}\\\\ \boldone \otimes X & (H\otimes \boldone) \operatorname{SWAP}\\\\ \boldone \otimes Y & (HS ^ \dagger\otimes \boldone) \ operatorname {SWAP}\\\\ Z\otimes Z & \operatorname{CNOT}\_{10}\\\\ X\otimes Z & \operatorname{CNOT}\_{10}(H\otimes \boldone)\\\\ Y\otimes Z & \ operatorname {CNEM}\_{10}(HS ^ \dagger\otimes \boldone)\\\\ Z\otimes X & \operatorname{CNOT}\_{10}(\boldone\otimes H)\\\\ X\otimes X & \operatorname{CNOT}\_@no__t _31_ (H\otimes H)\\\\ Y\otimes X & \operatorname{CNOT}\_{10}(HS ^ \dagger\otimes H)\\\\ Z\otimes Y & \operatorname{CNOT}\_{10}(\boldone \otimes HS ^ \dagger)\\\\ X\otimes Y & \operatorname{CNOT}\_{10}(H\otimes HS ^ \dagger)\\\\ Y\otimes Y & \operatorname{CNOT}\_{10}(HS ^ \dagger\otimes HS ^ \dagger)\\\\ \end{Array} $ $

Itt a Gate $ \operatorname{CNOT}\_{10}$ a következő okból jelenik meg.  Minden olyan Pauli-mérés, amely nem tartalmazza a $ \boldone $ mátrixot, egyenértékű a fenti indoklással $Z \otimes Z $ értékkel.  A $Z \otimes Z $ eigenvalues csak a qubits paritása függ, amely az egyes számítási erőforrások vektorait tartalmazza, és a listában megjelenő ellenőrzött műveletek a paritás kiszámításához és az első biten való tárolásához szolgálnak.  Ezután az első bit mérése után helyreállítjuk az eredményül kapott fél terület identitását, amely egyenértékű a Pauli-operátor mérésével.

Egy további Megjegyzés, míg az is előfordulhat, hogy azt feltételezi, hogy $Z \otimes Z $ érték mérése megegyeznek a $Z \otimes \id $, majd a $ \id \otimes Z $ érték mérésével, ez a feltételezés hamis lenne.  Ennek az az oka, hogy a $Z \otimes Z $-projektek a kvantum-állapotot a fenti operátorok $ + $1 vagy $-$1 eigenstate mérik.  $Z \otimes \id $, majd a $ \id \otimes Z $ projektek mérése után a Quantum State Vector először a $Z \otimes \id $ fél területére, majd a $ \id \otimes Z $-ra.  Mivel négy számítási alap vektor létezik, mindkét mérés végrehajtása csökkenti az állapotot egy negyedéves területre, és így csökkenti azt egyetlen számítási célú vektorban.


## <a name="correlations-between-qubits"></a>Qubits közötti korrelációk
Paulis (például $X \otimes X $ vagy $Z \otimes Z $) mérőszámának mérésének egy másik módja, hogy ezek a mérések lehetővé teszik a két qubits közötti összefüggésekben tárolt információk megkeresését.  $X \otimes \id $ mérésével megtekintheti az első qubit helyileg tárolt információit.  Habár a kvantum-számítástechnika mindkét típusú mérése egyenlően értékes, a korábbi megvilágítja a kvantum-számítástechnika erejét. Ez azt mutatja, hogy a kvantum-számítástechnikaban a megtanulni kívánt információ nem egyetlen qubit van tárolva, hanem nem helyileg, hanem az összes qubits, és csak úgy, hogy egy közös mérésen keresztül történik, és $Z \otimes Z $-vel nyilvánvaló.

Az önkényes Pauli-operátorok, például a $X \otimes Y \otimes Z \otimes \boldone $ is mérhetők.  A Pauli-operátorok összes ilyen tenser-terméke csak két eigenvalues $ \pm $1, és mindkét eigenspaces a teljes vektoros terület felét képezi.  Így a fent említett követelmények egybeesnek.

A Q #-ban az ilyen mérések $j $ értéket adnak vissza, ha a mérés eredménye a $ (-1) ^ j $ eigenspace eredményezi.  Ha ez a Q # beépített funkciója, akkor hasznos, mert az ilyen operátorok méréséhez hosszú láncú vezérelt nem kapuk és átalakítások szükségesek, hogy leírják a diagonalizing $U $ Gate-t, amely a műveletnek a $Z $ és $ \id $ tízes termékként való kifejezéséhez szükséges.  Ha egyszerűen meg szeretné határozni, hogy ezeket az előre definiált méréseket kívánja elvégezni, nem kell aggódnia, hogy hogyan alakíthatja át az alapjait, hogy a számítási alap a szükséges információkat tartalmazza.  A Q # az összes szükséges átalakítást automatikusan kezeli. Lásd [a Q # Library-referenciát a Pauli-mérésekhez](/qsharp/api/canon/microsoft.quantum.canon.measurepaulis)

## <a name="the-no-cloning-theorem"></a>A klónozás nélküli tétel
A Quantum információi hatékonyak.  Lehetővé teszi, hogy elképesztően olyan dolgokat végezzenek, mint a faktorok száma exponenciálisan, mint a legismertebb klasszikus algoritmusok, vagy hatékonyan szimulálja a korrelált elektron-rendszereket, amelyekkel a klasszikusan exponenciálisan kell szimulálni a pontos műveleteket.  A kvantum-számítástechnika hatékonysága azonban korlátozott.  Az egyik ilyen korlátozást a *nem klónozási tétel*adja meg.

A nem klónozási tétel találó elnevezésű.
Az általános kvantum-állapotok egy kvantum-számítógép általi klónozását nem teszi lehetővé.
A tétel bizonyítása rendkívül egyszerű.
Habár a nem klónozási tétel teljes bizonyítéka egy kicsit túl sok technikai megoldás a vitához, a tétel igazolása abban az esetben, ha a szóban forgó kvantum-számítógép nem rendelkezik további Ancilla qubits (Ancilla qubits a felhasználatlan qubits. a számítás során a terület könnyen használható és felügyelhető a Q #-ban, lásd: <xref:microsoft.quantum.techniques.qubits>).
Ilyen kvantum-számítógép esetén a klónozási műveletnek egységes mátrixnak kell lennie. Megtiltjuk a mérést, mivel az sérült a klónozott állapotot. A kívánt egységes mátrixnak a következő tulajdonsággal kell rendelkeznie: $ $ U \ket{\psi} \ket{0} = \ket{\psi} \ket{\psi}, $ $ bármely állapothoz $ \ket{\psi} $.
A mátrix szorzásának lineáris tulajdonsága azt jelenti, hogy bármely második kvantum-állapothoz $ \ket{\phi} $,

\begin{align} & U\left [\frac{1}{\sqrt{2}} \left (\ket{\phi} + \ket{\psi} \right) \right] \ket{0}= \frac{1}{\sqrt{2}} U\ket {\ Phi} \ ket{0}+ \frac{1}{\sqrt{2}} U\ket {\ PSI} \ ket{0}@no__ t_9_ \\ & \qquad\qquad = \frac{1}{\sqrt{2}} \left (\ket{\phi}\ket{\phi} + \ket{\psi}\ket{\psi}\right)\\\\ & \qquad\qquad\ne \left (\frac{1}{\sqrt{2}} \left (\ket{\phi} + \ket{\psi} \ Right) \right) \otimes\left (\frac{1}{\sqrt{2}} \left (\ket{\phi} + \ket{\psi} \right) \right).
\end{align}

Ez biztosítja az alapvető intuíciót a nem klónozási tétel mögött: minden olyan eszközön, amely egy ismeretlen kvantum-állapotot másol, a hibákat legalább néhány, az általa használt állapotból kell kiváltani.  Míg a fő feltételezés, hogy a Cloner a bemeneti állapot alapján lineárisan működik, megsértheti a Ancilla-qubits hozzáadásával és a Ancilla mérésével, ezek az interakciók a rendszerre vonatkozó információkat is megsérthetik a mérési statisztikán keresztül, és megakadályozhatják a pontos klónozás ilyen esetekben is.  A nem klónozási tétel részletesebb igazolását a [További tudnivalókat](xref:microsoft.quantum.more-information)ismertető témakörben talál.

A nem klónozási tétel fontos a kvantum-számítástechnika minőségi megismerése érdekében, mert ha a kvantum-állapotok költséges klónozását, akkor közel varázslatos képességet kap a kvantum-állapotok megismeréséhez.  Valójában megsértheti a Heisenberg hencegő bizonytalansági elvét.  Azt is megteheti, hogy az optimális Cloner használatával egyetlen mintát vesz igénybe egy összetett kvantum-eloszlásból, és megtudhatja, hogy az adott disztribúcióról csak egyetlen mintából lehet tájékozódni.  Ez olyan lenne, mint egy érme tükrözése és a fejek betartása, majd egy barátomnak szól az eredményről, amelyeknek válaszoltak "Ah az érme eloszlásának Bernoulli kell lennie $p = 0.512643 \ ldots $!"  Egy ilyen utasítás nem sensical, mert egy kis információ (a fejek végeredménye) egyszerűen nem tudja biztosítani az elosztás kódolásához szükséges több bitet a jelentős előzetes információk nélkül.  Hasonlóképpen, az előzetes információk nélkül nem tudjuk tökéletesen klónozott állapotba állítani a kvantum-állapotot, mivel nem tudjuk előkészíteni az ilyen érmék együttesét anélkül, hogy tudnám $p $-t.

Az információk nem ingyenesek a Quantum Computing szolgáltatásban.  A mért qubit egyetlen kis mennyiségű információt biztosítanak, a nem klónozási tétel pedig azt mutatja, hogy nincs olyan hátsó ajtó, amely felhasználható a rendszerről szerzett információk és a meghívott zavarok közötti alapvető kompromisszum megszerzéséhez.

