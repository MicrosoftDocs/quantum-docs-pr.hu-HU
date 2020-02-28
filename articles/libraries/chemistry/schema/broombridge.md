---
title: Broombridge – Quantum kémia séma
description: A Broombridge Quantum kémia sémájának áttekintése, amely a Microsoft Quantum Development Kit a valós kémiai problémák modellezésére szolgál.
author: martinro
ms.author: martinro@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.broombridge
ms.openlocfilehash: a746b63055bb1b2c1168b89993a7459ca9597f86
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907817"
---
# <a name="broombridge-quantum-chemistry-schema"></a>Broombridge Quantum kémia-séma # 

A nagy teljesítményű számítási kémia szoftverek, például a [NWChem](http://www.nwchem-sw.org/) lehetővé teszik a valós kémiai problémák széles körének modellezését. A NWChem molekuláris modelljeinek a Microsoft Quantum kémia könyvtárral való eléréséhez egy [YAML](https://en.wikipedia.org/wiki/YAML)-alapú sémát használunk, amelyet **Broombridge**hívunk meg. A név egy olyan [mérföldkőre](https://en.wikipedia.org/wiki/Broom_Bridge) való hivatkozásként lett kiválasztva, amely bizonyos körökben a Hamiltonians szülővárosának ünnepelt. 

A [NWChem](https://github.com/nwchemgit/nwchem) egy nyílt forráskódú projekt, amely a megengedő oktatási közösségi licenc (ECL) 2,0-licenccel rendelkezik. A Broombridge egy nyílt forráskódú séma, amely [itt](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) van meghatározva, és a következő [definíciót](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/broombridge-0.1.schema.json) tartalmazza, amely a mit licenc alá tartozó [RFC 2119](https://tools.ietf.org/html/rfc2119) és [validator parancsfájlt](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/validator.py) tartalmaz. 

Az YAML-alapú Broombridge strukturált, ember által olvasható és emberi módon szerkeszthető módszert jelent az elektronikus struktúrákkal kapcsolatos problémák kezelésére. Különösen a következő adatokat lehet megjeleníteni: 
- A Fermionic-Hamiltonians egy-és kételektronos integráltak használatával is megjeleníthető. 
- A terep és az izgatott állapotok létrehozási folyamatokkal jeleníthetők meg.
- Az energia felső és alsó határa megadható.

Az adatformátum könnyen létrehozható a NWChem-ből: számos különböző módszer érhető el, amely a NWChem teljes telepítéséről a kémia-fedélzetek, például az [itt](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests) megadott, a Futtatás részeként kimeneti Broombridge, a NWChem Docker-rendszerképén keresztül is használható, amely a kémia-Fedélzetekről Broombridge hozható létre. Végül egy vizuális módszer a számítási kémia gyors megkezdéséhez anélkül, hogy bármilyen kémiai szoftvert kellene telepítenie, a [EMSL Arrows](https://arrows.emsl.pnnl.gov/api/qsharp_chem) felülete NWChem. 

Magas szinten a NWChem és a Microsoft Quantum Development Kit közötti interakció az alábbiak szerint jeleníthető meg: ![kémiai verem](~/media/broombridge.png) a kék árnyékolt mező a Broombridge sémát jelöli, a különböző szürke árnyékolt dobozok más belső adatábrázolásokat jelentenek, amelyek a számítási kémia számára a kvantummechanika és a valós kémiai problémák alapján döntöttek. 

[Itt](https://github.com/microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML)több, a Broombridge sémával meghatározott kémiai ábrázolás is elérhető.
