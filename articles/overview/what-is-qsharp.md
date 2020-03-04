---
title: Mi az a Q# és a QDK?
description: Ismeretek a Q#-ról, a Microsoft által létrehozott programozási nyelvről, amellyel kvantumszámítógépekre fejleszthet alkalmazásokat, és amely a Microsoft Quantum Development Kit egyik kulcsfontosságú eleme
author: natke
ms.author: nakersha
ms.date: 10/22/2019
ms.topic: article
uid: microsoft.quantum.overview.qsharp
ms.openlocfilehash: a4bf21887e34ac85f75e5e0b9a033138464fd09d
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907001"
---
# <a name="what-are-q-and-the-qdk"></a>Mi az a Q# és a QDK?

A Q# egy kifejezetten a kvantum-számítástechnikához kifejlesztett programozási nyelv.
A Microsoft Quantum Development Kit (QDK) egyik kulcsfontosságú elemeként a Q# egy olyan keretrendszert kínál a kvantumprogramozóknak, amely segít az algoritmusokra koncentrálni anélkül, hogy olyan technikai részletekkel kéne törődni, mint a kapuszekvencia optimalizálása vagy egy kvantumszámítógép fizikai implementálása.

A QDK számos különféle eszközt tartalmaz, így a fejlesztők számára minden olyan funkciót biztosít, amelyre a kvantumprogramok írásakor szükségük lehet.
A QDK a Q# nyelven kívül a következőket tartalmazza:
* *Q#-kódtárak*, amelyekkel a fejlesztők azonnal munkához láthatnak, és rögtön valós körülmények között használható kvantumalkalmazásokat hozhatnak létre
* különböző *célszámítógépek* a Q#-programok futtatásához. Ilyenek például a nagyobb kvantumprogramokhoz tartozó erőforrásbecslők és szimulátorok, valamint a teljes körű funkciókkal rendelkező kvantumszimulátor, amely zajtalan kvantumszámítógépként viselkedik. Az utóbbi kifejezetten hasznos az ötletelés, a programok hibakeresése és a kvantumfizika megismerése során, de csak a viszonylag kevés qubitből álló programok esetében hatékony. Izgatottan várjuk a célszámítógépként használható kvantum-számítástechnikai hardvereink jövőbeli bevezetését.
* olyan *eszközök*, amelyek a Q# nyelv zökkenőmentes használatát segítik, például a Visual Studio és a VS Code bővítményei, valamint a Python- és Jupyter-notebookokhoz használható csomagok.
* *API-dokumentáció* a Q# klasszikus gazdagépnyelvekkel (például a Python és a C#) való párosításához

A Microsoft Quantum Development Kittel fejlesztett alkalmazások általában két részből állnak:
1. Egy vagy több kvantumalgoritmusból, amelyek a Q# kvantumprogramozási nyelvvel lettek implementálva, és a klasszikus gazdaprogrammal lettek meghívva. Ezek a következőkből állnak: 
    - Q#-műveletek: kvantumműveleteket tartalmazó alrutinok, és 
    - Q#-funkciók: klasszikus alrutinok a kvantumalgoritmuson belül.
2. Egy klasszikus programból, amely a Pythonhoz vagy C#-hoz hasonló klasszikus programozási nyelven van implementálva, és amely a fő belépési pontként szolgál, valamint Q#-műveleteket hív meg egy kvantumalgoritmus végrehajtásához.

## <a name="write-quantum-programs-not-quantum-circuits"></a>Kvantumprogramok írása kvantumkörök helyett

A kvantum-számítástechnika korai időszakában az algoritmusokat még diagramként vizualizálták, hasonlóan a klasszikus számítástechnikában használt kapcsolási rajzokhoz.
Bár a körmodell sok éven át hasznosnak bizonyult a kvantum-számítástechnikai kutatásokban, a Microsoftnál úgy gondoljuk, hogy a fejlesztők túl tudnak lépni a kvantumkörökön, és a Q# segítségével arra is képesek lehetnek, hogy kvantumalgoritmusokat és -alkalmazásokat fejlesszenek ki.
A Q# úgy lett kialakítva, hogy építkezzen a klasszikus szoftverfejlesztésből évtizedek alatt leszűrt tapasztalatokra, és magas szintű programnyelvi funkciókat adjon a kvantumfejlesztők kezébe, amelyek a kvantum-számítástechnikára vannak kiélezve.

## <a name="how-does-q-work"></a>Hogyan működik a Q#?

A Q# programozási nyelv típusok, műveletek és logikai kifejezések intuitív készletét biztosítja, amelyek lehetővé teszik, hogy az algoritmusok kifejlesztése során ne kelljen foglalkoznia a kvantumszámítógép belső logikájával.

A Q# egyik alapvető építőeleme a `Qubit` típus, amit nem lehet lemásolni vagy közvetlenül elérni, pontosan úgy, mint egy igazi qubitet.
Ehelyett megmérhetjük, az eredményt pedig egy `Result` változóban tárolhatjuk, ami egy Q#-típus két lehetséges értékkel: `Zero` és `One`.
Az ehhez hasonló konstrukciók garantálják, hogy az algoritmusok mindig tiszteletben tartják a kvantumfizika törvényeit, és megfelelően futnak a kvantumszámítógépeken és szimulátorokon.

A Q# emellett olyan klasszikus logikai függvényeket is tartalmaz, mint a feltételes értékek vagy a hurkok, néhány apró részlettel egyetemben, amelyek gondoskodnak az összes kvantumszabály betartásáról.
Ilyen például a hurkok végrehajtási módjának korlátozása, amellyel biztosítható, hogy a csak determinisztikus klasszikus alrutinokra korlátozódó függvényekben ne lehessen kvantumműveleteket meghívni.

A Q#-programok gyakran vannak párban egy C# vagy Python nyelven írt gazdaprogrammal, amely biztosítja a klasszikus és a kvantumkód megfelelő szervezettségét.
Az olyan nyelvek támogatása mellett, mint a C# vagy a Python, a QDK Jupyter-notebook-támogatást is nyújt az IQ# Jupyter kernel révén.

## <a name="what-can-i-use-q-for"></a>Mire használható a Q# nyelv?

### <a name="use-q-to-learn-quantum-computing"></a>A Q# használata a kvantum-számítástechnika elsajátításához

Mostanáig a kvantum-számítástechnika elsajátításához meg kellett tanulni a kapcsolatcsoport-modellt, hogy az algoritmusokat a kvantumkapuk és mérések rendezett sorozataként lehessen értelmezni. A Q# egy másik utat is járhatóvá tesz: a kvantum-számítástechnika kvantumprogramok írása révén történő elsajátítását.

### <a name="use-q-to-design-quantum-algorithms"></a>A Q# használata kvantumalgoritmusok megtervezéséhez

A Q# egyre több kódtárat és felhasználó által definiált típust biztosít, amelyek segítenek az eszközök használatában és a speciális kvantumalgoritmusok megalkotásában. Vegyük például azt a helyzetet, hogy össze kell fonnia két qubitet (q1 és q2). A qubitek összefonásához szükséges kapuk egyenkénti alkalmazása helyett alkalmazhatja a már beépített `PrepareEntangledState([q1], [q2])` műveletet.

### <a name="use-q-to-estimate-quantum-resources"></a>A Q# használata kvantum-erőforrások becsléséhez

A Q#-program végrehajtásának szimulálása a teljes állapotú kvantumszimulátor használatával lehetséges, amely a Quantum Development Kit (QDK) része.  A QDK olyan erőforrásbecslő eszközöket is tartalmaz, amelyek megállapításokat nyújtanak az olyan Q#-programok teljesítményéről, amelyek túl nagyok a szimulátoron való futtatáshoz.  Ezek rendkívül értékesek az algoritmusok tervezői számára, akik ezáltal úgy tudják finomhangolni a programjaikat, hogy azok kevesebb erőforrást használjanak (például kevesebb qubit fusson kevesebb műveletre esően) és futtathatók legyenek a korai, kisebb léptékű kvantumhardvereken is.

### <a name="use-q-to-validate-hardware-performance"></a>A Q# használata hardverteljesítmény ellenőrzéséhez

A Q# szépsége az, hogy a programokat elég egyszer megírni, majd kvantumszimulátorokon való futtatásukkal elvégezhető a hibakeresésük, valamint különböző kvantumszámítógépek hardverén is futtathatók.  Ahogy a kvantumszámítógépek fejlődnek, és új kvantumszámítógépek válnak elérhetővé, a Q# nyelven írt teljesítménytesztelési programok futtathatók a hardverteljesítmény ellenőrzése és az eredmények összehasonlítása céljából.  

## <a name="next-steps"></a>További lépések

* [Hogyan tudhatok meg többet a kvantum-számítástechnikáról?](xref:microsoft.quantum.overview.learn)
* [Bevezetés a Microsoft Quantum Development Kit használatába](xref:microsoft.quantum.welcome)
