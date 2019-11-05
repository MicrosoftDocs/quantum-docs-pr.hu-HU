---
title: Mi az a Q#?
description: Ismeretek a Q#-ról, a Microsoft által létrehozott programozási nyelvről, amellyel kvantumszámítógépekre fejleszthet alkalmazásokat
author: natke
ms.author: nakersha
ms.date: 10/22/2019
ms.topic: article
uid: microsoft.quantum.overview.qsharp
ms.openlocfilehash: e04228ff62092a15c529297bd56b9ee48399f4a5
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/02/2019
ms.locfileid: "73443953"
---
# <a name="what-is-q"></a>Mi az a Q#?

A Q# egy jellemzően a kvantum-számítástechnikában használható programozási nyelv. A Q# egy olyan keretrendszert kínál a kvantumprogramozóknak, amely segít az algoritmusokra koncentrálni anélkül, hogy olyan technikai részletekkel kéne törődni, mint a kapuszekvencia optimalizálása vagy egy kvantumszámítógép fizikai implementálása.

A Q# programozási nyelv típusok, műveletek és logikai kifejezések intuitív készletét biztosítja, amelyek lehetővé teszik, hogy az algoritmusok kifejlesztése során ne kelljen foglalkoznia a kvantumszámítógép belső logikájával.

## <a name="code-algorithms"></a>Kódalgoritmusok

A kvantum-számítástechnika korai időszakában az algoritmusokat még diagramként vizualizálták, hasonlóan a klasszikus számítástechnikában használt kapcsolási rajzokhoz.  Bár a körmodell sok éven át hasznosnak bizonyult a kvantum-számítástechnikai kutatásokban, a Microsoftnál úgy gondoljuk, hogy a fejlesztők túl tudnak lépni a kvantumkörökön, és a Q# segítségével arra is képesek lehetnek, hogy kvantumalgoritmusokat és -alkalmazásokat fejlesszenek ki. A Q# úgy lett kialakítva, hogy építkezzen a klasszikus szoftverfejlesztésből évtizedek alatt leszűrt tapasztalatokra, és magas szintű programnyelvi funkciókat adjon a kvantumfejlesztők kezébe, amelyek kifejezetten a kvantum-számítástechnikára vannak kiélezve.


## <a name="how-does-q-work"></a>Hogyan működik a Q#?

A Q# egyik alapvető építőeleme a `Qubit` típus, amit nem lehet lemásolni vagy közvetlenül elérni, pontosan úgy, mint egy igazi qubitet. Ehelyett megmérhetjük, az eredményt pedig egy `Result` változóban tárolhatjuk, ami egy Q#-típus két lehetséges értékkel: `Zero` és `One`. Az ehhez hasonló konstrukciók garantálják, hogy az algoritmusok mindig tiszteletben tartják a kvantumfizika törvényeit, és megfelelően futnak a kvantumszámítógépeken és szimulátorokon.

A Q# emellett olyan klasszikus logikai függvényeket is tartalmaz, mint a feltételes értékek vagy a hurkok, néhány apró részlettel egyetemben, amelyek gondoskodnak az összes kvantumszabály betartásáról. Például a kvantumműveleteknek visszafejthetőnek kell lenniük. Ez némi korlátozást jelent a hurkok végrehajtása terén.

A Q#-programok gyakran vannak párban egy C# vagy Python nyelven írt gazdaprogrammal, amely biztosítja a klasszikus és a kvantumkód megfelelő szervezettségét. A .NET-nyelvek, például a C# és a Python támogatása mellett a QDK Jupyter-notebook-támogatást is nyújt az IQ# Jupyter kernel révén.

## <a name="use-q-to-learn-quantum-computing"></a>A Q# használata a kvantum-számítástechnika elsajátításához

Mostanáig a kvantum-számítástechnika elsajátításához meg kellett tanulni a kapcsolatcsoport-modellt, hogy az algoritmusokat a kvantumkapuk és mérések rendezett sorozataként lehessen értelmezni. A Q# egy másik utat is járhatóvá tesz: a kvantum-számítástechnika kvantumprogramok írása révén történő elsajátítását.

## <a name="use-q-to-design-quantum-algorithms"></a>A Q# használata kvantumalgoritmusok megtervezéséhez

A Q# egyre több kódtárat és felhasználó által definiált típust biztosít, amelyek segítenek az eszközök használatában és a speciális kvantumalgoritmusok megalkotásában. Vegyük például azt a helyzetet, hogy össze kell fonnia két qubitet (q1 és q2). A qubitek összefonásához szükséges kapuk egyenkénti alkalmazása helyett alkalmazhatja a már beépített `PrepareEntangledState([q1], [q2])` műveletet.

## <a name="use-q-to-estimate-quantum-resources"></a>A Q# használata kvantum-erőforrások becsléséhez

A Q#-program végrehajtásának szimulálása a teljes állapotú kvantumszimulátor használatával lehetséges, amely a Quantum Development Kit (QDK) része.  A QDK olyan erőforrásbecslő eszközöket is tartalmaz, amelyek megállapításokat nyújtanak az olyan Q#-programok teljesítményéről, amelyek túl nagyon a szimulátoron való futtatáshoz.  Ezek rendkívül értékesek az algoritmusok tervezői számára, akik ezáltal úgy tudják finomhangolni a programjaikat, hogy azok kevesebb erőforrást használjanak (például kevesebb qubit fusson kevesebb műveletre esően) és futtathatók legyenek a korai, kisebb léptékű kvantumhardvereken is.   

## <a name="use-q-to-validate-hardware-performance"></a>A Q# használata hardverteljesítmény ellenőrzéséhez

A Q# szépsége az, hogy a programokat elég egyszer megírni, majd kvantumszimulátorokon való futtatásukkal elvégezhető a hibakeresésük, valamint több kvantumszámítógép hardverén is futtathatók.  Ahogy a kvantumszámítógépek fejlődnek, és új kvantumszámítógépek válnak elérhetővé, a Q# nyelven írt teljesítménytesztelési programok futtathatók a hardverteljesítmény ellenőrzése és az eredmények összehasonlítása céljából.  

## <a name="next-steps"></a>További lépések

* [Hogyan tanulhatok kvantum-számítástechnikát?](xref:microsoft.quantum.overview.learn)
* [Bevezetés a Microsoft Quantum Development Kit használatába](xref:microsoft.quantum.welcome)
