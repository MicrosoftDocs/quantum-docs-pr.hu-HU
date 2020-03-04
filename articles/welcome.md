---
uid: microsoft.quantum.welcome
title: Bevezetés a Quantum Development Kit (QDK) használatába
description: Ismerkedjen meg a kvantum-projektek programozásával Q# nyelven, a Microsoft Quantum Development Kit (QDK) használatával.
author: natke
ms.author: nakersha
ms.date: 10/23/2019
ms.topic: overview
ms.openlocfilehash: cea39e47ec5e7e2ad97adbbb39ba586274564967
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907630"
---
# <a name="get-started-with-the-quantum-development-kit-qdk"></a>Bevezetés a Quantum Development Kit (QDK) használatába

Üdvözli a Microsoft Quantum Development Kit!  
A QDK tartalmazza az összes olyan eszközt, amely a kvantumprogramok létrehozásához és a Q#-val való kísérletezéshez szükséges. A Q# egy olyan programozási nyelv, amely kifejezetten a kvantumalkalmazások fejlesztéséhez készült. 

A [QDK telepítési útmutatója](xref:microsoft.quantum.install) segítségével azonnal nekivághat.
Miután a rendszer végigvezette Önt a Quantum Development Kit Windows, Linux vagy macOS rendszerre való telepítésén, lehetősége lesz saját kvantumprogramokat írni.

Ha még nem áll teljesen készen a kódolás megkezdésére, de szeretne többet megtudni a kvantum-számítástechnikáról és a Q#-ról, akkor is érdemes elolvasnia ezt a cikket, hogy képet kaphasson a rendelkezésére álló erőforrásokról. Az [Öt kérdés a kvantum-számítástechnikáról](#five-questions-about-quantum-computing) című szakaszban található hivatkozások segítenek megtalálni, amit keres.

## <a name="get-started-programming"></a>A programozás első lépései

A Quantum Development Kit sokféle módszert kínál a Q# használatával történő kvantumprogramozás elsajátítására.
A kvantumprogramozás gyors megkezdéséhez érdemes kipróbálni a *gyorsútmutatóinkat*:

* A [kvantum-véletlenszámgenerátor](xref:microsoft.quantum.quickstarts.qrng) egy „Q# Hello World” jellegű alkalmazás, amely röviden ismerteti a kvantumprogramozási fogalmakat, miközben lehetővé teszi egy kvantumalkalmazás elkészítését és futtatását mindössze néhány perc alatt.
* A [kvantumalapokat a Q# nyelven keresztül](xref:microsoft.quantum.write-program) ismertető útmutató végigvezeti Önt egy olyan Q#-program megírásán, amely során megismerkedhet a kvantumprogramozás alapvető fogalmaival. 
    Ha még nem áll készen a programozásra, akkor is követheti az útmutatót a QDK telepítése nélkül, hogy áttekintést kapjon a Q# programozási nyelvről és a kvantum-számítástechnika alapvető fogalmairól.
* A [Grover keresési algoritmusa](xref:microsoft.quantum.quickstarts.search) példaként bemutat egy olyan Q#-programot, amellyel megtapasztalhatja, hogyan lehet a Q# segítségével olyan kvantumalgoritmusokat összeállítani, amelyek absztrahálják az alacsonyabb szintű kvantumműveleteket. 
    Ez a gyorsútmutató végigvezeti Önt a program különböző programozási környezetekben történő összeállításán (Python-környezetben, .NET nyelvi környezetben, Visual Studióval vagy Visual Studio Code-dal).

### <a name="learning-further"></a>További ismeretszerzés
* Ha szeretne mélyebben elmerülni a Q#-val történő programozásban, tekintse meg a [Kvantum Katákat](https://github.com/Microsoft/QuantumKatas), az egyéni ütemben végezhető, Q# nyelven alapuló programozási gyakorlatok gyűjteményét, amelyek részletesebb kvantumprogramozási ismereteket nyújtanak.
    A katák nagy része Q# Notebook formájában is elérhető. 
* [Mintaadattárunk](https://github.com/Microsoft/Quantum) többféle példát tartalmaz a kvantumprogramok Q#-val történő létrehozására. E minták többsége a nyílt forráskódú [kvantumkódtáraink](https://github.com/Microsoft/QuantumLibraries) használatával készült, beleértve [standard](xref:microsoft.quantum.libraries.standard.intro) és [vegyészeti](xref:microsoft.quantum.chemistry.concepts.intro) kódtárainkat (ezekről bővebben alább olvashat).

## <a name="five-questions-about-quantum-computing"></a>Öt kérdés a kvantum-számítástechnikáról

Tisztában vagyunk azzal, hogy mindez elsőre túl nagy feladatnak tűnhet, ha még csak most ismerkedik a kvantumfejlesztéssel. A források a kvantum-számítástechnika megismerésének első lépéseihez nyújtanak segítséget. Biztosak vagyunk abban, hogy ezeknek a rövid cikkeknek a segítségével azonnal megjön a kedve a programozáshoz.
* [Mi az a kvantum-számítástechnika?](xref:microsoft.quantum.overview.what)
* [Mire képesek a kvantumszámítógépek?](xref:microsoft.quantum.overview.computers)
* [Miért érdemes kvantum-számítástechnikát tanulni?](xref:microsoft.quantum.overview.why)
* [Mi az a Q#?](xref:microsoft.quantum.overview.qsharp)
* [Ismerkedés a kvantum-számítástechnikával Q# nyelven](xref:microsoft.quantum.overview.learn)

## <a name="quantum-development-kit-documentation"></a>A Quantum Development Kit dokumentációja

A jelen dokumentáció az alábbi további témaköröket tartalmazza.

### <a name="using-q"></a>A Q# használata
* A [Kvantumfejlesztési technikák](xref:microsoft.quantum.techniques.intro) szakasz a kvantumprogramok Q# használatával történő létrehozásakor alkalmazott alapvető fogalmakat ismerteti. A témakörök a fájlstruktúrákkal, a műveletekkel és a függvényekkel, valamint a qubitek használatával kapcsolatosak, továbbá néhány haladó témakört is érintenek.
* A [Q# nyelvi referencia](xref:microsoft.quantum.language.intro) részletesen ismerteti a Q# nyelvet, beleértve a típusmodellt, a kifejezéseket, az utasításokat és a fordító használatát.
* A [Kvantumszimulátorok és gazdaalkalmazások](xref:microsoft.quantum.machines) szakasz a kvantumalgoritmusok végrehajtását, az elérhető kvantumgépeket és a nem Q# nyelvű illesztők kvantumprogramhoz való megírását ismerteti.

### <a name="q-libraries"></a>Q#-kódtárak
* A [Szabványos Q#-kódtárak](xref:microsoft.quantum.libraries.standard.intro) szakasz a klasszikus nyelvvezérlési követelményt és a Q#-kvantumalgoritmusokat egyaránt támogató műveleteket és függvényeket ismerteti. 
    A témakörök az átvitelvezérléssel, az adatstruktúrákkal, a hibajavítással, a teszteléssel és a hibakereséssel foglalkoznak. 
* A [Vegyészeti Q#-kódtár](xref:microsoft.quantum.chemistry.concepts.intro) szakasz a kvantumkémia-szimulációt – a kvantum-számítástechnika egyik legfontosabb alkalmazási területét – támogató műveleteket és függvényeket ismerteti. A témakörök többek között a Hamilton-operátorok dinamikájának szimulálásával és a kvantumfázisbecsléssel foglalkoznak.
* A [Numerikus Q#-kódtár](xref:microsoft.quantum.numerics.intro) szakasz az összetett aritmetikai függvények kifejezését támogató műveleteket és függvényeket ismerteti a célgépek natív műveletei szempontjából.
* A [Q#-kódtárreferencia](xref:microsoft.quantum.standardlibsintro) szakasz kódtárentitásokkal kapcsolatos referenciainformációkat tartalmaz névtér szerint.

### <a name="general-quantum-computing"></a>Általános kvantum-számítástechnika
* A [Kvantum-számítástechnikai fogalmak](xref:microsoft.quantum.concepts.intro) szakasz olyan témaköröket tartalmaz, mint a lineáris algebra relevanciája a kvantum-számítástechnika szempontjából, a qubitek természete és használata, a kvantumkörök olvasása és így tovább.
* A [Kvantum-számítástechnikai szószedet](xref:microsoft.quantum.glossary) egy olyan szószedet, amely a kvantum-számítástechnikára és a programfejlesztésre jellemző legfontosabb kifejezéseket tartalmazza. 
    Ha ez a terület új az Ön számára, hasznos referencia lehet a dokumentáció olvasása során.
* A [További olvasnivalók](xref:microsoft.quantum.more-information) olyan speciálisan kiválasztott referenciákat tartalmaznak, amelyekkel részletesebben is megismerheti a kvantum-számítástechnikai témaköröket.

### <a name="additional-info"></a>További információ
* [A Microsoft Quantum Development Kit kibocsátási megjegyzései](xref:microsoft.quantum.relnotes).


## <a name="be-a-part-of-the-q-open-source-community"></a>Legyen része a Q# nyílt forráskódú közösségének
A Quantum Development Kit egy nyílt forráskódú fejlesztőkészlet, amelynek segítségével a fejlesztők szélesebb körben is hozzáférhetővé tehetik a kvantum-számítástechnikát annak érdekében, hogy mind együtt dolgozhassunk a világ legsürgetőbb problémáinak megoldásán.  A nyílt forráskódú szoftverekre igényt tartó tudományos intézmények képesek lesznek alkalmazni a Q#-t a kvantumtanuláshoz és -fejlesztéshez. A fejlesztőkészlet nyílt forráskódúvá tételének köszönhetően a fejlesztők és az ágazati szakértők javításokkal és ötletekkel járulhatnak hozzá a kódon keresztül a kvantum-számítástechnikához.

Fontos a Quantum Development Kittel kapcsolatos visszajelzése, részvétele és hozzájárulása.  A Quantum Development Kit forrásaival kapcsolatos további információért, visszajelzés küldéséhez, valamint annak megismeréséhez, hogy miként vehet részt a döntéshozatalban, illetve járulhat hozzá ehhez a növekvő kvantumfejlesztési platformhoz, tekintse meg a [Hozzájárulás a Quantum Development Kithez](xref:microsoft.quantum.contributing) című szakaszt.

A Microsoft kvantum-számítástechnikai kezdeményezésével kapcsolatos általánosabb információért tekintse meg a [Microsoft Quantum](https://www.microsoft.com/en-us/quantum/) oldalát.
