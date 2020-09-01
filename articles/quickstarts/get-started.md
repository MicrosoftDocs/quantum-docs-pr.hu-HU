---
uid: microsoft.quantum.welcome
title: Bevezetés a Quantum Development Kit (QDK) használatába
description: Ismerje meg a kvantumprojektek Q# nyelven való programozását a Microsoft Quantum Development Kit használatával.
author: bradben
ms.author: bradben
ms.date: 5/10/2020
ms.topic: overview
no-loc:
- Q#
- $$v
ms.openlocfilehash: 06198f3b5b806bab49abf9fca38b5d2f15cfb65f
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863743"
---
# <a name="get-started-with-the-quantum-development-kit-qdk"></a>Bevezetés a Quantum Development Kit (QDK) használatába

Üdvözli a Microsoft Quantum Development Kit!  

A Quantum Development Kit (QDK) tartalmazza az összes olyan eszközt, amely a kvantumprogramok létrehozásához és a Q# nyelvvel való kísérletezéshez szükséges. Ez egy olyan programozási nyelv, amely kifejezetten a kvantumalkalmazások fejlesztéséhez készült.

A [QDK telepítési útmutatója](xref:microsoft.quantum.install) segítségével azonnal nekivághat.
Miután a rendszer végigvezette Önt a Quantum Development Kit Windows, Linux vagy macOS rendszerre való telepítésén, lehetősége lesz saját kvantumprogramokat írni.

Ha nem ismeri a kvantum-számítástechnikát, tekintse meg az [Áttekintés](xref:microsoft.quantum.overview.introduction) szakaszban, hogy mire képesek a kvantumszámítógépek, és mik a kvantum-számítástechnika alapjai.

## <a name="get-started-programming"></a>A programozás első lépései

A Quantum Development Kit sokféle módszert kínál a Q# használatával történő kvantumprogramozás elsajátítására.
A kvantumprogramozás gyors megkezdéséhez érdemes kipróbálni az oktatóanyagokat:

* [Kvantum-véletlenszámgenerátor](xref:microsoft.quantum.quickstarts.qrng) – Kezdjen egy „Q# nyelven létrehozott Hello World” jellegű alkalmazással, amely röviden ismerteti a kvantumprogramozási fogalmakat, miközben lehetővé teszi egy kvantumalkalmazás elkészítését és futtatását mindössze néhány perc alatt.
* [Az összefonódás megismerése a Q# segítségével](xref:microsoft.quantum.write-program) – Ez az oktatóanyag végigvezeti Önt egy Q#-program megírásán, amely során megismerkedhet a kvantumprogramozás alapvető fogalmaival.
    Ha még nem áll készen a programozásra, akkor is követheti az útmutatót a QDK telepítése nélkül, hogy áttekintést kapjon a Q# programozási nyelvről és a kvantum-számítástechnika alapvető fogalmairól.
* [Grover keresési algoritmusa](xref:microsoft.quantum.quickstarts.search) – Példaként megismerhet egy olyan Q#-programot, amellyel megtapasztalhatja, hogyan lehet a Q# segítségével olyan kvantumalgoritmusokat összeállítani, amelyek absztrahálják az alacsonyabb szintű kvantumműveleteket.
    Ez az oktatóanyag végigvezeti a program Q#-alkalmazásként való fejlesztésén, amely során a Visual Studiót vagy a Visual Studio Code-ot használhatja.

### <a name="learning-further"></a>További ismeretszerzés
* A [kvantum-számítástechnikával kapcsolatos Microsoft Learn-modulokban](https://docs.microsoft.com/learn/browse/?term=quantum) a saját tempójában, a saját időbeosztása szerint sajátíthatja el a fő alapelveket. Az [első modulban](https://docs.microsoft.com/learn/modules/qsharp-create-first-quantum-development-kit/) megismerheti a kvantumprogramok QDK-val való létrehozásának alapjait.
* Ha szeretne mélyebben elmerülni a Q# nyelven történő programozásban, tekintse meg a [Kvantum katákat](https://github.com/Microsoft/QuantumKatas), az egyéni ütemben végezhető, Q# nyelven alapuló programozási gyakorlatok gyűjteményét, amelyek részletesebb kvantumprogramozási ismereteket nyújtanak.
    A katák nagy része Q#-jegyzetfüzet formájában is elérhető. 
* [Mintaadattárunk](https://github.com/Microsoft/Quantum) többféle példát tartalmaz a kvantumprogramok Q# nyelven történő létrehozására. E minták többsége a nyílt forráskódú [kvantumkódtáraink](https://github.com/Microsoft/QuantumLibraries) használatával készült, beleértve [standard](xref:microsoft.quantum.libraries.standard.intro) és [vegyészeti](xref:microsoft.quantum.chemistry.concepts.intro) kódtárainkat (ezekről bővebben alább olvashat).

## <a name="key-concepts-for-quantum-computing"></a>A kvantum-számítástechnika legfontosabb alapelvei

Tisztában vagyunk azzal, hogy mindez elsőre túl nagy feladatnak tűnhet, ha még csak most ismerkedik a kvantumfejlesztéssel. Ezek a kulcsfontosságú alapelvek úgy vannak kialakítva, hogy segítsenek a kvantum világának megismerésében, illetve annak megértésében, hogy miben különbözik a kvantum-számítástechnika a hagyományos számítástechnikától.

* [A kvantum-számítástechnika ismertetése](xref:microsoft.quantum.overview.understanding)
* [A kvantumszámítógépek és a kvantumszimulátorok](xref:microsoft.quantum.overview.simulators)
* [Mi az a Q# programozási nyelv és a QDK?](xref:microsoft.quantum.overview.q-sharp)
* [A kvantum-számítástechnika lineáris algebrája](xref:microsoft.quantum.overview.algebra)

## <a name="quantum-development-kit-documentation"></a>A Quantum Development Kit dokumentációja

A jelen dokumentáció az alábbi további témaköröket tartalmazza.

### <a name="no-locq-developer-guides"></a>Q# fejlesztői útmutatók

* A [Q# felhasználói útmutatója](xref:microsoft.quantum.guide) azokat az alapvető fogalmakat részletezi, amelyeket a kvantumprogramok Q# használatával történő létrehozásakor alkalmazhat.
* A [Kvantumszimulátorok és gazdaalkalmazások](xref:microsoft.quantum.machines) című szakasz a kvantumalgoritmusok végrehajtását, az elérhető kvantumgépeket és a nem Q# nyelvű illesztők kvantumprogramhoz való megírását ismerteti.

### <a name="no-locq-libraries"></a>Q#-kódtárak

* A [Szabványos Q#-kódtárak](xref:microsoft.quantum.libraries.standard.intro) című szakasz a klasszikus nyelvvezérlési követelményt és a Q#-kvantumalgoritmusokat egyaránt támogató műveleteket és függvényeket ismerteti. 
    A témakörök az átvitelvezérléssel, az adatstruktúrákkal, a hibajavítással, a teszteléssel és a hibakereséssel foglalkoznak. 
* A [Vegyészeti Q#-kódtár](xref:microsoft.quantum.chemistry.concepts.intro) című szakasz a kvantumkémia-szimulációt – a kvantum-számítástechnika egyik legfontosabb alkalmazási területét – támogató műveleteket és függvényeket ismerteti. A témakörök többek között a Hamilton-operátorok dinamikájának szimulálásával és a kvantumfázisbecsléssel foglalkoznak.
* A [Numerikus Q#-kódtár](xref:microsoft.quantum.numerics.intro) című szakasz az összetett aritmetikai függvények kifejezését támogató műveleteket és függvényeket ismerteti a célgépek natív műveletei szempontjából.
* A [Q#-kódtárreferencia](xref:microsoft.quantum.standardlibsintro) című szakasz kódtárentitásokkal kapcsolatos referenciainformációkat tartalmaz névtér szerint.

### <a name="general-quantum-computing"></a>Általános kvantum-számítástechnika

* A [Kvantum-számítástechnikai fogalmak](xref:microsoft.quantum.concepts.intro) szakasz olyan témaköröket tartalmaz, mint a lineáris algebra relevanciája a kvantum-számítástechnika szempontjából, a qubitek természete és használata, a kvantumkörök olvasása és így tovább.
* A [Kvantum-számítástechnikai szószedet](xref:microsoft.quantum.glossary) egy olyan szószedet, amely a kvantum-számítástechnikára és a programfejlesztésre jellemző legfontosabb kifejezéseket tartalmazza.
    Ha ez a terület új az Ön számára, hasznos referencia lehet a dokumentáció olvasása során.
* A [További olvasnivalók](xref:microsoft.quantum.more-information) olyan speciálisan kiválasztott referenciákat tartalmaznak, amelyekkel részletesebben is megismerheti a kvantum-számítástechnikai témaköröket.

### <a name="additional-info"></a>További információ

* [A Microsoft Quantum Development Kit kibocsátási megjegyzései](xref:microsoft.quantum.relnotes).


## <a name="be-a-part-of-the-no-locq-open-source-community"></a>Legyen a Q# nyílt forráskódú fejlesztőkészlet közösségének tagja

A Quantum Development Kit egy nyílt forráskódú fejlesztőkészlet, amelynek segítségével a fejlesztők szélesebb körben is hozzáférhetővé tehetik a kvantum-számítástechnikát annak érdekében, hogy mind együtt dolgozhassunk a világ legsürgetőbb problémáinak megoldásán.  A nyílt forráskódú szoftverekre igényt tartó tudományos intézmények üzembe helyezhetik a Q#-ot a kvantumtanuláshoz és -fejlesztéshez. A fejlesztőkészlet nyílt forráskódúvá tételének köszönhetően a fejlesztők és az ágazati szakértők javításokkal és ötletekkel járulhatnak hozzá a kódon keresztül a kvantum-számítástechnikához.

Fontos a Quantum Development Kittel kapcsolatos visszajelzése, részvétele és hozzájárulása.  A Quantum Development Kit forrásaival kapcsolatos további információért, visszajelzés küldéséhez, valamint annak megismeréséhez, hogy miként vehet részt a döntéshozatalban, illetve járulhat hozzá ehhez a növekvő kvantumfejlesztési platformhoz, tekintse meg a [Hozzájárulás a Quantum Development Kithez](xref:microsoft.quantum.contributing) című szakaszt.

A Microsoft kvantum-számítástechnikai kezdeményezésével kapcsolatos általánosabb információért tekintse meg a [Microsoft Quantum](https://www.microsoft.com/en-us/quantum/) oldalát.
