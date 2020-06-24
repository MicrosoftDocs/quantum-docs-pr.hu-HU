---
title: Broombridge Quantum kémia-séma
description: A Broombridge Quantum kémia sémájának áttekintése, amely a Microsoft Quantum Development Kit a valós kémiai problémák modellezésére szolgál.
author: martinro
ms.author: martinro@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.broombridge
ms.openlocfilehash: 708c4277080c358cb35a49fbf1dde0394d331043
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275079"
---
# <a name="broombridge-quantum-chemistry-schema"></a>Broombridge Quantum kémia-séma # 

A nagy teljesítményű számítási kémia szoftverek, például a [NWChem](http://www.nwchem-sw.org/) lehetővé teszik a valós kémiai problémák széles körének modellezését. Ahhoz, hogy NWChem molekuláris modelleket lehessen elérni a Microsoft Quantum kémiát tartalmazó könyvtárral, egy **Broombridge**nevű [YAML](https://en.wikipedia.org/wiki/YAML)sémát kell használnia. A név egy olyan [mérföldkőre](https://en.wikipedia.org/wiki/Broom_Bridge) való hivatkozásként lett kiválasztva, amely bizonyos körökben a Hamiltonians szülővárosának ünnepelt. 

A [NWChem](https://github.com/nwchemgit/nwchem) egy nyílt forráskódú projekt, amely a megengedő oktatási közösségi licenc (ECL) 2,0-licenccel rendelkezik. A [Broombridge Quantum kémiai sémája](https://docs.microsoft.com/quantum/libraries/chemistry/schema/spec_v_0_2)egy nyílt forráskódú séma, amely [a következő](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/broombridge-0.1.schema.json) [RFC 2119](https://tools.ietf.org/html/rfc2119) -es és az mit licenc alá tartozó [validator-szkriptet](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/validator.py) tartalmazza: 

Az YAML-alapú Broombridge strukturált, ember által olvasható és emberi módon szerkeszthető módszert jelent az elektronikus struktúrákkal kapcsolatos problémák kezelésére. Különösen a következő adatokat lehet megjeleníteni:
- A Fermionic-Hamiltonians egy-és kételektronos integráltak használatával is megjeleníthető.
- A terep és az izgatott állapotok létrehozási folyamatokkal jeleníthetők meg.
- Az energia felső és alsó határa megadható.

Az adatok a NWChem különböző módszerekkel hozhatók létre, például a NWChem teljes telepítése a kémia-fedélzetek futtatására (például a [NWChem-könyvtárban](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests) , amely a Futtatás részét képező Broombridge kimenete), vagy egy NWChem Docker-rendszerképét, amely a Broombridge kémiai pakliból való generálására is használható. A számítási kémia gyors megkezdéséhez anélkül, hogy bármilyen kémiai szoftvert kellene telepítenie, a vizuális felületet használhatja a [EMSL-nyilak](https://arrows.emsl.pnnl.gov/api/qsharp_chem)által biztosított NWChem.

Magas szinten a NWChem és a Microsoft Quantum Development Kit közötti interakció az alábbiak szerint jeleníthető meg: ![ kémia stack ](~/media/broombridge.png) a kék árnyékolt mező a Broombridge sémát jelöli, a különböző szürke árnyékolt dobozok más belső adatábrázolásokat jelképeznek, amelyek a számítási kémia alapjául szolgáló kvantum-algoritmusok megjelenítésére és feldolgozására lettek kiválasztva a valós kémiai problémák alapján.

A Quantum Development Kit Samples adattárának [szerves/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML) mappája több, a Broombridge sémával meghatározott kémiai ábrázolást tartalmaz.
