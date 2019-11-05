---
title: Ismerkedés a kvantum-számítástechnikával Q# nyelven
description: ''
author: natke
ms.author: nakersha
ms.date: 10/23/2019
ms.topic: article
uid: microsoft.quantum.overview.learn
ms.openlocfilehash: 8967fee11931c6cef4b2d98084b2e319cea55284
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/02/2019
ms.locfileid: "73444106"
---
# <a name="how-to-learn-quantum-computing"></a>Ismerkedés a kvantum-számítástechnikával

Útmutatást kaphat a kvantum-számítástechnikához és az első program megírásához. Ez nem egy teljes körű leírás, inkább csak egy jó kiindulópontként szolgál.

## <a name="getting-started-overview"></a>Első lépések áttekintése

A [Bevezetés a Microsoft Quantum Development Kit használatába](xref:microsoft.quantum.welcome) című cikk általános áttekintést nyújt a Q# nyelvre épülő kvantum-számítástechnikáról. A cikk tartalmaz még egy oktatóanyagokat az első Q#-program megírásához, az első lépéseket ismertető útmutatókat, valamint egy bevezetést a kvantumprogramok fejlesztésére szolgáló Q#-kvantumkódtárak használatába.

## <a name="learning-the-basics-what-do-you-need-to-know"></a>Az alapok és az alapvető tudnivalók

Nem kell ismernie a kvantumfizikát ahhoz, hogy megismerkedjen a Q#-pal és a kvantum-számítástechnikával, vagy elkezdjen kvantumalkalmazásokat írni.

Ezek az alapfogalmak kiváló kiindulópontot nyújtanak a kvantumprogramok írásához szükséges alaptudás megteremtéséhez.  

* [Alapszintű kvantummechanikák](xref:microsoft.quantum.concepts.intro): Épp most említettük, hogy nincs szüksége a kvantumfizikára a programozás elkezdéséhez (és ez igaz is!). De a kvantummechanika és a matematikai jelölések alapfogalmai hasznosak lesznek a kvantumprogramozás megértésében.

* **Lineáris algebra (vektorok és mátrixok)** : A kvantum-számítástechnikában a kvantumállapotokat vektorok jelzik, a kvantumműveletek pedig az ezekre a vektorokra alkalmazott lineáris transzformációk.  Itt talál egy [Jupyter-notebook-oktatóanyagot a lineáris algebráról](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/LinearAlgebra).  Erről a témáról részletesebben a [vektorok és mátrixok](xref:microsoft.quantum.concepts.vectors) fogalmait ismertető cikkünkben is tájékozódhat.

* **Összetett aritmetika**: A kvantumállapot-vektorok együtthatói komplex számok. Nélkülük is megértheti az alapszintű kvantum-számítástechnikai alapfogalmakat, de hosszabb távon mindenképpen be kell építenie őket a kvantumeszköztárába.  Itt talál egy [Jupyter-notebook-oktatóanyagot az összetett aritmetikáról](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ComplexArithmetic), amely betekintést nyújt a kvantum-számítástechnika használatához szükséges matematikai háttérismeretekbe. 

Most, hogy elsajátította az alapokat, készen áll arra, hogy megtanulja a kvantumprogramok megírásának menetét.  Ennek számos módja van:

## <a name="do-the-quantum-katas"></a>A Kvantum Katák használata

A [Kvantum Katák](xref:microsoft.quantum.overview.katas) nyílt forráskódú, saját ütemben elvégezhető oktatóanyagok, amelyek célja a kvantum-számítástechnika elemeinek és a Q#-programozás egyidejű megismertetése.  Mindegyik katához további oktatóanyagok tartoznak, amelyekből megismerheti a katák sikeres teljesítéséhez szükséges kvantum-számítástechnikai fogalmakat.  

## <a name="dive-into-the-theory"></a>Elmélyedés az elméletben

Esetleg mélyreható betekintést szeretne a kvantummechanika elméletébe és a kvantum-számítástechnikába. Az alábbiakban a hasznos segédletek listáját találja:

* Kezdje [kvantum-számítástechnikai alapfogalmakhoz](xref:microsoft.quantum.concepts.intro) készült útmutatónkkal, a kvantum-számítástechnika alapszintű fogalmainak gyűjteményével.
* _A kvantum-számítástechnika Pythonnal és Q#-pal történő megismerésével_ (Sarah C. Kaiser és Christopher E. Granade) nagyszerű betekintést kaphatnak azok, akiknek kevés vagy nulla tapasztalatuk van a kvantummechanikával kapcsolatban, de rendelkeznek némi programozási háttérrel.
* A _kvantum-számítástechnika és a kvantuminformáció_ (Michael A. Nielsen, Isaac L. Chuang) a kvantum-számítástechnika területén leggyakrabban idézett írás. Alapműnek tekinthető a témában. A könyv minimális előzetes tapasztalatot feltételez a kvantummechanikával és a számítástechnikával kapcsolatban. Remek választás azoknak az olvasóknak, akik a témakör alapos bevezetését igénylik, és azoknak is, akik a haladó szintű fogalmakkal is megismerkednének.
* Az MIT OpenCourseWare Allan Adams által vezetett [online képzése](https://www.youtube.com/watch?v=lZ3bPUKo5zc&list=PLUl4u3cNGP61-9PEhRognw5vryrSEVLPr) kiváló a kvantummechanika alapjainak megismerésére. Tökéletes azoknak, akik szeretnék jobban megérteni a háttérben rejlő fizikai jelenségeket.

## <a name="join-the-quantum-community"></a>Csatlakozás a kvantumközösséghez

Nem kell egyedül megtanulnia mindezt – az amatőrökből és szakértőkből álló közössége örömmel segít Önnek. Ne féljen kérdezni!

* Ha bármilyen kérdése van a Q#-ról vagy a kvantum-számítástechnikáról, ne legyen rest ellátogatni a kvantum-számítástechnika StackExchange-oldalára. Ha nem találja meg a kérdését, bármikor tehet fel újakat. 
* Tekintse meg a [Q# blogot](https://devblogs.microsoft.com/qsharp/) és a [Microsoft Quantum Blogot](https://cloudblogs.microsoft.com/quantum/), hogy naprakész legyen a Q# legfrissebb újdonságaival és forrásanyagaival kapcsolatban.
* Látogasson el a [Q# közösségébe](https://qsharp.community/) és a [Nagyszerű Q#](https://project-awesome.org/ebraminio/awesome-qsharp) oldalra, hogy új segédletekre és forrásanyagokra találjon.

 Ha egy kvantum-számítástechnikai tanfolyam keretében készül oktatást tartani, a [Microsoft Quantum Network](https://info.microsoft.com/LearnMoreAboutMicrosoftQuantumNetwork.html) segíthet a tanterv összeállításában.  

