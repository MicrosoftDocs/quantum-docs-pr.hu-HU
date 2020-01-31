---
title: Hozzájárulás a Quantum Development Kithez | Microsoft Docs
description: Hozzájárulás a Quantum Development Kithez
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing
ms.openlocfilehash: 3f27f7502c83574e6bd8f950d7e17ee481e44a3c
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76819858"
---
# <a name="contributing-to-the-quantum-development-kit"></a>Hozzájárulás a Quantum Development Kithez #

A Quantum Development Kit több, mint a kvantumprogramok írásához szükséges eszközök gyűjteménye.
Egy nagy közösséghez tartozik, ahol az emberek felfedezhetik a kvantum-számítástechnikát, kutatást végezhetnek a kvantum-algoritmusokkal, új alkalmazásokat fejleszthetnek a kvantumeszközökre, és egyéb módokon használhatják ki a kvantumprogramozásban rejlő lehetőségeket.
A közösség részeként a Quantum Development Kit célja, hogy biztosítsa a szükséges funkciókat a legkülönbözőbb háttérrel rendelkező kvantumfejlesztők számára.
Az Önök Quantum Development Kithez való hozzájárulásai segítenek e cél megvalósításában a kvantumfejlesztők által használt eszközök továbbfejlesztése, az eszközök hatékonyabb dokumentációja, és akár új funkciók létrehozása révén is, amelyek segítségével a kvantumprogramozási közösség a felfedezés és alkotás helye lehet.
Nagyon hálásak vagyunk az Önök közreműködéséért, és azért is, hogy együtt dolgozhatunk Önökkel a közösség jobbá tételén.

Ebben az útmutatóban néhány tanácsot adunk arról, hogy miként teheti hozzájárulását a lehető leghasznosabbá a szélesebb értelemben vett kvantumprogramozási közösség számára.

## <a name="building-community"></a>A közösség kiépítése ##

A közreműködés kapcsán mindig észben kell tartani, hogy milyen közösségről is van szó.
Azáltal, hogy tiszteletteljesen és professzionálisan kezeli a kvantumprogramozási közösség és a szélesebb értelemben vett közösség többi tagját, segít abban, hogy a lehető legjobb és legbarátságosabb közösséget teremtsük meg.

Ennek elősegítése érdekében minden Quantum Development Kit-projekt a [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/) hatálya alá esik.
További információért tekintse át a [viselkedési szabályzat GYIK dokumentumát](https://opensource.microsoft.com/codeofconduct/faq/), illetve további kérdések vagy megjegyzések esetén írjon az [opencode@microsoft.com](mailto:opencode@microsoft.com) e-mail-címre.

## <a name="what-kinds-of-contributions-help-the-community"></a>Milyen típusú hozzájárulások hasznosak a közösség számára? ##

Számos különböző módon lehet a kvantumprogramozási közösség segítségére a hozzájárulásai révén.
Ebben az útmutatóban három olyan módszert mutatunk be, amelyek különösen hasznosak a Quantum Development Kit kapcsán.
Ezen módszerek mindegyike kritikus fontosságú egy olyan kvantumközösség kiépítésében, amely elősegíti a hatékony munkát.
Ez azonban egyáltalán nem egy kimerítő lista – ezért arra biztatjuk, hogy fedezzen fel egyéb módokat is, amelyekkel segíthet a közösségnek megvalósítani a kvantumprogramozásban rejlő lehetőségeket.

- **Hibajelentés.** A hibák és egyéb problémák megoldásának első lépése azok azonosítása. Ha hibát észlelt a Quantum Development Kit használata során, visszajelzésével segíthet a hiba kijavításában és hatékonyabb eszközök létrehozásában a kvantumprogramozási közösség számára.
- **A dokumentáció továbbfejlesztése.** Nincs olyan dokumentációkészlet, amely ne lehetne továbbfejleszthető, még több részletre kiterjedő vagy könnyebben elérhető.
- **Kód közzététele.** Természetesen a hozzájárulás egyik legegyértelműbb módja az új kód hozzáadása a Quantum Development Kithez.

Ezek a különböző típusú hozzájárulások rendkívül értékesek, és nagyon hálásak vagyunk értük.
Az útmutató további részében a különböző típusú hozzájárulási módokhoz adunk javaslatokat.

## <a name="where-do-contributions-go"></a>Hova kerülnek a hozzájárulások? ##

A Quantum Development Kit számos különböző részből áll, amelyek együtt hozzák létre a kvantumprogramok írását elősegítő platformot.
Ezek a különböző részek mindegyike különböző adattárakba tartozik, így rögtön az elején érdemes tisztázni, hogy az adott hozzájárulás hova való leginkább.

- [**microsoft/Quantum**](https://github.com/Microsoft/Quantum): A Quantum Development Kit használatának megkezdését elősegítő minták és eszközök.
- [**microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries): Standard és tartományspecifikus kódtárak a Quantum Development Kithez.
- [**microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas): Saját ütemben elvégezhető programozási feladatok a kvantum-számítástechnika és a Q# programozási nyelv megismeréséhez.
- [**microsoft/qsharp-compiler**](https://github.com/microsoft/qsharp-compiler): Q#-fordító, Visual Studio-bővítmény és Visual Studio Code-bővítmény.
- [**microsoft/qsharp-runtime**](https://github.com/microsoft/qsharp-runtime): Szimulációs keretrendszer, kódlétrehozás és szimulációs célgépek a Quantum Development Kithez.
- [**microsoft/iqsharp**](https://github.com/microsoft/iqsharp): Jupyter kernel és Python-gazdagépfunkciók a Q#-hoz, valamint Docker-lemezképek az IQ# felhőalapú környezetekben való használatához.
- [**MicrosoftDocs/quantum-docs-pr**](https://github.com/MicrosoftDocs/quantum-docs-pr): Forráskód a következő helyen közzétett dokumentációhoz: https://docs.microsoft.com/quantum.

> [!NOTE]
> Sajnos a [**microsoft/Quantum-NC**](https://github.com/microsoft/Quantum-NC) adattár esetében jelenleg nem tudunk kóddal és dokumentációval kapcsolatos hozzájárulásokat elfogadni, de a hibajelentéseket továbbra is nagyra értékeljük.

Vannak még további speciálisabb adattárak, amelyek a Quantum Development Kithez kapcsolódó különböző eseményeket vagy kiegészítő funkciókat tartalmaznak.

- [**msr-quarc/qsharp.sty**](https://github.com/msr-quarc/qsharp.sty): LaTeX formázási támogatás a Q#-szintaxishoz.
- [**msr-quarc/intern-workshop-2019**](https://github.com/msr-quarc/intern-workshop-2019): IQ#-jegyzetfüzet a 2019-es gyakornoki műhely keretében bemutatott Deutsch–Jozsa-oktatóanyaghoz.

## <a name="next-steps"></a>További lépések ##

Köszönjük, hogy a Quantum Development Kit közösségének tagja! izgatottan várjuk a közreműködését!
Amennyiben többet szeretne megtudni a hozzájárulásokról, olvassa el a következő útmutatók egyikét.

> [!div class="nextstepaction"]
> [Ismerje meg, hogyan jelentheti a hibákat](xref:microsoft.quantum.contributing.reporting)

> [!div class="nextstepaction"]
> [Ismerje meg, hogyan tölthet fel dokumentációt](xref:microsoft.quantum.contributing.docs)

> [!div class="nextstepaction"]
> [Ismerje meg, hogyan nyithat lekéréses kérelmeket](xref:microsoft.quantum.contributing.pulls)

