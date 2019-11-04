---
title: Közreműködő dokumentáció | Microsoft Docs
description: Közreműködő dokumentáció
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.docs
ms.openlocfilehash: 1e24dd859c0b75a161f4f3c7151e2eec227075a2
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183675"
---
# <a name="improving-documentation"></a>A dokumentáció fejlesztése #

A Quantum Development Kit dokumentációja számos különböző formát vesz igénybe, így az információk könnyen elérhetők a kvantum-fejlesztők számára.

A [dokumentumok kód szerinti](https://www.writethedocs.org/guide/docs-as-code/)alapelveit követve az összes Quantum Development Kit-dokumentáció kódként van formázva, és a git használatával felügyelhető ugyanúgy, mint a Quantum Development Kit felépítéséhez használt forráskód.
A legtöbb esetben a kód hátterének dokumentációja a [Markdown](https://daringfireball.net/projects/markdown/)különböző formáiból tevődik össze, és a parancssorban, az ide-ben és a Source Control használatával könnyen használható, formázatlan szöveges formátumú szöveg kiírására szolgáló nyelv.
Hasonlóképpen fogadjuk el a [MathJax](https://www.mathjax.org/) -függvénytárat, hogy a latex nyelv használatával formázza a matematika használatát a dokumentációban, az alább részletezett módon.


Így a dokumentáció minden formája némileg eltér a részletektől:

- A **koncepcionális dokumentáció** a https://docs.microsoft.com/quantum közzétett cikkekből áll, amelyek a Quantum Computing alapjaiból ismertetik az adatcsere formátumának technikai specifikációit. Ezek a cikkek a [DocFX-stílusú Markdown (DFM)](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html), a gazdag dokumentációs készletek létrehozásához használt Markdown-változatok.
- Az **API-hivatkozás** az egyes Q # függvényekhez, műveletekhez és felhasználó által definiált típusokhoz tartozó lapok összessége, https://docs.microsoft.com/qsharp/api/ közzétéve. Ezek az oldalak dokumentálják az összes meghívható bemenetet és műveletet, valamint példákat és további információkra mutató hivatkozásokat. Az API-referenciát a rendszer automatikusan Kinyeri a kis DFM-dokumentumokból a Q # forráskódban az egyes verziók részeként.
- Az egyes mintákhoz és Kata-hoz tartozó **README<!---->. MD** fájlok azt írják le, hogyan használható a minta vagy a Kata, mit takar, és hogyan kapcsolódik a többihez a Quantum Development Kit-hez. Ezek a fájlok a GitHub-stílusú [Markdown (GFM)](https://github.github.com/gfm/)használatával íródnak, amely egy egyszerűbb alternatíva a DFM, amely a dokumentáció közvetlen csatolásához használható a kódokhoz.

## <a name="contributing-to-the-conceptual-documentation"></a>A fogalmi dokumentációhoz való hozzájárulás ##

A koncepcionális vagy a README dokumentációjának fejlesztéséhez, majd egy lekéréses kérelemmel kezdődik a [**MicrosoftDocs/Quantum-docs-PR**](https://github.com/MicrosoftDocs/quantum-docs-pr/
), a [**Microsoft/Quantum**](https://github.com/Microsoft/Quantum)vagy a [**Microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas), a megfelelő módon.
Részletesebben ismertetjük a lekéréses kérelmeket, de most van néhány dolog, ami jó szem előtt tartani a dokumentáció tökéletesítése során:

- Az olvasók rendkívül széles körben érkeznek a Quantum Development Kit dokumentációjában. Mindenki a diákoknak, akik szeretnék megtanulni, hogy milyen új és izgalmas, hogy a kihasználatlan szakirányú oktatói képzésben részt vevő szakterületek elolvassák a dokumentációt. A lehetséges mértékig ne Tételezzük fel, hogy az olvasók részéről nem vállalunk széleskörű ismeretet, mivel ezek csak most kezdik el. Ez a leghasznosabb, ha egyértelmű és hozzáférhető leírásokat is biztosít, vagy további információkra mutató hivatkozásokat is biztosíthat más erőforrásokhoz.
- A dokumentációs készletek nem rendelkeznek például könyvekkel vagy dokumentumokkal, így az olvasók a "középső"-ként látszanak. Előfordulhat például, hogy a keresőmotorok nem javasolják az indexet, vagy ha egy barátja olyan hivatkozást kapott, amely a segítségére tett kísérletet. Próbálja ki az olvasót úgy, hogy mindig egyértelmű kontextust biztosít, valamint a hivatkozásokat, ahol szükséges.
- Egyes olvasók az absztrakt és a definíciókat is hasznosnak találják, míg a többi olvasó az adott példákból kikövetkeztetve a legjobban működik. Az általános eset és a konkrét példák egyaránt segítenek abban, hogy az olvasók a lehető legtöbbet hozzanak ki a kvantum-programozásból.
- Különösen, ha azt is írta, hogy a kód dokumentálva van, előfordulhat, hogy a dolgok nyilvánvalóak, hogy az olvasója egyáltalán nem látható. Nincs a legjobb módszer a programhoz, így nem számít, hogy milyen okos vagy tapasztalt olvasó lehet, nem tudja kitalálni, hogy milyen tervezési mintákat talál a leghasznosabb, hogy kifejezzék ötleteit a kódban. Egyértelművé teszi, hogy az olvasó Hogyan várhatja el a kód használatát, így biztosíthatja ezt a környezetet.
- A kvantum-programozási Közösség számos tagja tudományos kutató, és elsősorban a Közösséghez való hozzájárulásuk alapján ismerik fel őket. Amellett, hogy az olvasóknak további anyagokat is találnak, érdemes megadnia, hogy az oktatási segédanyagok, például a dokumentumok, a megbeszélések, a blogbejegyzések és a szoftveres eszközök megfelelően adják meg az oktatási közreműködőket, hogy a lehető legjobb munkát használják a Közösség fejlesztéséhez.
- A Quantum programozási Közösség egy széles körű és csodálatosan sokszínű Közösség. A harmadik féltől származó példákban (például: "Ha egy felhasználó...,...") a nem a Belefoglalás helyett a nemek közötti különbségeket is használhatja. Ha a személyek neve szerepel az idézetek és a hivatkozások között, és a nem ASCII-karakterek megfelelő bevonása a Közösség sokféleségét szolgálja ki a tagjainak tiszteletben tartásával. Hasonlóképpen, az angol nyelv számos szavát gyakran gyűlölködő módon használják, például hogy a technikai dokumentációban való használatuk az egyes olvasóknak és a Közösségnek is kárt okozhat.

## <a name="contributing-to-the-api-references"></a>Hozzájárulás az API-hivatkozásokhoz ##

Az API-referenciák fejlesztésének elősegítése érdekében célszerű a lekéréses kérelmeket közvetlenül a dokumentált kódban megnyitni.
Minden függvény, művelet vagy felhasználó által definiált típus támogatja a dokumentációs megjegyzést (`///` `//`helyett).
A Quantum Development Kit minden kiadásának fordításakor ezek a megjegyzések az API-referenciák előállítására szolgálnak https://docs.microsoft.com/qsharp/api/ ban, beleértve az egyes meghívásos bemenetek és kimenetek adatait, valamint az egyes meghívásos feltételezéseket és példákat a használatuk módjára.

> [!IMPORTANT]
> Győződjön meg arról, hogy nem módosítja manuálisan a generált API-dokumentációt, mivel ezeket a fájlokat a rendszer felülírja az egyes új kiadásokkal.
> Értékeljük a Közösséghez való hozzájárulását, és azt szeretnénk, hogy a módosítások továbbra is a kiadás után is elérhetők legyenek a felhasználók számára.

Vegyünk például egy műveletet `PrepareTrialState(angles : Double[], register : Qubit[]) : Unit`.
A dokumentációs megjegyzéseknek segíteniük kell a felhasználótól a `angles`értelmezését, hogy a művelet hogyan feltételezi `register`kezdeti állapotát, milyen hatással van a `register`re, és így tovább.
Ezek a különböző információk a Q # Compiler számára a dokumentációs Megjegyzés speciális elnevezett Markdown szakaszában adhatók meg.
A `PrepareTrialState`például a következőhöz hasonló módon írhat:

```qsharp
/// # Summary
/// Given a register of qubits, prepares them in a trial state by rotating each
/// independently.
///
/// # Description
/// This operation prepares the input register by performing a
/// $Y$ rotation on each qubit by an angle given in `angles`.
///
/// # Input
/// ## angles
/// An array of parameters
/// ## register
/// A register of qubits initially in the $\ket{00\cdots0}$ state.
///
/// # Example
/// To prepare an equal superposition $\ket{++\cdots+}$ over all input qubits:
/// ```qsharp
/// PrepareTrialState(ConstantArray(Length(register), PI() / 2.0), register);
/// ```
///
/// # Remarks
/// This operation is generally useful in the inner loop of an optimization
/// algorithm.
///
/// # See Also
/// - Microsoft.Quantum.Intrinsic.Ry
operation PrepareTrialState(angles : Double[], register : Qubit[]) : Unit {
    // ...
}
```

A dokumentáció írásának általános gyakorlata mellett az API-dokumentációs megjegyzések írásakor a következő szempontokat is segít megőrizni:

- Az egyes dokumentációs megjegyzések formátumának egyeznie kell azzal, amit a Q # fordító a dokumentáció megfelelő megjelenítésére vár. Egyes szakaszok, például a `/// # Remarks` lehetővé teszik a szabadkézi tartalmak használatát, míg a szakaszok, például a `/// # See Also` szakasz szigorúbbak.
- Az olvasó elolvashatja az API-dokumentációt a fő API-referenciát tartalmazó helyen, az egyes névterek összegzésén, vagy akár az IDE-n belül, a hover-információk használatával. Győződjön meg arról, hogy a `/// # Summary` nem hosszabb, mint a mondatok, így az olvasó gyorsan rendezheti, hogy szükség van-e további vagy máshol való keresésre, és segíthet a névtér-összegzések gyors vizsgálatában.
- Előfordulhat, hogy a dokumentáció jóval hosszabb ideig tart, mint maga a kód, de ez rendben van. Még egy kis kódrészlet is váratlan hatással lehet a felhasználókra, akik nem ismerik azt a kontextust, amelyben a kód létezik. A konkrét példákkal és a egyértelmű magyarázatokkal segítheti a felhasználókat abban, hogy a lehető leghatékonyabban használják a számukra elérhető kódot.

<!-- ## LaTeX Formatting ##

**TODO** -->
