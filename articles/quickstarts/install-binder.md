---
title: Fejlesztés Q#-pal és Binderrel
description: Megtudhatja, hogyan hozhat létre Q#-alkalmazást a Binder használatával.
author: bradben
ms.author: v-benbra
ms.date: 9/03/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.binder
no-loc:
- Q#
- $$v
ms.openlocfilehash: f993a1145dd8c01045d4cc7cfd0c98efd574ea78
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/21/2020
ms.locfileid: "90836533"
---
# <a name="develop-with-no-locq-and-binder"></a><span data-ttu-id="6a415-103">Fejlesztés Q#-pal és Binderrel</span><span class="sxs-lookup"><span data-stu-id="6a415-103">Develop with Q# and Binder</span></span>

<span data-ttu-id="6a415-104">A Jupyter-notebookok online futtatásához és megosztásához használhatja a Bindert.</span><span class="sxs-lookup"><span data-stu-id="6a415-104">You can use Binder to run and share your Jupyter Notebooks online.</span></span>

## <a name="use-binder-with-the-microsoft-qdk-samples"></a><span data-ttu-id="6a415-105">A Binder használata a Microsoft QDK-mintákkal</span><span class="sxs-lookup"><span data-stu-id="6a415-105">Use Binder with the Microsoft QDK samples</span></span>

<span data-ttu-id="6a415-106">A Binder konfigurálása a Microsoft QDK-minták automatikus használatához:</span><span class="sxs-lookup"><span data-stu-id="6a415-106">To configure Binder automatically to use the Microsoft QDK samples:</span></span>

1. <span data-ttu-id="6a415-107">Nyissa meg a böngészőt, és futtassa a következőt: https://aka.ms/try-qsharp.</span><span class="sxs-lookup"><span data-stu-id="6a415-107">Open a browser and run https://aka.ms/try-qsharp.</span></span>
1. <span data-ttu-id="6a415-108">A **Quantum Development Kit-minták** kezdőlapján kattintson a **Q#-notebookra**, hogy megtudhassa, hogyan írhat saját kvantumalkalmazás-notebookot az IQ# használatával.</span><span class="sxs-lookup"><span data-stu-id="6a415-108">On the **Quantum Development Kit Samples** landing page, click **Q# notebook** to learn how to use IQ# to write your own quantum application notebooks.</span></span>

![A QDK kezdőlapja](~/media/binder-install.png)

## <a name="use-binder-with-your-own-notebooks-and-repository"></a><span data-ttu-id="6a415-110">A Binder használata saját notebookjaival és adattáraival</span><span class="sxs-lookup"><span data-stu-id="6a415-110">Use Binder with your own notebooks and repository</span></span>

<span data-ttu-id="6a415-111">Ha már rendelkezik notebookokkal egy GitHub-adattárban, a Bindert saját adattárának használatára is konfigurálhatja:</span><span class="sxs-lookup"><span data-stu-id="6a415-111">If you already have notebooks in a GitHub repository, you can configure Binder to work with your repo:</span></span>

1. <span data-ttu-id="6a415-112">Ellenőrizze, hogy van-e *Dockerfile* nevű fájl az adattár gyökerében.</span><span class="sxs-lookup"><span data-stu-id="6a415-112">Ensure that there is a file named *Dockerfile* in the root of your repository.</span></span> <span data-ttu-id="6a415-113">A fájlnak legalább az alábbi sorokat kell tartalmaznia:</span><span class="sxs-lookup"><span data-stu-id="6a415-113">The file must contain at least the following lines:</span></span>

    ```bash
    FROM mcr.microsoft.com/quantum/iqsharp-base:0.12.20082513
    
    USER root
    COPY . ${HOME}
    RUN chown -R ${USER} ${HOME}
    
    USER ${USER}
    ```

    > [!NOTE]
    > <span data-ttu-id="6a415-114">Az IQ# aktuális verzióját a [kibocsátási megjegyzésekben](xref:microsoft.quantum.relnotes) ellenőrizheti.</span><span class="sxs-lookup"><span data-stu-id="6a415-114">You can verify the most current version of IQ# in the [Release Notes](xref:microsoft.quantum.relnotes).</span></span>

    <span data-ttu-id="6a415-115">A Docker-fájlok létrehozásával kapcsolatos további információért tekintse meg a [Docker-fájlra vonatkozó referenciákat](https://docs.docker.com/engine/reference/builder/).</span><span class="sxs-lookup"><span data-stu-id="6a415-115">For more information about creating a Dockerfile, see the [Dockerfile reference](https://docs.docker.com/engine/reference/builder/).</span></span>

2. <span data-ttu-id="6a415-116">Nyissa meg valamilyen böngészőben a [mybinder.org](https://mybinder.org) webhelyet.</span><span class="sxs-lookup"><span data-stu-id="6a415-116">Open a browser to [mybinder.org](https://mybinder.org).</span></span>
3. <span data-ttu-id="6a415-117">Adja meg az adattár nevét a **GitHub URL-címeként** (például *SajátNév/SajátAdattár*), majd kattintson az **Indítás** elemre.</span><span class="sxs-lookup"><span data-stu-id="6a415-117">Enter your repository name as the **GitHub URL** (for example *MyName/MyRepo*), and click **launch**.</span></span>

![A MyBinder űrlapja](~/media/mybinder.png)
    
## <a name="next-steps"></a><span data-ttu-id="6a415-119">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="6a415-119">Next steps</span></span>

<span data-ttu-id="6a415-120">Most, hogy beállította a Binder-környezetet, megírhatja és futtathatja [az első kvantumprogramját](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="6a415-120">Now that you have set up your Binder environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
