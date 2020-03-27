---
title: Több qubit
description: Megtudhatja, hogyan hajthat végre műveleteket két vagy több qubits.
author: QuantumWriter
uid: microsoft.quantum.concepts.multiple-qubits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 239073b7e7edafc49bc65cb60c9f45cf0af83dbe
ms.sourcegitcommit: a0e50c5f07841b99204c068cf5b5ec8ed087ffea
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/26/2020
ms.locfileid: "80320891"
---
# <a name="multiple-qubits"></a>Több qubits

Míg az qubit-kapuk olyan intuitív funkciókkal rendelkeznek, mint például az, hogy egy adott időpontban egynél több állapotban legyenek, ha a kvantum-számítógépeken volt egy qubit-kapu, akkor egy olyan számítási teljesítménnyel rendelkező eszközre lenne szükség, amelyet a még a számológép is egy klasszikus szuperszámítógép.
A kvantum-számítástechnika valódi ereje csak akkor válik nyilvánvalóvá, ha növeljük a qubits számát.
Ez a teljesítmény részben fordul elő, mivel a kvantum állapotú vektorok vektoros területének dimenziója exponenciálisan növekszik a qubits számával.
Ez azt jelenti, hogy habár egy qubit-típust is használhat, a 50-qubit kvantum-számítás szimulálása vélhetően leküldi a meglévő szuperszámítógépek korlátait.
A számítások méretének növelése egy további qubit *megduplázza* az állapot tárolásához szükséges memóriát, és nagyjából *megduplázza* a számítási időt.
A számítási teljesítmény gyors megkettőzése miatt a viszonylag kis mennyiségű qubits rendelkező kvantum-számítógép a mai, holnapi és újabb számítási feladatokhoz képest messze felülmúlja a leghatalmasabb számítógépeket.

Miért van exponenciálisan növekedni a Quantum State vectors?  Ennek a szakasznak a célja, hogy áttekintse azokat a szabályokat, amelyek segítségével qubit állapotokat építhet ki az qubit állapotokból, valamint megbeszélheti a kapunk azon műveleteit, amelyekkel egy univerzális, sok qubit kvantum-számítógép alkotható.
Ezek az eszközök feltétlenül szükségesek ahhoz, hogy megértsék a Q # Code-ban gyakran használt kapukat, valamint azt is, hogy a kvantum-effektusok, például a felakadás vagy az interferencia nagyobb teljesítményű, mint a klasszikus számítástechnika terén.

## <a name="representing-two-qubits"></a>Két qubits képvisel
Az egy-és qubit állapot közötti fő különbség az, hogy a két qubit állapot nem két dimenziós, hanem négy dimenziós.
Ennek az az oka, hogy a kétqubitos állapotok számítási alapjait az egy qubit-állapotú transzeurópai termékek alkotják.  Például a \begin{align} 00 \equiv \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix}1 \\\\ 0 \end{bmatrix} & = \begin{bmatrix}1 \\\\ 0\\\\ 0\\\\ 0 \end{bmatrix}, \qquad 01 \equiv \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix}0 \\\\ 1 \end{bmatrix} = \begin{bmatrix}0 \\\\ 1\\\\ 0\\\\ 0 \end{bmatrix} ,\\\\ 10 \equiv \begin{bmatrix}0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix}1 \\\\ 0 \end{bmatrix} & = \begin{bmatrix}0 \\\\ 0\\\\ 1\\\\ 0 \end{bmatrix}, \qquad 11 \equiv \begin{bmatrix}0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix}0 \\\\ \end{bmatrix} = \begin{bmatrix}0 \\\\ 0\\\\ 0\\\\ 1 \end{bmatrix}.
\end{align}

Könnyen megtekinthető, hogy a $n $ qubits kvantum-állapota az adott konstrukció alapján a $2 ^ n $ dimenzió egy egységnyi vektora.  A vektor

$ $ \begin{bmatrix} \ alpha_{00} \\\\ \ alpha_{01} \\\\ \ alpha_{10} \\\\ \ alpha_{11} \end{bmatrix} $ $

a kvantum-állapotot jelöli két qubits, ha $ | \ alpha_{00}| ^ 2 + | \ alpha_{01}| ^ 2 + | \ alpha_{10}| ^ 2 + | \ alpha_{11}| ^ 2 = 1 $. Akárcsak az egyetlen qubits esetében, a több qubits kvantum-állapot vektora a rendszerviselkedés leírásához szükséges összes információt tartalmazza.

Ha két különálló qubits adunk meg, akkor az egyik a $ \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $ és egy második qubit a \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} $ értéknél, a megfelelő két qubit állapot

$ $ \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} \otimes \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} = \begin{bmatrix} \alpha \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} \\\\ \beta \begin{bmatrix}\gamma \\\\ \delta \end{bmatrix} \end{bmatrix} = \begin{bmatrix} \alpha\gamma \\\\ \alpha\delta \\\\ \beta\gamma \\\\ \beta\delta \end{bmatrix} , $$

a $ \otimes $ műveletnek a vektorok Kronecker-termékének (vagy-termékének) nevezzük. Vegye figyelembe, hogy habár a kétqubitos állapotú kétféle qubit esetében mindig megteheti a kétlépcsős adatmennyiséget, nem minden két qubit Quantum-állapot írható be kétféle qubit-állapotú kétszintű termékként.
Például nincsenek állapotok $ \psi = \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $ és $ \phi = \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} $, hogy a tízes termék állapota 

$ $ \psi\otimes \phi = \begin{bmatrix} 1/\ SQRT{2} \\\\ 0 \\\\ 0 \\\\ 1/\ SQRT{2} \end{bmatrix}. $ $ 

Ez a két qubit állapot, amely nem írható egyetlen qubit-állapotú tenser-termékként, "kusza állapotnak" nevezzük. azt mondják, hogy a két qubits [*összekeverve*](https://en.wikipedia.org/wiki/Quantum_entanglement)van.  Lazán szólva, mivel a Quantum State nem lehet úgy gondolni, mint egy qubit-állapotú kétféle termék, az állam által birtokolt információk nem korlátozódnak egyetlen qubits sem.  Ehelyett a rendszer nem helyileg tárolja az adatokat a két állapot közötti összefüggésekben.  Ez a nem területi információ a Quantum Computing egyik fő megkülönböztető funkciója a klasszikus számítástechnika terén, és számos kvantum-protokoll esetében elengedhetetlen, beleértve a [kvantum](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/teleportation) -és a [kvantum-hibajavítást](xref:microsoft.quantum.libraries.error-correction)is.

## <a name="measuring-two-qubit-states"></a>Két Qubit állapot mérése ##
A két qubit állapot mérése nagyon hasonlít az egyszeres qubit mérésekhez. Az állapot mérése

$ $ \begin{bmatrix} \ alpha_{00} \\\\ \ alpha_{01} \\\\ \ alpha_{10} \\\\ \ alpha_{11} \end{bmatrix} $ $

$0 $ értékű, valószínűséggel $ | \ alpha_{00}| ^ $2, $1 $ with valószínűség $ | \ alpha_{01}| ^ $2, $10 $ with valószínűség $ | \ alpha_{10}| ^ $2 és $11 $ with valószínűség $ | \ alpha_{11}| ^ $2. A (z) $ \ alpha_{00}, \ alpha_{01}, \ alpha_{10}, $ és $ \ alpha_{11}$ változók szándékosan lettek elnevezve ahhoz, hogy ez a kapcsolódás egyértelmű legyen. Ha a mérés után az eredmény $0 $, akkor a két qubit rendszer kvantum állapota összeomlott, és most már

$ $0 \equiv \begin{bmatrix} 1 \\\\ 0 \\\\ 0 \\\\ 0 \end{bmatrix}.
$$

Az is lehetséges, hogy csak egy qubit kell mérni egy qubit kvantum-állapotból. Azokban az esetekben, amikor csak az egyik qubits méri, a mérés hatása finoman eltérő, mert a teljes állapot nem a számítási alapú állapotba van csukva, hanem csak egy alrendszerre van összecsukva.  Más szóval, ebben az esetben, ha csak egy qubit kell mérnie, csak az alrendszerek egyikét csukja össze, de nem mindegyiket.  

Ennek megtekintéséhez érdemes megfontolni a következő állapot első qubit mérését, amely a Hadamard-transzformáció $H $ két qubits való alkalmazásával jön létre, kezdetben a "0" állapotra van állítva: $ $ H ^ {\otimes 2} \left (\begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix}1 \\\\ 0 \end{bmatrix} \right) = \frac{1}{2}\begin{bmatrix}1 & 1 & 1 & 1 \\\\ 1 &-1 & 1 &-1 \\\\ 1 & 1 \ 1 &-1 & \\1 \\-1 &-1 & 1 \ End {bmatrix} \begin{bmatrix}1\\\\ 0\\\\ 0\\\\ 0 \ Befejezés {bmatrix} = \frac{1}{2}\begin{bmatrix}1\\\\ 1\\\\ 1\\\\ 1 \ End {bmatrix} \mapsto \begin{Cases}\text{outcome} = 0 & \frac{1}{\sqrt{2}} \begin{bmatrix}1\\\\ 1\\\\ 0\\\\ 0 \end{bmatrix}\\\\ \text{outcome} = 1 & \frac{1}{\sqrt{2}} \begin{bmatrix}0\\\\ 0\\\\ 1\\\\ 1 \end{bmatrix}\\\\ \end{Cases}.
$ $ Mindkét eredmény 50%-os valószínűséggel rendelkezik.  Az eredmény a 50%-os valószínűsége annak, hogy mindkét eszköz esetében a kezdeti kvantum-állapot vektora invariáns a $0 $ és $1 $ értékkel az első qubit.

Az első vagy második qubit mérésére szolgáló matematikai szabály egyszerű.  Ha hagyjuk, hogy $e _k $ legyen a $k ^ {\rm th} $ számítási alap vektor, és hagyja, $S $ legyen az összes $e _k $ érték, hogy a szóban forgó qubit $1 $ értéket vesz igénybe $k $ érték esetén.  Ha például érdekli az első qubit mérése, akkor $S $ $e _1 \ EQUIV $10 és $e _3 \ EQUIV $11.  Hasonlóképpen, ha érdeklik a második qubit $S $ $e _2 \ EQUIV $1 és $e _3 \equiv $11.  Ezt követően a kiválasztott qubit $1 $ értékre való mérésének valószínűsége az állapot Vector $ \psi $

$ $ P (\text{outcome} = 1) = \ sum_ {e_k \text{a set} S} \psi ^ \dagger e_k e_k ^ \dagger \psi.
$$

> [!NOTE]
> Ebben a dokumentumban a kis endian formátumot használjuk a számítási alap címkézéséhez. Kis endian formátumban a legkevésbé jelentős bitek jönnek először. Például a kis endian formátumú négy számot a BITS 001 karakterlánca jelöli.

Mivel az egyes qubit-mérések csak $0 $ vagy $1 $ értéket adhatnak meg, a $0 $ mérés valószínűsége egyszerűen $1-P (\text{outcome} = 1) $.  Ezért csak explicit módon adunk meg egy képletet a $1 $ mérés valószínűségére.

Az a művelet, amely szerint egy ilyen mérték az adott állapotban van, matematikailag lehet kifejezni

$ $ \psi \mapsto \frac{\ sum_ {e_k \text{a set} S} e_k e_k ^ \dagger \psi}{\sqrt{P (\text{outcome} = 1)}}.
$$

Az óvatos olvasónak nem kell aggódnia, hogy mi történik, ha a mérték valószínűsége nulla.  Habár az eredő állapot technikailag nincs meghatározva ebben az esetben, soha nem kell aggódnia az ilyen eshetőségre, mert a valószínűség nulla!


Ha a \psi $ értéket a fent megadott egységes állapotú vektorba vesszük, és érdeklik az első qubit mérése, akkor 

$ $ P (\text{Measurement az első qubit} = 1) = (\psi ^ \dagger e_1) (e_1 ^ \dagger \psi) + (\psi ^ \dagger e_3) (e_3 ^ \dagger \psi) = | e_1 ^ \dagger \psi | ^ 2 + | e_3 ^ \dagger \psi | ^ 2.
$$

Vegye figyelembe, hogy ez csak azon két valószínűség összege, amelyek várhatóan a $10 $ és a $11 $ eredmény méréséhez szükségesek voltak a qubits.
A példánkban ez a következőt értékeli:

$ $ \frac{1}{4}\left | \begin{bmatrix}0 & 0 & 1 & 0 \ Befejezés {bmatrix} \ BEGIN {bmatrix} 1\\\\ 1\\\\ 1\\\\ 1 \ End {bmatrix} \right | ^ 2 + \frac{1}{4}\left | \begin{bmatrix}0 & 0 & 0 & 1 \ Befejezés {bmatrix} \ BEGIN {bmatrix} 1\\\\ 1\\\\ 1\\\\ 1 \ End {bmatrix} \right | ^ 2 = \frac{1}{2}.
$$

amely tökéletesen illeszkedik a mi intuíciónk számára, hogy a valószínűség legyen.  Ehhez hasonlóan az állapot is írható

$ $ \frac{\frac{e_1}{2}+ \frac{e_3}{2}} {\sqrt{\frac{1}{2}}} = \frac{1}{\sqrt{2}} \begin{bmatrix} 0\\\\ 0\\\\ 1\\\\ 1 \ End {bmatrix} $ $

ismét az intuíciónk alapján.

## <a name="two-qubit-operations"></a>Két Qubit művelet
Ahogy az egyetlen qubit esetében is, az egységes átalakítás a qubits-on érvényes művelet. Általánosságban elmondható, hogy a $n $ qubits egy egységes átalakítása egy mátrix $U $2 ^ n \times 2 ^ n $ (azaz 2 ^ n $ méretű vektorokra van kialakítva), például $U ^{-1} = U ^ \dagger $.
Például a CNEM (vezérelt-NOT) Gate egy gyakran használt két qubit-kapu, amelyet a következő egységes mátrix képvisel:

$ $ \operatorname{CNOT} = \begin{bmatrix} 1 \ 0 \ 0 \ 0 \\\\ 0 \ 1 \ 0 \ 0 \\\\ 0 \ 0 \ 0 \ 1 \\\\ 0 \ 0 \ 1 \ 0 \end{bmatrix} $ $

Két qubit kapunk is alkotható egyetlen qubit-kapuk mindkét qubits való alkalmazásával. Ha például a kapukat alkalmazzuk 

$ $ \begin{bmatrix} a \ b\\\\ c \ d \end{bmatrix} $ $

és

$ $ \begin{bmatrix} e \ f\\\\ g \ h \end{bmatrix} $ $

az első és a második qubits ez egyenértékű a kétlépcsős qubit által nyújtott, a kétféle, a kétszintű termékkel való alkalmazásával: $ $ \begin{bmatrix} a \ b\\\\ c \ d \end{bmatrix} \otimes \begin{bmatrix} e \ f\\\\ g \ h \end{bmatrix} = \begin{bmatrix} AE \ AF \ lehet \ BF \\\\ AG \ ah \ BG \ BH \\\\ CE \ CF \ de \ DF \\\\ CG \ CH \ DG \ DH \end{bmatrix}. $ $, így két qubit kaput lehet kiváltani, ha néhány ismert qubit-kaput használ a tenser termékben. Néhány példa két qubit-kapura: $H \otimes H $, $X \otimes \boldone $, és $X \otimes Z $.

Vegye figyelembe, hogy míg a két qubit-kapu két qubit-kaput határoz meg a tízes termékével, a Converse nem igaz. Nem mind a két qubit kapu írható, mint az qubit-kapuk kétszintű szorzata.  Az ilyen kapukat *összekeverő* kapunak nevezzük. Egy összekeverő kapu például a CNEM kapu.

A vezérelt nem kapu mögötti intuíció tetszőleges kapuk általánosítható.  Egy vezérelt kapu általában egy olyan kapu, amely identitásként viselkedik (azaz nincs művelet), kivéve, ha egy adott qubit $1 $.  Ebben az esetben a $x $ címkével ellátott qubit-t, a $ \Lambda\_x (U) $ értéket jelöljük.  Példa: $ \ Lambda_0 (U) e\_{1}\otimes {\psi} = e\_{1}\otimes U {\psi} $ és $ \Lambda\_0 (U) e\_{0}\otimes {\psi} = e\_{0}\otimes{\psi} $, ahol $e\_$0 és $e\_$1 a számítási alap vektorok egyetlen qubit, amely megfelel a $0 $ és a $1 $ értéknek.  Tegyük fel például, hogy a következő felügyelt $Z $ Gate-t fogjuk kifejezni, mint $ $ \Lambda\_0 (Z) = \begin{bmatrix}1 & 0 & 0 & 0\\\\0 & 1 & 0 & 0\\\\0 & 0 & 1 & 0\\\\0 & 0 & 0 &-1 \end{bmatrix} = (\boldone\otimes H) \operatorname{CNOT} (\boldone\otimes H).
$$

Az ellenőrzött unitaries hatékony módon történő létrehozása nagy kihívást jelent.  Ennek a legegyszerűbb módja, ha az alapvető kapuk ellenőrzött verzióit tartalmazó adatbázist hoz létre, és az eredeti egységes művelet minden alapvető kapuját lecseréli az ellenőrzése alatt álló megfelelő elemre.  Ez gyakran meglehetősen pazarló és okos betekintést nyújt gyakran arra, hogy csak néhány, ellenőrzött verzióval rendelkező kaput cseréljen le ugyanezen hatás eléréséhez.  Ebben az esetben a keretrendszerünk lehetővé teszi, hogy a "naiv" vezérlési módszert végezze el, vagy engedélyezzük a felhasználó számára, hogy meghatározza az egységes felügyelt változatát, ha az optimalizált, kézzel hangolt verzió ismert.

A Gates a klasszikus információk használatával is szabályozható.  Egy klasszikusan vezérelt, nem kapus, például csak egy egyszerű, nem Gate, de csak akkor alkalmazza, ha egy klasszikus bit $1 $, és nem egy kvantum-bit.  Ebben az értelemben egy klasszikusan vezérelt kapu lehet úgy gondolni, mint egy if utasítás a Quantum Code-ban, amelyben a kapu csak a kód egy ágában lesz alkalmazva.


Ahogy az egyetlen qubit esetében is, a két qubit-készlet univerzális, ha bármely $4 \ alkalommal $4 egységes mátrixot a kapuk szorzata tetszőleges pontossággal közelítheti meg.
Egy univerzális Gate-készlet például a Hadamard kapu, a T-kapu és a CNEM kapu. Ezeknek a kapuknak a termékeinek használatával megközelítheti az egységes mátrixot két qubits.

## <a name="many-qubit-systems"></a>Számos Qubit rendszer
Pontosan ugyanazokat a mintákat követjük, mint a két qubit esetében, így több qubit kvantum-állapotot építhet ki kisebb rendszerekből.  Az ilyen állapotok létrehozásához a kisebb állapotú tenser-termékek kiépítését kell megalkotni.  Tegyük fel például, hogy a $1011001 $ bites karakterláncot egy kvantum-számítógépen kódolja.  Ezt a következő módon lehet kódolni

$ $1011001 \equiv \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}.
$$

A Quantum Gates pontosan ugyanúgy működnek.  Ha például a $X $ Gate-t az első qubit szeretné alkalmazni, majd a második és harmadik qubits közötti CNEM hajt végre, akkor ezt a transzformációt is kifejezzük

\begin{align} & (X \otimes \operatorname{CNOT}_{12}\otimes \boldone\otimes \boldone \otimes \boldone \otimes \boldone) \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\\\\ & \qquad\qquad\equiv 0011001.
\end{align}

Számos qubit-rendszerben gyakran szükség van olyan qubits lefoglalására és lefoglalására, amelyek ideiglenes memóriát szolgálnak a kvantum-számítógép számára.  Az ilyen qubit neve Ancilla.  Alapértelmezés szerint feltételezzük, hogy a qubit állapota $e _0 $-ra van inicializálva a foglaláskor.  Azt is feltételezzük, hogy ismét visszaadja a rendszer a _0 $ értéket a lefoglalás előtt $e.  Ez a feltételezés azért fontos, mert ha egy Ancilla-qubit egy másik qubit-regisztrációval válik elérhetővé, ha az kiosztása megszűnik, akkor a lefoglalási folyamat kárt okoz a Ancilla.  Ezért mindig feltételezzük, hogy az ilyen qubits a kiadás előtt visszaállnak a kezdeti állapotukba.

Végezetül, habár új kapuk hozzáadására van szükség a kapunk számára ahhoz, hogy az univerzális kvantum-számítástechnika két qubit kvantum-számítógép esetében elérhető legyen, nem kell új kapukat bevezetni a multi-qubit esetben.  A Gates $H $, $T $ és a CNEM olyan univerzális kaput alkotnak, amely sok qubits van beállítva, mert az általános egységes átalakítás két qubit-elforgatási sorozatra osztható.  Ezután kihasználhatjuk a kétqubites esethez kifejlesztett elméletet, és itt újra fel kell használni, ha sok qubits van.

Míg az eddig használt lineáris algebrai-jelölést természetesen a qubit állapotok leírására is felhasználjuk, egyre nehezebb lesz az állapotok méretének növelésével.  Az eredményül kapott, 7 bites karakterlánchoz tartozó oszlop-vektor, például $128 $ dimenziós, ami a korábban leírt jelölést használja.  Ebből kifolyólag a kvantum-számítástechnika általános jelölését mutatjuk be, amely lehetővé teszi számunkra, hogy ezeket a nagy dimenziós vektorokat tömör módon ismertesse.
