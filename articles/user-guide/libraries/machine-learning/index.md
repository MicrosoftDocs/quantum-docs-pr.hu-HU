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
# <a name="introduction-to-the-quantum-machine-learning-library"></a><span data-ttu-id="35c29-103">A Kvantum gépi tanulási kódtár bemutatása</span><span class="sxs-lookup"><span data-stu-id="35c29-103">Introduction to the Quantum Machine Learning Library</span></span>

<span data-ttu-id="35c29-104">A Kvantum gépi tanulási kódtár egy Q#-ban írt API, amely lehetővé teszi a hibrid kvantum/klasszikus gépi tanulási kísérletek futtatását.</span><span class="sxs-lookup"><span data-stu-id="35c29-104">The Quantum Machine Learning Library is an API, written in Q#, that gives you the ability to run hybrid quantum/classical machine learning experiments.</span></span> <span data-ttu-id="35c29-105">A kódtár az alábbiakat teszi lehetővé:</span><span class="sxs-lookup"><span data-stu-id="35c29-105">The library gives you the ability to:</span></span>

- <span data-ttu-id="35c29-106">Saját adatainak betöltése a kvantumszimulátorokkal való osztályozáshoz</span><span class="sxs-lookup"><span data-stu-id="35c29-106">Load your own data to classify with quantum simulators</span></span>

- <span data-ttu-id="35c29-107">Minták és oktatóanyagok használata a kvantum gépi tanulás területének megismeréséhez</span><span class="sxs-lookup"><span data-stu-id="35c29-107">Use samples and tutorials to get introduced to the field of quantum machine learning</span></span>

<span data-ttu-id="35c29-108">A klasszikus gépi tanulási keretrendszerekhez képest alacsony teljesítmény várható (ne feledje, hogy minden egy kvantumeszköz szimulációja mellett fut, amely már eleve jelentős számításigénnyel rendelkezik).</span><span class="sxs-lookup"><span data-stu-id="35c29-108">You can expect low performance compared to current classical machine learning frameworks (remember that everything is running on top of the simulation of a quantum device that is already computationally expensive).</span></span>

<span data-ttu-id="35c29-109">Ez a dokumentáció:</span><span class="sxs-lookup"><span data-stu-id="35c29-109">The purpose of this documentation is:</span></span>

- <span data-ttu-id="35c29-110">Rövid bevezetést ad a hibrid kvantum/klasszikus tanuláshoz készült (Q\# nyelven írt) gépi tanulási eszközökhöz.</span><span class="sxs-lookup"><span data-stu-id="35c29-110">A concise introduction to machine learning tools (written in Q\#) for hybrid quantum/classical learning.</span></span>
- <span data-ttu-id="35c29-111">Ismerteti a gépi tanulási fogalmakat, különösen a kvantumkörközpontú osztályozókban (más néven kvantumszekvenciális osztályozókban) való megvalósulásukat.</span><span class="sxs-lookup"><span data-stu-id="35c29-111">Introduce machine learning concepts and specifically their realization in quantum circuit centric classifiers (also known as quantum sequential classifiers).</span></span>
- <span data-ttu-id="35c29-112">Az alapismereteket tárgyaló oktatóanyagokat tartalmaz a kódtár által biztosított eszközök használatának megkezdéséhez.</span><span class="sxs-lookup"><span data-stu-id="35c29-112">Provide a set of tutorials on the basics to start using the tools provided by the library.</span></span>
- <span data-ttu-id="35c29-113">Tárgyalja az ilyen osztályozók betanítási és ellenőrzési módszereit, valamint azt, hogy miként képezhetők le konkrét, a kódtár által biztosított Q\#-műveletekre.</span><span class="sxs-lookup"><span data-stu-id="35c29-113">Discuss the training and validation methods for such classifiers and how they translate into specific Q\# operations provided by the library.</span></span>

<span data-ttu-id="35c29-114">Az ebben a kódtárban implementált modell a [körközpontú kvantumosztályozókat tárgyaló cikkben](https://arxiv.org/abs/1804.00633) bemutatott kvantum–klasszikus betanítási sémán alapul.</span><span class="sxs-lookup"><span data-stu-id="35c29-114">The model implemented in this library is based on the quantum-classical training scheme presented in [Circuit-centric quantum classifiers](https://arxiv.org/abs/1804.00633)</span></span>
