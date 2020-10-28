---
title: Közreműködő dokumentáció a Microsoft QDK
description: Ismerje meg, Hogyan járulhat hozzá a koncepcionális vagy API-tartalmakhoz a Microsoft Quantum dokumentációs készletében.
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.docs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 2debef858c38b9a8f11264858130ed7cb41543ae
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691793"
---
# <a name="improving-documentation"></a>A dokumentáció továbbfejlesztése

A Quantum Development Kit dokumentációja számos különböző formát vesz igénybe, így az információk könnyen elérhetők a kvantum-fejlesztők számára.

A [dokumentumok kód szerinti](https://www.writethedocs.org/guide/docs-as-code/)alapelveit követve az összes Quantum Development Kit-dokumentáció kódként van formázva, és a git használatával felügyelhető ugyanúgy, mint a Quantum Development Kit felépítéséhez használt forráskód.
A legtöbb esetben a kód hátterének dokumentációja a [Markdown](https://daringfireball.net/projects/markdown/)különböző formáiból tevődik össze, és a parancssorban, az ide-ben és a Source Control használatával könnyen használható, formázatlan szöveges formátumú szöveg kiírására szolgáló nyelv.
Hasonlóképpen fogadjuk el a [MathJax](https://www.mathjax.org/) -függvénytárat, hogy a latex nyelv használatával formázza a matematika használatát a dokumentációban, az alább részletezett módon.


Így a dokumentáció minden formája némileg eltér a részletektől:

- A **koncepcionális dokumentáció** a közzétett cikkekből áll, amelyek a kvantum- https://docs.microsoft.com/quantum számítástechnika alapjait ismertetik a Interchange formats technikai előírásai alapján. Ezek a cikkek a [DocFX-stílusú Markdown (DFM)](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html), a gazdag dokumentációs készletek létrehozásához használt Markdown-változatok.
- Az **API-hivatkozás** az egyes Q# függvényekhez, műveletekhez és felhasználó által definiált típusokhoz tartozó lapok összessége https://docs.microsoft.com/qsharp/api/ . Ezek az oldalak dokumentálják az összes meghívható bemenetet és műveletet, valamint példákat és további információkra mutató hivatkozásokat. Az API-referenciát a rendszer automatikusan Kinyeri a forráskódban lévő kis DFM-dokumentumokból az Q# egyes kiadások részeként.
- Az egyes mintákhoz és Kata-hoz tartozó **readme <!----> . MD** fájlok azt írják le, hogyan használható a minta vagy a Kata, mit takar, és hogyan kapcsolódik a Quantum Development Kit további részeihez. Ezek a fájlok a GitHub-stílusú [Markdown (GFM)](https://github.github.com/gfm/)használatával íródnak, amely egy egyszerűbb alternatíva a DFM, amely a dokumentáció közvetlen csatolásához használható a kódokhoz.

## <a name="contributing-to-the-conceptual-documentation"></a>A fogalmi dokumentációhoz való hozzájárulás

A koncepcionális vagy a README dokumentációjának fejlesztéséhez, majd egy lekéréses kérelemmel kezdődik a [**MicrosoftDocs/Quantum-docs-PR**](https://github.com/MicrosoftDocs/quantum-docs-pr/
), a [**Microsoft/Quantum**](https://github.com/Microsoft/Quantum)vagy a [**Microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas), a megfelelő módon.
Részletesebben ismertetjük a lekéréses kérelmeket, de most van néhány dolog, ami jó szem előtt tartani a dokumentáció tökéletesítése során:

- Az olvasók rendkívül széles körben érkeznek a Quantum Development Kit dokumentációjában. Mindenki a diákoknak, akik szeretnék megtanulni, hogy milyen új és izgalmas, hogy a kihasználatlan szakirányú oktatói képzésben részt vevő szakterületek elolvassák a dokumentációt. A lehetséges mértékig ne Tételezzük fel, hogy az olvasók részéről nem vállalunk széleskörű ismeretet, mivel ezek csak most kezdik el. Ez a leghasznosabb, ha egyértelmű és hozzáférhető leírásokat is biztosít, vagy további információkra mutató hivatkozásokat is biztosíthat más erőforrásokhoz.
- A dokumentációs készletek nem rendelkeznek például könyvekkel vagy dokumentumokkal, így az olvasók a "középső"-ként látszanak. Előfordulhat például, hogy a keresőmotorok nem javasolják az indexet, vagy ha egy barátja olyan hivatkozást kapott, amely a segítségére tett kísérletet. Próbálja ki az olvasót úgy, hogy mindig egyértelmű kontextust biztosít, valamint a hivatkozásokat, ahol szükséges.
- Egyes olvasók az absztrakt és a definíciókat is hasznosnak találják, míg a többi olvasó az adott példákból kikövetkeztetve a legjobban működik. Az általános eset és a konkrét példák egyaránt segítenek abban, hogy az olvasók a lehető legtöbbet hozzanak ki a kvantum-programozásból.
- Különösen, ha azt is írta, hogy a kód dokumentálva van, előfordulhat, hogy a dolgok nyilvánvalóak, hogy az olvasója egyáltalán nem látható. Nincs a legjobb módszer a programhoz, így nem számít, hogy milyen okos vagy tapasztalt olvasó lehet, nem tudja kitalálni, hogy milyen tervezési mintákat talál a leghasznosabb, hogy kifejezzék ötleteit a kódban. Egyértelművé teszi, hogy az olvasó Hogyan várhatja el a kód használatát, így biztosíthatja ezt a környezetet.
- A kvantum-programozási Közösség számos tagja tudományos kutató, és elsősorban a Közösséghez való hozzájárulásuk alapján ismerik fel őket. Amellett, hogy az olvasóknak további anyagokat is találnak, érdemes megadnia, hogy az oktatási segédanyagok, például a dokumentumok, a megbeszélések, a blogbejegyzések és a szoftveres eszközök megfelelően adják meg az oktatási közreműködőket, hogy a lehető legjobb munkát használják a Közösség fejlesztéséhez.
- A Quantum programozási Közösség egy széles körű és csodálatosan sokszínű Közösség. A harmadik féltől származó példákban (például: "Ha egy felhasználó...,...") a nem a Belefoglalás helyett a nemek közötti különbségeket is használhatja. Ha a személyek neve szerepel az idézetek és a hivatkozások között, és a nem ASCII-karakterek megfelelő bevonása a Közösség sokféleségét szolgálja ki a tagjainak tiszteletben tartásával. Hasonlóképpen, az angol nyelv számos szavát gyakran gyűlölködő módon használják, például hogy a technikai dokumentációban való használatuk az egyes olvasóknak és a Közösségnek is kárt okozhat.

### <a name="referencing-sample-code-from-conceptual-articles"></a>Mintául szolgáló kód hivatkozása a koncepcionális cikkekből

Ha a [Samples adattárból](https://github.com/Microsoft/Quantum)szeretne kódot felvenni, ezt egy speciális DocFX-Flavored Markdown paranccsal teheti meg:

```markdown
:::code language="qsharp" source="~/quantum/samples/algorithms/chsh-game/Game.qs" range="4-8":::
```

Ez a parancs a [ `Game.qs` `chsh-game` mintából a fájl](https://github.com/microsoft/Quantum/blob/main/samples/algorithms/chsh-game/Game.qs)4 – 8. sorait importálja a Q# szintaxis kiemelése céljából, kódként megjelölve.
Ezzel a paranccsal elkerülhető a kód duplikálása a koncepcionális cikkek és a minták tárháza között, így a dokumentációban található mintakód mindig a lehető legnaprakészebb.

## <a name="contributing-to-the-api-references"></a>Hozzájárulás az API-hivatkozásokhoz

Az API-referenciák fejlesztésének elősegítése érdekében célszerű a lekéréses kérelmeket közvetlenül a dokumentált kódban megnyitni.
Minden függvény, művelet vagy felhasználó által definiált típus támogatja a dokumentációs megjegyzést (a `///` helyett `//` ).
A Quantum Development Kit minden kiadásának fordításakor ezek a megjegyzések az API-referenciák előállítására szolgálnak https://docs.microsoft.com/qsharp/api/ , beleértve az egyes hívható bemenetek és kimenetek adatait, valamint az egyes meghívásos feltételezéseket és példákat a használatuk módjára.

> [!IMPORTANT]
> Győződjön meg arról, hogy nem módosítja manuálisan a generált API-dokumentációt, mivel ezeket a fájlokat a rendszer felülírja az egyes új kiadásokkal.
> Értékeljük a Közösséghez való hozzájárulását, és azt szeretnénk, hogy a módosítások továbbra is a kiadás után is elérhetők legyenek a felhasználók számára.

Vegyük például a függvényt `ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)` .
A dokumentációs megjegyzéseknek segíteniük kell a felhasználó számára, hogy megismerjék, hogyan értelmezhető `bits` és `oracle` milyen funkciói vannak.
Ezek a különböző információk a Q# fordítók számára a dokumentációs Megjegyzés speciális elnevezett Markdown szakaszában adhatók meg.
A példa a `ControlledOnBitString` következőhöz hasonló lehet:

```qsharp
 /// # Summary
 /// Returns a unitary operation that applies an oracle on the target register if the 
 /// control register state corresponds to a specified bit mask.
 ///
 /// # Description
 /// The output of this function is an operation that can be represented by a
 /// unitary transformation $U$ such that
 /// \begin{align}
 ///     U \ket{b_0 b_1 \cdots b_{n - 1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_{n-1}} \otimes
 ///     \begin{cases}
 ///         V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_{n - 1}) = \texttt{bits} \\\\
 ///         \ket{\psi} & \textrm{otherwise}
 ///     \end{cases},
 /// \end{align}
 /// where $V$ is a unitary transformation that represents the action of the
 /// `oracle` operation.
 ///
 /// # Input
 /// ## bits
 /// The bit string to control the given unitary operation on.
 /// ## oracle
 /// The unitary operation to be applied on the target register.
 ///
 /// # Output
 /// A unitary operation that applies `oracle` on the target register if the control 
 /// register state corresponds to the bit mask `bits`.
 ///
 /// # Remarks
 /// The length of `bits` and `controlRegister` must be equal.
 ///
 /// Given a Boolean array `bits` and a unitary operation `oracle`, the output of this function
 /// is an operation that performs the following steps:
 /// * apply an `X` operation to each qubit of the control register that corresponds to `false` 
 /// element of the `bits`;
 /// * apply `Controlled oracle` to the control and target registers;
 /// * apply an `X` operation to each qubit of the control register that corresponds to `false` 
 /// element of the `bits` again to return the control register to the original state.
 ///
 /// The output of the `Controlled` functor is a special case of `ControlledOnBitString` where `bits` is equal to `[true, ..., true]`.
 ///
 /// # Example
 /// The following code snippets are equivalent:
 /// ```qsharp
 /// (ControlledOnBitString(bits, oracle))(controlRegister, targetRegister);
 /// ```
 /// and
 /// ```qsharp
 /// within {
 ///     ApplyPauliFromBitString(PauliX, false, bits, controlRegister);
 /// } apply {
 ///     Controlled oracle(controlRegister, targetRegister);
 /// }
 /// ```
 ///
 /// The following code prepares a state $\frac{1}{2}(\ket{00} - \ket{01} + \ket{10} + \ket{11})$:
 /// ```qsharp
 /// using (register = Qubit[2]) {
 ///     ApplyToEach(H, register);
 ///     (ControlledOnBitString([false], Z))(register[0..0], register[1]);
 /// }
 /// ```
 function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
 {
     return ControlledOnBitStringImpl(bits, oracle, _, _);
 }
```

A [ `ControlledOnBitString` függvény API-dokumentációjában](xref:Microsoft.Quantum.Canon.ControlledOnBitString)megtekintheti a fenti kód renderelt verzióját.

A dokumentáció írásának általános gyakorlata mellett az API-dokumentációs megjegyzések írásakor a következő szempontokat is segít megőrizni:

- Az egyes dokumentációs megjegyzések formátumának egyeznie kell azzal, amit a fordító arra vár, hogy a Q# dokumentáció helyesen jelenjen meg. Bizonyos szakaszok, például a `/// # Remarks` szabadkézi tartalmak engedélyezése, míg a szakaszok (például a `/// # See Also` szakasz) szigorúbbak.
- Az olvasó elolvashatja az API-dokumentációt a fő API-referenciát tartalmazó helyen, az egyes névterek összegzésén, vagy akár az IDE-n belül, a hover-információk használatával. Győződjön meg arról, hogy a `/// # Summary` mondatok nem hosszabbak, így az olvasó gyorsan rendezheti, hogy szükség van-e további vagy máshol való keresésre, és segíthet a névtér-összegzések gyors vizsgálatában.
- Előfordulhat, hogy a dokumentáció jóval hosszabb ideig tart, mint maga a kód, de ez rendben van. Még egy kis kódrészlet is váratlan hatással lehet a felhasználókra, akik nem ismerik azt a kontextust, amelyben a kód létezik. A konkrét példákkal és a egyértelmű magyarázatokkal segítheti a felhasználókat abban, hogy a lehető leghatékonyabban használják a számukra elérhető kódot.

<!-- ## LaTeX Formatting ##

**TODO** -->
