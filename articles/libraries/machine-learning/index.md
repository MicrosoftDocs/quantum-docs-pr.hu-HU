---
title: A Kvantum gépi tanulási csomag bemutatása | Microsoft Docs
description: A Kvantum gépi tanulási csomag bemutatása
author: QuantumWriter
ms.author: alexeib@microsoft.com
ms.date: 12/5/2019
ms.topic: article
uid: microsoft.quantum.machine-learning.concepts.intro
ms.openlocfilehash: 7f22d5d3212890abc764f88693937b534466170f
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2020
ms.locfileid: "77907851"
---
# <a name="introduction-to-the-quantum-machine-learning-library"></a><span data-ttu-id="1bb5b-103">A Kvantum gépi tanulási kódtár bemutatása</span><span class="sxs-lookup"><span data-stu-id="1bb5b-103">Introduction to the Quantum Machine Learning Library</span></span>

<span data-ttu-id="1bb5b-104">A Kvantum gépi tanulási kódtár egy Q#-ban írt API, amely lehetővé teszi a hibrid kvantum/klasszikus gépi tanulási kísérletek futtatását.</span><span class="sxs-lookup"><span data-stu-id="1bb5b-104">The Quantum Machine Learning Library is an API, written in Q#, that gives you the ability to run hybrid quantum/classical machine learning experiments.</span></span> <span data-ttu-id="1bb5b-105">A kódtár az alábbiakat teszi lehetővé:</span><span class="sxs-lookup"><span data-stu-id="1bb5b-105">The library gives you the ability to:</span></span>

- <span data-ttu-id="1bb5b-106">Saját adatainak betöltése a kvantumszimulátorokkal való osztályozáshoz</span><span class="sxs-lookup"><span data-stu-id="1bb5b-106">Load your own data to classify with quantum simulators</span></span>

- <span data-ttu-id="1bb5b-107">Minták és oktatóanyagok használata a kvantum gépi tanulás területének megismeréséhez</span><span class="sxs-lookup"><span data-stu-id="1bb5b-107">Use samples and tutorials to get introduced to the field of quantum machine learning</span></span>

<span data-ttu-id="1bb5b-108">A klasszikus gépi tanulási keretrendszerekhez képest alacsony teljesítmény várható (ne feledje, hogy minden egy kvantumeszköz szimulációja mellett fut, amely már eleve jelentős számításigénnyel rendelkezik).</span><span class="sxs-lookup"><span data-stu-id="1bb5b-108">You can expect low performance compared to current classical machine learning frameworks (remember that everything is running on top of the simulation of a quantum device that is already computationally expensive).</span></span>

<span data-ttu-id="1bb5b-109">Ez a dokumentáció:</span><span class="sxs-lookup"><span data-stu-id="1bb5b-109">The purpose of this documentation is:</span></span>

- <span data-ttu-id="1bb5b-110">Rövid bevezetést ad a hibrid kvantum/klasszikus tanuláshoz készült (Q\# nyelven írt) gépi tanulási eszközökhöz.</span><span class="sxs-lookup"><span data-stu-id="1bb5b-110">A concise introduction to machine learning tools (written in Q\#) for hybrid quantum/classical learning.</span></span>
- <span data-ttu-id="1bb5b-111">Ismerteti a gépi tanulási fogalmakat, különösen a kvantumkörközpontú osztályozókban (más néven kvantumszekvenciális osztályozókban) való megvalósulásukat.</span><span class="sxs-lookup"><span data-stu-id="1bb5b-111">Introduce machine learning concepts and specifically their realization in quantum circuit centric classifiers (also known as quantum sequential classifiers).</span></span>
- <span data-ttu-id="1bb5b-112">Az alapismereteket tárgyaló oktatóanyagokat tartalmaz a kódtár által biztosított eszközök használatának megkezdéséhez.</span><span class="sxs-lookup"><span data-stu-id="1bb5b-112">Provide a set of tutorials on the basics to start using the tools provided by the library.</span></span>
- <span data-ttu-id="1bb5b-113">Tárgyalja az ilyen osztályozók betanítási és ellenőrzési módszereit, valamint azt, hogy miként képezhetők le konkrét, a kódtár által biztosított Q\#-műveletekre.</span><span class="sxs-lookup"><span data-stu-id="1bb5b-113">Discuss the training and validation methods for such classifiers and how they translate into specific Q\# operations provided by the library.</span></span>

<span data-ttu-id="1bb5b-114">Az ebben a kódtárban implementált modell a [körközpontú kvantumosztályozókat tárgyaló cikkben](https://arxiv.org/abs/1804.00633) bemutatott kvantum–klasszikus betanítási sémán alapul.</span><span class="sxs-lookup"><span data-stu-id="1bb5b-114">The model implemented in this library is based on the quantum-classical training scheme presented in [Circuit-centric quantum classifiers](https://arxiv.org/abs/1804.00633)</span></span>
