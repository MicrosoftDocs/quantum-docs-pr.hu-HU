---
title: több qubits leírása: megtudhatja, hogyan hajthat végre műveleteket két vagy több qubits.
Szerző: bradben UID: Microsoft. Quantum. Concepts. Multiple-qubits MS. Author: v-benbra MS. Date: 12/11/2017 MS. topic: konceptuális No-Loc:
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

# <a name="multiple-qubits"></a>Több qubits

Míg az qubit-kapuk rendelkeznek olyan intuitív funkciókkal, mint például az, hogy egy adott időben egynél több állapotban legyenek, ha a kvantum-számítógépeken már volt egy qubit kapu, akkor egy számítási teljesítménnyel rendelkező eszközt is kihasználunk, amely még egy, a klasszikus szuperszámítógép által is megjelenő számításba kerülne.
A kvantum-számítástechnika valódi ereje csak akkor válik nyilvánvalóvá, ha növeljük a qubits számát.
Ez a teljesítmény részben fordul elő, mivel a kvantum állapotú vektorok vektoros területének dimenziója exponenciálisan növekszik a qubits számával.
Ez azt jelenti, hogy habár egy qubit-típust is használhat, a 50-qubit kvantum-számítás szimulálása vélhetően leküldi a meglévő szuperszámítógépek korlátait.
A számítások méretének növelése egy további qubit *megduplázza* az állapot tárolásához szükséges memóriát, és nagyjából *megduplázza* a számítási időt.
A számítási teljesítmény gyors megkettőzése miatt a viszonylag kis mennyiségű qubits rendelkező kvantum-számítógép a mai, holnapi és újabb számítási feladatokhoz képest messze felülmúlja a leghatalmasabb számítógépeket.

Miért van exponenciálisan növekedni a Quantum State vectors?  Ennek a szakasznak a célja, hogy áttekintse azokat a szabályokat, amelyek segítségével qubit állapotokat építhet ki az qubit állapotokból, valamint megbeszélheti a kapunk azon műveleteit, amelyekkel egy univerzális, sok qubit kvantum-számítógép alkotható.
Ezek az eszközök feltétlenül szükségesek ahhoz, hogy megértsék a kódban gyakran használt kapukat, Q# valamint azt is, hogy a kvantum-effektusok, például a felakadás vagy az interferencia, hogy a kvantummechanika nagyobb teljesítményű legyen, mint a klasszikus számítástechnika.

## <a name="representing-two-qubits"></a>Két qubits képvisel
Az egy-és qubit állapot közötti fő különbség az, hogy a két qubit állapot nem két dimenziós, hanem négy dimenziós.
Ennek az az oka, hogy a kétqubitos állapotok számítási alapjait az egy qubit-állapotú transzeurópai termékek alkotják.  Például: \begin{align}
00 \equiv \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 1 0 0 \end{bmatrix} & = \begin{bmatrix} \\\\ \\\\ \\\\ 0 \end{bmatrix} , \qquad 01 \equiv \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ 1 0 \end{bmatrix} = \begin{bmatrix} \\\\ 1 \\\\ 0 \\\\ 0 \end{bmatrix} ,\\\\
10 \equiv \begin{bmatrix} 0 \\\\ 1 1 0 0 0 \end{bmatrix} \otimes \begin{bmatrix} \\\\ \end{bmatrix} & = \begin{bmatrix} \\\\ \\\\ 1 \\\\ 0 \end{bmatrix} , \qquad 11 \equiv \begin{bmatrix} 0 1 0 1 0 0 \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ \end{bmatrix} = \begin{bmatrix} \\\\ \\\\ 0 \\\\ 1 \end{bmatrix} .
\end{align}

Könnyen láthatja, hogy az n qubits kvantum-állapota a $ $ 2 ^ n dimenzió egy egységének vektora, amely $ ezt az $ építkezést használja.  A vektor

$$
\begin{bmatrix}\alpha _{ 00 } 01 \\\\ 10 \alpha_ { } \\\\ \alpha _{ 11 } \\\\ \alpha_ { }  \end{bmatrix}
$$

a Quantum állapotot jelöli két qubits, ha $ | \alpha _{ 00 } | ^ | \alpha 2 +_ { 01 } | ^ 2 + | \alpha _{ 10 } | ^ | \alpha 2 +_ { 11 } | ^ 2 = 1 $ . Akárcsak az egyetlen qubits esetében, a több qubits kvantum-állapot vektora a rendszerviselkedés leírásához szükséges összes információt tartalmazza.

Ha két különálló qubits kap, az egyik az államban $ \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $ és egy második qubit az államban $ \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} $ , akkor a megfelelő két qubit állapot    

$$
\begin{bmatrix} \alpha \\\\  \beta \end{bmatrix} \otimes \begin{bmatrix} \gamma \\\\  \delta \end{bmatrix} 
=\begin{bmatrix} \alpha \begin{bmatrix} \gamma \\\\  \delta \end{bmatrix} \\\\ \beta \begin{bmatrix}\gamma \\\\  \delta \end{bmatrix} \end{bmatrix}
= \begin{bmatrix} \alpha\gamma \\\\  \alpha\delta \\\\  \beta\gamma \\\\  \beta\delta \end{bmatrix}, $$

ahol a művelet $ \otimes $ neve a vektorok tenser termékének (vagy Kronecker termékének). Vegye figyelembe, hogy habár a kétqubitos állapotú kétféle qubit esetében mindig megteheti a kétlépcsős adatmennyiséget, nem minden két qubit Quantum-állapot írható be kétféle qubit-állapotú kétszintű termékként.
Például nincsenek állapotok, és a $ \psi = \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $ $ \phi = \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} $ tízes termékük a következő:     

$$\psi\otimes\phi = \begin{bmatrix} 1/ \sqrt { 2 } \\\\ 0 \\\\ 0 \\\\ 1/ \sqrt { 2 } \end{bmatrix} .$$ 

Ez a két qubit állapot, amely nem írható egyetlen qubit-állapotú tenser-termékként, "kusza állapotnak" nevezzük. azt mondják, hogy a két qubits [*összekeverve*](https://en.wikipedia.org/wiki/Quantum_entanglement)van.  Lazán szólva, mivel a Quantum State nem lehet úgy gondolni, mint egy qubit-állapotú kétféle termék, az állam által birtokolt információk nem korlátozódnak egyetlen qubits sem.  Ehelyett a rendszer nem helyileg tárolja az adatokat a két állapot közötti összefüggésekben.  Ez a nem területi információ a Quantum Computing egyik fő megkülönböztető funkciója a klasszikus számítástechnika terén, és számos kvantum-protokoll esetében elengedhetetlen, beleértve a [kvantum](https://github.com/microsoft/Quantum/tree/main/samples/getting-started/teleportation) -és a [kvantum-hibajavítást](xref:microsoft.quantum.libraries.error-correction)is.

## <a name="measuring-two-qubit-states"></a>Two-Qubit állapotok mérése ##
A két qubit állapot mérése nagyon hasonlít az egyszeres qubit mérésekhez. Az állapot mérése

$$
    \begin{bmatrix}
        \alpha_{ 00 } 01 \\\\ \alpha_ { }\\\\ 
        \alpha_{ 10 } 11 \\\\ \alpha_ {}
    \end{bmatrix}
$$

00 ^ 2, $ $ $ | \alpha _{ } | $ $ $ 01 $ valószínűséggel, 01 ^ 2, 10, valószínűség 10 ^ 2 és 11, a 11 ^ 2 valószínűséggel. | \alpha_ { } | $ $ $ $ | \alpha _{ } | $ $ $ $ | \alpha_ { } | $ A $ \alpha _{ 00 } , \alpha_ { 01 } , \alpha _{ 10 } $ és $ 11 változók szándékosan lettek elnevezve, hogy ez a kapcsolódás egyértelmű legyen \alpha_ { } $ . Ha a mérés után az eredmény 00, $ $ akkor a qubit rendszer kvantum állapota összeomlott, és most már

$$
    00 \equiv
    \begin{bmatrix}
        1 \\\\ 
        0 \\\\ 
        0 \\\\ 
        0 \end{bmatrix} .
$$

Az is lehetséges, hogy csak egy qubit kell mérni egy qubit kvantum-állapotból. Azokban az esetekben, amikor csak az egyik qubits méri, a mérés hatása finoman eltérő, mert a teljes állapot nem a számítási alapú állapotba van csukva, hanem csak egy alrendszerre van összecsukva.  Más szóval, ebben az esetben, ha csak egy qubit kell mérnie, csak az alrendszerek egyikét csukja össze, de nem mindegyiket.  

Ennek megtekintéséhez érdemes megfontolni a következő állapot első qubit mérését, amely a Hadamard átalakítási H két qubits való alkalmazásával jön létre, $ $ kezdetben a "0" állapotra: $$
H ^ 2 (1 0 1 0) 1 2 1 1 1 1 1-1-1-1 1-1-1-1-1-1-1 0 0 0 { \otimes } \left \begin{bmatrix} \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ \end{bmatrix} \right = \frac { } { } \begin{bmatrix} & & & \\\\ & & & \\\\ & & & \\\\ & & & \end{bmatrix} \begin{bmatrix} 1 2 1 1 1 1 \\\\ \\\\ \\\\ \end{bmatrix} = \frac { } { } \begin{bmatrix} \\\\ \\\\ \\\\ \end{bmatrix} \mapsto \begin{cases} \text { eredmény } = 0 & \frac { 1 } { \sqrt { 2 } } \begin{bmatrix} 1 \\\\ 1 \\\\ 0 0 \\\\ \end{bmatrix} \\\\ \text { eredmény } = 1 1 & \frac { } { \sqrt { 2 } } \begin{bmatrix} 0 \\\\ 0 1 1 \\\\ \\\\ \end{bmatrix} \\\\ \end{cases} .  
$$
Mindkét eredmény 50%-os valószínűséggel rendelkezik.  Az eredmény a 50%-os valószínűsége annak, hogy mindkét eszköz esetében lehetséges, hogy a kezdeti kvantum-állapot vektora invariáns a $ 0 és az 1 érték között $ $ $ az első qubit.

Az első vagy második qubit mérésére szolgáló matematikai szabály egyszerű.  Ha hagyjuk, hogy $ e_k $ legyen a $ k ^ { \rm th } $ számítási alapja vektor, és hagyja, hogy az $ $ összes e_k, $ $ hogy a kérdéses qubit az 1 értéket adja meg a $ $ k értékeként $ $ .  Ha például az első qubit mérését érdeklik, akkor az $ S $ $ e_1 \equiv 10 $ és $ e_3 \equiv 11 $ közé állna.  Hasonlóképpen, ha a második qubit-k érdeklik $ , $ $ e_2 \equiv 01 $ és $ e_3 \equiv 11 $ .  Ezután a kiválasztott qubit 1 értékre való mérésének valószínűsége az $ $ állapot vektoros $\psi$

$$
P ( \text { } = 1. eredmény) = \sum _ { e_k \text { a set } S } \psi ^ \dagger e_k e_k ^ \dagger \psi .
$$

> [!NOTE]
> Ebben a dokumentumban a kis endian formátumot használjuk a számítási alap címkézéséhez. Kis endian formátumban a legkevésbé jelentős bitek jönnek először. Például a kis endian formátumú négy számot a BITS 001 karakterlánca jelöli.

Mivel minden qubit-mérés csak $ 0 $ vagy 1 értéket eredményezhet $ $ , a 0 mérési valószínűsége $ $ egyszerűen $ 1 – P (1 – P \text { } = ) $ .  Ezért csak explicit módon adunk meg egy képletet az 1. mérési valószínűséghez $ $ .

Az a művelet, amely szerint egy ilyen mérték az adott állapotban van, matematikailag lehet kifejezni

$$
\psi\mapsto \frac{\sum _ { e_k \text { a set } S } e_k e_k ^ \dagger \psi } { \sqrt { P ( \text { } = 1. eredmény) } } .
$$

Az óvatos olvasónak nem kell aggódnia, hogy mi történik, ha a mérték valószínűsége nulla.  Habár az eredő állapot technikailag nincs meghatározva ebben az esetben, soha nem kell aggódnia az ilyen eshetőségre, mert a valószínűség nulla!


Ha $ \psi $ a fent megadott egységes állapotú vektort vesszük figyelembe, és érdeklik az első qubit mérése, akkor 

$$
P ( \text { az első qubit mérése } = 1) = ( \psi ^ \dagger e_1) (e_1 ^ \dagger \psi ) + ( \psi ^ \dagger e_3) (e_3 ^ \dagger \psi ) = | e_1 ^ \dagger \psi | ^ 2 + | e_3 ^ \dagger \psi | ^ 2.
$$

Vegye figyelembe, hogy ez csak azon két valószínűség összege, amelyek várhatóan a $ 10. és a 11. eredmény méréséhez szükségesek $ $ voltak a $ qubits.
A példánkban ez a következőt értékeli:

$$
\frac{1 } { 4 } \left | \begin{bmatrix} 0 & 0 1 0 1 1 1 1 ^ 2 & + 1 4 0 & \end{bmatrix} \begin{bmatrix} \\\\ \\\\ \\\\ \end{bmatrix} \right | \frac { } { } \left | \begin{bmatrix} & & & \end{bmatrix} \begin{bmatrix} \\\\ \\\\ \\\\ \end{bmatrix} \right | = \frac { } { } 0 0 1 1 1 1 1 ^ 2 1 2.
$$

amely tökéletesen illeszkedik a mi intuíciónk számára, hogy a valószínűség legyen.  Ehhez hasonlóan az állapot is írható

$$
\frac{\frac{e_1 } { 2 } + \frac { e_3 } { 2 } } { \sqrt { \frac { 1 } { 2 } } } = \frac { 1 } { \sqrt { 2 } } \begin{bmatrix} 0 \\\\ 0 \\\\ 1 \\\\ 1\end{bmatrix}
$$

ismét az intuíciónk alapján.

## <a name="two-qubit-operations"></a>Two-Qubit műveletek
Ahogy az egyetlen qubit esetében is, az egységes átalakítás a qubits-on érvényes művelet. Általánosságban elmondható, hogy az n qubits egy egységes transzformációja $ $ $ $ $ 2 ^ n \times 2 ^ n méretű mátrix U $ (tehát 2 ^ n méretű vektorok $ esetén működik $ ), például $ u ^ { -1 } = u ^ \dagger $ .
Például a CNEM (vezérelt-NOT) Gate egy gyakran használt két qubit-kapu, amelyet a következő egységes mátrix képvisel:

$$
\operatorname{CNEM } = \begin{bmatrix} 1 \ 0 \ 0 \ 0  \\\\  0 \ 1 \ 0 \ 0 \\\\  0 \ 0 \ 0 \ 1 \\\\  0 \ 0 \ 1 \ 0 \end{bmatrix}
$$

Két qubit kapunk is alkotható egyetlen qubit-kapuk mindkét qubits való alkalmazásával. Ha például a kapukat alkalmazzuk 

$$
\begin{bmatrix}
a \ b \\\\ c \ d \end{bmatrix}
$$

és

$$\begin{bmatrix}
e \ f \\\\ g \ h \end{bmatrix}
$$

az első és a második qubits ez egyenértékű a kétlépcsős qubit által nyújtott, a kétféle, a kétszintű termékkel való alkalmazásával: $$\begin{bmatrix}
a \ b \\\\ c \ d \end{bmatrix}
\otimes 
\begin{bmatrix}
e \ f \\\\ g \ h \end{bmatrix}=
    \begin{bmatrix}
    AK \ AF \ be \ BF \\\\
    AG \ ah \ BG \ BH \\\\
    CE \ CF \ de \ DF \\\\
    CG \ CH \ DG \ DH \end{bmatrix} .$$
Így két qubit kaput lehet kiváltani, ha több ismert qubit kaput használunk. A két qubit kapu például a $ h \otimes h, az $ $ x \otimes \boldone $ és az $ x \otimes Z $ .

Vegye figyelembe, hogy míg a két qubit-kapu két qubit-kaput határoz meg a tízes termékével, a Converse nem igaz. Nem mind a két qubit kapu írható, mint az qubit-kapuk kétszintű szorzata.  Az ilyen kapukat *összekeverő* kapunak nevezzük. Egy összekeverő kapu például a CNEM kapu.

A vezérelt nem kapu mögötti intuíció tetszőleges kapuk általánosítható.  Egy vezérelt kapu általában egy olyan kapu, amely identitásként viselkedik (azaz nincs művelet), kivéve, ha egy adott qubit $ 1 $ .  Ebben az esetben az $ x $ $ \Lambda \_ (U) $ címkével ellátott, qubit jelölésű, ellenőrzött, egységes és szabályozott egységeket jelölünk.  Példaként $ \Lambda _0 (u) e \_ { 1 } \otimes { \psi } = e \_ { 1 } \otimes U { \psi } $ és $ \Lambda \_ 0 (u) e \_ { 0 } \otimes { \psi } = e 0 \_ { } \otimes { \psi } $ , ahol $ az e \_ 0 $ és $ \_ az e 1 $ a számítási alapja a 0 és az 1 értéknek megfelelő egyetlen qubit $ $ $ $ .  Tegyük fel például, hogy a következő felügyelt- $ Z $ kaput fogjuk kifejezni: $$
\Lambda\_0 (Z) 1 0 0 0 0 1 0 0 0 0 1 0 0 0 0 = \begin{bmatrix} & & & \\\\ & & & \\\\ & & & \\\\ & & & -1 \end{bmatrix} = ( \boldone \otimes h) \operatorname { cnem } ( \boldone \otimes h).
$$

Az ellenőrzött unitaries hatékony módon történő létrehozása nagy kihívást jelent.  Ennek a legegyszerűbb módja, ha az alapvető kapuk ellenőrzött verzióit tartalmazó adatbázist hoz létre, és az eredeti egységes művelet minden alapvető kapuját lecseréli az ellenőrzése alatt álló megfelelő elemre.  Ez gyakran meglehetősen pazarló és okos betekintést nyújt gyakran arra, hogy csak néhány, ellenőrzött verzióval rendelkező kaput cseréljen le ugyanezen hatás eléréséhez.  Ebben az esetben a keretrendszerünk lehetővé teszi, hogy a "naiv" vezérlési módszert végezze el, vagy engedélyezzük a felhasználó számára, hogy meghatározza az egységes felügyelt változatát, ha az optimalizált, kézzel hangolt verzió ismert.

A Gates a klasszikus információk használatával is szabályozható.  Egy klasszikusan vezérelt, nem kapus, például csak egy egyszerű, nem Gate, de csak akkor alkalmazza, ha egy klasszikus bit $ 1 $ , és nem egy kvantum-bit.  Ebben az értelemben egy klasszikusan vezérelt kapu lehet úgy gondolni, mint egy if utasítás a Quantum Code-ban, amelyben a kapu csak a kód egy ágában lesz alkalmazva.


Ahogy az egyetlen qubit esetében is, a két qubit is univerzális, ha bármely $ 4 \times 4 $ egységes mátrixot a kapuk szorzata tetszőleges pontossággal közelítheti meg.
Egy univerzális Gate-készlet például a Hadamard kapu, a T-kapu és a CNEM kapu. Ezeknek a kapuknak a termékeinek használatával megközelítheti az egységes mátrixot két qubits.

## <a name="many-qubit-systems"></a>Many-Qubit rendszerek
Pontosan ugyanazokat a mintákat követjük, mint a két qubit esetében, így több qubit kvantum-állapotot építhet ki kisebb rendszerekből.  Az ilyen állapotok létrehozásához a kisebb állapotú tenser-termékek kiépítését kell megalkotni.  Tegyük fel például, hogy a 1011001 bites karakterláncot $ $ egy kvantum-számítógépen kódolja.  Ezt a következő módon lehet kódolni

$$
1011001 \equiv \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 1 \end{bmatrix} \otimes \begin{bmatrix} \\\\ 0 0 \end{bmatrix} \otimes \begin{bmatrix} \\\\ 1 \end{bmatrix} .
$$

A Quantum Gates pontosan ugyanúgy működnek.  Ha például az $ X $ kaput szeretné alkalmazni az első qubit, majd cnem hajt végre a második és a harmadik qubits között, akkor ezt a transzformációt is kifejezzük

\begin{align}
&(X \otimes \operatorname { cnem } _ { 12 } \otimes \boldone \otimes \boldone \otimes \boldone \otimes \boldone ) \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ 0 1 0 0 1\end{bmatrix}\\\\
&\qquad\qquad\equiv 0011001. \end{align}

Számos qubit-rendszerben gyakran szükség van olyan qubits kiosztására és felszabadítására, amelyek ideiglenes memóriát szolgálnak a kvantum-számítógép számára.  Az ilyen qubit neve Ancilla.  Alapértelmezés szerint a rendszer inicializálja a qubit állapotot, hogy $ e_0 a $ foglalás után.  Azt javasoljuk, hogy a felszabadítás előtt ismét visszaadja a $ e_0 $ .  Ez a feltételezés azért fontos, mert ha egy Ancilla-qubit egy másik qubit-regisztrációval válik elérhetővé, amikor felszabadításra kerül, akkor a felszabadítási folyamat károsítja a Ancilla.  Ezért mindig feltételezzük, hogy az ilyen qubits a kiadás előtt visszaállnak a kezdeti állapotukba.

Végezetül, habár új kapuk hozzáadására van szükség a kapunk számára ahhoz, hogy az univerzális kvantum-számítástechnika két qubit kvantum-számítógép esetében elérhető legyen, nem kell új kapukat bevezetni a multi-qubit esetben.  A $ H $ , $ T és cnem kapuk $ egy univerzális kaput alkotnak a sok qubits, mivel az általános egységes átalakítás különböző qubit-elforgatások sorozatára osztható.  Ezután kihasználhatjuk a kétqubites esethez kifejlesztett elméletet, és itt újra fel kell használni, ha sok qubits van.

Míg az eddig használt lineáris algebrai-jelölést természetesen a qubit állapotok leírására is felhasználjuk, egyre nehezebb lesz az állapotok méretének növelésével.  Az eredményül kapott, 7 bites karakterlánchoz tartozó oszlop-vektor, például $ 128 $ dimenziós, amely a korábban leírt jelöléssel fejezi ki azt.  Ebből kifolyólag a kvantum-számítástechnika általános jelölését mutatjuk be, amely lehetővé teszi számunkra, hogy ezeket a nagy dimenziós vektorokat tömör módon ismertesse.
