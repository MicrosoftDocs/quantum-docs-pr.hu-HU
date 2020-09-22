---
title: A Kvantum gépi tanulási csomag bemutatása | Microsoft Docs
description: A Kvantum gépi tanulási csomag bemutatása
author: QuantumWriter
ms.author: alexeib
ms.date: 12/5/2019
ms.topic: article
uid: microsoft.quantum.machine-learning.concepts.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 321901a7976e4633a672495827c27c5f1645ad30
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835689"
---
# <a name="introduction-to-the-quantum-machine-learning-library"></a>A Kvantum gépi tanulási kódtár bemutatása

A Kvantum gépi tanulási kódtár egy Q#-ban írt API, amely lehetővé teszi a hibrid kvantum/klasszikus gépi tanulási kísérletek futtatását. A kódtár az alábbiakat teszi lehetővé:

- Saját adatainak betöltése a kvantumszimulátorokkal való osztályozáshoz

- Minták és oktatóanyagok használata a kvantum gépi tanulás területének megismeréséhez

A klasszikus gépi tanulási keretrendszerekhez képest alacsony teljesítmény várható (ne feledje, hogy minden egy kvantumeszköz szimulációja mellett fut, amely már eleve jelentős számításigénnyel rendelkezik).

Ez a dokumentáció:

- Rövid bevezetést ad a hibrid kvantum/klasszikus tanuláshoz készült (Q\# nyelven írt) gépi tanulási eszközökhöz.
- Ismerteti a gépi tanulási fogalmakat, különösen a kvantumkörközpontú osztályozókban (más néven kvantumszekvenciális osztályozókban) való megvalósulásukat.
- Az alapismereteket tárgyaló oktatóanyagokat tartalmaz a kódtár által biztosított eszközök használatának megkezdéséhez.
- Tárgyalja az ilyen osztályozók betanítási és ellenőrzési módszereit, valamint azt, hogy miként képezhetők le konkrét, a kódtár által biztosított Q\#-műveletekre.

Az ebben a kódtárban implementált modell a [körközpontú kvantumosztályozókat tárgyaló cikkben](https://arxiv.org/abs/1804.00633) bemutatott kvantum–klasszikus betanítási sémán alapul.
