---
title: a qubit a kvantum-számítástechnikai leírásban: Ismerje meg a qubits, a Quantum Computing információinak alapvető egységét.
Szerző: QuantumWriter UID: Microsoft. Quantum. Concepts. qubit MS. Author: nawiebe@microsoft.com MS. Date: 12/11/2017 MS. topic: cikk No-Loc:
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
# <a name="the-qubit"></a>A Qubit

Akárcsak a BITS a klasszikus számítástechnikai információk alapvető információi, a [*qubits*](https://en.wikipedia.org/wiki/Qubit) (Quantum BITS) a kvantum-számítástechnika alapvető információi.  A levelezés megismeréséhez nézzük meg a legegyszerűbb példát: egyetlen qubit.

## <a name="representing-a-qubit"></a>Qubit jelölő

Egy kis-vagy bináris számjegy esetén $ 0 vagy 1 érték is lehet $ $ $ , a qubit értéke lehet ezek egyike, vagy egy $ 0 és 1 kvantum-pozíció $ $ $ .

Egyetlen qubit állapotát az egység normájának kétdimenziós oszlopos vektora is ismertetheti, azaz a bejegyzéseinek nagyságrendjét 1 értékre kell állítani $ $ . Ez a "Quantum State Vector" nevű vektor tartalmazza az összes olyan információt, amely az qubit kvantum-rendszer leírásához szükséges, ugyanúgy, mint egyetlen bit a bináris változók állapotának leírásához szükséges összes információt tartalmazza.

Az 1. normával rendelkező, valós vagy összetett számok két dimenziós oszlopai a $ $ qubit által tárolt lehetséges kvantum-állapotot jelentik. Így $ \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $ qubit-állapotot képvisel $ \alpha $ , ha $ \beta $ a és a $ | \alpha | ^ 2 + | \beta | ^ 2 = 1 $ értékkel rendelkező összetett számok.   Néhány példa a qubits jelölő érvényes kvantum-állapotú vektorokra

$$\begin{bmatrix}1 \\\\ 0 \end{bmatrix} , \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} , \begin{bmatrix} \frac { 1 } { \sqrt { 2 } } \\\\ \frac { 1 } { \sqrt { 2 } } \end{bmatrix} , \begin{bmatrix} \frac { 1 } { \sqrt { 2 } } \\\\ \frac { – 1 } { \sqrt { 2 } } \end{bmatrix} , \text { és } \begin{bmatrix} \frac { 1 } { \sqrt { 2 2 } } \\\\ \frac { } { \sqrt { } } \end{bmatrix} .      $$

A kvantum-állapot vektorai $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} $ és $ \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $ speciális szerepkört igényelnek. Ez a két vektor képezi a qubit állapotát leíró vektoros terület alapját. Ez azt jelenti, hogy a kvantum-állapot vektora ezen alapul szolgáló vektorok összegeként írható. Pontosabban, az $ \begin{bmatrix} x \\\\ y vektor írható \end{bmatrix} $ $ x \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} + y \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $ . Habár ezek a vektorok bármilyen forgása tökéletesen érvényes alapként szolgál a qubit számára, úgy döntünk, hogy ezt a jogosultságot a *számítási alap*meghívásával emeljük ki.

Ezt a két kvantum-állapotot a klasszikus bit két állapotának, azaz $ 0 és 1 értéknek kell megfelelnie $ $ $ . A standard konvenció a következő választás

$$0 \equiv \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} , \qquad 1 \equiv \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} ,$$

Habár a szemközti választási lehetőség is megfelelő lehet. Így a lehetséges qubit kvantum-állapotú vektorok végtelen száma közül csak kettő felel meg a klasszikus bitek állapotának. az összes többi kvantum-állapot nem.

## <a name="measuring-a-qubit"></a>Qubit mérése

Most, hogy már tudjuk, hogyan jelentheti a qubit, megtudhatjuk, hogy mit jelentenek ezek az államok a [*mérés*](https://en.wikipedia.org/wiki/Measurement_in_quantum_mechanics)koncepciójának megvitatása során. A mérések a "looking" kifejezésnek a qubit, amely azonnal Összecsukja a kvantum-állapotot a két klasszikus állapot közül $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} $ vagy $ \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $ . Ha a Quantum State Vector által megadott qubit $ \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $ mérik, akkor a 0 értéket kapjuk meg a " $ $ ^ 2" valószínűséggel, $ | \alpha | $ az 1. eredményt pedig a " $ $ $ | \beta | ^ 2 $ " valószínűséggel.   A $ 0. eredménynél $ a qubit új állapota $ \begin{bmatrix} 1 \\\\ 0; az \end{bmatrix} $ eredmény $ 1. értéke $ $ \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $ . Vegye figyelembe, hogy ezek a valószínűségek legfeljebb 1 értékkel vannak elfoglalva $ $ a következő normalizálás feltétele miatt: $ | \alpha | ^ 2 + | \beta | ^ 2 = 1 $ .

A mérés tulajdonságai azt is jelenti, hogy a kvantum-állapot vektorának általános aláírása lényegtelen. A vektor megtagadásának értéke a $ \alpha \right nyíl \alpha $ és a $ \beta \right nyíl \beta $ . Mivel a 0 és az 1 mérési valószínűsége a $ $ $ $ feltételek méretétől függ, az ilyen jelek beillesztése nem változtatja meg a valószínűségeket. Az ilyen fázisokat általában [ `` *globális fázisoknak*](https://en.wikipedia.org/wiki/Phase_factor) nevezik, és általánosabban az $ e ^ nem csak a { \phi } $ $ \pm 1 lehet $ .

A mérés utolsó fontos tulajdonsága, hogy nem szükségszerűen károsítja az összes kvantum-állapotú vektort. Ha az 1 0 állapotú qubit kezdjük, $ \begin{bmatrix} \\\\ \end{bmatrix} $ amely a klasszikus állapotnak felel meg $ $ , akkor ez az állapot mindig a 0 eredmény lesz, $ $ és változatlanul hagyja a kvantum-állapotot. Ebben az értelemben, ha csak klasszikus bitek vannak (azaz $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} $ vagy $ \begin{bmatrix} 0 \\\\ 1 qubits), \end{bmatrix} $ akkor a mérés nem károsítja a rendszerét. Ez azt jelenti, hogy a klasszikus adatmennyiséget replikálhatja, és a kvantum-számítógépeken ugyanúgy kezelheti azt, mint egy klasszikus számítógépen. Ugyanakkor az információk mindkét állapotban való tárolása egyszerre történik, ami túlmutat a kvantum-számítástechnika a klasszikusan lehetségesnél, és tovább megfosztja a kvantum-számítógépeket a Quantum-adatok válogatás nélküli másolásának lehetőségével, lásd még [a nem klónozási tétel](https://en.wikipedia.org/wiki/No-cloning_theorem).

## <a name="visualizing-qubits-and-transformations-using-the-bloch-sphere"></a>Qubits és átalakítások megjelenítése a Bloch szférával

$ $ A qubits a [*Bloch szféra*](https://en.wikipedia.org/wiki/Bloch_sphere) képviseletének használatával 3 D képen is megjelenhet.  A Bloch szférában egy qubit kvantum-állapot (amely egy kétdimenziós, összetett vektor), amely háromdimenziós, valós értékű vektor.  Ez azért fontos, mert lehetővé teszi, hogy megjelenítse az qubit állapotokat, és ezáltal a qubit állapotok megismerése szempontjából felbecsülhetetlen értékűek legyenek.  A Bloch gömb a következőképpen látható:

<!--- ![](.\media\bloch.svg) { szélessége = 50%} --->
![Bloch gömb](~/media/concepts_bloch.png)

Az ábrán látható nyilak azt mutatják be, hogy a kvantum-állapot vektora hogyan mutat, és a nyíl minden átalakítása a kardinális tengelyek egyikére mutat.
Miközben a kvantum-számítási folyamatra gondol, mivel a Forgások sorozatából egy hatékony intuíció van, nagy kihívást jelent az algoritmusok megtervezése és leírása. Q#a probléma megoldásához adjon meg egy nyelvet az ilyen elforgatások leírásához.

## <a name="single-qubit-operations"></a>Qubit műveletek

A kvantum-számítógépek a kvantum-kapuk univerzális készletének használatával dolgozzák fel az adatfeldolgozást, amely a kvantum-állapot vektorának bármilyen forgását Emulálhatja.
Ez az egyetemességi koncepció hasonlít a hagyományos (azaz klasszikus) számítástechnikai koncepcióhoz, ahol a kapuk univerzálisnak tekintendők, ha a bemeneti bitek minden átalakítása véges hosszúságú áramkör használatával végezhető el.
A kvantum-számítástechnika esetében a qubit elvégezhető érvényes átalakítások egységes átalakítások és mérések.
A *adjoint művelet* vagy az összetett konjugátum átültetése rendkívül fontos a Quantum Computing számára, mivel ez szükséges a kvantum-átalakítások megfordításához.
Q#Ez azt mutatja be, hogy a metódusok automatikusan lefordítják a Gate-sorrendeket a adjoint, így sok esetben menti a programozót a adjoints. Alább látható egy példa:

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Adj { // Auto-generate the adjoint of the operation
    H(qubit);
}
```

Bár ez egy triviális példa (az < xref: Microsoft. Quantum. belső. h > művelet önadjoint), láthatja, hogy ez a bonyolultabb qubit-műveletek során felbecsülhetetlen értékű lesz.
További információ: [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).

A klasszikus számítógépeken csak négy függvény képezhető le egy kicsit. Ezzel szemben a kvantum-számítógépek egyetlen qubit végtelen számú egységes átalakítás létezik. Ezért a " [*Gates*](https://en.wikipedia.org/wiki/Quantum_logic_gate)" nevű egyszerű kvantum-műveletek egyetlen véges halmaza sem tudja pontosan replikálni a kvantum-számítástechnikai szolgáltatásban engedélyezett, egységes átalakítások végtelen készletét. Ez azt jelenti, hogy a klasszikus számítástechnikai rendszertől eltérően a kvantum-számítógép nem tudja megvalósítani az összes lehetséges kvantum-programot, amely pontosan véges számú kaput használ. Így a kvantum-számítógépek nem lehetnek univerzálisak a klasszikus számítógépek azonos értelemben. Ennek eredményeképpen, amikor azt mondjuk, hogy a kapuk halmaza *univerzális* a Quantum Computing esetében, valójában némileg gyengébb, mint a klasszikus számítástechnika.
Az egyetemesség esetében követelmény, hogy a kvantum-számítógép csak a véges hosszúságú Gate-sorozatot használva *közelítse* meg az összes egységes mátrixot egy véges hibán belül.
Más szóval, a Gates egy univerzális Gate-készlet, ha bármely egységes átalakítás a készletből származó Gates-termékként is írható. Megköveteljük, hogy az előírt hibákhoz kötve legyenek a Gates $ G_ { 1 } , G_ { 2 } , a \ldots, a G_N a $ Gate készletből, amely

$$
G_N G_ { N-1 } \cdots G_2 G_1 \approx U.$$

Vegye figyelembe, hogy mivel a mátrixok szorzási konvenciója, hogy a jobbról az első kapu műveletét az ebben a sorozatban, $ G_N $ , valójában az utolsó lett alkalmazva a kvantum-állapot vektorára. Többek között úgy mondhatjuk, hogy egy ilyen Gate-készlet univerzális, ha minden hibatűrési $ \epsilon > 0 $ létezik $ G_1, \ldots, G_N $ úgy, hogy a $ G_N \ldots G_1 és az U közötti távolság a $ $ $ legtöbb $ \epsilon $ . Ideális esetben a $ $ \epsilon ezen távolságának eléréséhez szükséges N értéknek a $ $ poli-logaritmikusan $ 1/\ epszilon kell lennie $ .

Mit jelent ez az univerzális Gate-készlet a gyakorlatban?  Az egyszeres qubit kapuk legegyszerűbb univerzális kapuja csak két kapuból áll: a Hadamard Gate $ H $ és az úgynevezett $ T $ -Gate (más néven $ \ PI/8 $ Gate):

$$
H = \frac { 1 } { \sqrt { 2 } } \begin{bmatrix} 1 & 1 \\\\ 1 & -1 \end{bmatrix} , \qquad T = \begin{bmatrix} 1 & 0 \\\\ 0 & e ^ { i \ PI/4 } \end{bmatrix} .
$$

A kvantum-hibák kijavításával kapcsolatos gyakorlati okokból azonban kényelmesebb lehet a nagyobb kapuk készletének megfontolása, vagyis az, hogy a H és a T használatával hozható létre $ $ $ $ . A Quantum Gates két kategóriába sorolhatók: Clifford Gates és a $ T $ -Gate.
Ez az albontás azért hasznos, mert számos kvantum-hibajavítási sémában az úgynevezett Clifford-kapuk könnyen megvalósítható, ezért nagyon kevés erőforrásra van szükségük a működés és a qubits számára a hibatűrő megoldás megvalósításához, míg a nem Clifford-kapuk rendkívül költségesek a hibatűrés megkövetelése esetén. A- [ben Q# alapértelmezés ](xref:microsoft.quantum.libraries.standard.prelude)szerint a qubit Clifford Gates standard készlete tartalmazza a következőket:

$$
H = \frac { 1 } { \sqrt { 2 } } \begin{bmatrix} 1 & 1 \\\\ 1 & -1 \end{bmatrix} , \qquad S = \begin{bmatrix} 1 & 0 \\\\ 0 & i \end{bmatrix} = T ^ 2, \qquad X = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} = HT ^ 4h,$$

$$
Y = \begin{bmatrix} 0 & – i \\\\ & 0 \end{bmatrix} = t ^ 2HT ^ 4 HT ^ 6, \qquad Z = \begin{bmatrix} 1 & 0 \\\\ 0 & – 1 \end{bmatrix} = T ^ 4.
$$

Itt az $ X $ , $ Y $ és Z műveletek $ $ különösen gyakran használatosak, és Pauli- [*operátorok*](https://en.wikipedia.org/wiki/Pauli_matrices) nevezték el a Wolfgang Paulit követően.
A nem Clifford-kapuval (a $ T $ -Gate) együtt ezek a műveletek összeállíthatók egyetlen qubit egységes átalakításának megközelítve.

További információ ezekről a műveletekről, valamint a Bloch-szférában végzett képviseletekről és Q# megvalósításokról: [belső műveletek és függvények](xref:microsoft.quantum.libraries.standard.prelude#intrinsic-operations-and-functions).

Példa arra, hogy az egységes átalakítások hogyan használhatók ezekből a primitívekről, a fenti Bloch szférában látható három átalakítás az 1 0 $ \begin{bmatrix} \\\\ \end{bmatrix} \mapsto HZH \begin{bmatrix} 1 0 \\\\ \end{bmatrix} = \begin{bmatrix} \\\\ 1 \end{bmatrix} $ .

Míg az előző a legnépszerűbb primitív kapuk, amelyek a verem logikai szintjén lévő műveletek leírására szolgálnak (gondoljunk a logikai szintre a kvantum-algoritmus szintjére), gyakran érdemes megfontolni kevesebb alapvető műveletet az algoritmus szintjén, például a függvények leírási szintjéhez közelebbi műveleteket. Szerencsére a Q# magasabb szintű unitaries megvalósításához is vannak olyan metódusok, amelyek lehetővé teszik a magas szintű algoritmusok megvalósítását anélkül, hogy explicit módon le kellene bontani a Clifford és a $ T $ -Gates közötti összes információt.

A legegyszerűbb ilyen primitív az egyetlen qubit. A rendszer általában három qubit-rotációt vesz figyelembe: $ R_x $ , $ R_y $ és $ R_z $ . A rotációs $ R_x (\theta) működésének megjelenítéséhez $ Képzelje el például, hogy a Bloch gömb x tengelyének irányába mutat a jobb oldali hüvelykujját, $ és a vektort a kézzel, a $ $ \ THÉTA/2 radián szögével forgatja $ . Ez a 2. zavaros tényező abból ered, hogy a (z $ $ ) a $ Bloch-szférán kívüli merőleges vektorok 180 ^ \circ $ , de egyelőre a $ 90 ^ \circ $ fok egymástól mérten. A megfelelő egységes mátrixok a következők:

\begin{igazítás* } 
 & R_z (\theta) = e ^ { -i\theta z/2 } = \begin{bmatrix} e ^ { -i \ THÉTA/2 } & 0 \\\\ 0 & e ^ { i \ THÉTA/2 } \end{bmatrix} , \\\\ 
 & R_x (\theta) = e ^ { -i\theta x/2 } = HR_z (\theta) H = \begin{bmatrix} \cos (\ THÉTA/2) & – i\sin (\ THÉTA/2) – \\\\ i\sin (\ THÉTA/2) & \cos (\ THÉTA/2) \end{bmatrix} , \\\\ 
 & R_y (\theta) = e ^ { -i\theta y/2 } = SHR_z (\theta) HS ^ \dagger = \begin{bmatrix} \cos (\ THÉTA/2) & -\sin (\ THÉTA/2) \\\\ \sin (\ THÉTA/2) & \cos (\ THÉTA/2) \end{bmatrix} . \end { igazítás*}

Ugyanúgy, mint három rotációt kombinálva, hogy tetszőleges rotációt végezzen három dimenzióban, láthatja a Bloch szférából, hogy bármely egységes mátrix három rotációs folyamatként is írható. Pontosabban, minden olyan egységes mátrixhoz, ahol $ $ létezik,,, például az $ \alpha \beta \gamma \delta $ $ u = e ^ { i \alpha } R_x () \beta R_z ( \gamma ) R_x ( \delta ) $ . Így $ a R_z (\theta $ ) $ és $ a H egy univerzális Gate-készletet is alkot, bár nem különálló készlet, mert a $ \theta $ bármilyen értéket igénybe vehet. Emiatt, és a kvantum-szimuláció alkalmazásai miatt az ilyen folyamatos kapuk elengedhetetlenek a kvantum-számításokhoz, különösen a Quantum algoritmus tervezési szintjén. A hibatűrő hardverek megvalósításához végső soron különálló kapuk lesznek lefordítva, amelyek szorosan megközelítik ezeket a rotációs folyamatokat.
